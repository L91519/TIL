# RecyclerView.LinearLayoutManager

I got to study this because I wanted to make Custom RecyclerView

## Custom Linear Layout Manager

+ fling this is needed in custom recyclerView 
  - This is included to animation 
  - If we want to make a recycler scroll smoothly, this is where you can use this.


## OnClick out of Adapter

1. Make OnClick interface
2. In adapter's constructor get onClick object as parameter
3. Get interface object also in activity or fragment
4. Bind interface onClick and base onClick 
5. Handle task when interface onClick in activity is clicked because since interface onClick and base onClick is binded that will allow certain task to be held also in activity (or fragment)

**WARNING : this should be edited**



