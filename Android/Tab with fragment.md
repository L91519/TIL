# Tab with fragment

### Process

1. TabLayout(design.widget.tabLayout)

2. ViewPager(v4.view.ViewPager)

3. Xml file for fragment.

4. PageAdapter.java (Create adapter class that handles tab)

   1. overrid getCount(), getitem(), getPageTitle()
   2. construct
   3. addFragemtn

5. MainActivity

   1. ```xml
      ViewPager viewPager = (ViewPager) findViewById (R.id.viewPager);
      ```

   2. ```xml
      PagerAdapter pageAdapter = new PagerAdapter(getSupportFragmentAdapter());
      ```

      getSupportFragmentAdapter() : Return the FragmentManger for interacting with fragments associated with this activity.

   3. ```xml
      TabLayout tabLayout = (TabLayout) findViewById (R.id.tabs);
      tabLayout.setupWithViewPager(viewPger);
      ```

      setupWithViewPager : link two togeter

6. Make method to setViewPager

   1. Add fragment.
   2. setAdapter.

   ​

