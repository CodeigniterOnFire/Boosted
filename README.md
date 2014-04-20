Boosted
=======

Automatically-generated database like django, Automatic json api from models, Automatic Node.js calls from Controlers.

----------
Database:
Just set your model attributes using standard values. The database will be updated at the first load or at attributes changes detections. Example:


class Blogmodel extends CI_Model {
    var $title   = '';
    var $content = '';
    var $date    = "2012-09-09";
    var votes = 0;



 ----------
 JSON API

 On you model just use the onfire_ prefix on a specific method, this will enable the method in the controler using Reflexion the output will be a json encoded object of the return value of the model method.

MODEL

  function onfire_simplearray()
    {
        return Array(1,2,4,5,6,7);
    } 

CONTROLER

    public function __construct()
       {
            parent::__construct();
            // Add your models here
            $this->load->model('Blogmodel2');

       }

    URL: /index.php/CONTROLLER/onfire_simplearray/


    *Important: The model must be loaded in the contructor.


----------
Node.js Calls for hight performance calls.
Just call any method using the following url:

URL: /index.php/CONTROLLER/node_jsfile/

This will be load a jsfile.js in the CONTROLLER folder at the node folder.
The return value will be "echo"




