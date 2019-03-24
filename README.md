package com.example.conexionsql;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.ArrayAdapter;
import android.widget.Button;
import android.widget.EditText;
import android.widget.ListView;
import android.widget.Toast;

import java.util.ArrayList;

public class MainActivity extends AppCompatActivity {
    EditText nom, ap, rfc;
    Button registra,muestra;
    ListView lista;



    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        nom = (EditText) findViewById(R.id.tx1);
        ap = (EditText) findViewById(R.id.tx2);
        rfc = (EditText) findViewById(R.id.tx3);

        registra = findViewById(R.id.btn1);
        muestra= findViewById(R.id.btn4);
        lista=(ListView) findViewById(R.id.listaVistas);

        final BaseDatos develop = new BaseDatos(getApplicationContext());


        registra.setOnClickListener(v -> develop.agregarR(nom.getText().toString(),ap.getText().toString(),rfc.getText().toString()));
       registra.setOnClickListener(v ->  Toast.makeText(this, "Se ha registrado con exito", Toast.LENGTH_SHORT).show());






    }
}
