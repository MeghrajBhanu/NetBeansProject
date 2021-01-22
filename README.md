```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Bootstrap</title>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css">
        <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
        <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/js/bootstrap.min.js"></script>
    </head>
    <body> 
        <div class="container">
            <h2>Vertical form</h2>
            <form id="empform" method="post">
                <div class="form-group">
                    <span><label for="empId">Employee ID:</label> <label id="empIdMsg"> </label></span>
                    <input type="text" class="form-control" name="empId" id="empId" 
                           placeholder="Enter Employee ID" required>
                </div>
                <div class="form-group">
                    <label for="empName">Employee Name:</label>
                    <input type="text" class="form-control" id="empName"  placeholder="Enter Employee Name" name="empName">
                </div>
                <div class="form-group">
                    <label for="empEmail">Email:</label>
                    <input type="email" class="form-control" id="empEmail"  placeholder="Enter Employee email" name="empEmail">

                </div>
                <input type="button" class="btn btn-primary" id="empSave" value="Save" onclick= "saveEmployee();">
            </form>
        </div>
        <script> 
            function createPUTRequest(connToken, jsonObj, dbName, relName) {
                var putRequest = "{\n"
                        + "\"token\" : \""
                        + connToken
                        + "\","
                        + "\"dbName\": \""
                        + dbName
                        + "\",\n" + "\"cmd\" : \"PUT\",\n"
                        + "\"rel\" : \""
                        + relName + "\","
                        + "\"jsonStr\": \n"
                        + jsonObj
                        + "\n"
                        + "}";
                return putRequest;
            }
            function executeCommandAtGivenBaseUrl(reqString, dbBaseUrl, apiEndPointUrl) {
                var url = dbBaseUrl + apiEndPointUrl;
                var jsonObj;
                $.post(url, reqString, function (result) {
                    jsonObj = JSON.parse(result);
                }).fail(function (result) {
                    var dataJsonObj = result.responseText;
                    jsonObj = JSON.parse(dataJsonObj);
                });
                return jsonObj;
            }
            function  validateAndGetFormData(){
                var empIdVar=$("#empId").val();
                 
                if(empIdVar === ""){
                    alert("Employee Id is required");
                    $("#empId").focus();
                    
                }
                var empNameVar=$("#empName").val();
                if(empNameVar === ""){
                    alert("Employee name is required");
                    $("#empName").focus();
                    
                }
                 
                var empEmailVar=$("#empEmail").val();
                if(empEmailVar === ""){
                    alert("Employee email is required");
                    $("#empEmail").focus();
                    
                }
                 
                var Obj = {
                    empId: empIdVar,
                    empName: empNameVar,
                    empEmail: empEmailVar,
                };
                
                return JSON.stringify(Obj);
            }
            function resetForm(){
                $("empId").val("");
                $("empName").val("");
                $("empEmail").val("");
                $("empId").focus();
            }
            function saveEmployee(){
                var jsonStr = validateAndGetFormData();
                alert(jsonStr);
                if(jsonStr === ""){
                    return;
                }
                var putReqStr = createPUTRequest("90937141|-31948799583822676|90931330",jsonStr,"SAMPLE","Emp-Rel");
                alert(putReqStr);
                jQuery.ajaxSetup({async:false});
                var resultObj = executeCommandAtGivenBaseUrl(putReqStr,"http://api.login2explore.com:5577", "/api/iml");
                jQuery.ajaxSetup({async:true});
                alert(JSON.stringify(resultObj));

                resetForm();
            }
        </script>  
    </body>
</html>
```html
