---
title: <net.tcp>
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 85a9112def77fc31c8e4b826454894fe7372b31b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257654"
---
# <a name="nettcp"></a><span data-ttu-id="f2d5a-102">\<net.tcp></span><span class="sxs-lookup"><span data-stu-id="f2d5a-102">\<net.tcp></span></span>
<span data-ttu-id="f2d5a-103">Gibt Konfigurationseinstellungen für den NET.TCP-Anschlussfreigabedienst an, der ermöglicht, dass mehrere Prozesse den gleichen TCP-Anschluss nutzen.</span><span class="sxs-lookup"><span data-stu-id="f2d5a-103">Specifies configuration settings for the NET.TCP Port Sharing Service, which allows multiple processes to share the same TCP port.</span></span>  
  
 <span data-ttu-id="f2d5a-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="f2d5a-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="f2d5a-105">\<net.tcp></span><span class="sxs-lookup"><span data-stu-id="f2d5a-105">\<net.tcp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2d5a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f2d5a-106">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="f2d5a-107">Typ</span><span class="sxs-lookup"><span data-stu-id="f2d5a-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f2d5a-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f2d5a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f2d5a-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f2d5a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f2d5a-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="f2d5a-110">Attributes</span></span>  
  
|<span data-ttu-id="f2d5a-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="f2d5a-111">Attribute</span></span>|<span data-ttu-id="f2d5a-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2d5a-112">Description</span></span>|  
|---------------|-----------------|  
|`listenBacklog`|<span data-ttu-id="f2d5a-113">Eine ganze Zahl, die den Höchstwert für ausstehenden Verbindungen angibt, die von der freigegebenen Verbindung angenommen werden, aber noch nicht auf Windows Communication Foundation (WCF)-Dienste weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="f2d5a-113">An integer that specifies the maximum outstanding connections that are accepted from the shared connection, but are not yet dispatched to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="f2d5a-114">Der Standard ist 10.</span><span class="sxs-lookup"><span data-stu-id="f2d5a-114">The default is 10.</span></span>|  
|`maxPendingAccepts`|<span data-ttu-id="f2d5a-115">Eine ganze Zahl, die den Höchstwert für ausstehende gleichzeitig annehmende Threads am überwachenden Endpunkt für den Freigabedienst festlegt.</span><span class="sxs-lookup"><span data-stu-id="f2d5a-115">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="f2d5a-116">Der Standard ist 2.</span><span class="sxs-lookup"><span data-stu-id="f2d5a-116">The default is 2.</span></span>|  
|`MaxPendingConnections`|<span data-ttu-id="f2d5a-117">Die maximale Anzahl von Verbindungen, die für einen Listener darauf warten können, von der Anwendung angenommen zu werden.</span><span class="sxs-lookup"><span data-stu-id="f2d5a-117">The maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="f2d5a-118">Wenn dieser Kontingentwert überstiegen wird, werden neue eingehende Verbindungen gelöscht, statt weiter auf die Annahme zu warten.</span><span class="sxs-lookup"><span data-stu-id="f2d5a-118">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> <span data-ttu-id="f2d5a-119">Verbindungsfunktionen, wie Nachrichtensicherheit, können dazu führen, dass ein Client mehr als eine Verbindung öffnet.</span><span class="sxs-lookup"><span data-stu-id="f2d5a-119">Connection features such as message security can cause a client to open more than one connection.</span></span> <span data-ttu-id="f2d5a-120">Dienstadministratoren sollten diese zusätzlichen Verbindungen bei der Einrichtung des Kontingentwerts berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="f2d5a-120">Service administrators should account for these additional connections when setting this quota value.</span></span> <span data-ttu-id="f2d5a-121">Der Standard ist 10.</span><span class="sxs-lookup"><span data-stu-id="f2d5a-121">The default is 10.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="f2d5a-122">Eine `TimeSpan`, die das Timeout für das Lesen der Rahmendaten und das Ausführen der Verbindungsverteilung der zugrunde liegenden Verbindungen angibt.</span><span class="sxs-lookup"><span data-stu-id="f2d5a-122">A `TimeSpan` that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="f2d5a-123">Der Standardwert ist "00:00:10".</span><span class="sxs-lookup"><span data-stu-id="f2d5a-123">The default is "00:00:10".</span></span>|  
|`teredoEnabled`|<span data-ttu-id="f2d5a-124">Ein boolescher Wert, der angibt, ob der anschlussfreigabedienst den Dienst Microsoft Teredo verwendet, für das Lauschen an TCP-Anschlüssen für WCF-Dienste.</span><span class="sxs-lookup"><span data-stu-id="f2d5a-124">A Boolean value that indicates whether the port sharing service uses Microsoft Teredo service to listen on TCP ports on behalf of WCF services.</span></span> <span data-ttu-id="f2d5a-125">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="f2d5a-125">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f2d5a-126">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f2d5a-126">Child Elements</span></span>  
  
|<span data-ttu-id="f2d5a-127">Element</span><span class="sxs-lookup"><span data-stu-id="f2d5a-127">Element</span></span>|<span data-ttu-id="f2d5a-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2d5a-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f2d5a-129">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="f2d5a-129">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="f2d5a-130">Eine Auflistung von Konfigurationselementen, enthalten eine `securityIdentifier` Attribut, um Benutzerkonten für Prozesse angeben, die WCF-Dienste hosten, und denen Verbindungszugriff auf den Freigabedienst gewährt wurde.</span><span class="sxs-lookup"><span data-stu-id="f2d5a-130">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f2d5a-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f2d5a-131">Parent Elements</span></span>  
  
|<span data-ttu-id="f2d5a-132">Element</span><span class="sxs-lookup"><span data-stu-id="f2d5a-132">Element</span></span>|<span data-ttu-id="f2d5a-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2d5a-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f2d5a-134">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="f2d5a-134">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="f2d5a-135">Enthält Konfigurationseinstellungen für den Listenerprozess SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="f2d5a-135">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2d5a-136">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f2d5a-136">Remarks</span></span>  
 <span data-ttu-id="f2d5a-137">Weitere Informationen zur Anschlussfreigabe finden Sie unter [Net.TCP Port Sharing](../../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md).</span><span class="sxs-lookup"><span data-stu-id="f2d5a-137">For more information on port sharing, see [Net.TCP Port Sharing](../../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md).</span></span> <span data-ttu-id="f2d5a-138">Um zu verstehen, wie der anschlussfreigabedienst den Dienst zu konfigurieren, finden Sie unter [konfigurieren den Net.TCP-Portfreigabedienst](../../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span><span class="sxs-lookup"><span data-stu-id="f2d5a-138">To understand how to configure the port sharing service, see [Configuring the Net.TCP Port Sharing Service](../../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2d5a-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2d5a-139">See also</span></span>
- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>
- [<span data-ttu-id="f2d5a-140">Net.TCP-Portfreigabe</span><span class="sxs-lookup"><span data-stu-id="f2d5a-140">Net.TCP Port Sharing</span></span>](../../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)
- [<span data-ttu-id="f2d5a-141">Konfigurieren des Net.TCP-Portfreigabediensts</span><span class="sxs-lookup"><span data-stu-id="f2d5a-141">Configuring the Net.TCP Port Sharing Service</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
