---
title: '&lt;NET.TCP&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4a63d32cc4c0e48b8d3fb40526d810e2f66089d4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltnettcpgt"></a><span data-ttu-id="7e6ca-102">&lt;NET.TCP&gt;</span><span class="sxs-lookup"><span data-stu-id="7e6ca-102">&lt;net.tcp&gt;</span></span>
<span data-ttu-id="7e6ca-103">Gibt Konfigurationseinstellungen für den NET.TCP-Anschlussfreigabedienst an, der ermöglicht, dass mehrere Prozesse den gleichen TCP-Anschluss nutzen.</span><span class="sxs-lookup"><span data-stu-id="7e6ca-103">Specifies configuration settings for the NET.TCP Port Sharing Service, which allows multiple processes to share the same TCP port.</span></span>  
  
 <span data-ttu-id="7e6ca-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="7e6ca-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="7e6ca-105">\<NET.TCP ></span><span class="sxs-lookup"><span data-stu-id="7e6ca-105">\<net.tcp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e6ca-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="7e6ca-106">Syntax</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <net.tcp listenBacklog="Integer"  
          maxPendingAccepts="Integer"  
          maxPendingConnections="Integer"  
          receiveTimeout="TimeSpan"  
          teredoEnabled="Boolean">  
          <allowAccounts>  
             <!-- LocalSystem account -->   
             <add securityIdentifier="S-1-5-18"/>  
             <!-- LocalService account -->   
             <add securityIdentifier="S-1-5-19"/>  
             <!-- Administrators account -->   
             <add securityIdentifier="S-1-5-20"/>  
             <!-- Network Service account -->   
             <add securityIdentifier="S-1-5-32-544" />  
             <!-- IIS_IUSRS account (Vista only)-->   
             <add securityIdentifier="S-1-5-32-568"/>  
           </allowAccounts>  
       </net.tcp>  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a><span data-ttu-id="7e6ca-107">Typ</span><span class="sxs-lookup"><span data-stu-id="7e6ca-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e6ca-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7e6ca-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7e6ca-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7e6ca-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e6ca-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="7e6ca-110">Attributes</span></span>  
  
