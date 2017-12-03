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
ms.openlocfilehash: cd6206d3b9445b321230bf5968891773abcac9c5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="configuring-timeout-values-on-a-binding"></a><span data-ttu-id="0bb30-102">Konfigurieren von Timeoutwerten für eine Bindung</span><span class="sxs-lookup"><span data-stu-id="0bb30-102">Configuring Timeout Values on a Binding</span></span>
<span data-ttu-id="0bb30-103">Für WCF-Bindungen stehen eine Reihe von Timeouteinstellungen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="0bb30-103">There are a number of timeout settings available in WCF bindings.</span></span> <span data-ttu-id="0bb30-104">Wenn diese Timeouteinstellungen ordnungsgemäß festgelegt sind, verbessert sich nicht nur die Leistung des Diensts, sondern auch dessen Anwenderfreundlichkeit und Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="0bb30-104">Setting these timeout settings correctly can improve not only your service’s performance but also play a role in the usability and security of your service.</span></span> <span data-ttu-id="0bb30-105">Die folgenden Timeouts sind für WCF-Bindungen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="0bb30-105">The following timeouts are available on WCF bindings:</span></span>  
  
1.  <span data-ttu-id="0bb30-106">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="0bb30-106">OpenTimeout</span></span>  
  
2.  <span data-ttu-id="0bb30-107">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="0bb30-107">CloseTimeout</span></span>  
  
3.  <span data-ttu-id="0bb30-108">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="0bb30-108">SendTimeout</span></span>  
  
4.  <span data-ttu-id="0bb30-109">ReceiveTimeout</span><span class="sxs-lookup"><span data-stu-id="0bb30-109">ReceiveTimeout</span></span>  
  
## <a name="wcf-binding-timeouts"></a><span data-ttu-id="0bb30-110">WCF-Timeouts für Bindungen</span><span class="sxs-lookup"><span data-stu-id="0bb30-110">WCF Binding Timeouts</span></span>  
 <span data-ttu-id="0bb30-111">Jede der in diesem Thema erläuterten Einstellungen wird für die Bindung selbst festgelegt, entweder im Code oder in der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="0bb30-111">Each of the settings discussed in this topic are made on the binding itself, either in code or configuration.</span></span> <span data-ttu-id="0bb30-112">Der folgende Code zeigt, wie Sie programmgesteuert Timeouts für eine WCF-Bindung im Kontext eines selbst gehosteten Diensts festlegen.</span><span class="sxs-lookup"><span data-stu-id="0bb30-112">The following code shows how to programmatically set timeouts on a WCF binding in the context of a self-hosted service.</span></span>  
  
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
  
 <span data-ttu-id="0bb30-113">Das folgende Beispiel veranschaulicht, wie die Timeouts für eine Bindung in einer Konfigurationsdatei konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="0bb30-113">The following example shows how to configure timeouts on a binding in a configuration file.</span></span>  
  
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
  
 <span data-ttu-id="0bb30-114">Weitere Informationen zu diesen Einstellungen finden Sie in der Dokumentation zur <xref:System.ServiceModel.Channels.Binding>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="0bb30-114">More information about these settings can be found in the documentation for the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
### <a name="client-side-timeouts"></a><span data-ttu-id="0bb30-115">Clientseitige Timeouts</span><span class="sxs-lookup"><span data-stu-id="0bb30-115">Client-side Timeouts</span></span>  
 <span data-ttu-id="0bb30-116">Auf der Clientseite:</span><span class="sxs-lookup"><span data-stu-id="0bb30-116">On the client side:</span></span>  
  
1.  <span data-ttu-id="0bb30-117">
          SendTimeout: Wird zur Initialisierung von OperationTimeout verwendet. Die Einstellung steuert den gesamten Sendevorgang einer Nachricht, einschließlich des Empfangs einer Antwortnachricht für einen Vorgang des Anforderung-Antwort-Diensts.</span><span class="sxs-lookup"><span data-stu-id="0bb30-117">SendTimeout – used to initialize the OperationTimeout, which governs the whole process of sending a message, including receiving a reply message for a request/reply service operation.</span></span> <span data-ttu-id="0bb30-118">Dieses Timeout gilt auch beim Senden von Antwortnachrichten von einer Rückrufvertragsmethode.</span><span class="sxs-lookup"><span data-stu-id="0bb30-118">This timeout also applies when sending reply messages from a callback contract method.</span></span>  
  
2.  <span data-ttu-id="0bb30-119">
          OpenTimeout: Wird beim Öffnen von Kanälen verwendet, wenn kein expliziter Timeoutwert angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="0bb30-119">OpenTimeout – used when opening channels when no explicit timeout value is specified</span></span>  
  
3.  <span data-ttu-id="0bb30-120">
          CloseTimeout: Wird beim Schließen von Kanälen verwendet, wenn kein expliziter Timeoutwert angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="0bb30-120">CloseTimeout – used when closing channels when no explicit timeout value is specified</span></span>  
  
4.  <span data-ttu-id="0bb30-121">ReceiveTimeout: Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="0bb30-121">ReceiveTimeout – is not used</span></span>  
  
### <a name="service-side-timeouts"></a><span data-ttu-id="0bb30-122">Dienstseitige Timeouts</span><span class="sxs-lookup"><span data-stu-id="0bb30-122">Service-side Timeouts</span></span>  
 <span data-ttu-id="0bb30-123">Auf der Dienstseite:</span><span class="sxs-lookup"><span data-stu-id="0bb30-123">On the service side:</span></span>  
  
1.  <span data-ttu-id="0bb30-124">SendTimeout, OpentTimeout und CloseTimeout sind mit den Einstellungen auf dem Client identisch.</span><span class="sxs-lookup"><span data-stu-id="0bb30-124">SendTimeout, OpentTimeout, CloseTimeout are the same as on the client</span></span>  
  
2.  <span data-ttu-id="0bb30-125">ReceiveTimeout: Wird von der Dienstframeworkebene verwendet, um das Timeout für Sitzungen im Leerlauf zu initialisieren, das steuert, wie lange eine Sitzung bis zum Timeout im Leerlauf sein kann.</span><span class="sxs-lookup"><span data-stu-id="0bb30-125">ReceiveTimeout – used by the Service Framework Layer to initialize the session-idle timeout which controls how long a session can be idle before timing out.</span></span>
