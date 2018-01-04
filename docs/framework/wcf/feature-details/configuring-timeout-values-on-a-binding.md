---
title: "Konfigurieren von Timeoutwerten für eine Bindung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5c825a2-b48f-444a-8659-61751ff11d34
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 164b4e3bff3e327b82c78c403a0e65ec8db744ff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="configuring-timeout-values-on-a-binding"></a>Konfigurieren von Timeoutwerten für eine Bindung
Für WCF-Bindungen stehen eine Reihe von Timeouteinstellungen zur Verfügung. Wenn diese Timeouteinstellungen ordnungsgemäß festgelegt sind, verbessert sich nicht nur die Leistung des Diensts, sondern auch dessen Anwenderfreundlichkeit und Sicherheit. Die folgenden Timeouts sind für WCF-Bindungen verfügbar:  
  
1.  OpenTimeout  
  
2.  CloseTimeout  
  
3.  SendTimeout  
  
4.  ReceiveTimeout  
  
## <a name="wcf-binding-timeouts"></a>WCF-Timeouts für Bindungen  
 Jede der in diesem Thema erläuterten Einstellungen wird für die Bindung selbst festgelegt, entweder im Code oder in der Konfiguration. Der folgende Code zeigt, wie Sie programmgesteuert Timeouts für eine WCF-Bindung im Kontext eines selbst gehosteten Diensts festlegen.  
  
```csharp  
public static void Main()
{
    Uri baseAddress = new Uri("http://localhost/MyServer/MyService");
    
    try
    {
        ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService));
        
        WSHttpBinding binding = new WSHttpBinding();
        binding.OpenTimeout = new TimeSpan(0, 10, 0);
        binding.CloseTimeout = new TimeSpan(0, 10, 0);
        binding.SendTimeout = new TimeSpan(0, 10, 0);
        binding.ReceiveTimeout = new TimeSpan(0, 10, 0);
        
        serviceHost.AddServiceEndpoint("ICalculator", binding, baseAddress);
        serviceHost.Open();
        
        // The service can now be accessed.
        Console.WriteLine("The service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();
    }
    catch (CommunicationException ex)
    {
        // Handle exception ...
    }
}
```  
  
 Das folgende Beispiel veranschaulicht, wie die Timeouts für eine Bindung in einer Konfigurationsdatei konfiguriert werden.  
  
```xml  
<configuration>
  <system.serviceModel>
    <bindings>
      <wsHttpBinding>
        <binding openTimeout="00:10:00" 
                 closeTimeout="00:10:00" 
                 sendTimeout="00:10:00" 
                 receiveTimeout="00:10:00">
        </binding>
      </wsHttpBinding>
    </bindings>
  </system.serviceModel>
</configuration>
```  
  
 Weitere Informationen zu diesen Einstellungen finden Sie in der Dokumentation zur <xref:System.ServiceModel.Channels.Binding>-Klasse.  
  
### <a name="client-side-timeouts"></a>Clientseitige Timeouts  
 Auf der Clientseite:  
  
1.  SendTimeout: Wird zur Initialisierung von OperationTimeout verwendet. Die Einstellung steuert den gesamten Sendevorgang einer Nachricht, einschließlich des Empfangs einer Antwortnachricht für einen Vorgang des Anforderung-Antwort-Diensts. Dieses Timeout gilt auch beim Senden von Antwortnachrichten von einer Rückrufvertragsmethode.  
  
2.  OpenTimeout: Wird beim Öffnen von Kanälen verwendet, wenn kein expliziter Timeoutwert angegeben ist.  
  
3.  CloseTimeout: Wird beim Schließen von Kanälen verwendet, wenn kein expliziter Timeoutwert angegeben ist.  
  
4.  ReceiveTimeout: Wird nicht verwendet.  
  
### <a name="service-side-timeouts"></a>Dienstseitige Timeouts  
 Auf der Dienstseite:  
  
1.  SendTimeout, OpentTimeout und CloseTimeout sind mit den Einstellungen auf dem Client identisch.  
  
2.  ReceiveTimeout: Wird von der Dienstframeworkebene verwendet, um das Timeout für Sitzungen im Leerlauf zu initialisieren, das steuert, wie lange eine Sitzung bis zum Timeout im Leerlauf sein kann.
