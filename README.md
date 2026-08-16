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

<details>
<summary><strong>🌬️ Wind Turbine Site Planner</strong> — ArcGIS Pro planning and validation automation</summary>

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
<summary><strong>⚡ EnergyGIS</strong> — Desktop GIS platform with automated Bruttoertrag calculation</summary>

<br>

**EnergyGIS** is a modular Python desktop application that brings mapping, data management and geoprocessing tools into one independent workspace. It is designed to make repeatable GIS workflows easier to run, extend and distribute without relying on a full proprietary desktop-GIS installation.

![EnergyGIS desktop geospatial analysis workspace](assets/energygis-profile.webp)

### Automated Bruttoertrag workflow

One of the central EnergyGIS workflows automates the process from wind-resource data preparation to the final annual gross-yield result:

1. Retrieves and prepares the required wind-resource inputs
2. Reads turbine coordinates, hub height, model and rated capacity from Excel
3. Samples mean wind speed, Weibull **A/K** parameters and air density at reference heights
4. Adjusts the wind parameters to the exact turbine hub height
5. Matches each turbine model to the appropriate power curve
6. Calculates the annual **Bruttoertrag in MWh/a**
7. Writes the results and validation status back to a structured Excel output

The calculation combines spatial raster sampling, height interpolation, air-density correction, Weibull wind-speed distributions and density-dependent turbine power curves. Missing coordinates, unmatched power curves or unavailable raster values are reported transparently instead of being silently ignored.

**Generated values include:** gross yield, matched power curve, mean wind speed at hub height, air density, Weibull A/K parameters and calculation status.

### Application capabilities

- Automated wind-resource data preparation and Bruttoertrag calculation
- Interactive map workspace with layer management
- Attribute-table viewing and spatial dataset browsing
- Modular registry for adding and organizing GIS tools
- Vector, raster, wind-energy and gross-yield tool categories
- Reusable parameter framework with validation and progress feedback
- Integrated Python console and tool documentation
- Local map-service components for desktop visualization
- Admin-free portable Windows packaging for user testing

### Geoprocessing architecture

EnergyGIS separates the user interface, processing services and individual GIS tools. This modular structure allows new workflows to be registered consistently and executed through a common parameter interface.

Current processing areas include:

| Area | Examples |
|---|---|
| Vector processing | Buffer, dissolve, geometry repair and spatial workflows |
| Raster processing | Raster-based analysis and data preparation |
| Wind analysis | Wind-project and turbine-related processing |
| Gross yield | Automated data preparation, raster sampling, power-curve matching and annual MWh/a calculation |
| Data management | Layer properties, attribute tables and dataset discovery |

**Technology:** Python · PySide6 · GDAL · GeoPandas · Shapely · Pyogrio · PyProj · Geofileops · Pandas

> EnergyGIS is under active development. Source code and project-specific data are maintained in a private repository.

</details>

## Current interests

- Scalable GIS tools and reusable processing workflows
- Desktop GIS applications independent of proprietary processing extensions
- Renewable-energy and wind-project assessment
- Geospatial APIs, data integration and workflow automation
- Practical applications of AI in GIS

## Connect

[LinkedIn](https://www.linkedin.com/in/ahmad-fahim-omar-9bb95b272/)
