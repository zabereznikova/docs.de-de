---
title: WAS-Aktivierungsarchitektur
ms.date: 03/30/2017
ms.assetid: 58aeffb0-8f3f-4b40-80c8-15f3f1652fd3
ms.openlocfilehash: 71546bf6fb13c9d2fecf09b79460a953f60e4e3b
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2019
ms.locfileid: "58465758"
---
# <a name="was-activation-architecture"></a><span data-ttu-id="2cccb-102">WAS-Aktivierungsarchitektur</span><span class="sxs-lookup"><span data-stu-id="2cccb-102">WAS Activation Architecture</span></span>
<span data-ttu-id="2cccb-103">In diesem Thema werden die einzelnen Komponenten des Windows-Prozessaktivierungsdiensts (auch WAS genannt) aufgeführt und erläutert.</span><span class="sxs-lookup"><span data-stu-id="2cccb-103">This topic itemizes and discusses the components of the Windows Process Activation Service (also known as WAS).</span></span>  
  
## <a name="activation-components"></a><span data-ttu-id="2cccb-104">Aktivierungskomponenten</span><span class="sxs-lookup"><span data-stu-id="2cccb-104">Activation Components</span></span>  
 <span data-ttu-id="2cccb-105">WAS umfasst mehrere Architekturkomponenten:</span><span class="sxs-lookup"><span data-stu-id="2cccb-105">WAS consists of several architectural components:</span></span>  
  
-   <span data-ttu-id="2cccb-106">Listeneradapter.</span><span class="sxs-lookup"><span data-stu-id="2cccb-106">Listener adapters.</span></span> <span data-ttu-id="2cccb-107">Windows-Dienste, die Nachrichten über bestimmte Netzwerkprotokolle empfangen und mit WAS kommunizieren, leiten eingehende Nachrichten an den richtigen Arbeitsprozess weiter.</span><span class="sxs-lookup"><span data-stu-id="2cccb-107">Windows services that receive messages on specific network protocols and communicate with WAS to route incoming messages to the correct worker process.</span></span>  
  
-   <span data-ttu-id="2cccb-108">WAS.</span><span class="sxs-lookup"><span data-stu-id="2cccb-108">WAS.</span></span> <span data-ttu-id="2cccb-109">Der Windows-Dienst, der die Erstellung und die Lebensdauer von Arbeitsprozessen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="2cccb-109">The Windows service that manages the creation and lifetime of worker processes.</span></span>  
  
-   <span data-ttu-id="2cccb-110">Die ausführbare Datei für generische Arbeitsprozesse (w3wp.exe).</span><span class="sxs-lookup"><span data-stu-id="2cccb-110">The generic worker process executable (w3wp.exe).</span></span>  
  
-   <span data-ttu-id="2cccb-111">Anwendungs-Manager</span><span class="sxs-lookup"><span data-stu-id="2cccb-111">Application manager.</span></span> <span data-ttu-id="2cccb-112">Verwaltet die Erstellung und die Lebensdauer der Anwendungsdomänen, die innerhalb des Arbeitsprozesses als Host von Anwendungen fungieren.</span><span class="sxs-lookup"><span data-stu-id="2cccb-112">Manages the creation and lifetime of application domains that host applications within the worker process.</span></span>  
  
