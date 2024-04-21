# code-20240421-joecook
 
## What manual tasks would you perform?
Manual tasks here involve identifying extreme values, charting the data and replacing missing values where appropriate.

I have manually identified issues with dates and date ranges. However, with me not being too familiar with the data I have not made any changes here. 
- Some publish dates are before start dates and some are after. 
- Some durations do not match the length of the start date to end date extended. 

I've created a new "actual_months" column as it may be a useful column.


## What automated approaches can you use?
I've automated the identification of anomalies by removing values where they exceed thresholds using the interquartile range and upper and lower quartiles. I attempted to use the Z-score but due to the extreme nature of some values, it made others not look as extreme.

I have also replaced missing values (atc) with the modal value where it shares the same SKU.

To ensure there are no price formatting issues with scientific notation in the concatenated strings, I have stripped these and then reformatted before joining them together again.

I did a lot of work in a jupyter notebook to cleanly display the process, but for an automated approach I would just use a .py file.


## How would you improve this process long term and how would you build your roadmap?
Long term after getting familiar with the data, this would be part of the ML pipeline, cleaning the data then ready for the model to be applied.

## Would you change anything if you would need to scale this process from a few SKU's to hundreds and thousands.
As mentioned above, the atc replacement was done in a way to future proof. If the dataset becomes much larger and contains a variety of SKUs then we cant impute based on the modal across all SKUs, we need to group things.
In general though, we should approach the data as if it is a large amount and the process will then be scalable from the start.

## Other Notes
Deleting data is never ideal, ultimately this was done because the rows contained values that are too extreme. However in a real world scenario, these rows may need to instead be highlighted to the team and they can go to the relevant sources to correct the data to create an accurate prediction.