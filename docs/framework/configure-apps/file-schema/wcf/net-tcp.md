---
title: <net.tcp>
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 4a3a17655f5469fe84c0b684ebdac9848bbfba84
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397695"
---
# \<net.tcp>
<span data-ttu-id="56199-102">Gibt Konfigurationseinstellungen für den NET.TCP-Anschlussfreigabedienst an, der ermöglicht, dass mehrere Prozesse den gleichen TCP-Anschluss nutzen.</span><span class="sxs-lookup"><span data-stu-id="56199-102">Specifies configuration settings for the NET.TCP Port Sharing Service, which allows multiple processes to share the same TCP port.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<net.tcp>**  
  
## <a name="syntax"></a><span data-ttu-id="56199-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="56199-103">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="56199-104">type</span><span class="sxs-lookup"><span data-stu-id="56199-104">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56199-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="56199-105">Attributes and Elements</span></span>  
 <span data-ttu-id="56199-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="56199-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56199-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="56199-107">Attributes</span></span>  
  
|<span data-ttu-id="56199-108">attribute</span><span class="sxs-lookup"><span data-stu-id="56199-108">Attribute</span></span>|<span data-ttu-id="56199-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="56199-109">Description</span></span>|  
|---------------|-----------------|  
|`listenBacklog`|<span data-ttu-id="56199-110">Eine ganze Zahl, die die maximale Anzahl ausstehender Verbindungen angibt, die von der freigegebenen Verbindung angenommen werden, aber noch nicht an Windows Communication Foundation (WCF)-Dienste weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="56199-110">An integer that specifies the maximum outstanding connections that are accepted from the shared connection, but are not yet dispatched to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="56199-111">Der Standardwert ist 10.</span><span class="sxs-lookup"><span data-stu-id="56199-111">The default is 10.</span></span>|  
|`maxPendingAccepts`|<span data-ttu-id="56199-112">Eine ganze Zahl, die den Höchstwert für ausstehende gleichzeitig annehmende Threads am überwachenden Endpunkt für den Freigabedienst festlegt.</span><span class="sxs-lookup"><span data-stu-id="56199-112">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="56199-113">Der Standardwert ist 2.</span><span class="sxs-lookup"><span data-stu-id="56199-113">The default is 2.</span></span>|  
|`MaxPendingConnections`|<span data-ttu-id="56199-114">Die maximale Anzahl von Verbindungen, die für einen Listener darauf warten können, von der Anwendung angenommen zu werden.</span><span class="sxs-lookup"><span data-stu-id="56199-114">The maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="56199-115">Wenn dieser Kontingentwert überstiegen wird, werden neue eingehende Verbindungen gelöscht, statt weiter auf die Annahme zu warten.</span><span class="sxs-lookup"><span data-stu-id="56199-115">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> <span data-ttu-id="56199-116">Verbindungsfunktionen, wie Nachrichtensicherheit, können dazu führen, dass ein Client mehr als eine Verbindung öffnet.</span><span class="sxs-lookup"><span data-stu-id="56199-116">Connection features such as message security can cause a client to open more than one connection.</span></span> <span data-ttu-id="56199-117">Dienstadministratoren sollten diese zusätzlichen Verbindungen bei der Einrichtung des Kontingentwerts berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="56199-117">Service administrators should account for these additional connections when setting this quota value.</span></span> <span data-ttu-id="56199-118">Der Standardwert ist 10.</span><span class="sxs-lookup"><span data-stu-id="56199-118">The default is 10.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="56199-119">Eine <xref:System.TimeSpan>, die das Timeout für das Lesen der Rahmendaten und das Ausführen der Verbindungsverteilung der zugrunde liegenden Verbindungen angibt.</span><span class="sxs-lookup"><span data-stu-id="56199-119">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="56199-120">Der Standardwert ist "00:00:10".</span><span class="sxs-lookup"><span data-stu-id="56199-120">The default is "00:00:10".</span></span>|  
|`teredoEnabled`|<span data-ttu-id="56199-121">Ein boolescher Wert, der angibt, ob der Port Freigabe Dienst den Microsoft Teredo-Dienst verwendet, um im Auftrag von WCF-Diensten TCP-Ports zu lauschen.</span><span class="sxs-lookup"><span data-stu-id="56199-121">A Boolean value that indicates whether the port sharing service uses Microsoft Teredo service to listen on TCP ports on behalf of WCF services.</span></span> <span data-ttu-id="56199-122">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="56199-122">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56199-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="56199-123">Child Elements</span></span>  
  
|<span data-ttu-id="56199-124">Element</span><span class="sxs-lookup"><span data-stu-id="56199-124">Element</span></span>|<span data-ttu-id="56199-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="56199-125">Description</span></span>|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|<span data-ttu-id="56199-126">Eine Auflistung von Konfigurationselementen, die ein `securityIdentifier` -Attribut zum Angeben von Benutzerkonten für Prozesse enthalten, die WCF-Dienste hosten und Verbindungs Zugriff auf den Freigabe Dienst erhalten.</span><span class="sxs-lookup"><span data-stu-id="56199-126">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="56199-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="56199-127">Parent Elements</span></span>  
  
|<span data-ttu-id="56199-128">Element</span><span class="sxs-lookup"><span data-stu-id="56199-128">Element</span></span>|<span data-ttu-id="56199-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="56199-129">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|<span data-ttu-id="56199-130">Enthält Konfigurationseinstellungen für den Listenerprozess SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="56199-130">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56199-131">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="56199-131">Remarks</span></span>  
 <span data-ttu-id="56199-132">Weitere Informationen zur Port Freigabe finden Sie unter [net. TCP-Port Freigabe](../../../wcf/feature-details/net-tcp-port-sharing.md).</span><span class="sxs-lookup"><span data-stu-id="56199-132">For more information on port sharing, see [Net.TCP Port Sharing](../../../wcf/feature-details/net-tcp-port-sharing.md).</span></span> <span data-ttu-id="56199-133">Informationen zum Konfigurieren des Port Freigabe diensdienstanbieter finden Sie unter [Konfigurieren des net. TCP-Port Freigabe Dienstanbieter](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span><span class="sxs-lookup"><span data-stu-id="56199-133">To understand how to configure the port sharing service, see [Configuring the Net.TCP Port Sharing Service](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56199-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56199-134">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>
- [<span data-ttu-id="56199-135">Net.TCP-Anschlussfreigabe</span><span class="sxs-lookup"><span data-stu-id="56199-135">Net.TCP Port Sharing</span></span>](../../../wcf/feature-details/net-tcp-port-sharing.md)
- [<span data-ttu-id="56199-136">Konfigurieren des Net.TCP-Portfreigabediensts</span><span class="sxs-lookup"><span data-stu-id="56199-136">Configuring the Net.TCP Port Sharing Service</span></span>](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