-   <span data-ttu-id="2cccb-113">Protokollhandler.</span><span class="sxs-lookup"><span data-stu-id="2cccb-113">Protocol handlers.</span></span> <span data-ttu-id="2cccb-114">Protokollspezifische Komponenten, die im Arbeitsprozess ausgeführt werden und die Kommunikation zwischen Arbeitsprozess und den einzelnen Listeneradaptern verwalten.</span><span class="sxs-lookup"><span data-stu-id="2cccb-114">Protocol-specific components that run in the worker process and manage communication between the worker process and the individual listener adapters.</span></span> <span data-ttu-id="2cccb-115">Es sind zwei Typen von Protokollhandlern verfügbar: Prozessprotokollhandler und AppDomain-Protokollhandler.</span><span class="sxs-lookup"><span data-stu-id="2cccb-115">Two types of protocol handlers exist: process protocol handlers and AppDomain protocol handlers.</span></span>  
  
 <span data-ttu-id="2cccb-116">Wenn WAS eine Arbeitsprozessinstanz aktiviert, werden die erforderlichen Prozessprotokollhandler in den Arbeitsprozess geladen, und mit dem Anwendungs-Manager wird eine Anwendungsdomäne erstellt, in der die Anwendung gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="2cccb-116">When WAS activates a worker process instance, it loads the process protocol handlers required into the worker process and uses the application manager to create an application domain to host the application.</span></span> <span data-ttu-id="2cccb-117">Die Anwendungsdomäne lädt sowohl den Anwendungscode als auch die AppDomain-Protokollhandler, die für die von der Anwendung verwendeten Netzwerkprotokolle erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="2cccb-117">The application domain loads the application’s code as well as the AppDomain protocol handlers that the network protocols used by the application require.</span></span>  
  
 ![Screenshot mit der WAS-Architektur.](./media/was-activation-architecture/windows-process-application-service-architecture.gif)  
  
### <a name="listener-adapters"></a><span data-ttu-id="2cccb-119">Listeneradapter</span><span class="sxs-lookup"><span data-stu-id="2cccb-119">Listener Adapters</span></span>  
 <span data-ttu-id="2cccb-120">Listeneradapter sind einzelne Windows-Dienste, welche für die Netzwerkprotokolle, bei denen sie lauschen, die Netzwerkprotokolllogik zum Empfang von Nachrichten implementieren.</span><span class="sxs-lookup"><span data-stu-id="2cccb-120">Listener adapters are individual Windows services that implement the network communication logic used to receive messages using the network protocol on which they listen.</span></span> <span data-ttu-id="2cccb-121">Die folgende Tabelle enthält die Listeneradapter für Windows Communication Foundation (WCF)-Protokolle.</span><span class="sxs-lookup"><span data-stu-id="2cccb-121">The following table lists the listener adapters for Windows Communication Foundation (WCF) protocols.</span></span>  
  
|<span data-ttu-id="2cccb-122">Dienstname des Listeneradapters</span><span class="sxs-lookup"><span data-stu-id="2cccb-122">Listener adapter service name</span></span>|<span data-ttu-id="2cccb-123">Protokoll</span><span class="sxs-lookup"><span data-stu-id="2cccb-123">Protocol</span></span>|<span data-ttu-id="2cccb-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2cccb-124">Notes</span></span>|  
|-----------------------------------|--------------|-----------|  
|<span data-ttu-id="2cccb-125">W3SVC</span><span class="sxs-lookup"><span data-stu-id="2cccb-125">W3SVC</span></span>|<span data-ttu-id="2cccb-126">http</span><span class="sxs-lookup"><span data-stu-id="2cccb-126">http</span></span>|<span data-ttu-id="2cccb-127">Allgemeine Komponente, die für IIS 7.0 und WCF-HTTP-Aktivierung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="2cccb-127">Common component that provides HTTP activation for both IIS 7.0 and WCF.</span></span>|  
|<span data-ttu-id="2cccb-128">NetTcpActivator</span><span class="sxs-lookup"><span data-stu-id="2cccb-128">NetTcpActivator</span></span>|<span data-ttu-id="2cccb-129">net.tcp</span><span class="sxs-lookup"><span data-stu-id="2cccb-129">net.tcp</span></span>|<span data-ttu-id="2cccb-130">Hängt vom NetTcpPortSharing-Dienst ab.</span><span class="sxs-lookup"><span data-stu-id="2cccb-130">Depends on the NetTcpPortSharing service.</span></span>|  
|<span data-ttu-id="2cccb-131">NetPipeActivator</span><span class="sxs-lookup"><span data-stu-id="2cccb-131">NetPipeActivator</span></span>|<span data-ttu-id="2cccb-132">net.pipe</span><span class="sxs-lookup"><span data-stu-id="2cccb-132">net.pipe</span></span>||  
|<span data-ttu-id="2cccb-133">NetMsmqActivator</span><span class="sxs-lookup"><span data-stu-id="2cccb-133">NetMsmqActivator</span></span>|<span data-ttu-id="2cccb-134">net.msmq</span><span class="sxs-lookup"><span data-stu-id="2cccb-134">net.msmq</span></span>|<span data-ttu-id="2cccb-135">Für die Verwendung mit WCF-basierten Message Queuing-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="2cccb-135">For use with WCF-based Message Queuing applications.</span></span>|  
|<span data-ttu-id="2cccb-136">NetMsmqActivator</span><span class="sxs-lookup"><span data-stu-id="2cccb-136">NetMsmqActivator</span></span>|<span data-ttu-id="2cccb-137">msmq.formatname</span><span class="sxs-lookup"><span data-stu-id="2cccb-137">msmq.formatname</span></span>|<span data-ttu-id="2cccb-138">Stellt Abwärtskompatibilität mit vorhandenen Message Queuing-Anwendungen bereit.</span><span class="sxs-lookup"><span data-stu-id="2cccb-138">Provides backwards compatibility with existing Message Queuing applications.</span></span>|  
  
 <span data-ttu-id="2cccb-139">Listeneradapter für bestimmte Protokolle werden während der Installation in der Datei applicationHost.config registriert. Dies wird im folgenden XML-Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2cccb-139">Listener adapters for specific protocols are registered during installation in the applicationHost.config file, as shown in the following XML example.</span></span>  
  
