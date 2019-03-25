---
title: <net.pipe>
ms.date: 03/30/2017
ms.assetid: 6a0f0318-f8f6-466c-9fae-199d7274a82e
ms.openlocfilehash: 90d081c1287362669286aaa1185ed3b0bbe09b07
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2019
ms.locfileid: "58412109"
---
# <a name="netpipe"></a><span data-ttu-id="eb9e8-102">\<net.pipe></span><span class="sxs-lookup"><span data-stu-id="eb9e8-102">\<net.pipe></span></span>
<span data-ttu-id="eb9e8-103">Gibt Konfigurationseinstellungen für den Aktivierungsdienst der benannten Pipes an, der die Lebensdauer der Verbindung der benannten Pipes verwaltet und Aktivierungsanforderungen verarbeitet, die über benannte Pipes eintreffen.</span><span class="sxs-lookup"><span data-stu-id="eb9e8-103">Specifies configuration settings for the Named Pipe Activation Service, which manages the lifetime of the named pipe connection, and handles activation requests that arrive over named pipes.</span></span>  
  
 <span data-ttu-id="eb9e8-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="eb9e8-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="eb9e8-105">\<net.pipe></span><span class="sxs-lookup"><span data-stu-id="eb9e8-105">\<net.pipe></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb9e8-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb9e8-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <net.pipe maxPendingAccepts="Integer"
              maxPendingConnections="Integer"
              receiveTimeout="TimeSpan">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18" />
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19" />
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-20" />
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only) -->
        <add securityIdentifier="S-1-5-32-568" />
      </allowAccounts>
    </net.pipe>
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="eb9e8-107">Typ</span><span class="sxs-lookup"><span data-stu-id="eb9e8-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb9e8-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="eb9e8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="eb9e8-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eb9e8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb9e8-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="eb9e8-110">Attributes</span></span>  
  
|<span data-ttu-id="eb9e8-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="eb9e8-111">Attribute</span></span>|<span data-ttu-id="eb9e8-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb9e8-112">Description</span></span>|  
|---------------|-----------------|  
|`maxPendingAccepts`|<span data-ttu-id="eb9e8-113">Eine ganze Zahl, die den Höchstwert für ausstehende gleichzeitig annehmende Threads am überwachenden Endpunkt für den Freigabedienst festlegt.</span><span class="sxs-lookup"><span data-stu-id="eb9e8-113">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="eb9e8-114">Der Standardwert ist&amp;#160;2.</span><span class="sxs-lookup"><span data-stu-id="eb9e8-114">The default is 2.</span></span>|  
|`maxPendingConnections`|<span data-ttu-id="eb9e8-115">Eine ganze Zahl, die die maximale Anzahl von Verbindungen angibt, die auf eine Verteilung warten können.</span><span class="sxs-lookup"><span data-stu-id="eb9e8-115">An integer that specifies the maximum number of connections that can wait for dispatch.</span></span> <span data-ttu-id="eb9e8-116">Der Standard ist 100.</span><span class="sxs-lookup"><span data-stu-id="eb9e8-116">The default is 100.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="eb9e8-117">Eine <xref:System.TimeSpan>, die das Timeout für das Lesen der Rahmendaten und das Ausführen der Verbindungsverteilung der zugrunde liegenden Verbindungen angibt.</span><span class="sxs-lookup"><span data-stu-id="eb9e8-117">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="eb9e8-118">Der Standardwert ist "00:00:10".</span><span class="sxs-lookup"><span data-stu-id="eb9e8-118">The default is "00:00:10"</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eb9e8-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eb9e8-119">Child Elements</span></span>  
  
|<span data-ttu-id="eb9e8-120">Element</span><span class="sxs-lookup"><span data-stu-id="eb9e8-120">Element</span></span>|<span data-ttu-id="eb9e8-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb9e8-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb9e8-122">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="eb9e8-122">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="eb9e8-123">Eine Auflistung von Konfigurationselementen, enthalten eine `securityIdentifier` Attribut, um Benutzerkonten für Prozesse angeben, die WCF-Dienste hosten, und denen Verbindungszugriff auf den Freigabedienst gewährt wurde.</span><span class="sxs-lookup"><span data-stu-id="eb9e8-123">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eb9e8-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eb9e8-124">Parent Elements</span></span>  
  
|<span data-ttu-id="eb9e8-125">Element</span><span class="sxs-lookup"><span data-stu-id="eb9e8-125">Element</span></span>|<span data-ttu-id="eb9e8-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb9e8-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb9e8-127">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="eb9e8-127">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="eb9e8-128">Enthält Konfigurationseinstellungen für den Listenerprozess SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="eb9e8-128">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eb9e8-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb9e8-129">See also</span></span>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection>
