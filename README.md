# -REST-API-CLIENT

NAME: HARSHAL MALI

INTERN ID: CT08QVR

DOMAIN: JAVA PROGRAMMING

DURATION: 4 WEEEKS

MENTOR: NEELA SANTOSH

#description -

This Java code defines a program that retrieves and displays weather information for a user-specified city.  The program utilizes two external APIs: one for geocoding (converting city names to geographical coordinates) and another for retrieving weather forecasts.  The core functionality is encapsulated within the WeatherAPIData class, which contains the main method and several helper methods to handle API interaction, data parsing, and output.

The program's execution begins in the main method, which sets up a loop to continuously prompt the user for a city name.  The loop continues until the user enters "No," at which point the program terminates.  Inside the loop, the program first calls the getLocationData method, passing the user-provided city name as an argument.  This method constructs a URL for the geocoding API, which is hosted by open-meteo.com.  The URL includes the city name, and parameters to limit the number of results to one, specify the language as English, and request the data in JSON format.  The getLocationData method then uses the fetchApiResponse method to establish a connection with the geocoding API and retrieve the JSON response.  The fetchApiResponse method handles the low-level details of creating a HttpURLConnection object, setting the request method to GET, and returning the connection object.  The getLocationData method checks the HTTP response code to ensure the connection was successful. If successful, it calls the readApiResponse method to read the JSON response from the API connection's input stream and convert it into a String.  The readApiResponse method uses a Scanner to read the input stream line by line and appends each line to a StringBuilder to efficiently construct the complete JSON string.  The resulting JSON string is then parsed using the JSONParser class from the org.json.simple library, converting it into a JSONObject.  The getLocationData method extracts the latitude and longitude from the parsed JSON object, which represent the geographical coordinates of the requested city, and returns these coordinates as a JSONObject.

Back in the main method, after retrieving the latitude and longitude, the program calls the displayWeatherData method, passing these coordinates as arguments.  This method constructs a URL for the weather forecast API, also hosted by open-meteo.com.  This URL includes the latitude and longitude, and specifies that the program is interested in the current weather conditions, specifically temperature, relative humidity, and wind speed.  Similar to the getLocationData method, displayWeatherData uses fetchApiResponse to connect to the weather API, checks the HTTP response code, and uses readApiResponse to retrieve the JSON response as a String.  The JSON response is then parsed into a JSONObject, and the current weather data is extracted from the "current" field of the JSON object.  The displayWeatherData method then retrieves the current time, temperature, relative humidity, and wind speed from this JSON object.  The temperature is retrieved as a double, relative humidity as a long, and wind speed as a double.  Finally, the method prints the current time, temperature, relative humidity, and wind speed to the console.

Both the getLocationData and displayWeatherData methods include comprehensive error handling using try-catch blocks.  If any exception occurs during the API interaction, data parsing, or any other part of the process, the exception's stack trace is printed to the console, providing valuable debugging information.  This ensures that the program handles potential errors gracefully and provides informative feedback to the user.  The use of the org.json.simple library simplifies the process of parsing JSON responses, making the code more readable and maintainable.  The program's modular design, with separate methods for different tasks, enhances code organization and promotes reusability.  The clear and concise variable names further contribute to the code's readability.  Overall, the code demonstrates a well-structured approach to interacting with external APIs, parsing JSON data, and presenting weather information to the user in a user-friendly format.




#OUTPUT - 

![Image](https://github.com/user-attachments/assets/0c8d3a21-e79d-4cb6-b110-eb3c326be621)
