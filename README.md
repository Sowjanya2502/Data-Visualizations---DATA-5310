

 ***Seattle Airbnb Market: A Data Visualization Analysis***

Introduction 

Short-term rentals are becoming an increasingly popular option for urban lodging, and Seattle provides a compelling case study for understanding how these markets are growing and evolving. This report will examine recent patterns in Seattle’s Airbnb market with a goal of identifying meaningful trends, clustering similar types of short-term rentals, and informs the expectations of visitors choosing accommodations across the city. By exploring the variations in property types, pricing, amenities, and different neighborhoods, this analysis offers insights that are valuable both for prospective tourists and for understanding broader shifts in the hospitality industry towards Airbnb rentals. The findings can be further contextualized by comparing Seattle’s Airbnb trends with those observed in other major urban areas and considering how the rise of short-term rentals interacts with other traditional services in the industry like hotels or hostels. Raw data is drawn primarily from InsideAirbnb.com, which is a mission driven project that provides publicly accessible data and advocates for the impacts of Airbnb rentals on residential communities. The platform complies detailed, web-scraped Airbnb listings collected on a quarterly basis for cities, such as the Greater Seattle Area. While the dataset offers valuable insights into local short-term rental markets, the automated data collection process introduces several limitations including potential inaccuracies, missing values, and data integrity concerns. These factors result in requiring careful data cleaning, validation, and interpretation. Acknowledging these nuances ensures that the visualizations and findings remain transparent, and reflective of both the strengths and constraints of the underlying data.  

Data Preparation 

To enable accurate and insightful visualizations, the main data set on Seattle Airbnb listings was first cleaned and transformed to ensure data integrity and suitability for data exploration and analysis. Firstly, all columns unrelated to the planned visualizations were removed, keeping the data columns mainly focused on price, accommodation characteristics, location, and Airbnb reviews. Handling missing values were tricky, but ultimately all missing or incomplete records were excluded reducing the data set from roughly seven thousand to about three and a half thousand records. Imputing average values did not make sense for columns like price, number of beds, and bathrooms, as these attributes could vary widely among different types of Airbnb’s, likely skewing plots and visualization analyses. About a thousand rows lacked review information, since all of these Airbnb rows shared missing values, these were removed to maintain data quality and relevance. The reduction in data also ensured compatibility with Altair, as the package works optimally for data sets under five thousand rows. 

To better organize listings within the greater Seattle area, the Airbnb data was compared with a separate neighborhoods dataset that grouped smaller neighborhoods into larger, more manageable clusters. This allows for more consistent neighborhood categorization and allowed for choropleth maps to be more easily interpreted. Additionally, neighborhoods with very few entries or neighborhoods that were further away from the central Seattle area were removed to prevent outliers from skewing visualizations, ensuring that the resulting plots accurately reflected typical trends across the city. Finally, key accommodation characteristics were examined for consistency. Listings reporting no beds, bedrooms, or bathrooms likely represent atypical units like studios or listings with communal bathrooms, or represented scraping errors. Entries with these inconsistencies were removed to support clearer and more interpretable visualizations.  

Several assumptions were made during data preparation. For example, some listings had unusually high minimum or maximum stay requirements, indicating that they might function more similarly to medium-term rentals. These entries were retained, as they likely reflect genuine trends within the broader rental market and do not significantly impact the analysis. Further filtering was anticipated during the creation of exploratory plots, with adjustments applied on a plot-specific basis depending on the goals of each visualization. This approach allows for more precise and meaningful representations without compromising the integrity of the underlying dataset.  

Motivation 

The analysis is guided by five key questions aimed at understanding and communicating patterns within Seattle’s Airbnb market. First, the analysis seeks to determine how Airbnb characteristics, such as price, number of beds and bathrooms, and guest capacity, vary across different neighborhoods in the Greater Seattle Area. Second, it explores various factors and features of an Airbnb that generally influence its pricing. Third, the study examines the relationship between a host’s response time and overall listing ratings, highlighting the impact of host engagement on perceived quality. Fourth, it investigates whether certain neighborhoods tend to feature specific types of Airbnb accommodations, revealing potential spatial trends and market segmentation. Finally, the analysis identifies the most common amenities offered in Seattle Airbnbs, offering a clearer picture of the typical guest experience and some factors that contribute to listing appeal. Together, these questions aim to provide a comprehensive understanding of the local short-term rental market in the greater Seattle area and informs meaningful comparisons and recommendations for visitors coming to the city.  

