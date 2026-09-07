import 'package:flutter/material.dart';

void main() {
  runApp(const MaterialApp(
    home: ResponsiveDemo(),
  ));
}

class ResponsiveDemo extends StatelessWidget {
  const ResponsiveDemo({super.key});

  @override
  Widget build(BuildContext context) {
    double width = MediaQuery.of(context).size.width;

    return Scaffold(
      appBar: AppBar(
        title: const Text("Responsive UI"),
      ),
      body: Center(
        child: Container(
          width: width < 600 ? 200 : 500,
          height: 200,
          color: width < 600 ? Colors.blue : Colors.green,
          child: Center(
            child: Text(
              width < 600 ? "Mobile" : "Desktop",
              style: const TextStyle(
                color: Colors.white,
                fontSize: 30,
              ),
            ),
          ),
        ),
      ),
    );
  }
}
