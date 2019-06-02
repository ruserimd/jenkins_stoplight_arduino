/*************************************************************
* Jenkins stop light for IOT Demo
* 
* A basic stop light (red/yellow/green) that is controlled by * a remote Jenkins installation via a REST API in order to 
* reflect a built job status.
* 
* The board runs a basic HTTP Server, that allows to control a 3 color 24V StackLight.
* 
* The stacklight is connected via a relay module and it is controlled via simple digital outputs.
* 
* The board also has a infrared obstacle detection sensor (with digital output) that is used as a reset button.
* 
* Ethernet uses DHCP. At startup it will output the assigned IP into the serial monitor.
* 
* REST API:
* | Request | URI                    | Reply                       | Result  
* | GET     | HTTP://board_IP/stop/  | HTTP 200 OK                 | Turn stoplight OFF 
* | GET     | HTTP://board_IP/start/ | HTTP 200 OK                 | Turn only YELLOW color on 
* | GET     | HTTP://board_IP/ok/    | HTTP 200 OK                 | Turn only GREEN color on 
* | GET     | HTTP://board_IP/nok/   | HTTP 200 OK                 | Turn only RED color on 
* | ANY     | any                    | HTTP 405 Method Not Allowed | Any other call is not allowed, board won't do anything
* 
*************************************************************/
