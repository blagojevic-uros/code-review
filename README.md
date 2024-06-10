# Code Review for Team6

## Introduction
Code review is essential for maintaining high code quality by identifying defects, ensuring following of coding standards, and improving overall code structure and readability. It acts as a learning opportunity for both the reviewer and the author, facilitating the exchange of best practices and new techniques. Also, it enhances team collaboration, as it encourages open communication and shared understanding of the codebase, leading to more maintainable and scalable software.

## Linting
Linting is the process of analyzing source code for potential errors, bugs, stylistic issues. Linting helps developers identify and fix problems early in the development cycle, improving code quality and consistency. It catches common mistakes such as syntax errors, variable naming issues, and code formatting problems, making the code easier to read, maintain, and less prone to bugs.

> [!TIP]
>
> <img width="332" alt="ss01" src="https://github.com/blagojevic-uros/code-review/assets/71049196/5e864ce0-e54c-4752-bb1f-191f59e227fa">
>
> Inside of various number of classes, we can see some class fields that have only been instantiated inside of a constructor. Since a variable is only defined once and does not change it's value again, it can also be declared as "final". This issue is present in at least 30 different class files.

> [!TIP]
>
> <img width="240" alt="ss02" src="https://github.com/blagojevic-uros/spirit/assets/71049196/56d3cd3e-405d-4460-a1a9-4361ac571d75">
>
> DRY ( Don't repeat yoursleft ) principle violation is spotted here. This chunk of code is used in multiple places and since it stops and then clears the timer, we could extract this chunk into a function called "resetTimer".

> [!TIP]
>
> <img width="633" alt="ss03" src="https://github.com/blagojevic-uros/spirit/assets/71049196/2b37f80e-0701-4533-a641-336b95080010">
>
> Since variable is defined and immediately after that is returned ( no other usages except in return statement ), we could refactor this into a single line, where we don't need variable definition.

> [!CAUTION]
>
> <img width="790" alt="ss04" src="https://github.com/blagojevic-uros/spirit/assets/71049196/690ec351-ee59-4183-b373-dcb1ce9244b6">
>
> By comparing String with "=", we actually compare with it's address, not value. This is a potential bug.

> [!TIP]
>
> <img width="814" alt="ss05" src="https://github.com/blagojevic-uros/spirit/assets/71049196/4c26b2c7-1119-4c17-9926-ca80b69bf71a">
>
> Chunk of code from upper image could be replaced like the example bellow. This way redundant function call to "setGameStateAndUpdateScreen" is evaded.
>
> <img width="790" alt="ss06" src="https://github.com/blagojevic-uros/spirit/assets/71049196/8e99f656-10e8-4022-8286-c5c77e8c2702">

> [!TIP]
>
> <img width="317" alt="ss07" src="https://github.com/blagojevic-uros/spirit/assets/71049196/5e9793cd-65ed-498c-a259-ef86f4a22326">
>
> Why not introduce State.ALIVE. It could be defined in Enum as NOT DEAD, since ALIVE & DEAD is more clean than NOT DEAD & DEAD.

> [!TIP]
>
> <img width="304" alt="ss08" src="https://github.com/blagojevic-uros/spirit/assets/71049196/b95a793c-6078-4625-9694-99c2c13d3635">
>
> No need to compare Booleans like this.

> [!TIP]
>
> <img width="331" alt="ss09" src="https://github.com/blagojevic-uros/spirit/assets/71049196/19face96-77d9-477c-ad8b-46aadebff40f">
>
> Chunk of code from upper image could be replaced like the example bellow. By default, if array values are not specified, they are null.
>
> <img width="302" alt="ss10" src="https://github.com/blagojevic-uros/spirit/assets/71049196/3bd48daa-98e1-43a3-85c3-bf65e9b40d5b">

> [!TIP]
>
> <img width="593" alt="ss11" src="https://github.com/blagojevic-uros/spirit/assets/71049196/ce9fe70b-63a0-4329-b643-2add37b0a4b2">
>
> Chunk of code from upper image could be replaced like the example bellow.
>
> <img width="661" alt="ss12" src="https://github.com/blagojevic-uros/spirit/assets/71049196/9723a9f8-ec45-48a3-8d70-643bc6fb0bfe">

> [!TIP]
>
> <img width="1245" alt="ss13" src="https://github.com/blagojevic-uros/spirit/assets/71049196/e98e51ee-e524-4609-b063-516350c39f5c">
>
> All of this can be transformed into this, since all the classes share the same Parent class.
>
> <img width="879" alt="ss14" src="https://github.com/blagojevic-uros/spirit/assets/71049196/42f49f5c-36c4-4f10-bd3f-8cddb97c3bb3">

> [!TIP]
>
> <img width="505" alt="ss15" src="https://github.com/blagojevic-uros/spirit/assets/71049196/a24598a4-844d-4d2b-9fa0-fb1e33eece85">
>
> This could've been done using a loop.

> [!WARNING]
>
> <img width="478" alt="ss16" src="https://github.com/blagojevic-uros/spirit/assets/71049196/deadfbd4-9d89-4bbf-ba9f-f478cfe480fa">
>
> Instead of having 28 iterations, we could have 8.
>
> <img width="542" alt="ss17" src="https://github.com/blagojevic-uros/spirit/assets/71049196/ba9d7b6c-8b53-46e1-8e1e-89bc6b48ab02">

> [!TIP]
>
> <img width="449" alt="ss18" src="https://github.com/blagojevic-uros/spirit/assets/71049196/c7659edd-a017-477f-8e74-ab9532cd918d">
>
> We do not need to compare variables when passed as argument, since there is a defined function for that.
>
> <img width="427" alt="ss19" src="https://github.com/blagojevic-uros/spirit/assets/71049196/f36a5074-ff54-4768-b120-48f4b894583d">

> [!TIP]
>
> <img width="566" alt="ss20" src="https://github.com/blagojevic-uros/spirit/assets/71049196/9f8ff09d-7381-443c-8da2-624066506f7c">
> 
> Return true can be called just once, hence the reduction.
>
> <img width="496" alt="ss21" src="https://github.com/blagojevic-uros/spirit/assets/71049196/609872f6-4ac5-4a65-8819-b6678abd799f">

> [!IMPORTANT]
>
> <img width="461" alt="ss22" src="https://github.com/blagojevic-uros/spirit/assets/71049196/3c4022e9-61e4-4b82-99a2-83dec475e057">
>
> By defining some state as a boolean, we remove the possibility of adding some new states in the future. For now this is not a problem, but at some point if we want to add something other than day/night ( i.e. dawn ), we would need to alter the logic completely. By introducing some state ( enum or a complex type ), we have that possibility.
>
> <img width="482" alt="ss23" src="https://github.com/blagojevic-uros/spirit/assets/71049196/e7d6923f-65e5-4dce-8486-c3d05f20597d">
> 
> The same applies here. If we had 10 states, we would need 10 class fields. This could be introduced in a Map-like structure.

> [!TIP]
>
> <img width="347" alt="ss24" src="https://github.com/blagojevic-uros/spirit/assets/71049196/8ba3d144-1b52-4d8c-956d-0ffac6b8395e">
>
> Assertion not needed.

> [!TIP]
>
> <img width="533" alt="ss25" src="https://github.com/blagojevic-uros/spirit/assets/71049196/6c6e3f2c-6099-4793-ba3b-db8c0bbf17d5">
>
> Why not declare worldX as 0.

> [!WARNING]
>
> <img width="568" alt="ss26" src="https://github.com/blagojevic-uros/spirit/assets/71049196/afe1a179-d577-44fa-8ff4-fe802557bfe4">
>
> This could be very simplified.

> [!TIP]
>
> <img width="656" alt="ss27" src="https://github.com/blagojevic-uros/spirit/assets/71049196/ed445057-bcc1-44cd-a00f-3125fb0b4655">
>
> No need to print stackTrace inside a Test.

> [!WARNING]
>
> <img width="674" alt="ss28" src="https://github.com/blagojevic-uros/spirit/assets/71049196/583b70e4-a1d3-4be6-9ebf-f2a58a8f65f6">
>
> No need to Mock it both via Annotation and in setUp method.

> [!TIP]
>
> <img width="873" alt="ss29" src="https://github.com/blagojevic-uros/spirit/assets/71049196/e67246ac-73e3-4826-a967-5fca481e165c">
>
> No need to introduce variables that aren't used.

> [!WARNING]
>
> <img width="618" alt="ss30" src="https://github.com/blagojevic-uros/spirit/assets/71049196/12aa3f21-a07f-4be7-9442-dc5035f7da44">
>
> Assertion missing for GameState
