# WEEK 3 LAB REPORT BY YOURS TRULY
## Part 1: Simplest Search Engine + Errors
Here's my attempt at creating a search engine (only some of it works):
```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class SearchHandler implements URLHandler{
    int capacity = 2;
    ArrayList<String> searches = new ArrayList<>(capacity);
    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("What are you waiting for? Search already!");
        } 
        else if (url.getPath().contains("/add")) {
            String[] param = url.getQuery().split("=");
            if (param[0].equals("s")) {
                    searches.add(param[1]);
                    return String.format("Search term successfully added!");
            }
        }
        else if (url.getPath().contains("/search")) {
            String[] param = url.getQuery().split("=");
            if (param[0].equals("s")) {
                String search = param[1];
                for (int i = 0; i < searches.size(); i++) {
                    if (searches.contains(search)) {
                        String found = searches.get(i);
                        return String.format("Searches: ", found);
                    }
                }
            }
        }
        return "404 Not Found!";
    }
}
class SearchEngine {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new SearchHandler());
    }
}
```
Here's the default/root path for the search engine (it really wants you to search for something):
![Image](Default.PNG)
``` 
if (url.getPath().equals("/")) {
            return String.format("What are you waiting for? Search already!");
        } 
```

![Image](add.PNG)
Hooray! I added a search term to the list of searches!
```
else if (url.getPath().contains("/add")) {
            String[] param = url.getQuery().split("=");
            if (param[0].equals("s")) {
                    searches.add(param[1]);
                    return String.format("Search term successfully added!");
            }
```

![Image](search.PNG)
And I searched the exact term and I didn't get my search item, what happened?
```
else if (url.getPath().contains("/search")) {
            String[] param = url.getQuery().split("=");
            if (param[0].equals("s")) {
                String search = param[1];
                for (int i = 0; i < searches.size(); i++) {
                    if (searches.contains(search)) {
                        String found = searches.get(i);
                        return String.format("Searches: ", found);
                    }
                }
            }
        }
```
## Part 2: Supreme Debugging
Debuggers