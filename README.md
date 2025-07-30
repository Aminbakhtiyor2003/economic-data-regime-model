# economic-data-regime-model

This project is an attempt to impose structure on the messiness of macroeconomic data, creating what I call a “macro fingerprint” of the U.S. economy. The goal was to take decades of data, organize it into a coherent framework, and produce a consistent signal that captures the prevailing economic regime at any point in time.

The model ingests a broad set of indicators from the Federal Reserve Economic Data (FRED) API and classifies them into four key dimensions of the macro environment: Growth, Inflation, Liquidity, and Policy. These are, in my view, the fundamental pillars that define the economic backdrop against which all assets trade. For each month since 1970, the model assigns both numeric scores and qualitative labels (e.g., Strong Growth, Falling Inflation, Loose Policy, Liquid Markets).

The pipeline was built to be systematic and transparent:

Data retrieval: Pulls long-run time series from FRED.

Cleaning and alignment: Handles frequency mismatches, missing values, and converts raw levels to percentage changes for comparability.

Standardization: Applies Z-score normalization to eliminate scale differences between indicators.

Weighted aggregation: Groups signals into themes using a judgment-based weighting scheme informed by academic research and practitioner heuristics.

Labeling: Translates scores into intuitive regime descriptors to make patterns more interpretable.

Output: Produces structured CSV datasets for each theme and a combined macro regime timeline.

This was not designed to be a trading model. Instead, it is a thinking tool that helps explore how macro conditions evolve and how different combinations of growth, inflation, liquidity, and policy environments might influence risk asset performance. The next stage is to align these fingerprints with asset return data to study conditional performance across regimes, identifying which asset classes and strategies historically fared well under different macro conditions.

Key observations and limitations
Building this framework clarified several realities about using macro data in investment decision-making:

Lagging nature of economic data: By the time indicators are released, markets have often repriced to anticipated conditions.

Most information is priced in: Prices react to surprises versus expectations, not the reported numbers themselves. Especially since certiant funds already use alt data to track inflation, growth, ect. 

Data incompleteness: Official statistics miss crucial elements of market dynamics such as positioning, liquidity shocks, and non-economic risks.

Manual weighting bias: My current weights reflect personal judgment, not empirical optimization. This introduces subjectivity that can materially affect regime classification.

Thematic grouping assumptions: Indicators were clustered based on academic literature and reasoning. A data-driven clustering or dimensionality reduction approach might yield a different structure.

Low-to-moderate explanatory power: Macro factors typically explain only ~30–40% of asset price variation, and their relationships change over time.

These limitations do not make the exercise futile. They make it educational. Constructing the model forced me to think carefully about what truly drives markets, why prices often move ahead of data, and how investor psychology interacts with fundamentals. My next iteration will focus on:

Incorporating forecast errors and surprises instead of static data points.

Using machine learning and regression techniques to learn weights directly from asset return sensitivities.

Expanding the dataset to include leading indicators and alternative data sources that are timelier than official releases.

This project is a first attempt at structuring macro complexity into an interpretable framework. It is imperfect, but it has value: it provides a disciplined, repeatable way of looking at the economy, builds intuition about regime dynamics, and sets the foundation for future research into systematic links between macro conditions and asset returns. 
