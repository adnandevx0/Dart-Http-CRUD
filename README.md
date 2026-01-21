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
