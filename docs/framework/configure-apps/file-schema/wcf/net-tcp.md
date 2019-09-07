---
title: <net.tcp>
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 4a3a17655f5469fe84c0b684ebdac9848bbfba84
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397695"
---
# <a name="nettcp"></a><span data-ttu-id="4cde0-102">\<net.tcp></span><span class="sxs-lookup"><span data-stu-id="4cde0-102">\<net.tcp></span></span>
<span data-ttu-id="4cde0-103">Gibt Konfigurationseinstellungen für den NET.TCP-Anschlussfreigabedienst an, der ermöglicht, dass mehrere Prozesse den gleichen TCP-Anschluss nutzen.</span><span class="sxs-lookup"><span data-stu-id="4cde0-103">Specifies configuration settings for the NET.TCP Port Sharing Service, which allows multiple processes to share the same TCP port.</span></span>  
  
<span data-ttu-id="4cde0-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4cde0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4cde0-105">&nbsp;&nbsp;[ **\<System. Service Model. Activation->** ](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="4cde0-105">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="4cde0-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<NET. TCP->**</span><span class="sxs-lookup"><span data-stu-id="4cde0-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<net.tcp>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cde0-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="4cde0-107">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="4cde0-108">Typ</span><span class="sxs-lookup"><span data-stu-id="4cde0-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4cde0-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4cde0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4cde0-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4cde0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4cde0-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="4cde0-111">Attributes</span></span>  
  
|<span data-ttu-id="4cde0-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="4cde0-112">Attribute</span></span>|<span data-ttu-id="4cde0-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4cde0-113">Description</span></span>|  
|---------------|-----------------|  
|`listenBacklog`|<span data-ttu-id="4cde0-114">Eine ganze Zahl, die die maximale Anzahl ausstehender Verbindungen angibt, die von der freigegebenen Verbindung angenommen werden, aber noch nicht an Windows Communication Foundation (WCF)-Dienste weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="4cde0-114">An integer that specifies the maximum outstanding connections that are accepted from the shared connection, but are not yet dispatched to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="4cde0-115">Der Standard ist 10.</span><span class="sxs-lookup"><span data-stu-id="4cde0-115">The default is 10.</span></span>|  
|`maxPendingAccepts`|<span data-ttu-id="4cde0-116">Eine ganze Zahl, die den Höchstwert für ausstehende gleichzeitig annehmende Threads am überwachenden Endpunkt für den Freigabedienst festlegt.</span><span class="sxs-lookup"><span data-stu-id="4cde0-116">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="4cde0-117">Der Standardwert ist&#160;2.</span><span class="sxs-lookup"><span data-stu-id="4cde0-117">The default is 2.</span></span>|  
|`MaxPendingConnections`|<span data-ttu-id="4cde0-118">Die maximale Anzahl von Verbindungen, die für einen Listener darauf warten können, von der Anwendung angenommen zu werden.</span><span class="sxs-lookup"><span data-stu-id="4cde0-118">The maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="4cde0-119">Wenn dieser Kontingentwert überstiegen wird, werden neue eingehende Verbindungen gelöscht, statt weiter auf die Annahme zu warten.</span><span class="sxs-lookup"><span data-stu-id="4cde0-119">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> <span data-ttu-id="4cde0-120">Verbindungsfunktionen, wie Nachrichtensicherheit, können dazu führen, dass ein Client mehr als eine Verbindung öffnet.</span><span class="sxs-lookup"><span data-stu-id="4cde0-120">Connection features such as message security can cause a client to open more than one connection.</span></span> <span data-ttu-id="4cde0-121">Dienstadministratoren sollten diese zusätzlichen Verbindungen bei der Einrichtung des Kontingentwerts berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="4cde0-121">Service administrators should account for these additional connections when setting this quota value.</span></span> <span data-ttu-id="4cde0-122">Der Standard ist 10.</span><span class="sxs-lookup"><span data-stu-id="4cde0-122">The default is 10.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="4cde0-123">Eine <xref:System.TimeSpan>, die das Timeout für das Lesen der Rahmendaten und das Ausführen der Verbindungsverteilung der zugrunde liegenden Verbindungen angibt.</span><span class="sxs-lookup"><span data-stu-id="4cde0-123">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="4cde0-124">Der Standardwert ist "00:00:10".</span><span class="sxs-lookup"><span data-stu-id="4cde0-124">The default is "00:00:10".</span></span>|  
|`teredoEnabled`|<span data-ttu-id="4cde0-125">Ein boolescher Wert, der angibt, ob der Port Freigabe Dienst den Microsoft Teredo-Dienst verwendet, um im Auftrag von WCF-Diensten TCP-Ports zu lauschen.</span><span class="sxs-lookup"><span data-stu-id="4cde0-125">A Boolean value that indicates whether the port sharing service uses Microsoft Teredo service to listen on TCP ports on behalf of WCF services.</span></span> <span data-ttu-id="4cde0-126">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="4cde0-126">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4cde0-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4cde0-127">Child Elements</span></span>  
  
|<span data-ttu-id="4cde0-128">Element</span><span class="sxs-lookup"><span data-stu-id="4cde0-128">Element</span></span>|<span data-ttu-id="4cde0-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4cde0-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4cde0-130">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="4cde0-130">\<allowAccounts></span></span>](allowaccounts.md)|<span data-ttu-id="4cde0-131">Eine Auflistung von Konfigurationselementen, die ein `securityIdentifier` -Attribut zum Angeben von Benutzerkonten für Prozesse enthalten, die WCF-Dienste hosten und Verbindungs Zugriff auf den Freigabe Dienst erhalten.</span><span class="sxs-lookup"><span data-stu-id="4cde0-131">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4cde0-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4cde0-132">Parent Elements</span></span>  
  
|<span data-ttu-id="4cde0-133">Element</span><span class="sxs-lookup"><span data-stu-id="4cde0-133">Element</span></span>|<span data-ttu-id="4cde0-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4cde0-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4cde0-135">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="4cde0-135">\<system.serviceModel.activation></span></span>](system-servicemodel-activation.md)|<span data-ttu-id="4cde0-136">Enthält Konfigurationseinstellungen für den Listenerprozess SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="4cde0-136">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4cde0-137">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4cde0-137">Remarks</span></span>  
 <span data-ttu-id="4cde0-138">Weitere Informationen zur Port Freigabe finden Sie unter [net. TCP-Port Freigabe](../../../wcf/feature-details/net-tcp-port-sharing.md).</span><span class="sxs-lookup"><span data-stu-id="4cde0-138">For more information on port sharing, see [Net.TCP Port Sharing](../../../wcf/feature-details/net-tcp-port-sharing.md).</span></span> <span data-ttu-id="4cde0-139">Informationen zum Konfigurieren des Port Freigabe diensdienstanbieter finden Sie unter [Konfigurieren des net. TCP-Port Freigabe Dienstanbieter](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span><span class="sxs-lookup"><span data-stu-id="4cde0-139">To understand how to configure the port sharing service, see [Configuring the Net.TCP Port Sharing Service](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cde0-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4cde0-140">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>
- [<span data-ttu-id="4cde0-141">Net.TCP-Portfreigabe</span><span class="sxs-lookup"><span data-stu-id="4cde0-141">Net.TCP Port Sharing</span></span>](../../../wcf/feature-details/net-tcp-port-sharing.md)
- [<span data-ttu-id="4cde0-142">Konfigurieren des Net.TCP-Portfreigabediensts</span><span class="sxs-lookup"><span data-stu-id="4cde0-142">Configuring the Net.TCP Port Sharing Service</span></span>](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
