# OpenWeatherMap, Chuck Norris, and Google.com Load Test using Apache JMeter

This JMeter project performs load testing on two different APIs and one website: the OpenWeatherMap API to fetch current weather data for Sibiu, Romania; the Chuck Norris API to retrieve sports-related jokes; and the Google.com website to measure response times. The test is configured to run with 5 concurrent users and includes elements for managing cookies and cache, as well as for visualizing and summarizing the results.

## Project Structure

- **Thread Group**: Configures the number of users, ramp-up period, and iterations.
- **HTTP Cookie Manager**: Manages cookies for each user.
- **HTTP Cache Manager**: Manages HTTP cache.
- **HTTP Request (Sibiu)**: Configures the HTTP request to the OpenWeatherMap API for Sibiu, Romania.
- **HTTP Request (Chuck Norris)**: Configures the HTTP request to the Chuck Norris API for sports-related jokes.
- **HTTP Request (Google)**: Configures the HTTP request to Google.com to verify response time.
- **View Results Tree**: Displays detailed results of the test.
- **Summary Report**: Summarizes test results.

## Configuration

### Thread Group

- **Number of Threads (users)**: 5
- **Ramp-Up Period**: 5 seconds
- **Loop Count**: 1

### HTTP Request (Weather in Sibiu)

For this test, visit the website [OpenWeatherMap API](https://openweathermap.org/api) to obtain an API key (you need to create an account on the website and generate one). After obtaining the API key, configure the test with 5 users and a 5-second ramp-up period.

![image](https://github.com/MihaiPopescu31/jMeter-Tests/assets/138394009/f99cd882-70ac-4047-831c-d7482d30ae3b)
![image](https://github.com/MihaiPopescu31/jMeter-Tests/assets/138394009/92ce353f-4af5-4fa9-9618-27b11a2eb370)

Create the test with the specified number of users and ramp-up period, complete the HTTP request configuration, and start the test.

![image](https://github.com/MihaiPopescu31/jMeter-Tests/assets/138394009/2235107c-80b7-46b7-b232-23dd33ca0a77)
![image](https://github.com/MihaiPopescu31/jMeter-Tests/assets/138394009/324b9b82-0465-4228-bb17-5751207ba5ec)

- **Protocol**: `https`
- **Server Name or IP**: `api.openweathermap.org`
- **Method**: `GET`
- **Path**: `/data/2.5/weather`
- **Parameters**:
  - **Name**: `q`
  - **Value**: `Sibiu,RO`
  - **Name**: `appid`
  - **Value**: `b4458723386616a33859cfabde55a9ce`
  
Run the test to see the weather for Sibiu, Romania, and verify that the test executes successfully.

![image](https://github.com/MihaiPopescu31/jMeter-Tests/assets/138394009/be4177ed-9e00-47e5-8949-c6d7e1fc6622)

The response times are also good, without any errors.

![image](https://github.com/MihaiPopescu31/jMeter-Tests/assets/138394009/1fa9685f-955c-4656-abe8-e260973fe0e1)

### HTTP Request (Chuck Norris)

Visit the website [Chuck Norris API](https://api.chucknorris.io/) and choose an endpoint for category-based jokes. Add the necessary parameters, ensuring to include the name `category` and value `sport` for a sports-related joke.

![image](https://github.com/MihaiPopescu31/jMeter-Tests/assets/138394009/86ac2cd8-ae49-4e5b-bc97-da49c1b2c209)
![image](https://github.com/MihaiPopescu31/jMeter-Tests/assets/138394009/a8a4d60b-675a-4bb0-9193-c4f162792302)
![image](https://github.com/MihaiPopescu31/jMeter-Tests/assets/138394009/b345054f-9a7e-49c8-aa3d-ba4932e8977f)

- **Protocol**: `https`
- **Server Name or IP**: `api.chucknorris.io`
- **Method**: `GET`
- **Path**: `/jokes/random`
- **Parameters**:
  - **Name**: `category`
  - **Value**: `sport`

Run the test and verify the results in the "View Results Tree" element. The test should return a 200 OK response code, and the joke should be displayed.

![image](https://github.com/MihaiPopescu31/jMeter-Tests/assets/138394009/8885b146-7198-423e-8fb8-29aec92b5a44)

The "Summary Report" will show the timing results and all relevant information.

![image](https://github.com/MihaiPopescu31/jMeter-Tests/assets/138394009/68b636f0-d667-41fc-adfe-d26934159ee7)

### HTTP Request (Google)

- **Protocol**: `https`
- **Server Name or IP**: `www.google.com`
- **Method**: `GET`

![image](https://github.com/MihaiPopescu31/jMeter-Tests/assets/138394009/f3f8d0f4-05f5-4d3d-a5e2-ebe4166728fa)
![image](https://github.com/MihaiPopescu31/jMeter-Tests/assets/138394009/58a5327b-0d6e-4469-b396-baf616a71102)

As seen in the test results in the "View Results Tree" section, each user receives two response codes: 301 to redirect the URL, and 200 indicating the test is successful. The "Summary Report" shows an average response time of 337 milliseconds, with the shortest load time being 232 milliseconds and the longest load time being 677 milliseconds.

![image](https://github.com/MihaiPopescu31/jMeter-Tests/assets/138394009/1a79b523-d96d-4457-a5dc-dfcd6a80f078)
![image](https://github.com/MihaiPopescu31/jMeter-Tests/assets/138394009/144b709e-f76a-4a76-a73d-f75c098fd7a4)

## Running the Test

1. Open Apache JMeter version 5.6.3.
2. Load the test plan (`.jmx`).
3. Configure the `Thread Group` according to the specifications above.
4. Verify the `HTTP Request` configuration to ensure all details are correct.
5. Press the `Start` button (green triangle icon) to run the test.
