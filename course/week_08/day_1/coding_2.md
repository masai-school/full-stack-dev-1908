![](https://img.shields.io/badge/MASAI-SPARTANS-red?logo=&style=for-the-badge)

![](https://img.shields.io/badge/WEEK8-DAY1-green)



#### Coding Session - 1


install [react-chart-js-2](https://www.npmjs.com/package/react-chartjs-2)

```
npm install --save react-chartjs-2 chart.js
```

Example
```
import { Doughnut } from 'react-chartjs-2';
 
<Doughnut data={...} />
```

Properties:

    data: (PropTypes.object | PropTypes.func).isRequired,
    width: PropTypes.number,
    height: PropTypes.number,
    id: PropTypes.string,
    legend: PropTypes.object,
    options: PropTypes.object,
    redraw: PropTypes.bool,
    getDatasetAtEvent: PropTypes.func,
    getElementAtEvent: PropTypes.func,
    getElementsAtEvent: PropTypes.func
    onElementsClick: PropTypes.func, // alias for getElementsAtEvent (backward compatibility)


Create an object with data sets for days in the month June
The object should contain infromation of stock prices for 30 days
Add other details that are needed according to documentation

Refer this Codesandbox example on how to use [react-chartjs-2](https://codesandbox.io/s/react-chartjs-2-example-zmvmd)

Create the Line chart component, and display the information of the stock prices on the chart

## Minimum Viable Product

MVP or minimum viable product is the least amount of functionality you must have done by the end of today.

- [ ] Implement the Line Chart without any errors
- [ ] Display all the information on the chart
- [ ] Show labels, grids and date


## Stretch Goals

If you are able to complete the MVP in time, implement this additional functionality. 

- [ ] Find the max and min stock price from the data set
- [ ] Users should be able to edit and change values of the data. This should rerender the chart automatically