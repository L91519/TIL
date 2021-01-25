# Using Filter

If we want to create a filter, there are two necessary thing that we need to do.

First, we need to implement Filterable interface.

Second, we need to extend Filter class.

## Filterable

It might look that there are many things to override in this class but actually there is only one method existing in this interface!

### getFilter()

absract Filter gerFilter() : 

This is usually implemented by Adapter class.

It returns customized Filter

## Filter

### performFiltering(CharSequence constraint)

abstract Filter.FilterResults performFiltering(CharSequence constraint) : 

'constraint' here mean a text that we type.

If we finish the work that is supposed to be done, such as using 'contain' method to check if constraint is included in certain ArrayList or etc, we have the return the result. 

As it is written up there, what we need to return if Filter.FilterResults.

##### Filter.FilterResults

This is a inner class that is included in Filter class.

There are two variable in this method.

1. public int count
2. public Object values



When returning FilterResult, in 'count' variable we need length of the items that we are done with filtering. And in 'values' variable, we need the items itself.

In here, items means ArrayList or Array that have items.

#### publishResults (CahrSequence constraint, FilterResult result)

1. constraint : Input data
2. result : Filter.FilterResults that is returned.