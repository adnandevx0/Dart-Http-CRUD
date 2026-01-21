# Dart-Http-CRUD

<h4>Http Get Request via Api</h4>

<pre>
import 'package:http/http.dart' as http;
import 'dart:convert'; // JSON ডেটা ডিকোড করার জন্য এটি প্রয়োজন

void main() async {
  String url = "https://jsonplaceholder.typicode.com/posts";

  // var res = await http.get(Uri.parse(url));
  var res = await http.get(
    Uri.parse(url),
    headers: {
      "User-Agent":
          "PostmanRuntime/7.26.8", // সার্ভারকে জানানো যে এটি একটি বৈধ রিকোয়েস্ট
      "Accept": "*/*",
    },
  );

  print("Status Code: ${res.statusCode}");
  if (res.statusCode == 200) {
    var v = jsonDecode(res.body);
    print(v);
  } else {
    print("Not data Found");
  }
}

</pre>





<h4>Http Post Request via Api</h4>

<pre>

import 'package:http/http.dart' as http;
import 'dart:convert'; // JSON ডেটা ডিকোড করার জন্য এটি প্রয়োজন

void main() async {
  String url = "https://jsonplaceholder.typicode.com/posts";

  Map<String, dynamic> myData = {
    "title": "Adnan's Post",
    "body": "Hello World",
    "userId": 1,
  };

  var res = await http.post(
    Uri.parse(url),
    headers: {
      "Content-Type":
          "application/json", // সার্ভারকে জানানো হচ্ছে আমরা JSON পাঠাচ্ছি
      "Accept": "application/json",
    },
    body: jsonEncode(myData),
  );

  print("Status Code: ${res.statusCode}");
  if (res.statusCode == 201) {
    var v = jsonDecode(res.body);
    print(v);
  } else {
    print("Not data Found");
  }
}


</pre>
