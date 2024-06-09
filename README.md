```markdown
# CoWIN Dashboard

In this project, I have built a **CoWIN Dashboard** by applying various concepts.

### Screenshots:

**Success View**

<br/>
<div style="text-align: center;">
    <img src="https://assets.ccbp.in/frontend/content/react-js/cowin-dashbaord-output.gif" alt="cowin-dashboard-success-view" style="max-width:70%;box-shadow:0 2.8px 2.2px rgba(0, 0, 0, 0.12)">
</div>
<br/>

**Failure View**

<br/>
<div style="text-align: center;">
    <img src="https://assets.ccbp.in/frontend/content/react-js/cowin-dashbaord-failure-view-output.gif" alt="cowin-dashboard-failure-view" style="max-width:70%;box-shadow:0 2.8px 2.2px rgba(0, 0, 0, 0.12)">
</div>
<br/>

### Design Files

<details>
<summary>Click to view</summary>

- [Extra Large Devices (Size >= 1200px) - Success View](https://assets.ccbp.in/frontend/content/react-js/cowin-dashboard-xl-output.png)
- [Extra Large Devices (Size >= 1200px) - Failure View](https://assets.ccbp.in/frontend/content/react-js/cowin-dashbaord-xl-failure-view-output.png)

</details>

### Implementation Details

The app has the following functionalities:

- On page load, an HTTP GET request is made to **covidVaccinationDataApiUrl**.
- A **loader** is displayed while the HTTP request is fetching the data.
- After successful data fetch, the response is displayed using different charts from `recharts`.
  - Last 7 days vaccination data is displayed using the `BarChart` component.
  - Vaccination data by gender and age are displayed using the `PieChart` component.
- If the HTTP GET request fails, a **FailureView** is displayed.

### API Requests & Responses

**covidVaccinationDataApiUrl**

- **API:** `https://apis.ccbp.in/covid-vaccination-data`
- **Method:** `GET`
- **Description:** Returns a response containing the vaccination data.

#### Success Response Example:

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
```

### Components Structure

<br/>
<div style="text-align: center;">
    <img src="https://assets.ccbp.in/frontend/content/react-js/cowin-dashbaord-component-structure-breakdown.png" alt="component-breakdown-structure" style="max-width:100%;box-shadow:0 2.8px 2.2px rgba(0, 0, 0, 0.12)">
</div>
<br/>

### Implementation Files

Use these files for reference:

- `src/components/CowinDashboard/index.js`
- `src/components/CowinDashboard/index.css`
- `src/components/VaccinationCoverage/index.js`
- `src/components/VaccinationCoverage/index.css`
- `src/components/VaccinationByGender/index.js`
- `src/components/VaccinationByGender/index.css`
- `src/components/VaccinationByAge/index.js`
- `src/components/VaccinationByAge/index.css`

### Important Note

For the tests to pass, ensure the following:

- Wrap the Loader component with an HTML container element and add the `data-testid` attribute value as `loader`.

  ```jsx
  <div data-testid="loader">
    <Loader type="ThreeDots" color="#ffffff" height={80} width={80} />
  </div>
  ```

- Provide `width` and `height` to the respective chart component.

  ```jsx
  <BarChart width={1000} height={300} />
  ```

### Resources

<details>
<summary>Image URLs</summary>

- [Failure View](https://assets.ccbp.in/frontend/react-js/api-failure-view.png)
- [Website Logo](https://assets.ccbp.in/frontend/react-js/cowin-logo.png)

</details>

<details>
<summary>Colors</summary>

- Hex: #161625
- Hex: #2cc6c6
- Hex: #cbd5e1
- Hex: #ffffff
- Hex: #1c1c2b
- Hex: #2d87bb
- Hex: #a3df9f
- Hex: #64c2a6
- Hex: #94a3b8
- Hex: #f54394
- Hex: #5a8dee
- Hex: #6c757d

</details>

<details>
<summary>Font-families</summary>

- Roboto

</details>
