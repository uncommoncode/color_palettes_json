# color_palettes
Beautiful color palettes in json.

Are you tired of manual conversions of your favorite colors to whatever project and programming lanuage you're working on? Me too. 

These json files provide an easy to parse format for common colors used in visualization and artistic projects, and can be used to generate libraries, or just specific colors, across a variety of usecases from embedded development to the web.

# Format

Each `.json` file is a JSON object containing a field that comments the source of the palette, and then one or more Color Palette Types.

A colormap with the `divergent` Color Pallete Type would look like:
```
{
  "comment": "These color palettes were developed by Cynthia Brewer (see http://colorbrewer2.org/).", 
  "divergent": {
    "BrBG": {
      "3": [
        [
          216, 
          179, 
          101
        ], 
...
```

For a colormap with the `named` Color Palette Type this would look like:

```
{
  "comment": "Created by Mike Bostock et. al. (https://github.com/d3/d3-color/)\nCreated by Mike Bostock et. al. (https://github.com/d3/d3)", 
  "named": {
    "aliceblue": [
      240, 
      248, 
      255
    ], 
...
```

## Color Palette Type

There are four main color palette types for different visualization and artistic usages. These types are keys in the main JSON object, and the value is either a Multi-Color Palette or Single-Color Palette.
 * `qualitative`: A Multi-Color Palette useful for qualitative values, such as categorical variables like various countries.
 * `sequential`: A Multi-Color Palette useful for values where there is a monotonic ordering.
 * `divergent`: A Multi-Color Palette useful for values where there is a logical seperation of the range into two sequential regions, such as positive and negative numbers, or values above and below a mean.
 * `named`: A Single-Color Palette useful for general drawing purposes.

## Multi-Color Palette

Some color palettes have been tuned for different numbers of colors, pariticlarly with qualitative types. The object contains a map of color count to an array of sRGB values. For example, a 3 color map for "BrBG" may look like:

```
...
    "BrBG": {
      "3": [
        [
          216, 
          179, 
          101
        ], 
        [
          245, 
          245, 
          245
        ], 
        [
          90, 
          180, 
          172
        ]
      ]
    }  
...
```


## Single-Color Palette

Single named colors are represented compactly as a key value map between the name of the color and the sRGB value:

```
...
    "aliceblue": [
      240, 
      248, 
      255
    ]
...
```
