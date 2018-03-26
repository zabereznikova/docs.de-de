---
title: WSHttpBinding
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WS Profile binding
ms.assetid: 22d85b19-0135-4141-9179-a0e9c343ad73
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8ff105c626f72d34cf6963586a84aba945b5af01
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2018
---
# <a name="wshttpbinding"></a><span data-ttu-id="a5903-102">WSHttpBinding</span><span class="sxs-lookup"><span data-stu-id="a5903-102">WSHttpBinding</span></span>
<span data-ttu-id="a5903-103">Dieses Beispiel zeigt, wie mithilfe von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ein typischer Dienst und ein typischer Client implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="a5903-103">This sample demonstrates how to implement a typical service and a typical client using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="a5903-104">Das Beispiel besteht aus einem Clientkonsolenprogramm (client.exe) und einer von IIS (Internet Information Services, Internetinformationsdienste) gehosteten Dienstbibliothek.</span><span class="sxs-lookup"><span data-stu-id="a5903-104">This sample consists of a client console program (client.exe) and a service library hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="a5903-105">Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert.</span><span class="sxs-lookup"><span data-stu-id="a5903-105">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="a5903-106">Der Vertrag wird von der `ICalculator`-Schnittstelle definiert, die mathematische Operationen (Addieren, Subtrahieren, Multiplizieren und Dividieren) verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="a5903-106">The contract is defined by the `ICalculator` interface, which exposes math operations (add, subtract, multiply, and divide).</span></span> <span data-ttu-id="a5903-107">Der Client stellt synchrone Anforderungen an eine gegebene mathematische Operation, und der Dienst antwortet mit dem Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="a5903-107">The client makes synchronous requests to a given math operation and the service replies with the result.</span></span> <span data-ttu-id="a5903-108">Die Clientaktivität ist im Konsolenfenster sichtbar.</span><span class="sxs-lookup"><span data-stu-id="a5903-108">Client activity is visible in the console window.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a5903-109">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="a5903-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a5903-110">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="a5903-110">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a5903-111">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="a5903-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a5903-112">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a5903-112">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsHttp`  
  
> [!NOTE]
>  <span data-ttu-id="a5903-113">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="a5903-113">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="a5903-114">In diesem Beispiel macht die `ICalculator` -Vertrags mithilfe der [ \<WsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="a5903-114">This sample exposes the `ICalculator` contract using the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span> <span data-ttu-id="a5903-115">Die Konfiguration dieser Bindung wurde in der Datei „Web.config“ erweitert.</span><span class="sxs-lookup"><span data-stu-id="a5903-115">The configuration of this binding has been expanded in the Web.config file.</span></span>  
  
```xml
<bindings>  
  <wsHttpBinding>  
    <!--The following is the expanded configuration section for a-->  
    <!--WSHttpBinding. Each property is configured with the default-->   
    <!--value. See the ReliableSession, TransactionFlow, -->  
    <!--TransportSecurity, and MessageSecurity samples in the WS -->  
    <!--directory to learn how to configure these features. -->  
    <binding name="Binding1"  
              bypassProxyOnLocal="false"   
              transactionFlow="false"   
              hostNameComparisonMode="StrongWildcard"  
              maxBufferPoolSize="524288"   
              maxReceivedMessageSize="65536"  
              messageEncoding="Text"   
              textEncoding="utf-8"   
              useDefaultWebProxy="true"  
              allowCookies="false">  
      <reliableSession ordered="true"   
                       inactivityTimeout="00:10:00"  
                       enabled="false" />  
      <security mode="Message">  
        <message clientCredentialType="Windows"   
                 negotiateServiceCredential="true"  
                 algorithmSuite="Default"   
                 establishSecurityContext="true" />  
      </security>  
    </binding>  
  </wsHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="a5903-116">Im `binding`-Basiselement können Sie mit dem `maxReceivedMessageSize`-Wert die maximale Größe einer eingehenden Nachricht (in Bytes) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a5903-116">On the base `binding` element, the `maxReceivedMessageSize` value lets you configure the maximum size of an incoming message (in bytes).</span></span> <span data-ttu-id="a5903-117">Mit dem `hostNameComparisonMode`-Wert können Sie konfigurieren, ob beim Demultiplexing von Nachrichten für den Dienst der Hostname eine Rolle spielt.</span><span class="sxs-lookup"><span data-stu-id="a5903-117">The `hostNameComparisonMode` value lets you configure whether the hostname is considered when de-multiplexing messages to the service.</span></span> <span data-ttu-id="a5903-118">Mit dem `messageEncoding`-Wert können Sie konfigurieren, ob Text- oder MTOM-Codierung für Nachrichten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a5903-118">The `messageEncoding` value lets you configure whether to use Text or MTOM encoding for messages.</span></span> <span data-ttu-id="a5903-119">Mit dem `textEncoding`-Wert können Sie die Zeichencodierung für Nachrichten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a5903-119">The `textEncoding` value lets you configure the character encoding for messages.</span></span> <span data-ttu-id="a5903-120">Mit dem `bypassProxyOnLocal`-Wert können Sie konfigurieren, ob ein HTTP-Proxy zur lokalen Kommunikation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a5903-120">The `bypassProxyOnLocal` value lets you configure whether to use an HTTP proxy for local communication.</span></span> <span data-ttu-id="a5903-121">Der `transactionFlow`-Wert konfiguriert, ob die aktuelle Transaktion übergeben wird (wenn ein Vorgang für den Transaktionsfluss konfiguriert ist).</span><span class="sxs-lookup"><span data-stu-id="a5903-121">The `transactionFlow` value configures whether the current transaction is flowed (if an operation is configured for transaction flow).</span></span>  
  
 <span data-ttu-id="a5903-122">Auf der [ \<ReliableSession >](../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md) Element, der aktivierte boolesche Wert konfiguriert, ob zuverlässige Sitzungen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="a5903-122">On the [\<reliableSession>](../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md) element, the enabled Boolean value configures whether reliable sessions are enabled.</span></span> <span data-ttu-id="a5903-123">Der `ordered`-Wert konfiguriert, ob die Nachrichtenreihenfolge beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="a5903-123">The `ordered` value configures whether message ordering is preserved.</span></span> <span data-ttu-id="a5903-124">Der `inactivityTimeout`-Wert konfiguriert, wie lange sich eine Sitzung im Leerlauf befinden darf, bevor sie einen Fehler verursacht.</span><span class="sxs-lookup"><span data-stu-id="a5903-124">The `inactivityTimeout` value configures how long a session can be idle before being faulted.</span></span>  
  
 <span data-ttu-id="a5903-125">Auf der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)die `mode` -Wert konfiguriert, welcher Sicherheitsmodus verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a5903-125">On the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md), the `mode` value configures which security mode should be used.</span></span> <span data-ttu-id="a5903-126">In diesem Beispiel nachrichtensicherheit verwendet wird, daher die [ \<Nachricht >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) wird angegeben, in der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="a5903-126">In this sample, messages security is being used, which is why the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) is specified inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="a5903-127">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a5903-127">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="a5903-128">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="a5903-128">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a5903-129">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="a5903-129">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="a5903-130">Installieren Sie [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 mithilfe des folgenden Befehls.</span><span class="sxs-lookup"><span data-stu-id="a5903-130">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="a5903-131">Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a5903-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="a5903-132">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="a5903-132">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="a5903-133">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a5903-133">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5903-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5903-134">See Also</span></span>
