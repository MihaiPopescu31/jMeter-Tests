# OpenWeatherMap, Chuck Norris, and Google.com Load Test using Apache JMeter

This JMeter project tests the OpenWeatherMap API to fetch current weather data for Sibiu, Romania, the Chuck Norris API to fetch Chuck Norris jokes related to sports, and verifies the response time of Google.com. The test is configured to run with 5 concurrent users and includes elements for managing cookies and cache, as well as visualizing and summarizing results.

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

### HTTP Request (Sibiu)

- **Protocol**: `https`
- **Server Name or IP**: `api.openweathermap.org`
- **Method**: `GET`
- **Path**: `/data/2.5/weather`
- **Parameters**:
  - **Name**: `q`
  - **Value**: `Sibiu,RO`
  - **Name**: `appid`
  - **Value**: `b4458723386616a33859cfabde55a9ce`

### HTTP Request (Chuck Norris)

- **Protocol**: `https`
- **Server Name or IP**: `api.chucknorris.io`
- **Method**: `GET`
- **Path**: `/jokes/random`
- **Parameters**:
  - **Name**: `category`
  - **Value**: `sport`

### HTTP Request (Google)

- **Protocol**: `https`
- **Server Name or IP**: `www.google.com`
- **Method**: `GET`

## Running the Test

1. Open Apache JMeter version 5.6.3.
2. Load the test plan (`.jmx`).
3. Configure the `Thread Group` according to the specifications above.
4. Verify the `HTTP Request` configuration to ensure all details are correct.
5. Press the `Start` button (green triangle icon) to run the test.
