# Set-a-List-of-Data-into-Android-Firebase-Realtime-Database-

Easy Way to set a list of data into android firebase Realtime Database 






package oshin.tasnuva.firebase;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.EditText;

import com.google.firebase.database.DatabaseReference;
import com.google.firebase.database.FirebaseDatabase;

import java.util.ArrayList;
import java.util.HashMap;

public class MainActivity extends AppCompatActivity {
     private EditText editText;
     private DatabaseReference databaseReference;
     private ArrayList<UserData> arrayList;

     String[] names ={"Saif","Anwar","Rocky","Nisha","Tanmoy","mufik","Rinky"};

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        databaseReference = FirebaseDatabase.getInstance().getReference().child("Info");
        arrayList = new ArrayList<UserData>();
        int i=0;
        while(i<names.length)
           {
            UserData userData = new UserData(names[i]);
            arrayList.add(userData);
               i++;
           }


           databaseReference.child("list").setValue(arrayList);





    }








}



##################################################################################################
UserData.java




package oshin.tasnuva.firebase;

public class UserData {

    String data;

    public String getData() {
        return data;
    }

    public void setData(String data) {
        this.data = data;
    }

    public UserData() {
    }

    public UserData(String data) {
        this.data = data;
    }
}







