---
title: "Xamarin.Essentials SMS"
description: "The Sms class enables an application to open the default SMS application with a specified message to send to a recipient."
ms.assetid: 81A757F2-6F2A-458F-B9BE-770ADEBFAB58
author: jamesmontemagno
ms.author: jamont
ms.date: 05/04/2018
---
# Xamarin.Essentials SMS

![Pre-release NuGet](~/media/shared/pre-release.png)

The **Sms** class enables an application to open the default SMS application with a specified message to send to a recipient.

## Using Sms

Add a reference to Xamarin.Essentials in your class:

```csharp
using Xamarin.Essentials;
```

The SMS functionality works by calling the `ComposeAsync` method an `SmsMessage` that contains the message's recipient and the body of the message, both of which are optional.

```csharp
public class SmsTest
{
    public async Task SendSms(string messageText, string recipient)
    {
        try
        {
            var message = new SmsMessage(messageText, recipient);
            await Sms.ComposeAsync(message);
        }
        catch (FeatureNotSupportedException ex)
        {
            // Sms is not supported on this device.
        }
        catch (Exception ex)
        {
            // Other error has occurred.
        }
    }
}
```

## API

- [Sms source code](https://github.com/xamarin/Essentials/tree/master/Xamarin.Essentials/Sms)
- [Sms API documentation](xref:Xamarin.Essentials.Sms)
