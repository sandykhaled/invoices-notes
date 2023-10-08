## Notes
1. 
عشان احدد تاريخ اليوم عند الإضافة هنستخدم 
value={{date('Y-m-d')}} in input filed of type=text
```
 <input class="form-control fc-datepicker" name="invoice_Date" placeholder="YYYY-MM-DD"
    type="text" value="{{ date('Y-m-d') }}" required>
```
 **Note** fc-datepicker => عشان اخلي التاريخ فورمات التاريخ <br/>
 <br/>
2. إضافة صورة في php يجب إضافة في form
```
 enctype="multipart/form-data"
```

3. 