1. Do Airbnb characteristics (i.e. price, bed/baths, number of guests accommodated, etc.) change across different neighborhoods in the Greater Seattle Area? 

2. What qualities of an Airbnb influence the pricing? 

3. How does an Airbnb host's response time impact the overall rating of the Airbnb? 

4. Do different neighborhoods more commonly feature different Airbnb characteristics? 

5. What are some common amenities offered in Seattle Airbnb's? 

 

Results and Analysis 

This section presents a comprehensive exploration of Airbnb listings in Seattle, examining how pricing, property characteristics, availability, and amenities vary across different neighborhoods. A combination of plots including small multiples, compound figures, choropleth maps, and interactive visualizations highlights the relationships between nightly price, guest capacity, listing features, and spatial context. These visualizations reveal patterns and trends that cannot be easily understood from the raw data, enabling comparisons across different neighborhoods, market segmentations, and insights into different geographic distributions, providing a detailed view of the short-term rental market in Seattle.  

 

Figure I. Small Multiples plot visualizing the relationship between guests accommodated and price per night of Airbnb listings across different neighborhoods in Seattle. 
![alt text](https://github.com/Sowjanya2502/Data-Visualizations---DATA-5310/blob/main/Final_Project/Plots/SmallMultiplesPlot.png)


To investigate how an Airbnb’s nightly price per night changes as more guests are accommodated, a small multiples visualization is utilized to analyze these trends across different neighborhoods in the greater Seattle area. Each plot iteration is a scatter plot, which effectively captures the continuous relationship between the two quantitative variables, being guests accommodated and price. The point encoding reduces the point size and transparency to help reduce over plotting while still allowing viewers to analyze dense areas. The x and y-axes are encoded with consistent quantitative scales across all plot iterations, to ensure meaningful and effective comparisons across neighborhoods. The column encoding creates a series of side by side plots, each representing a distinct neighborhood, which makes price trends easier to interpret than if they were combined into a single plot with color encoding instead. The tooltip interact enhances the chart usability, allowing viewers to inspect listing-level details without cluttering the chart. Lastly, Airbnb outliers with priced over $600 per night are filtered out of this chart to maintain a balanced scale and prevent extreme values from compressing majority of the data. Overall, small multiples provide a clean, comparative lends for understanding how pricing behaves across various Seattle neighborhoods.  

The small multiples plot reveals how the relationship between guest capacity and nightly Airbnb price varies across some of Seattle’s major neighborhoods, including the Central Area, Downtown, Queen Anne, West Seattle, and other. Across all neighborhoods there is a clear positive linear trend, meaning that generally as Airbnbs accommodate more guests their prices tend to be higher. However, the structure of each panel highlights important differences among neighborhoods. The Downtown plot stands out for having a dense cluster of listings at generally accommodate fewer people, typically in the mid-range of Airbnb nightly prices. This pattern likely reflects the prevalence of compact urban units and higher costs closer to the city. In contrast, neighborhoods such as West Seattle, Queen Anne, and Central Area display a wider spread of both guests accommodated and price values, indicating more diverse short term rental options. The plot showing other neighborhoods shows a similar broad variation of rentals, suggesting that areas outside of major hubs in Seattle offer a full spectrum of listing types. Overall, this small multiples plot identifies how neighborhood context shapes both the size and pricing of Airbnb rentals, which can vary from neighborhood to neighborhood.  

 

 

Figure II. Compound Figure showing Seattle Airbnb listings prices: the scatter plot matrix illustrates relationships between price, bedrooms, and bathrooms; layered bar charts compare average prices by bedrooms, bathrooms, and guest capacity with the overall average price; and the line chart shows average price trends as guest capacity increases. Together, the compound figure provides a comprehensive view of pricing patterns and accommodation features in Seattle Airbnbs. Top of Form 

![alt text](https://github.com/Sowjanya2502/Data-Visualizations---DATA-5310/blob/main/Final_Project/Plots/Compiund_Figures.png)


To investigate how Airbnb characteristics influence the price distribution in the greater Seattle area, a compound figure was created to provide a clear and integrated view of multiple relationships and their impacts on Airbnb pricing. The scatter plot matrix (SPLOM) was selected to examine pairwise correlations between price, number of bedrooms, and bathrooms. The semi-transparent data point encoding reduces the ambiguity of overlapping records and allows dense regions to remain visible. The scale encoding provides intermittent gridlines to help guide spatial comparisons across scatter plots without overwhelming the viewer. The layered bar chart is designed to compare average Airbnb prices across various room characteristics like the number of bedrooms, bathrooms, and guests accommodated. The horizontal red line is an intentional encoding that represents the overall market average for a nightly Airbnb price in Seattle. The scale encoding only provides gridlines for the y-axis, as the bar height is really the main aspect which the viewer interprets. Removing the x-axis gridlines increases the data ink ratio by reducing non-essential visual elements. The line chart visualizes how price changes as guest capacity increases. The average transformation summarizes the price variable into an average of Airbnb pricing as the number of guests increase. Certain visualization choices like the color palette, axes labels, and filtering of outlier data points are consistent across all plots in the dashboard to ensure consistency and continuity as a viewer looks over the figure as a whole. Together, these design choices leverage the principles of compound figures to allow viewers to interpret multiple price-related relationships at once and develop a deeper understanding of how Airbnb listing characteristics shape Seattle’s short term rental industry. 

The compound figure reveals how Seattle’s Airbnb market is shaped by a combination of predictable structural patterns, with some pockets of variability that reflect the city’s diverse short term renal disposal. The scatterplot matrix reveals consistently positive relationships among price, bedrooms, and bathrooms, suggesting that larger listings tend to imply higher nightly rates. Notably, the price starts to vary significantly more for listings with more than four bedrooms or two bathrooms, indicating a broader range of property types such as luxury homes or condos that may be entering the market. The layered bar charts provide insight into what an average Airbnb listing in Seattle might offer. One might expect to pay roughly $200 per night for an Airbnb that accommodates about five guests, offering around two to three bedrooms and two bathrooms, which reflects a relatively standard mid-sized rental in the market. The line chart reinforces these patterns by showing that nightly pricing generally increases as more guests can be accommodated. For Airbnb’s with more and most guests being accommodated, price tends to fluctuate, likely due to these data points being outliers with fewer listings skewing the average prices more profoundly. High-capacity properties may be more variable on price depending on some amenities offered or unseen characteristics in this visualization specifically. Overall, this figure indicates that generally while price increases, smaller to mid-size Airbnb’s likely follow a consistent positive correlation pattern, where visitors can expect a pretty typical Airbnb price for something like a two bedroom, two bathroom rental. Unusually large or premium listings can introduce variability into the Airbnb pricing and should be considered on a case-by-case basis by the visitor.  

 

 

 

 

 

 

 

 

 

 

To further investigate the relationship between host response time and overall listing ratings, we developed two complementary visualizations examining four response time categories: "within an hour," "within a few hours," "within a day," and "a few days or more." 

Figure III. Layered area chart showing Response Penalty Stream: Rating Penalty as Flow from Baseline 
![alt text](https://github.com/Sowjanya2502/Data-Visualizations---DATA-5310/blob/main/Final_Project/Plots/ResponsePenalty.png)

 

A layered area chart visualization communicates the mean Airbnb rating penalties relative to a baseline for each hose response-time cateogry. The chart calculates penalties by comparing mean ratings for each response time category against the fastest response group ("within an hour"), which serves as the zero baseline. The area encoding uses basis interpolation to create smooth curves, with color encoding using a green-to-red gradient. The visualization incorporates multiple layers: a dashed horizontal rule at zero, semi-transparent confidence interval bands, and circle marks highlighting exact penalty values. The x-axis encodes response time categories as ordered numeric values, while the y-axis uses a signed format to distinguish positive and negative penalties. 

The response penalty stream reveals that the fastest response category ("within an hour") serves as the baseline with a mean rating of approximately 4.82 (2,851 listings). The "within a few hours" category shows a slight positive penalty of +0.075 (197 listings), though this falls within statistical uncertainty. The "within a day" category shows a small negative penalty of -0.023, while "a few days or more" demonstrates a substantial negative penalty of -0.354 (20 listings). This pattern suggests that while moderate delays may have minimal impact, significant delays substantially harm a listing's perceived quality. 

Figure IV. Faceted scatter plot showing Host Reliability Orbit: Rating Distribution by Response Time 
![altText](https://github.com/Sowjanya2502/Data-Visualizations---DATA-5310/blob/main/Final_Project/Plots/Rating%20by%20response%20type.png)

A faceted scatter plot examines the relationship between Airbnb review scores and review volume across four host response time category. Each panel uses a scatter plot where points represent individual listings, with the x-axis encoding number of reviews and the y-axis encoding review scores. Faceting by response time allows each category to be compared on identical axes, preserving scale consistency and preventing misleading interpretations for across category comparisons. Point size and opacity are mapped to review count, reinforcing the distribution of high volume listings while preventing overplotting. A dashed horizontal line represents the mean rating for each category, serving as a visual benchmark to see whether a panel skews above or below a typical rating.  

The orbit visualization reveals distinct patterns, showing patterns across facets that highlights how host responsiveness aligns with both rating quality and volume. The "within an hour" panel shows the densest clustering in high-rating, high-review-count regions, suggesting responsive hosts accumulate both positive ratings and substantial review volumes. The "within a few hours" panel shows a similar pattern with fewer listings. The "within a day" panel shows more dispersion, while "a few days or more" demonstrates the most dramatic differences, with greater variability in ratings, lower mean ratings, and fewer high-review-count listings, suggesting slower-responding hosts are associated with lower guest satisfaction and reduced market traction, as listings accumulate reviews on a slower basis. 

Together, these visualizations demonstrate that host responsiveness plays a pivotal role in shaping listing performance. While moderate delays show mixed, but generally manageable effects, substantial response delays are associated with both lower average ratings and reduced capacity to generate reviews.  

 

 

 

 

 

 

 

Figure V. Property Constellation: Multi-dimensional Property Galaxy 

![altText](https://github.com/Sowjanya2502/Data-Visualizations---DATA-5310/blob/main/Final_Project/Plots/PCA.png)

This visualization employs Principal Component Analysis (PCA) to project high-dimensional property characteristics into a two-dimensional space. The PCA transformation reduces multiple features—price, bedrooms, bathrooms, accommodations, and review scores—into two principal components. The scatter plot uses circle marks with size mapped to accommodation capacity, color assigned to property types, and opacity mapped to number of reviews. Interactive encoding enables zooming and panning for detailed exploration. 

The constellation reveals that different property types form distinct clusters. Entire homes and condos occupy different regions, reflecting different combinations of size, price, and amenities. Guest suites and private rooms form their own clusters in regions associated with smaller accommodation capacities and different price points. 

 

 

 

 

 

 

Figure VI. Price Distribution by Property Type 

 ![altText](https://github.com/Sowjanya2502/Data-Visualizations---DATA-5310/blob/main/Final_Project/Plots/PricebyProperty%20type.png)

A box plot visualization displays the distribution of nightly prices for each property type, using a logarithmic y-axis scale to accommodate the wide price range. Property types are sorted by median price in descending order. The visualization reveals clear differences: entire homes and condos command the highest median prices, reflecting larger size and greater amenities, while guest suites and private rooms show lower median prices consistent with smaller accommodation capacities. Box plot widths reveal variability within each property type. 

 

 

 

 

 

 

 

 

 

 

 

 

Figure VII.  Interactive Property Characteristics by Property Type 
![altText](https://github.com/Sowjanya2502/Data-Visualizations---DATA-5310/blob/main/Final_Project/Plots/PropertyChara_byproperty.png)
 

An interactive visualization with a dropdown menu allows viewers to select which characteristic to examine—bedrooms, bathrooms, or review scores—displayed as box plot distributions across property types. The y-axis scale is fixed from 0 to 5 to maintain consistent visual reference points when switching categories. The visualization reveals that entire homes and condos show higher median values for bedrooms and bathrooms, while review scores vary by property type, with some maintaining consistently high ratings and others showing greater variability. 

 

 

A faceted scatter plot identifies "efficiency frontiers" representing the maximum rating achievable at different price points for each property type. Separate panels show the top four property types, with scatter plots positioned by price (logarithmic scale) and rating. The efficiency frontier line, calculated as the upper envelope of ratings at each price level, is encoded as a dashed line. A median rating line provides additional reference. 

The visualization reveals that steeper frontier lines indicate higher prices are required for high ratings, while flatter lines suggest high ratings can be achieved across a wider price range, indicating better value opportunities. Some property types have listings concentrated in high-rating, moderate-price regions, suggesting good value propositions and identifying "sweet spots" where visitors can achieve high ratings without premium prices. 

Together, these four visualizations provide a comprehensive view of how property type influences Airbnb market dynamics, revealing clustering patterns, pricing expectations, characteristic variations, and value opportunities across different property types in Seattle's Airbnb market. 

 

 

 

 

 

 

 

 

 

 

Choropleth map 

Figure IX. Choropleth map to explore average nightly price and availability for next 30 days across various neighborhood in Seattle. 

![altText](https://github.com/Sowjanya2502/Data-Visualizations---DATA-5310/blob/main/Final_Project/Plots/PriceByNeighborhoood_nicole.png) 

In this part of the analysis, we wanted to understand how Airbnb price, property types, and short-term availability vary across Seattle’s neighborhoods. Since these variables are inherently spatial, we designed an interactive geospatial dashboard that allows users to click on any neighborhood and immediately explore patterns specific to that location. The interactive nature of the visualization helps reveal localized relationships that would be difficult to see in a static plot. For example, this kind of plot help to answer how certain property types dominate expensive neighborhoods, or how availability differs depending on the type of listing. 

The left side of the dashboard uses a choropleth map, where each neighborhood is encoded with a color scale representing the average nightly price. Darker teal shades correspond to higher prices, while lighter shades represent more affordable areas. This encoding makes it visually intuitive to identify premium markets such as Queen Anne and Downtown, which consistently appear in the darkest hues. We chose a choropleth because it is the most effective way to communicate geographic variation and spatial clustering in pricing helps us to identify which neighborhoods are less expensive. To complement the map, we added linked bar charts on the right side of the dashboard. When we click on any neighborhood on the map, two bar charts update dynamically. The first bar chart shows the distribution of property types (e.g., entire home/unit, private room, shared room). The categories are sorted in descending order based on the number of listings, allowing the most common property types to appear at the top for quick comparison. Colors are assigned based on property type using a teal-blue palette. Tooltips are included to show the neighbourhood name, property type, and exact count, enabling precise interpretation on hover. The second bar chart presents the average availability over the next 30 days, encoded using both bar length and a color gradient. This chart uses the raw dataset and applies the neighbourhood filter interactively, ensuring that the aggregation happens dynamically. The x-axis encodes mean(availability_30), meaning the bar length represents how many days listings of that property type are available within a 30-day window. Longer bars indicate greater availability. 

If we want to understand the booking patterns and demand pressure within that neighborhood we can do this just by clicking on that map. When a neighborhood is clicked on the choropleth map, the two bar charts on the right update dynamically to display information specific to that selected area as shown below. 

Figure X. Interactive dashboard with average nightly price and average availability for next 30 days of each property across various neighborhoods. 

![altText](https://github.com/Sowjanya2502/Data-Visualizations---DATA-5310/blob/main/Final_Project/Plots/Interactive_neighborhood.png)    

The above plot will be shown when we click on Queen Anne (a high-priced area). The first bar chart in the top right reveals that availability, indicating stronger booking demand. This interactive filtering shows that the neighborhood is dominated by entire-home listings and that these units tend to have relatively lower availability, indicating stronger booking demand for entire-home listings. 

Text Analysis 

In the next visualization, we wanted to expore what are the most common amenities the seattle airbnb’s are offering. Before we visualize our data consists of hundreds of inconsistent strings for each listing with everything from long description to encoded unicode characters. We cleaned this data by  

Removing brackets(‘[]’), quotes(‘ ‘), digits(ex: ‘55 inch HDTV’) and unnecessary punctuation. 

Removing brackets 

Removing literal escaped unicode characters(‘\u’).(eg. ‘Free washer \u2013 in unit’ → “Free washer – In unit’) 

Converted all text to lowercase for consistency. 

Split raw string into individual amenity tokens.  

Normalization:   

All forms of Wi-Fi → "wifi". (e.g., ''wi-fi'', ''fast wifi 434 Mbps'') 

 Any string containing both “free” and “parking” → "free parking"(e.g., "free parking on premises",  "free driveway parking on premises") 

 Any string beginning with “free washer …” → "free washer"(e.g., "free washer in building", "free washer in unit") 

 Any string beginning with 'free dryer ..." → "free dryer" (e.g., "free dryer in unit" 

This preprocessing of text data step allows us to analyze amenities consistently and avoids inflating counts due to messy text. Once this amenities text was cleaned and normalized, we were able to extract meaningful patterns. 

 

 

 

 

 

 

 

 

 

Figure XI. Word cloud and bar plot of most common amenities in seattle airbnb’s. 
![altText](https://github.com/Sowjanya2502/Data-Visualizations---DATA-5310/blob/main/Final_Project/Plots/word_cloud_bar_plot.png)
 

To understand the overall distribution of amenities offered across Seattle Airbnb listings, we visualized the cleaned and normalized amenities data using both a word cloud and a frequency bar chart. The goal was to identify which amenities are most commonly provided in the seattle airbnb’s. The word cloud uses text size as the main encoding, where larger words represent amenities which are common among most of the listings. To complement this qualitative view, the bar chart presents the Top 20 amenities with exact frequencies, height of the bar represents the number of listings that include each amenity. The word cloud shows that wifi, smoke alarm, carbon monoxide alarm, reflecting safety compliance, kitchen essentials are among the most widely provided amenities across Seattle. This visualization provides an idea of what we can reliably expect across most Seattle Airbnb’s. 

Figure XII. Bar plot of top free amenities in seattle airbnb’s 

![altText](https://github.com/Sowjanya2502/Data-Visualizations---DATA-5310/blob/main/Final_Project/Plots/Barplot_amenities.png) 

Another interesting pattern we found in the amenities text relates to listings that offer free or complimentary services. To explore this, we filtered the cleaned amenities data for any items beginning with “free” , “complimentary” and visualized the most common ones using a horizontal bar chart. In this plot, the y-axis encodes the amenity category, while the x-axis represents the number of listings offering that free amenity, with bar length used to compare frequencies across categories. The results show that free parking is by far the most common complimentary amenity in Seattle Airbnb listings, appearing in nearly 4,000 properties. This is followed by free dryer and free washer, indicating that hosts frequently include laundry access at no additional cost. In contrast, amenities such as free residential garage or free exercise equipment are much less common. Overall, this visualization highlights that the majority of “free” amenities relate to parking and laundry, both of which can be strong value-adds for guests, particularly in a city like Seattle where parking and convenience amenities are highly important. 

Figure XIII. Interactive plot to visualize airbnb listings based on amenities. 
![altText](https://github.com/Sowjanya2502/Data-Visualizations---DATA-5310/blob/main/Final_Project/Plots/Interactive_listings.png)
To further explore how specific amenities are distributed across Seattle’s Airbnb listings, we created an interactive geospatial visualization that allows users to select an amenity of interest and view all listings offering that amenity on a city map. In this dashboard, each listing is represented as a point whose position is determined by geographic coordinates (latitude and longitude), enabling us to observe spatial clustering patterns. The color of each point encodes the nightly price, using a continuous purple-to-yellow gradient where lighter colors represent more expensive listings. The interactive dropdown menu allows users to switch between amenities such as beach access, free parking, wifi and see how the map updates instantly based on the selection. 

From the visualizations, we observe that amenities like beach access are much more geographically concentrated, mainly appearing along the waterfront in West Seattle and northern coastal areas. If we look at listings providing free parking we can notice that its common inclusion in residential neighborhoods where parking availability is higher.  

Discussion 

The analyses presented in this study provides a comprehensive view of Seattle’s Airbnb market, revealing several consistent patterns as well as patterns influenced by specific neighborhood contexts. Across the city, there is a general trend that shows listings that accommodate more guests result in higher prices, but some variability can occur in different areas. For example, the Downtown neighborhood is dominated by smaller, and moderately priced units whereas neighborhoods outside of the city like Queen Anne or West Seattle provide a more diverse range of rental types. The spatial maps indicate that high-demand areas feature lower availability of rentals and high concentration of entire-home listings, whereas areas outside of the city offer more varied types of listings with consistent availability. The amenity analysis further reveals functional and convenient features offered in Airbnbs across Seattle, such as wi-fi, free parking, and laundry, which enhances the listing’s appeal along with certain geographical and spatial features. Together, these findings suggest that neighborhood, listing size, and amenity offerings jointly drive pricing and availability trends in Seattle Airbnbs. Interactive visualizations are particularly effective for uncovering multi-dimensional relationships and guiding visitor expectations and host strategies.  

References 

Inside Airbnb. “Get the Data.” Inside Airbnb, https://insideairbnb.com/get-the-data/ 

Altair Documentation. “Geoshape.” Altair, https://altairviz.github.io/user_guide/marks/geoshape.html 

Altair Documentation. “Data Transforms.” Altair, https://altairviz.github.io/user_guide/transform/index.html 

 
