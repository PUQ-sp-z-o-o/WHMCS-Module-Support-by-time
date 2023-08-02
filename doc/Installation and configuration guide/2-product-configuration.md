# 2. Product Configuration

#####  [Order now](https://puqcloud.com/index.php?rp=/store/whmcs-module-support-by-time) | [Dowload](https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-Support-by-time/) | [FAQ](https://faq.puqcloud.com/)

>**Purpose:**
>
>This module supports both One Time and Recurring billing cycles for services.
>
>**One Time Billing:**
>
>If you choose the One Time billing option, the service will remain active until the end of the purchased support hours package.
>
>**Recurring Billing:**
>
>If you choose the Recurring billing option, the support hours will be calculated on a monthly cycle basis.

### Add new product to WHMCS

```
System Settings->Products/Services->Create a New Product
```

In the **Module settings** section, select the **"PUQ Support by Time"** module

[![image-1664279910671.png](https://doc.puq.info/uploads/images/gallery/2022-09/scaled-1680-/image-1664279910671.png)](https://doc.puq.info/uploads/images/gallery/2022-09/image-1664279910671.png)

- - - - - -

### License key

A pre-purchased license key for the "*PUQ Support by time*" module. For the module to work correctly, the key must be active

[![image-1664280027816.png](https://doc.puq.info/uploads/images/gallery/2022-09/scaled-1680-/image-1664280027816.png)](https://doc.puq.info/uploads/images/gallery/2022-09/image-1664280027816.png)

- - - - - -

### Support package setup

**Hours per month** - Indicates the number of hours that are included in the paid service package

**Invoice Action -** How WHMCS will create an invoice to the customer

- **Don't invoice for now** — Keep it in the client's account as an unbilled item.
- **Invoice on Next Cron Run** — Generate an invoice for it the next time your daily cron job runs.
- **Add to User's Next Invoice** — Add it to the next automated recurring renewal invoice that the system generates for products and services.

[![image-1664280187419.png](https://doc.puq.info/uploads/images/gallery/2022-09/scaled-1680-/image-1664280187419.png)](https://doc.puq.info/uploads/images/gallery/2022-09/image-1664280187419.png)

- - - - - -

### Price per hour

In this section, you set the price per hour of support in all currencies that you have in the WHMCS system.

[![image-1664280923130.png](https://doc.puq.info/uploads/images/gallery/2022-09/scaled-1680-/image-1664280923130.png)](https://doc.puq.info/uploads/images/gallery/2022-09/image-1664280923130.png)
