# flutter-experimental

## From mobile to web

- First create a flutter web project from vscode
- Copy the entire lib folder from mobile project to web project
- web/Assets folder should create from the scratch
 -> Create AssetManifest.json
 -> Create FontManifest.json 
 with all the images & fonts that you will user for the prohect.
 - Change references from main.dart
  from 
     import 'package:flutter/material.dart';
  to
      import 'package:flutter_web/material.dart';

- Change the to the web project (if it's neccessary):
  from 
      import 'package:heros/pages/hero_screen.dart';
  to
     import 'package:hummingbird/pages/hero_screen.dart';
- Change all the pages to the new references flutter_web instead of flutter