# MVVM
I love the way he add models. A sample Android application using MVVM, Clean Architecture, Android Architecture Components

# Data Notes
1. Mappers in Data layer (awesome use of kotlin extensions)
2. Network and Room returns entities to Core. Mapping occurs in data (Repository) layer.

# Presentation Notes
1. Awesome use of extensions for ArchitecureComponents, such as LiveData observer
2. Using single Activity model
3. There Bases for some components: VieWModel, Fragment, Activity

# Domain (Core)
1. ResultState<T> --> is a must wrapper for network result.
2. Enity data class is  added inside another sealed class.
3. Interfaces dfor repository
4. UseCases (Interactor) interface with implementation
5. No @Inject in Domain (refrence no dependecies in core). In di module, use case is provided like this:
    ```
    @Provides
    //@PerFragment
    fun provideGetAlbumsUseCaseImpl(repository: AlbumsRepository): GetAlbumsUseCase = GetAlbumsUseCaseImpl(AsyncFTransformer(), AsyncSTransformer(), AsyncSTransformer(), repository)
    ```
    
