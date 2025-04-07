We try using openroad as our backend tool for PnR.
Openroad [https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts] itself presents as a kind of 'framework',
that incorporates some of the opensource EDA tools,
including yosys for synthesis, openroad itself for FP,P,CTS,R,
and klayout for final completion.

Since i'm more familiar with design compiler, we can do the synthesis process using DC instead of yosys,
and do the rest using openroad framework.

So, the remaining process are listed as follows:

- floorplan
- place
- clock tree synthesis, CTS
- route
- final
