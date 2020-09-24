# Compat

### ResourcesCompat.getDrawable( ) vs AppCompatResources.getDrawable( )

These two seems very similar and I think it actually is. If we are not using vector as our ImageView, we can use either of it. But if we are to use vector as our ImageView resource, we have to use ``AppCompatResources.getDrawable``. Because ``ResourcesCompat.getDrawable() ``doesn't support vector.

Reference : https://stackoverflow.com/questions/43004886/resourcescompat-getdrawable-vs-appcompatresources-getdrawable