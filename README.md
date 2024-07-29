# Assignments-
this github link would have assignment no. 1,2,3,4
Assignment no. 2:
Design screen layouts with static data.
1.	Activity_Static_Layout.xml:
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp"
    android:gravity="center">
    <TextView
        android:id="@+id/wmessage"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="welcome_message”
        android:textSize="24sp" 
       android:textStyle=”bold”
        android:layout_centerInParent="true"
        android:paddingbutton=”16sp” />
    <TextView
        android:id="@+id/tv_exercise"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Exercise:”
        android:textSize="20sp"
        android:paddingBottom="8dp" />
    <TextView
        android:id="@+id/ex1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="exercise_1”
        android:textSize="18sp"/>

<TextView
        android:id="@+id/ex2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="exercise_2”
        android:textSize="18sp"/>
<TextView
        android:id="@+id/ex3"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="exercise_3”
        android:textSize="18sp"/>

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="START_WORKOUT" />
</LinearLayout>
Assignment no. 3:
Implement menus including drawer OR tabs navigation
1.	Activity_main.xml:
<androidx.drawerlayout.widget.DrawerLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/drawer_layout"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:orientation="vertical">
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Main screen !" />
        
        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Open Drawer"
            android:onClick="openDrawer"/>
    </LinearLayout>

    <com.google.android.material.navigation.NavigationView
        android:id="@+id/nav_view"
        android:layout_width="wrap_content"
        android:layout_height="match_parent"
        android:layout_gravity="end"
        android:background="?android:attr/windowBackground"
        app:headerLayout="@layout/nav_header"
        app:menu="@menu/drawer_menu" />
    
</androidx.drawerlayout.widget.DrawerLayout>
2.	nav_header.xml:
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="vertical"
    android:padding="16dp"
    android:background="?attr/colorPrimaryDark">
    <ImageView
        android:id="@+id/profile_image"
        android:layout_width="64dp"
        android:layout_height="64dp"
        android:src="@drawable/ic_profile_placeholder"
        android:layout_gravity="center_horizontal"
        android:layout_marginBottom="8dp"
        android:contentDescription="@string/profile_picture" />
    <TextView
        android:id="@+id/profile_name"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="John Doe"
        android:textColor="@android:color/white"
        android:textSize="18sp"
        android:layout_gravity="center_horizontal" />
    <TextView
        android:id="@+id/profile_email"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="john.doe@example.com"
        android:textColor="@android:color/white"
        android:layout_gravity="center_horizontal" />
</LinearLayout>
3.	drawer_menu.xml:
<menu xmlns:android="http://schemas.android.com/apk/res/android">
    <item android:title="Profile">
        <menu>
            <item
                android:id="@+id/nav_profile"
                android:icon="@drawable/ic_profile"
                android:title="Profile" />
            <item
                android:id="@+id/nav_messages"
                android:icon="@drawable/ic_message"
                android:title="Messages" />
            <item
                android:id="@+id/nav_feedback"
                android:icon="@drawable/ic_feedback"
                android:title="Feedback" />
        </menu>
    </item>
    <item android:title="Additional Settings">
        <menu>
            <item
                android:id="@+id/nav_update_profile"
                android:icon="@drawable/ic_update"
                android:title="Update Profile" />
            <item
                android:id="@+id/nav_sign_out"
                android:icon="@drawable/ic_sign_out"
                android:title="Sign Out" />
        </menu>
    </item>
</menu>
4. MainActivity.java:
package com.example.myapp;
import android.os.Bundle;
import android.view.MenuItem;
import android.view.View;
import androidx.annotation.NonNull;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.view.GravityCompat;
import androidx.drawerlayout.widget.DrawerLayout;
import com.google.android.material.navigation.NavigationView;
public class MainActivity extends AppCompatActivity {
    private DrawerLayout drawerLayout;
    private NavigationView navigationView;
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        drawerLayout = findViewById(R.id.drawer_layout);
        navigationView = findViewById(R.id.nav_view);
        navigationView.setNavigationItemSelectedListener(new NavigationView.OnNavigationItemSelectedListener() {
            public boolean onNavigationItemSelected(@NonNull MenuItem item) {
                switch (item.getItemId()) {
                    case R.id.nav_profile;
                        break;
                    case R.id.nav_messages;
                        break;
                    case R.id.nav_feedback;
                        break;
                    case R.id.nav_update_profile;
                        break;
                    case R.id.nav_sign_out;
                        break;
                }
                drawerLayout.closeDrawer(GravityCompat.END);
                return true;
            }
        });
   } public void openDrawer(View view) {
        drawerLayout.openDrawer(GravityCompat.END);
    }    public void onBackPressed() {
        if (drawerLayout.isDrawerOpen(GravityCompat.END)) {
            drawerLayout.closeDrawer(GravityCompat.END);
        } else {
            super.onBackPressed();
        }
    }
}



