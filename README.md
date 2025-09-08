[assets] (./assets/)

## HTML (`index.html`)

<!DOCTYPE html>
<html lang ="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Weather App</title>
    <link rel="stylesheet" href="style.css">
    <script src="script.js" defer></script>
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@24,400,0,0" />
</head>
<body>

    <div>
        <img src="assets/photo.jpg">
    </div>
    <main class="main-container">

        <header class="input-container">
            <input class="city-input" placeholder="Search City" type="text">
            <button class="search-btn">
                <span class="material-symbols-outlined">
                search
                </span>
            </button>
        </header>
        <section class="weather-info" style="display: none;">
            <div class="location-date-container">
                <div class="location">
                    <span class="material-symbols-outlined">
                        location_on
                    </span>
                    <h4 class="country-txt">Delhi</h4>
                </div>
                <h5 class="current-date-txt regular-txt">Wed 07 Aug</h5>
            </div>
            <div class="weather-summary-container">
                <img src="assets/weather/clouds.svg" class="weather-summary-img">
                <div class="weather-summary-info">
                    <h1 class="temp-txt">29 °C</h1>
                    <h3 class="condition-txt regular-txt">Clouds</h3>
                </div>
            </div>
            <div class="weather-conditions-container">
                <div class="condition-item">
                    <span class="material-symbols-outlined">
                        water_drop
                    </span>
                    <div class="condition-info">
                        <h5 class="regular-txt">Humidity</h5>
                        <h5 class="humidity-value-txt">55%</h5>
                    </div>
                </div>
                    <div class="condition-item">
                    <span class="material-symbols-outlined">
                        air
                    </span>
                    <div class="condition-info">
                        <h5 class="regular-txt">Wind Speed</h5>
                        <h5 class="wind-value-txt">2 M/s</h5>
                    </div>
                </div>
            </div> 
                
                <div class="forecast-items-container">
                    <div class="forecast-item">
                        <h5 class="forecast-item-date regular-txt"> 05 Aug</h5>
                        <img src="/assets/weather/thunderstorm.svg" class="forecast-item-img">
                        <h5 class="forecaste-item-temp"> 29 °C</h5>
                    </div>

                <div class="forecast-item">
                        <h5 class="forecast-item-date regular-txt"> 05 Aug</h5>
                        <img src="/assets/weather/thunderstorm.svg" class="forecast-item-img">
                        <h5 class="forecaste-item-temp"> 29 °C</h5>
                    </div>

                <div class="forecast-item">
                        <h5 class="forecast-item-date regular-txt"> 05 Aug</h5>
                        <img src="/assets/weather/thunderstorm.svg" class="forecast-item-img">
                        <h5 class="forecaste-item-temp"> 29 °C</h5>
                    </div>
                
                <div class="forecast-item">
                        <h5 class="forecast-item-date regular-txt"> 05 Aug</h5>
                        <img src="/assets/weather/thunderstorm.svg" class="forecast-item-img">
                        <h5 class="forecaste-item-temp"> 29 °C</h5>
                    </div>
                </div>
        </section>

        <section class="search-city section-message">
            <img src="assets/message/search-city.png">
             <div>
                <h1>Search City</h1>
                <h4 class="regular-txt">
                    Find out the weather conditions of the city
                </h4>
             </div>
        </section>

         <section class="not-found section-message" style="display: none;">
            <img src="assets/message/not-found.png">
             <div>
                <h1>Search City</h1>
                <h4 class="regular-txt">
                    Find out the weather conditions of the city
                </h4>
             </div>
        </section>
    </main>
    <div class="img-container"> 
        <img src="assets/photo.jpg">
    </div>

</body>
</html>


## CSS (`styles.css`)

@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: "Poppins", sans-serif;
    color: white;
    font-weight: 600;
}

body {
    background: url('assets/bg.jpg');
    width: 100%;
    height: 100dvh;
    background-size: cover;
    background-position: center;
    display: flex;
    align-items: center;
    justify-content: center;
}

body::before{
    content: "";
    position: absolute;
    width: 100%;
    height: 100dvh;
    background: rgb(0, 0, 0, 0.15);
    backdrop-filter: blur(10px);
}
/*Utilities*/
.regular-txt {
    font-weight: 500;
}
/*End Utilities*/
.main-container {
    width: 300px;
    height: 496px;
    z-index: 1;
    background: linear-gradient(
        to top, rgb(0,0,0,0.15),
        rgb(255,255,255,0.15));
    border-radius: 12px;
    backdrop-filter: blur(100px);
    padding: 20px;
}

/* Input container */
.input-container {
    position: relative;
    margin-bottom: 25px;
}
.city-input {
    width: 100%;
    padding: 10px 16px;
    border-radius: 99px;
    border: 3px solid transparent;
    background: rgb(0, 0, 0, 0.15);
    outline: none;
    font-weight: 500;
    transition: 0.25s border;
    padding-right: 45px;
}
.city-input:focus {
    border: 3px solid rgb(0,0,0,0.15);
}
.city-input::placeholder {
    color: rgb(255,255,255,0.75);
}

.search-btn {
    position: absolute;
    right: 16px;
    top: 50%;
    transform: translateY(-50%);
    background: none;
    display: flex;
    border: none;
    cursor: pointer;
}
/* End Input container */

/* Section: Weather Info */
.weather-info {
    display: flex;
    flex-direction: column;
    gap: 25px;
}

.location-date-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.location {
    display: flex;
    align-items: center;
    gap: 6px;
}

.weather-summary-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.weather-summary-img {
    width: 120px;
    height: 120px;
}
.weather-summary-info {
    text-align: end;
}

.weather-conditions-container {
    display: flex;
    justify-content: space-between;
}

