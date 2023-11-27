import 'package:flutter/material.dart';

const Color darkBlue = Color.fromARGB(260, 20, 35, 50);

void main() {
  runApp(HelloWorldScreen());
}

class HelloWorldScreen extends StatelessWidget {
  List<String> names = ["Dan", "Reyes", "John"];

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      theme: ThemeData.dark().copyWith(
        scaffoldBackgroundColor: darkBlue,
        appBarTheme: AppBarTheme(
          backgroundColor: Colors.blue,
        ),
      ),
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        appBar: AppBar(
          title: Row(
            children: [
              Icon(Icons.contacts),
              SizedBox(width: 10),
              Text('Hello World', style: TextStyle(color: Colors.white)),
            ],
          ),
        ),
        body: Container(
          child: ListView.builder(
            itemCount: names.length,
            itemBuilder: (context, index) {
              String name = names[index];
              return ListTile(
                leading: Icon(
                  Icons.face,
                  size: 50,
                  color: Colors.blue,
                ),
                title: Text(
                  name,
                  style: TextStyle(color: Colors.blue),
                ),
                subtitle: Text('${name.length} letters',
                    style: TextStyle(color: Colors.white)),
              );
            },
          ),
        ),
      ),
    );
  }
}
