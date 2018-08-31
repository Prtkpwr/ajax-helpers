# ajax-helpers
ajax helpers


Everything about Datatables.
https://datatables.net/examples/


///////////    POST

$.ajax({
  type: "POST",
  url: "some.php",
  data: "name=John&location=Boston",
  success: function(msg){
        alert( "Data Saved: " + msg );
  },
  error: function(XMLHttpRequest, textStatus, errorThrown) {
     alert("some error");
  }
});




$(function () {
                $("#btnValidate1").click(function () {
                    var number = $("#txtNumber1").val();
                    $.ajax({
                        type: "POST",
                        url: " Default.aspx/ValidateNumber",
                        data: '{number: "' + number + '"}',
                        contentType: "application/json; charset=utf-8",
                        dataType: "json",
                        success: function (r) {
                            alert("Valid number.");
                        },
                        error: OnError
                    });
                });
            });






//////////  GET


$(document).ready(function() {

    $('#myBtnAjax').click(function() {

        
        $.ajax({
            url: '/non-existent-path-adsasd',

            type: "GET",

            dataType: "json",

            data: {
                name: "John",
                location: "Boston"
            },
            error: function(jqXHR,status) {
                console.log(status);
            },
            success: function(data, textStatus, jqXHR) {
                console.log(data);
            }
        });

    });

});



/// jquery data table example

////  HTML

<table id="example" class="display" style="width:100%">
        <thead>
            <tr>
                <th>Name</th>
                <th>Position</th>
                <th>Office</th>
                <th>Extn.</th>
                <th>Start date</th>
                <th>Salary</th>
            </tr>
        </thead>
        <tfoot>
            <tr>
                <th>Name</th>
                <th>Position</th>
                <th>Office</th>
                <th>Extn.</th>
                <th>Start date</th>
                <th>Salary</th>
            </tr>
        </tfoot>
    </table>

//////  JS

$(document).ready(function() {
    $('#example').DataTable( {
        "ajax": '../ajax/data/arrays.txt'
    } );
} );



//////// AJAX

{
  "data": [
    [
      "Tiger Nixon",
      "System Architect",
      "Edinburgh",
      "5421",
      "2011/04/25",
      "$320,800"
    ],
    [
      "Garrett Winters",
      "Accountant",
      "Tokyo",
      "8422",
      "2011/07/25",
      "$170,750"
    ],
    [
      "Ashton Cox",
      "Junior Technical Author",
      "San Francisco",
      "1562",
      "2009/01/12",
      "$86,000"
    ],
    [
      "Cedric Kelly",
      "Senior Javascript Developer",
      "Edinburgh",
      "6224",
      "2012/03/29",
      "$433,060"
    ],
    [
      "Airi Satou",
      "Accountant",
      "Tokyo",
      "5407",
      "2008/11/28",
      "$162,700"
    ],
    [
      "Brielle Williamson",
      "Integration Specialist",
      "New York",
      "4804",
      "2012/12/02",
      "$372,000"
    ]
  ]
}