.condition-item {
    display: flex;
    align-items: center;
    gap: 6px;
}

.condition-item span {
    font-size: 30px;
}

.forecast-items-container {
    display: flex;
    gap: 15px;
    overflow: scroll;
    padding-bottom: 12px;
}

.forecast-items-container::-webkit-scrollbar {
    height: 8px;
}

.forecast-items-container::-webkit-scrollbar-track {
    background: rgb(0, 0, 0, 0.1);
    border-radius: 99px;
}

.forecast-items-container::-webkit-scrollbar-thumb {
    background: rgb(0, 0, 0, 0.15);
    border-radius: 99px;
}
.forecast-item {
    min-width: 70px;
    background: rgb(255 ,255 ,255 ,0.1);
    display: flex;
    flex-direction: column;
    gap: 6px;
    padding: 10px;
    align-items: center;
    border-radius: 12px;
    transition: 0.3s background;
}

.forecast-item:hover {
    background: rgb(255, 255, 255, 0.15);
}
.forecast-item-img {
    width: 35px;
    height: 35px;
}
/* End Section: Weatehr Info */

/* Section: Message */
.section-message {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    gap: 15px;
    margin-top: 25%;
}
.section-message img {
    height: 180px;
    width: fit-content;
}

/* End Section: Message */

## JavaScript (`script.js`)

const cityInput = document.querySelector('.city-input')
const searchBtn = document.querySelector('.search-btn')

const weatherInfoSection = document.querySelector('.weather-info')
const notFoundSection = document.querySelector('.not-found')
const searchCitySection = document.querySelector('.search-city')

const countryTxt = document.querySelector('.country-txt')
const tempTxt = document.querySelector('.temp-txt')
const conditionTxt = document.querySelector('.condition-txt')
const humidityValuleTxt = document.querySelector('.humidity-value-txt')
const windValueTxt = document.querySelector('.wind-value-txt')
const weatherSummaryImg = document.querySelector('.weather-summary-img')
const currentDateTxt = document.querySelector('.current-date-txt')

const forecastItemsContainer = document.querySelector('.forecast-items-container')


const apiKey = '36cb851cd3775b9dcd0e7d20fbbfed8e'

searchBtn.addEventListener('click', () => {
    if (cityInput.value.trim() != '') {
        updateWeatherInfo(cityInput.value)
        cityInput.value = ''
        cityInput.blur()
    }
})

cityInput.addEventListener('keydown', (event) => {
    if (event.key == 'Enter' &&
        cityInput.value.trim() != ''
    ) {
        updateWeatherInfo(cityInput.value)
        cityInput.value = ''
        cityInput.blur()
    }

})

async function getFetchData(endPoint, city) {
    const apiUrl = `https://api.openweathermap.org/data/2.5/${endPoint}?q=${city}&appid=${apiKey}&units=metric`

    const response = await fetch(apiUrl)
    return response.json()
}

function getWeatherIcon (id)  {
    if (id <= 232) return 'thunderstorm.svg'
    if (id <= 321) return 'drizzle.svg'
    if (id <= 531) return 'rain.svg'
    if (id <= 622) return 'snow.svg'
    if (id <= 781) return 'atmosphere.svg'
    if (id <= 800) return 'clear.svg'
    else return 'clouds.svg'
}

function getCurrentDate () {
    const currentDate = new Date ()
    const options = {
        weekday: 'short',
        day: '2-digit',
        month: 'short',

    }
    return currentDate.toLocaleDateString('en-GB', options)
}

async function updateWeatherInfo(city) {
    const weatherData =await getFetchData('weather', city)

    if (weatherData.cod != 200) {
        showDisplaySection(notFoundSection)
        return
    }

    const {
        name: country,
        main: {temp, humidity },
        weather: [{ id, main }], 
        wind: { speed }
    } = weatherData

    countryTxt.textContent = country
    tempTxt.textContent = Math.round(temp) + ' °C'
    conditionTxt.textContent = main
    humidityValuleTxt.textContent = humidity + ' %'
    windValueTxt.textContent = speed + ' M/s'

    currentDateTxt.textContent = getCurrentDate()
    
    weatherSummaryImg.src = `assets/weather/${getWeatherIcon(id)}`

    await updateForecastsInfo(city)
    showDisplaySection(weatherInfoSection)
    console.log(weatherData)
}

async function updateForecastsInfo(city) {
    const forecastsData = await getFetchData('forecast', city)

    const timeTaken = '12:00:00'
    const todayDate = new Date().toISOString().split('T')[0]

    forecastItemsContainer.innerHTML = ''
    forecastsData.list.forEach(forecastWeather => {
        if (forecastWeather.dt_txt.includes(timeTaken) && 
            !forecastWeather.dt_txt.includes(todayDate)) {
            updateForecastItems(forecastWeather)
        }

    })
    
}

function updateForecastItems(weatherData) {
    console.log(weatherData)
    const {
        dt_txt: date,
        weather: [{ id }],
        main: {temp}
    } = weatherData

    const dateTaken = new Date(date)
    const dateOption = {
        day: '2-digit',
        month: 'short'
    }
    const dateResult = dateTaken.toLocaleDateString('en-US', dateOption)

    const forecastItem = `
    <div class="forecast-item">
            <h5 class="forecast-item-date regular-txt">${dateResult}</h5>
            <img src="/assets/weather/${getWeatherIcon(id)}" class="forecast-item-img">
            <h5 class="forecaste-item-temp">${Math.round(temp)} °C</h5>
    </div>
    `

    forecastItemsContainer.insertAdjacentHTML('beforeend', forecastItem)
}

function showDisplaySection(section) {
    [weatherInfoSection, searchCitySection, notFoundSection]
        .forEach(section => section.style.display = 'none')

    section.style.display = 'flex'
}