|<span data-ttu-id="7e6ca-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="7e6ca-111">Attribute</span></span>|<span data-ttu-id="7e6ca-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e6ca-112">Description</span></span>|  
|---------------|-----------------|  
|`listenBacklog`|<span data-ttu-id="7e6ca-113">Eine ganze Zahl, die den Höchstwert für ausstehende Verbindungen angibt, die von der freigegebenen Verbindung angenommen werden können, aber noch nicht an [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Dienste weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="7e6ca-113">An integer that specifies the maximum outstanding connections that are accepted from the shared connection, but are not yet dispatched to [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services.</span></span> <span data-ttu-id="7e6ca-114">Der Standard ist 10.</span><span class="sxs-lookup"><span data-stu-id="7e6ca-114">The default is 10.</span></span>|  
|`maxPendingAccepts`|<span data-ttu-id="7e6ca-115">Eine ganze Zahl, die den Höchstwert für ausstehende gleichzeitig annehmende Threads am überwachenden Endpunkt für den Freigabedienst festlegt.</span><span class="sxs-lookup"><span data-stu-id="7e6ca-115">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="7e6ca-116">Der Standard ist 2.</span><span class="sxs-lookup"><span data-stu-id="7e6ca-116">The default is 2.</span></span>|  
|`MaxPendingConnections`|<span data-ttu-id="7e6ca-117">Die maximale Anzahl von Verbindungen, die für einen Listener darauf warten können, von der Anwendung angenommen zu werden.</span><span class="sxs-lookup"><span data-stu-id="7e6ca-117">The maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="7e6ca-118">Wenn dieser Kontingentwert überstiegen wird, werden neue eingehende Verbindungen gelöscht, statt weiter auf die Annahme zu warten.</span><span class="sxs-lookup"><span data-stu-id="7e6ca-118">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> <span data-ttu-id="7e6ca-119">Verbindungsfunktionen, wie Nachrichtensicherheit, können dazu führen, dass ein Client mehr als eine Verbindung öffnet.</span><span class="sxs-lookup"><span data-stu-id="7e6ca-119">Connection features such as message security can cause a client to open more than one connection.</span></span> <span data-ttu-id="7e6ca-120">Dienstadministratoren sollten diese zusätzlichen Verbindungen bei der Einrichtung des Kontingentwerts berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="7e6ca-120">Service administrators should account for these additional connections when setting this quota value.</span></span> <span data-ttu-id="7e6ca-121">Der Standard ist 10.</span><span class="sxs-lookup"><span data-stu-id="7e6ca-121">The default is 10.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="7e6ca-122">Eine `TimeSpan`, die das Timeout für das Lesen der Rahmendaten und das Ausführen der Verbindungsverteilung der zugrunde liegenden Verbindungen angibt.</span><span class="sxs-lookup"><span data-stu-id="7e6ca-122">A `TimeSpan` that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="7e6ca-123">Der Standardwert ist "00:00:10".</span><span class="sxs-lookup"><span data-stu-id="7e6ca-123">The default is "00:00:10".</span></span>|  
|`teredoEnabled`|<span data-ttu-id="7e6ca-124">Ein boolescher Wert, der angibt, ob der Anschlussfreigabedienst den Dienst Microsoft Teredo verwendet, um TCP-Anschlüsse für [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Dienste zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="7e6ca-124">A Boolean value that indicates whether the port sharing service uses Microsoft Teredo service to listen on TCP ports on behalf of [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services.</span></span> <span data-ttu-id="7e6ca-125">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="7e6ca-125">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e6ca-126">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7e6ca-126">Child Elements</span></span>  
  
|<span data-ttu-id="7e6ca-127">Element</span><span class="sxs-lookup"><span data-stu-id="7e6ca-127">Element</span></span>|<span data-ttu-id="7e6ca-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e6ca-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e6ca-129">\<AllowAccounts ></span><span class="sxs-lookup"><span data-stu-id="7e6ca-129">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="7e6ca-130">Eine Auflistung von Konfigurationselementen, die ein `securityIdentifier`-Attribut zum Angeben von Benutzerkonten für Prozesse enthalten, die [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Dienste hosten und Verbindungszugriff auf den Freigabedienst haben.</span><span class="sxs-lookup"><span data-stu-id="7e6ca-130">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7e6ca-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7e6ca-131">Parent Elements</span></span>  
  
|<span data-ttu-id="7e6ca-132">Element</span><span class="sxs-lookup"><span data-stu-id="7e6ca-132">Element</span></span>|<span data-ttu-id="7e6ca-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e6ca-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e6ca-134">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="7e6ca-134">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="7e6ca-135">Enthält Konfigurationseinstellungen für den Listenerprozess SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="7e6ca-135">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e6ca-136">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7e6ca-136">Remarks</span></span>  
 <span data-ttu-id="7e6ca-137">Weitere Informationen über die Portfreigabe finden Sie unter [Net.TCP Port Sharing](http://msdn.microsoft.com/en-us/f13692ee-a179-4439-ae72-50db9534eded).</span><span class="sxs-lookup"><span data-stu-id="7e6ca-137">For more information on port sharing, see [Net.TCP Port Sharing](http://msdn.microsoft.com/en-us/f13692ee-a179-4439-ae72-50db9534eded).</span></span> <span data-ttu-id="7e6ca-138">Um zu verstehen, wie der anschlussfreigabedienst den Dienst zu konfigurieren, finden Sie unter [konfigurieren den Net.TCP-Portfreigabedienst](http://msdn.microsoft.com/en-us/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0).</span><span class="sxs-lookup"><span data-stu-id="7e6ca-138">To understand how to configure the port sharing service, see [Configuring the Net.TCP Port Sharing Service](http://msdn.microsoft.com/en-us/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e6ca-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e6ca-139">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>  
 [<span data-ttu-id="7e6ca-140">Net.TCP-Portfreigabe</span><span class="sxs-lookup"><span data-stu-id="7e6ca-140">Net.TCP Port Sharing</span></span>](http://msdn.microsoft.com/en-us/f13692ee-a179-4439-ae72-50db9534eded)  
 [<span data-ttu-id="7e6ca-141">Konfigurieren des Net.TCP-Portfreigabediensts</span><span class="sxs-lookup"><span data-stu-id="7e6ca-141">Configuring the Net.TCP Port Sharing Service</span></span>](http://msdn.microsoft.com/en-us/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)
