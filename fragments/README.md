##Fragments

#### What can be done using fragments
-> 

#### How to use
1. Get the fragment manager
2. Create a transaction
3. Add, remove and replace fragments
4. Commit transaction

### Add new custom fragment
	getFragmentManager().beginTransaction()
                    .add(R.id.container, new CustonFragment())
                    .commit();

### Custom Fragment Class

	public static class CustonFragment extends Fragment{
        //!important
        public CustonFragment(){}

        @Override
        public View onCreateView(LayoutInflater inflater, ViewGroup container,
                                 Bundle saveInstanceState){
            //inflate the container with fragment layout {fragment_main}
            View rootView = inflater.inflate(R.layout.fragment_main, container, false);
            return rootView;
        }
    }

### Add Fragment using xml

	<fragment
    	nd:id="@+id/xyz"
        nd:name=""
        nd:layout_width="fill_parent"
        nd:layout_height="fill_parent"
        tools:layout="@layout/my_custom_layout"/>
        <!-- This will link my_custom_layout to the above fragment -->

###Replacing Fragment
	CustomFragment fragment = new CustomFragment();
	
	fragment.setArguments(argsBundle);
    getFragmentManager().beginTransaction()
                    .replace(R.id.container, new fragment)
                    .commit();
#### More with fragments
1. Set Transition
2. Manage activity backstack
3. Show, Hide Fragment, managebreadcrumbs
4. 