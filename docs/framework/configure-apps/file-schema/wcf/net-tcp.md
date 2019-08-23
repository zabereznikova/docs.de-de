---
title: <net.tcp>
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 63cef2b85aa57b5c1c0e0add1794ebedc73d96c1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933052"
---
# <a name="nettcp"></a><span data-ttu-id="0bf7d-102">\<net.tcp></span><span class="sxs-lookup"><span data-stu-id="0bf7d-102">\<net.tcp></span></span>
<span data-ttu-id="0bf7d-103">Gibt Konfigurationseinstellungen für den NET.TCP-Anschlussfreigabedienst an, der ermöglicht, dass mehrere Prozesse den gleichen TCP-Anschluss nutzen.</span><span class="sxs-lookup"><span data-stu-id="0bf7d-103">Specifies configuration settings for the NET.TCP Port Sharing Service, which allows multiple processes to share the same TCP port.</span></span>  
  
 <span data-ttu-id="0bf7d-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="0bf7d-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="0bf7d-105">\<net.tcp></span><span class="sxs-lookup"><span data-stu-id="0bf7d-105">\<net.tcp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bf7d-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="0bf7d-106">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="0bf7d-107">Typ</span><span class="sxs-lookup"><span data-stu-id="0bf7d-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0bf7d-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0bf7d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0bf7d-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0bf7d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0bf7d-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="0bf7d-110">Attributes</span></span>  
  
|<span data-ttu-id="0bf7d-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="0bf7d-111">Attribute</span></span>|<span data-ttu-id="0bf7d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0bf7d-112">Description</span></span>|  
|---------------|-----------------|  
|`listenBacklog`|<span data-ttu-id="0bf7d-113">Eine ganze Zahl, die die maximale Anzahl ausstehender Verbindungen angibt, die von der freigegebenen Verbindung angenommen werden, aber noch nicht an Windows Communication Foundation (WCF)-Dienste weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="0bf7d-113">An integer that specifies the maximum outstanding connections that are accepted from the shared connection, but are not yet dispatched to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="0bf7d-114">Der Standard ist 10.</span><span class="sxs-lookup"><span data-stu-id="0bf7d-114">The default is 10.</span></span>|  
|`maxPendingAccepts`|<span data-ttu-id="0bf7d-115">Eine ganze Zahl, die den Höchstwert für ausstehende gleichzeitig annehmende Threads am überwachenden Endpunkt für den Freigabedienst festlegt.</span><span class="sxs-lookup"><span data-stu-id="0bf7d-115">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="0bf7d-116">Der Standardwert ist&#160;2.</span><span class="sxs-lookup"><span data-stu-id="0bf7d-116">The default is 2.</span></span>|  
|`MaxPendingConnections`|<span data-ttu-id="0bf7d-117">Die maximale Anzahl von Verbindungen, die für einen Listener darauf warten können, von der Anwendung angenommen zu werden.</span><span class="sxs-lookup"><span data-stu-id="0bf7d-117">The maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="0bf7d-118">Wenn dieser Kontingentwert überstiegen wird, werden neue eingehende Verbindungen gelöscht, statt weiter auf die Annahme zu warten.</span><span class="sxs-lookup"><span data-stu-id="0bf7d-118">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> <span data-ttu-id="0bf7d-119">Verbindungsfunktionen, wie Nachrichtensicherheit, können dazu führen, dass ein Client mehr als eine Verbindung öffnet.</span><span class="sxs-lookup"><span data-stu-id="0bf7d-119">Connection features such as message security can cause a client to open more than one connection.</span></span> <span data-ttu-id="0bf7d-120">Dienstadministratoren sollten diese zusätzlichen Verbindungen bei der Einrichtung des Kontingentwerts berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="0bf7d-120">Service administrators should account for these additional connections when setting this quota value.</span></span> <span data-ttu-id="0bf7d-121">Der Standard ist 10.</span><span class="sxs-lookup"><span data-stu-id="0bf7d-121">The default is 10.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="0bf7d-122">Eine <xref:System.TimeSpan>, die das Timeout für das Lesen der Rahmendaten und das Ausführen der Verbindungsverteilung der zugrunde liegenden Verbindungen angibt.</span><span class="sxs-lookup"><span data-stu-id="0bf7d-122">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="0bf7d-123">Der Standardwert ist "00:00:10".</span><span class="sxs-lookup"><span data-stu-id="0bf7d-123">The default is "00:00:10".</span></span>|  
|`teredoEnabled`|<span data-ttu-id="0bf7d-124">Ein boolescher Wert, der angibt, ob der Port Freigabe Dienst den Microsoft Teredo-Dienst verwendet, um im Auftrag von WCF-Diensten TCP-Ports zu lauschen.</span><span class="sxs-lookup"><span data-stu-id="0bf7d-124">A Boolean value that indicates whether the port sharing service uses Microsoft Teredo service to listen on TCP ports on behalf of WCF services.</span></span> <span data-ttu-id="0bf7d-125">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="0bf7d-125">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0bf7d-126">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0bf7d-126">Child Elements</span></span>  
  
