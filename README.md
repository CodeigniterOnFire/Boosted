CodeigniterOnFire Boosted 
=======

Automatically-generated database like django, Automatic json API from models, Automatic Node.js calls from Controllers to support high performance and complex processing.

----------
Database:
Just set your model attributes using standard values. The database will be updated at the first load or at attributes changes detections. Example:

    MODEL

        class Blogmodel extends CI_Model {
            var $title   = ''; //  type  TEXT 
            var $content = ''; //  type  TEXT
            var $date    = "2012-09-09"; //  type  DATETIME
            var votes = 0; //  type  DOUBLE

        // ...
        }


 ----------
 JSON API

 On your MODEL just use the onfire_  prefix on a  method, this will enable the method in the controller using Reflexion and Closure. The output will be a JSON encoded return value of the model method.

    MODEL

      function onfire_simplearray()
        {
            return Array(1,2,4,5,6,7);
        } 

    CONTROLLER

    public function __construct()
       {
            parent::__construct();
            // Add your models here
            $this->load->model('Blogmodel2');

       }

        URL: /index.php/CONTROLLER/onfire_simplearray/


    *Important: The model must be loaded in the constructor.


----------
Node.js  for high performance calls.
In your CONTROLLER just use "node_jsfile" to name a method. The node file can be called using the following url:

        URL: /index.php/CONTROLLER/node_jsfile/

This url will execute a jsfile.js in the CONTROLLER folder at the node folder.

 /application/node/CONTROLLER/jsfile.js

The node std output will be passed as the first argument of the "node_jsfile" method in the CONTROLLER:




