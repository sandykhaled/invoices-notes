**create notification**
```
php artisan make:notification InvoicePaid
```
**In InvoicePaid**
```
 private $invoice_id;
    public function __construct($invoice_id)
    {
        $this->invoice_id=$invoice_id;
    }
    
    public function toMail(object $notifiable): MailMessage
    {
        $url="http://127.0.0.1:8000/invoiceDetails/".$this->invoice_id;
        return (new MailMessage)
                    ->subject('إضافة فاتورة جديدة')
                    ->line('إضافة فاتورة جديدة')
                    ->action('عرض الفاتورة', $url)
                    ->line('شكرا لاستخدامك موراسوفت لادارة الفواتير');
    }
```
**In invoicecontroller**
```
 $user=User::first();
//        $user->notify(new InvoicePaid($invoice_id));
        Notification::send($user,new InvoicePaid($invoice_id));
```
**in .env**
```
MAIL_MAILER=smtp
MAIL_HOST=sandbox.smtp.mailtrap.io
MAIL_PORT=2525
MAIL_USERNAME=e86014372a6418
MAIL_PASSWORD=bbd09dc6b83288
MAIL_ENCRYPTION=ssl
MAIL_FROM_ADDRESS="example@gmail.com"
MAIL_FROM_NAME="${APP_NAME}"
```
