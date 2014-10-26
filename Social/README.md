Data_atlas_DUE2014
==================

###Data atlas of SPB



###Sources

- [Официальная статистика](http://gov.spb.ru/helper/new_stat/)
- 
Для api запроса Вконтакте, было разработано приложение, с помощью которого можно было авторизоваться для получения access_token: 

1. http://api.vk.com/oauth/authorize?client_id=3272739&redirect_uri=http://api.vk.com/blank.html&scope=(status,notify,friends,photos,audio,video,docs,notes,pages,wall,groups,messages,ads)&display=page&response_type=token

2. создаем вектор access_token=
Например: access_token=” 16e986aef7459f4155312c1850f4ce2d7d963ca01033d777f6b4e24795638ae845e483530fa96ae37b5ea”
3. после прохождения ссылки мы формируем api запрос
d <- GET(url=str_c(https://api.vk.com/method/groups.search?q=,  x, "&access_token=", access_token ))
4. в качестве x будут выступать ключевые слова (см. (что-то, что будет в вашем файле)),  которые будут автоматически подставляться с помощью циклической функции sapply
5. далее мы получаем данные : data <- content(d, as="parsed")$response
Пример api запроса: 
https://api.vk.com/method/groups.search?q=центральная&access_token=06e9baed7a58962ffcf0ac338932cb81ede88fba4c85f021011e26abafd491360e7db9e273a339e3aea79&offset=20
- [Уровень преступности](http://crimestat.ru/opendata) ||by Morozova Nadya

