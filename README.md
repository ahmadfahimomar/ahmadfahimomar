# Hi, I'm Ahmad Fahim Omar 👋

### GIS Analyst & Developer

I develop geospatial tools and automated workflows for spatial analysis, data processing, and renewable-energy planning. My work focuses on turning complex GIS processes into reliable, reusable, and user-friendly solutions.

📍 Hamburg, Germany

## Expertise

- **GIS development:** ArcGIS Pro, ArcGIS Pro SDK for .NET, ArcPy
- **Web GIS:** ArcGIS Experience Builder and ArcGIS APIs
- **Geospatial Python:** GDAL, GeoPandas, Shapely, Pyogrio and PyProj
- **Data processing:** Pandas, NumPy and spatial databases
- **Development:** Python, C#/.NET, Qt and Git
- **Focus:** GIS automation, desktop GIS applications and renewable energy

## Selected projects

Click a project below to view its details, workflow and technologies.

<details>
<summary><strong>🌬️ Wind Turbine Site Planner</strong> — ArcGIS Pro planning and validation automation · <em>View details</em></summary>

<br>

An ArcGIS Pro geoprocessing tool for preparing and validating wind-turbine planning data. Its main focus is the automated calculation of the German **Baulastkreis** according to the selected federal state, planning context and turbine geometry.

![Wind Turbine Site Planner showing an example Baulastkreis calculation](assets/wind-turbine-site-planner.svg)

### Baulastkreis calculation

Baulast requirements for wind turbines are not represented by one universal calculation. The tool selects the applicable rule using:

- the selected **Bundesland**
- whether a **Bebauungsplan** applies
- the state-specific eccentricity method
- the technical dimensions of the selected turbine

| Variable | Meaning |
|---|---|
| **tf** | Tower base diameter |
| **nh** | Hub height |
| **rr** | Rotor radius |
| **exz_mitte** | Eccentricity at rotor centre |
| **exz_oben** | Eccentricity at upper rotor position |

Depending on the selected rule, the calculation combines the relevant turbine dimensions and eccentricity parameters using the applicable state-specific method. Parameter changes are validated immediately, and the calculated value can be written to the output features together with a spatial buffer for map-based review.

### Calculated and enriched outputs

| Output | Description |
|---|---|
| Total turbine height | Overall height from the foundation reference to the upper rotor tip |
| Height above ground level | Turbine height relative to ground level, including foundation elevation or depth |
| Ground elevation | Terrain elevation sampled for each turbine location |
| Rotor geometry | Rotor diameter and rotor radius of the selected turbine model |
| Foundation geometry | Foundation radius and elevation/depth values |
| Eccentricity | Applicable centre or upper eccentricity according to the selected state rule |
| Baulastkreis | Calculated state-specific radius and spatial review buffer |
| Turbulence distances | Additional zones for preliminary spatial assessment |
| Location attributes | Federal state, parcel and administrative information |

The tool also provides automatic turbine-parameter lookup, validation inside the ArcGIS Pro dialog, attribute enrichment, and support for **EPSG:25832** and **EPSG:25833**.

**Technology:** Python · ArcPy · ArcGIS Pro · Geoprocessing

> Source code, calculation tables and project data are maintained in a private repository.

</details>


<details>
<summary><strong>⚡ EnergyGIS</strong> — Desktop GIS workflows for wind-energy analysis · <em>View details</em></summary>

<br>

**EnergyGIS** is a modular desktop GIS application I am building with Python and PySide6. The goal is simple: bring recurring geospatial and wind-energy tasks into one consistent workspace—from public source data to structured yield results.

![EnergyGIS desktop geospatial analysis workspace](assets/energygis-profile.webp)

### Wind Analysis workflow

The Wind toolbox connects four tools into a practical end-to-end workflow:

| Step | Tool | What it does |
|---|---|---|
| 1 | **MaStR Wind Turbines** | Downloads public wind-turbine records and filters them by federal state, operating status, and onshore/offshore location |
| 2 | **Create WTG Names** | Cleans turbine attributes and creates consistent model names for reliable power-curve matching |
| 3 | **Calculate Gross Yield** | Samples wind-atlas rasters, adjusts values to hub height, matches the turbine power curve, and calculates annual gross yield |
| 4 | **Calculate Net Yield** | Applies configurable project losses and calculates net yield and load factor for preliminary assessment |

The gross-yield workflow combines turbine coordinates, hub height, rated capacity, Weibull parameters, mean wind speed, air density, and density-dependent power curves. Results are written directly to the working Excel file together with clear status information for missing inputs, unmatched power curves, or unavailable raster values.

### Designed for repeatable work

- Shared parameter interface for all registered tools
- Dynamic worksheet and field selection
- Progress reporting and cancellation
- Separate worker process for the resource-intensive gross-yield calculation
- Map, layer, attribute-table, and dataset-management functions
- Portable Windows build for admin-free user testing
- Modular structure for adding further vector, raster, and energy tools

**Technology:** Python · PySide6 · GDAL · GeoPandas · Shapely · Pyogrio · PyProj · Geofileops · Pandas · OpenPyXL

> EnergyGIS is under active development. The source code and project-specific data are maintained in a private repository. Yield results are intended for technical screening and do not replace a certified energy-yield assessment.

</details>

<details>
<summary><strong>🔌 Cable Route Optimizer</strong> — Cost-aware routing between wind-energy areas and substations · <em>View details</em></summary>

<br>

**Cable Route Optimizer** is an ArcGIS Pro geoprocessing tool for identifying a practical cable corridor between wind-energy areas and substations. Instead of drawing a direct connection, it evaluates the surrounding terrain and infrastructure and searches for a lower-cost route.

![Cable Route Optimizer showing a completed route, attribute table and geoprocessing toolbox](assets/cable-route-optimizer.webp)

### Routing workflow

| Step | What happens |
|---|---|
| 1 | Validate the input locations and coordinate system |
| 2 | Define the analysis area around the wind-energy site and substation |
| 3 | Combine land use, terrain slope, transport infrastructure, water features, and optional project barriers |
| 4 | Convert the prepared spatial information into a weighted cost surface |
| 5 | Select suitable boundary points using a KD-tree search |
| 6 | Calculate an optimized route with a custom eight-direction A* algorithm |
| 7 | Export the result as a GIS polyline for technical review |

### Planning features

- Configurable cost and barrier weighting
- Terrain-slope integration
- Optional project-specific exclusion areas
- Efficient boundary-point matching
- ArcGIS Pro progress reporting and temporary-data cleanup
- Input validation for **ETRS89 / UTM zone 32N (EPSG:25832)**

**Technology:** Python · ArcPy · NumPy · SciPy · Raster analysis · A* pathfinding

> Source code, service endpoints, project data, and historical development versions are maintained in a private repository. The result supports preliminary route assessment and does not replace detailed engineering or permitting.

</details>


## Current interests

- Scalable GIS tools and reusable processing workflows
- Desktop GIS applications independent of proprietary processing extensions
- Renewable-energy and wind-project assessment
- Geospatial APIs, data integration and workflow automation
- Practical applications of AI in GIS

## Connect

[LinkedIn](https://www.linkedin.com/in/ahmad-fahim-omar-9bb95b272/)
