![[pin_map-2.png]]
Pour rajouter le wifi :
```cpp
#include <WiFi.h>

#define SSID "reseau"
#define PASSWD "motdepasse"

void setup() {
  // put your setup code here, to run once:
  WiFi.begin(SSID, PASSWD);
  Serial.begin(115200);

  while (WiFi.status() != WL_CONNECTED) {
    delay(100);
  }
  
  Serial.println(WiFi.localIP());
}
```
