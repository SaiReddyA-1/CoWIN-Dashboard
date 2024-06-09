# CoWIN Dashboard

In this project, I have built a **CoWIN Dashboard** by applying various concepts.

## Screenshots

**Success View**

![Success View](https://assets.ccbp.in/frontend/content/react-js/cowin-dashbaord-output.gif)

**Failure View**

![Failure View](https://assets.ccbp.in/frontend/content/react-js/cowin-dashbaord-failure-view-output.gif)

## Design Files

<details>
<summary>Click to view</summary>

- [Extra Large Devices (Size >= 1200px) - Success View](https://assets.ccbp.in/frontend/content/react-js/cowin-dashboard-xl-output.png)
- [Extra Large Devices (Size >= 1200px) - Failure View](https://assets.ccbp.in/frontend/content/react-js/cowin-dashbaord-xl-failure-view-output.png)

</details>

## Implementation Details

The app has the following functionalities:

- On page load, an HTTP GET request is made to **covidVaccinationDataApiUrl**.
- A **loader** is displayed while the HTTP request is fetching the data.
- After successful data fetch, the response is displayed using different charts from `recharts`.
  - Last 7 days vaccination data is displayed using the `BarChart` component.
  - Vaccination data by gender and age is displayed using the `PieChart` component.
- If the HTTP GET request fails, a **FailureView** is displayed.

## API Requests & Responses

**covidVaccinationDataApiUrl**

- **API:** `https://apis.ccbp.in/covid-vaccination-data`
- **Method:** `GET`
- **Description:** Returns a response containing the vaccination data.

### Success Response Example

```json
{
  "last_7_days_vaccination": [
    {
      "vaccine_date": "30th Jul",
      "dose_1": 3757930,
      "dose_2": 1817805
    }
  ],
  "vaccination_by_age": [
    {
      "age": "18-44",
      "count": 482792375
    }
  ],
  "vaccination_by_gender": [
    {
      "count": 4809680,
      "gender": "Male"
    }
  ]
}
