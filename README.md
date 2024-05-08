# U.S. Airline Slot Allocation Value Model
Value model for the nine large U.S. airlines under a large-scale slot auction. The set of slot-controlled aiports can be chosen arbitrarily in the code.

### Parameters:
The parameters included are for the nine largest U.S. airlines according to their IATA code. We used the following data from the Bureau of Transportation Statistics from the Summer 2023 season:

 - [On-Time Performance dataset](https://www.transtats.bts.gov/DL_SelectFields.aspx?gnoyr_VQ=FGJ&QO_fu146_anzr=b0-gvzr) from April 2023 - October 2023
 - [Schedule B-43 Aircraft Inventory](https://www.overleaf.com/project/662acb3d29aa67f306d40d33) from 2022
 - [Schedule P-52 Air Carrier Financial information](https://www.transtats.bts.gov/DL_SelectFields.aspx?gnoyr_VQ=FMK&QO_fu146_anzr=Nv4%20Pn44vr4%20Sv0n0pvny) from 2023 Q2
 - [DB1B Ticket Origin and Destination Survey](https://www.overleaf.com/project/662acb3d29aa67f306d40d33) from 2023 Q2 + Q3
  - [DB1B Coupon Origin and Destination Survey](https://www.overleaf.com/project/662acb3d29aa67f306d40d33) from 2023 Q2 + Q3

Please read Appendix A of the associated paper to understand how this data was used to form our model parameters.

### Usage:
First, you must apply for a free Guorbipy Academic Named-User License [here](https://www.gurobi.com/features/academic-named-user-license/) . Then, you can find the API parameters of your license [here](https://portal.gurobi.com/iam/licenses/list/). Add these to the variable `PARAM` at the top of `model.ipynb`.

Next, select your choice of airlines, slot-controlled airlines, and slot allocations. Then, run the notebook to completion. Results will be saved to the `results` directory as a Pandas DataFrame.

Note that the solution to the model without slot controls may still not choose to fly every flight. This is an artifact of the 10% sampling of passenger itineraries that is provided by BTS' DB1B, as all flights may not have enough expressed demand to become profitable to fly. We suggest comparing slot-controlled results relative to this solution.


### Citation:
TBD


