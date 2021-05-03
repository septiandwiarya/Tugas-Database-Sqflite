# Tugas-Database-Sqflite
import 'package:flutter/material.dart';

void main() => runApp(Myapp());

class Myapp extends StatefulWidget {
  _MyappState createState() => _MyappState();
}

class _MyappState extends State<Myapp> {
  //deklarasi variabel
  final txtkodebarang = TextEditingController();
  final txtnamabarang = TextEditingController();
  final txtmerk = TextEditingController();
  List<Widget> data = [];

  onTambah() {
    setState(() {
      data.add(ListTile(
        leading: Icon(Icons.circle),
        title: Text(txtkodebarang.text),
        subtitle: Text(txtnamabarang.text),
        trailing: Text(txtmerk.text),
        
      ));
    });
  }

  Widget build(BuildContext context) {
    return MaterialApp(
        home: new Scaffold(
            appBar: new AppBar(title: Text("ARYA SPAREPART")),
            body: new ListView(
              children: <Widget>[
                new Container(
                  padding: EdgeInsets.all(10.0),
                  child: Column(
                    mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                    children: <Widget>[
                      TextField(
                        controller: txtkodebarang,
                        decoration: InputDecoration(hintText: 'Kode Barang'),
                      ),
                      TextField(
                        controller: txtnamabarang,
                        decoration: InputDecoration(hintText: 'Nama Barang'),
                      ),
                      TextField(
                        controller: txtmerk,
                        decoration: InputDecoration(hintText: 'Merk'),
                      ),
                      RaisedButton(child: Text("Tambah"), onPressed: onTambah),
                    ],
                  ),
                ),
                new Column(
                  // Isi List View
                  children: data,
                )
              ],
            )));
  }
}
