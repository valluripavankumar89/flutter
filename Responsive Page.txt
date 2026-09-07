import 'package:flutter/material.dart';

void main() {
  runApp(const MaterialApp(
    home: ResponsiveDemo(),
    debugShowCheckedModeBanner: false,
  ));
}

class ResponsiveDemo extends StatelessWidget {
  const ResponsiveDemo({super.key});

  @override
  Widget build(BuildContext context) {
    double width = MediaQuery.of(context).size.width;
    bool isMobile = width < 600;

    return Scaffold(
      // MOBILE MENU
      drawer: isMobile
          ? Drawer(
              child: ListView(
                padding: EdgeInsets.zero,
                children: [
                  const DrawerHeader(
                    decoration: BoxDecoration(
                      color: Colors.blue,
                    ),
                    child: Text(
                      "Menu",
                      style: TextStyle(
                        color: Colors.white,
                        fontSize: 28,
                      ),
                    ),
                  ),
                  ListTile(
                    title: const Text("Home"),
                    onTap: () => Navigator.pop(context),
                  ),
                  ListTile(
                    title: const Text("About"),
                    onTap: () => Navigator.pop(context),
                  ),
                  ListTile(
                    title: const Text("Services"),
                    onTap: () => Navigator.pop(context),
                  ),
                  ListTile(
                    title: const Text("Contact"),
                    onTap: () => Navigator.pop(context),
                  ),
                ],
              ),
            )
          : null,

      // NAVIGATION BAR
      appBar: AppBar(
        backgroundColor: Colors.blue,
        title: const Text(
          "Responsive UI",
          style: TextStyle(color: Colors.white),
        ),

        // DESKTOP MENU
        actions: isMobile
            ? null
            : [
                TextButton(
                  onPressed: () {},
                  child: const Text(
                    "Home",
                    style: TextStyle(
                      color: Colors.white,
                      fontSize: 16,
                    ),
                  ),
                ),
                TextButton(
                  onPressed: () {},
                  child: const Text(
                    "About",
                    style: TextStyle(
                      color: Colors.white,
                      fontSize: 16,
                    ),
                  ),
                ),
                TextButton(
                  onPressed: () {},
                  child: const Text(
                    "Services",
                    style: TextStyle(
                      color: Colors.white,
                      fontSize: 16,
                    ),
                  ),
                ),
                TextButton(
                  onPressed: () {},
                  child: const Text(
                    "Contact",
                    style: TextStyle(
                      color: Colors.white,
                      fontSize: 16,
                    ),
                  ),
                ),
                const SizedBox(width: 20),
              ],
      ),

      // BODY
      body: Container(
        width: double.infinity,
        height: double.infinity,
        decoration: const BoxDecoration(
          image: DecorationImage(
            image: AssetImage("assets/wallpaper.jpg"),
            fit: BoxFit.cover,
          ),
        ),
        child: Center(
          child: Text(
            isMobile ? "Mobile View" : "Desktop View",
            style: const TextStyle(
              color: Colors.white,
              fontSize: 30,
              fontWeight: FontWeight.bold,
            ),
          ),
        ),
      ),
    );
  }
}
