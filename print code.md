#Print


**CSS CODE**
```
<style>
    @media print {
        #print_Button{
            display: none;
        }
    }
    </style>
```
**PHP CODE**
```
<a href="#" class="btn btn-danger float-left mt-3 mr-2" id="print_Button" onclick="printDiv()">
        <i class="mdi mdi-printer ml-1"></i>طباعة
 </a>
```
**JS code**
```
 function printDiv(){
        var printContents=document.getElementById('print').innerHTML;
        var originalContents=document.body.innerHTML;
        window.print();
        document.body.innerHTML=originalContents;
        location.reload();

        }
  ```