```xml  
<system.applicationHost>  
    <listenerAdapters>  
        <add name="http" />  
        <add name="net.tcp"   
          identity="S-1-5-80-3579033775-2824656752-1522793541-1960352512-462907086" />  
         <add name="net.pipe"   
           identity="S-1-5-80-2943419899-937267781-4189664001-1229628381-3982115073" />  
          <add name="net.msmq"   
            identity="S-1-5-80-89244771-1762554971-1007993102-348796144-2203111529" />  
           <add name="msmq.formatname"   
             identity="S-1-5-80-89244771-1762554971-1007993102-348796144-2203111529" />  
    </listenerAdapters>  
</system.applicationHost>  
```  
  
### <a name="protocol-handlers"></a><span data-ttu-id="2cccb-140">Protokollhandler</span><span class="sxs-lookup"><span data-stu-id="2cccb-140">Protocol Handlers</span></span>  
 <span data-ttu-id="2cccb-141">Prozess- und AppDomain-Protokollhandler für bestimmte Protokolle werden in der Datei Web.config auf Computerebene registriert.</span><span class="sxs-lookup"><span data-stu-id="2cccb-141">Process and AppDomain protocol handlers for specific protocols are registered in the machine-level Web.config file.</span></span>  
  
```xml  
<system.web>  
   <protocols>  
      <add name="net.tcp"   
        processHandlerType=  
         "System.ServiceModel.WasHosting.TcpProcessProtocolHandler"  
        appDomainHandlerType=  
         "System.ServiceModel.WasHosting.TcpAppDomainProtocolHandler"  
        validate="false" />  
      <add name="net.pipe"   
        processHandlerType=  
         "System.ServiceModel.WasHosting.NamedPipeProcessProtocolHandler"  
          appDomainHandlerType=  
           "System.ServiceModel.WasHosting.NamedPipeAppDomainProtocolHandler"/>  
      <add name="net.msmq"  
        processHandlerType=  
         "System.ServiceModel.WasHosting.MsmqProcessProtocolHandler"  
        appDomainHandlerType=  
         "System.ServiceModel.WasHosting.MsmqAppDomainProtocolHandler"  
        validate="false" />  
   </protocols>  
</system.web>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2cccb-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2cccb-142">See also</span></span>
- [<span data-ttu-id="2cccb-143">Konfigurieren von WAS für die Verwendung mit WCF</span><span class="sxs-lookup"><span data-stu-id="2cccb-143">Configuring WAS for Use with WCF</span></span>](../../../../docs/framework/wcf/feature-details/configuring-the-wpa--service-for-use-with-wcf.md)
- [<span data-ttu-id="2cccb-144">Windows Server AppFabric-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="2cccb-144">Windows Server App Fabric Hosting Features</span></span>](https://go.microsoft.com/fwlink/?LinkId=201276)