|<span data-ttu-id="0bf7d-127">Element</span><span class="sxs-lookup"><span data-stu-id="0bf7d-127">Element</span></span>|<span data-ttu-id="0bf7d-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0bf7d-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0bf7d-129">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="0bf7d-129">\<allowAccounts></span></span>](allowaccounts.md)|<span data-ttu-id="0bf7d-130">Eine Auflistung von Konfigurationselementen, die ein `securityIdentifier` -Attribut zum Angeben von Benutzerkonten für Prozesse enthalten, die WCF-Dienste hosten und Verbindungs Zugriff auf den Freigabe Dienst erhalten.</span><span class="sxs-lookup"><span data-stu-id="0bf7d-130">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0bf7d-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0bf7d-131">Parent Elements</span></span>  
  
|<span data-ttu-id="0bf7d-132">Element</span><span class="sxs-lookup"><span data-stu-id="0bf7d-132">Element</span></span>|<span data-ttu-id="0bf7d-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0bf7d-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0bf7d-134">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="0bf7d-134">\<system.serviceModel.activation></span></span>](system-servicemodel-activation.md)|<span data-ttu-id="0bf7d-135">Enthält Konfigurationseinstellungen für den Listenerprozess SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="0bf7d-135">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0bf7d-136">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0bf7d-136">Remarks</span></span>  
 <span data-ttu-id="0bf7d-137">Weitere Informationen zur Port Freigabe finden Sie unter [net. TCP-Port Freigabe](../../../wcf/feature-details/net-tcp-port-sharing.md).</span><span class="sxs-lookup"><span data-stu-id="0bf7d-137">For more information on port sharing, see [Net.TCP Port Sharing](../../../wcf/feature-details/net-tcp-port-sharing.md).</span></span> <span data-ttu-id="0bf7d-138">Informationen zum Konfigurieren des Port Freigabe diensdienstanbieter finden Sie unter [Konfigurieren des net. TCP-Port Freigabe Dienstanbieter](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span><span class="sxs-lookup"><span data-stu-id="0bf7d-138">To understand how to configure the port sharing service, see [Configuring the Net.TCP Port Sharing Service](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bf7d-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0bf7d-139">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>
- [<span data-ttu-id="0bf7d-140">Net.TCP-Portfreigabe</span><span class="sxs-lookup"><span data-stu-id="0bf7d-140">Net.TCP Port Sharing</span></span>](../../../wcf/feature-details/net-tcp-port-sharing.md)
- [<span data-ttu-id="0bf7d-141">Konfigurieren des Net.TCP-Portfreigabediensts</span><span class="sxs-lookup"><span data-stu-id="0bf7d-141">Configuring the Net.TCP Port Sharing Service</span></span>](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