MULTI-FRAGMENT APPLICATION 
Assignment no. 4:
Design some multi fragments app that should display some data from any of content providers either internal, external or cloud-based.
1.	Build.Gradle:
dependencies {
    implementation 'androidx.appcompat:appcompat:1.6.1'
    implementation 'androidx.fragment:fragment:1.5.5'
    implementation 'androidx.viewpager2:viewpager2:1.1.0'
    implementation 'androidx.constraintlayout:constraintlayout:2.1.4'
    implementation 'androidx.lifecycle:lifecycle-extensions:2.2.0'
}
2.	Activity_Main.xml:
<androidx.viewpager2.widget.ViewPager2 xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/view_pager"
    android:layout_width="match_parent"
    android:layout_height="match_parent" />
fragment_data_display.xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp">

    <TextView
        android:id="@+id/data_text_view"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Data will be displayed here"
        android:textSize="18sp" />
</LinearLayout>
3. DataDisplayFragment.java:
package com.example.myapp;

import android.database.Cursor;
import android.net.Uri;
import android.os.Bundle;
import android.provider.ContactsContract;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.widget.TextView;
import androidx.annotation.NonNull;
import androidx.annotation.Nullable;
import androidx.fragment.app.Fragment;

public class DataDisplayFragment extends Fragment {

    private static final String ARG_URI = "uri";
    private String uriString;

    public static DataDisplayFragment newInstance(String uri) {
        DataDisplayFragment fragment = new DataDisplayFragment();
        Bundle args = new Bundle();
        args.putString(ARG_URI, uri);
        fragment.setArguments(args);
        return fragment;
    }    public void onCreate(@Nullable Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        if (getArguments() != null) {
            uriString = getArguments().getString(ARG_URI);
        }
    }
    public View onCreateView(@NonNull LayoutInflater inflater, @Nullable ViewGroup container, @Nullable Bundle savedInstanceState) {
        return inflater.inflate(R.layout.fragment_data_display, container, false);
    }
    public void onViewCreated(@NonNull View view, @Nullable Bundle savedInstanceState) {
        super.onViewCreated(view, savedInstanceState);
        TextView dataTextView = view.findViewById(R.id.data_text_view);
        Uri uri = Uri.parse(uriString);
        Cursor cursor = getActivity().getContentResolver().query(uri, null, null, null, null);
        
        if (cursor != null && cursor.moveToFirst()) {
            StringBuilder data = new StringBuilder();
            do {
                data.append(cursor.getString(0)).append("\n");
            } while (cursor.moveToNext());
            dataTextView.setText(data.toString());
            cursor.close();
        }
    }
}
4.	FragmentPagerAdapter.java:
package com.example.myapp;

import androidx.annotation.NonNull;
import androidx.fragment.app.Fragment;
import androidx.fragment.app.FragmentManager;
import androidx.fragment.app.FragmentStatePagerAdapter;

public class FragmentPagerAdapter extends FragmentStatePagerAdapter {

    private static final String[] CONTENT_URIS = {
        ContactsContract.Contacts.CONTENT_URI.toString();    };

    public FragmentPagerAdapter(@NonNull FragmentManager fm, int behavior) {
        super(fm, behavior);
    }
    public Fragment getItem(int position) {
        return DataDisplayFragment.newInstance(CONTENT_URIS[position]);
    public int getCount() {
        return CONTENT_URIS.length;
    }
}
5.	MainActivity.java:
package com.example.myapp;
import android.os.Bundle;
import androidx.appcompat.app.AppCompatActivity;
import androidx.viewpager2.widget.ViewPager2;
public class MainActivity extends AppCompatActivity {
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        ViewPager2 viewPager = findViewById(R.id.view_pager);
        FragmentPagerAdapter pagerAdapter = new FragmentPagerAdapter(getSupportFragmentManager(), getLifecycle());
        viewPager.setAdapter(pagerAdapter);
    }
}


