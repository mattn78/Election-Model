# Task 1: Wrangling with Data

The first two objectives can be done independently, and in whichever order

This is definitely the least fun task, so I'll do most of it

You should at least try to do the first two objectives

The third objective can only be done after the first two objectives are done, but it's also where I will most need help

I will work on the first two objectives separately, and ask for help as I need in the third: This is the researching individual datapoints type of thing we discussed

As the week goes, I'll release my work on this task. It would be good for you to see how I do things, but it's not super important to know moving forward in the project. It's also good to at least try to replicate what I do.

We need to gather data that is the most clean as possible. Our priorities for the quality of data is as follows:

1. **Accuracy** - Data needs to be accurate. We will trust authorities on the matter. That is, a university/government/trusted nonprofit data should be assumed to be accurate until we find evidence that it's not. The correct way to do this would be to corroborate information across different data sources.

2. **Scope** - We want more data with more details covering more events across a longer timeframe. We can always cobble together multiple data sources to do this, but having one data source with a large scope ensures that the data is formatted and sourced in the same manner.

3. **Readability** - We need to turn this data into variables in python. If it's in a bunch of text (eg a bunch of wikipedia pages) this will make our jobs harder. A simply-formatted file, with just the enough information we need and not more, is the ideal version. Typically these would be csvs, tsvs, jsons, or simply-formatted excel tables. Though, some html tables are also good. Knowing a little pandas, and trying to read the data in with pandas is a good check for readability.

## Objective 1.1: Election Data
Now that we know the qualities of data to look for, what data do we actually need. I list the datasets we need in order of priority. Under each dataset, I list versions of the data from most ideal to least. When I say "Year by Year," I mean election year by election year, but each election cycle is different for the different positions

1. Presidential Election Data
   1. District by District (for ME and NE) and Year by Year
   2. State by State and Year by Year
   3. State by State
   4. National and Year by Year

2. House Election Data
   1. District by District and Year by Year
   2. State by State and Year by Year
   3. District by District
   4. State by State
   5. National and Year by Year

3. Senate Election Data
   1. District by District (for ME and NE) and Year by Year
   2. State by State and Year by Year
   3. State by State
   4. National and Year by Year

4. Gubernatorial Election Data
   1. District by District (for ME and NE) and Year by Year
   2. State by State and Year by Year
   3. State by State
   4. National and Year by Year

5. State Legistlature Election Data
   1. District by District (for ME and NE) and Year by Year
   2. State by State and Year by Year
   3. State by State
   4. National and Year by Year

## Objective 1.2: Demographic Data
Here, we need to do a little bit of discussion as to what demographic data we want to have.

There are several approaches here. We can first just try to do a broad search of demographic data that follows our three data priorities listed in the Task description. Then from there, we analyze the data in the next task to figure out what we want to use for our model.

The second, is that we discuss first what demographics we would want. Then, if we find demographics which we really want, we then try our best to find quality datasets that give us those demographic data. But these may not always exist. So, we might need to wrangle more with the data: joining several datasets, engineering the data, etc.

And the third way, which is probably what we should do, is do both. First, find just as much quality datasets around demographics that we can. As we do that, we discuss what demographics we might like. Then find datasets for the uncovered demographics, that we decided that we liked.

Now, I'm sure there exists already, somewhere out there, datasets which have demographics data aligning with election data. Try to look for those. And, these data are probably gathered by researchers which suggest that the demographic data and election data inform each other.

## Objective 1.2.1: Polling data
I know that answer for this one. And there's only one correct one. We want to have the qualities of datasets discussed in the Task Description. But, this is a bit weirder because we aren't looking for a complete dataset. Instead, we are looking for a dataset (a link to one/a link to REST endpoint) which updates as new polls come in. 

There is a dataset that already does this, and I've already mentioned where to find it since the first day. But I haven't mentioned the existence of this particular dataset. If you really really completed Objective 0.3, which I don't expect you to have done so (cause I haven't), then you know where to find this one. Think of this objective as a scavenger hunt.

## Objective 1.3: Cleaning the Data
So, somehow we need to bring all this data together in a meaningful way that gives us the fewest headaches when we begin to play with the data.

For election data, ideally we would have a table of data for each of the (up to 5) datasets listed above. This table would be formatted so that each row corresponds to election results for a given year and a given district/state. Then there would be columns for the Democratic vote share and the Republican vote share.

For demographic data, we should have corresponding rows to the formatted election data. But the columns this time would be demographic data.

The polling data as it is sourced would already be formatted well.

Now, as we clean the data into these schemas, we will find that there are certain datapoints that do not make sense. These datapoints need to be manually handled and researched so that we can make them fit the schemas. I will post about these problems as I find them, and I will need your help with figuring these out.