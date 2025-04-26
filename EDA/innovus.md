The file describes how i use innovus physical implementation system to implement open source RISCV processor.

# Steps involved
1. init_design, specifying mmmc, pgnets, input netlists...
2. Floorplan, including floorplan, macro placement, (optional)IO placement, tap-cap placement, and PDN generation.
3. Placement and optimization, place pins if it is block level design.
4. CTS, ccopt_design will do cts and both datapath and clockpath optimization. But remember refinePlace after it.
5. Routing. routeDesign is okay, it do global routing(assign wires to gcells), track assignment, and detail routing.
