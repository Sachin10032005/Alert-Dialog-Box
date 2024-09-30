# Alert-Dialog-Box
# Flutter Alert Dialog Example

## Introduction
This Flutter project demonstrates how to create and display an alert dialog box when a button is pressed. It showcases the use of the `AlertDialog` widget along with a button that triggers the dialog.

## Getting Started
To run this project, you need to have Flutter installed on your machine. If you haven't installed Flutter yet, follow the [official installation guide](https://flutter.dev/docs/get-started/install) to get started.

## Packages Used
This project does not use any third-party packages; it relies solely on Flutter's built-in widgets and libraries.

## Installation
1. Clone the project or create a new Flutter app using the command:

   ```bash
   flutter create alert_dialog_example
   Code Overview
The following Dart code demonstrates how to create a simple Flutter application with an alert dialog.
dart
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        appBar: AppBar(
          title: Text('Alert Dialog Box'),
          backgroundColor: Colors.redAccent,
        ),
        body: Center(
          child: AlertDialogButton(),
        ),
      ),
    );
  }
}

class AlertDialogButton extends StatefulWidget {
  @override
  _AlertDialogButtonState createState() => _AlertDialogButtonState();
}

class _AlertDialogButtonState extends State<AlertDialogButton> {
  @override
  Widget build(BuildContext context) {
    return ElevatedButton(
      onPressed: () {
        _showAlertDialog(context);
      },
      child: Text('Show Alert Dialog'),
    );
  }

  void _showAlertDialog(BuildContext context) {
    showDialog(
      context: context,
      builder: (BuildContext context) {
        return AlertDialog(
          title: Text('Alert Dialog'),
          content: Text('This is a simple alert dialog.'),
          actions: <Widget>[
            TextButton(
              child: Text('Cancel'),
              onPressed: () {
                Navigator.of(context).pop(); // Close the dialog
              },
            ),
            TextButton(
              child: Text('OK'),
              onPressed: () {
                // Do something when OK is pressed
                Navigator.of(context).pop(); // Close the dialog
              },
            ),
          ],
        );
      },
    );
  }
}
