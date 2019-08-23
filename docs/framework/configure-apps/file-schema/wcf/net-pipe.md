---
title: <net.pipe>
ms.date: 03/30/2017
ms.assetid: 6a0f0318-f8f6-466c-9fae-199d7274a82e
ms.openlocfilehash: 7d868d84318db8c9fe188293154dc275060a3952
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933181"
---
# <a name="netpipe"></a><span data-ttu-id="40c1c-102">\<net.pipe></span><span class="sxs-lookup"><span data-stu-id="40c1c-102">\<net.pipe></span></span>
<span data-ttu-id="40c1c-103">Gibt Konfigurationseinstellungen für den Aktivierungsdienst der benannten Pipes an, der die Lebensdauer der Verbindung der benannten Pipes verwaltet und Aktivierungsanforderungen verarbeitet, die über benannte Pipes eintreffen.</span><span class="sxs-lookup"><span data-stu-id="40c1c-103">Specifies configuration settings for the Named Pipe Activation Service, which manages the lifetime of the named pipe connection, and handles activation requests that arrive over named pipes.</span></span>  
  
 <span data-ttu-id="40c1c-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="40c1c-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="40c1c-105">\<net.pipe></span><span class="sxs-lookup"><span data-stu-id="40c1c-105">\<net.pipe></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40c1c-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="40c1c-106">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="40c1c-107">Typ</span><span class="sxs-lookup"><span data-stu-id="40c1c-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40c1c-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="40c1c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="40c1c-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="40c1c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40c1c-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="40c1c-110">Attributes</span></span>  
  
|<span data-ttu-id="40c1c-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="40c1c-111">Attribute</span></span>|<span data-ttu-id="40c1c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="40c1c-112">Description</span></span>|  
|---------------|-----------------|  
|`maxPendingAccepts`|<span data-ttu-id="40c1c-113">Eine ganze Zahl, die den Höchstwert für ausstehende gleichzeitig annehmende Threads am überwachenden Endpunkt für den Freigabedienst festlegt.</span><span class="sxs-lookup"><span data-stu-id="40c1c-113">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="40c1c-114">Der Standardwert ist&#160;2.</span><span class="sxs-lookup"><span data-stu-id="40c1c-114">The default is 2.</span></span>|  
|`maxPendingConnections`|<span data-ttu-id="40c1c-115">Eine ganze Zahl, die die maximale Anzahl von Verbindungen angibt, die auf eine Verteilung warten können.</span><span class="sxs-lookup"><span data-stu-id="40c1c-115">An integer that specifies the maximum number of connections that can wait for dispatch.</span></span> <span data-ttu-id="40c1c-116">Der Standard ist 100.</span><span class="sxs-lookup"><span data-stu-id="40c1c-116">The default is 100.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="40c1c-117">Eine <xref:System.TimeSpan>, die das Timeout für das Lesen der Rahmendaten und das Ausführen der Verbindungsverteilung der zugrunde liegenden Verbindungen angibt.</span><span class="sxs-lookup"><span data-stu-id="40c1c-117">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="40c1c-118">Der Standardwert ist "00:00:10".</span><span class="sxs-lookup"><span data-stu-id="40c1c-118">The default is "00:00:10"</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40c1c-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="40c1c-119">Child Elements</span></span>  
  
|<span data-ttu-id="40c1c-120">Element</span><span class="sxs-lookup"><span data-stu-id="40c1c-120">Element</span></span>|<span data-ttu-id="40c1c-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="40c1c-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40c1c-122">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="40c1c-122">\<allowAccounts></span></span>](allowaccounts.md)|<span data-ttu-id="40c1c-123">Eine Auflistung von Konfigurationselementen, die ein `securityIdentifier` -Attribut zum Angeben von Benutzerkonten für Prozesse enthalten, die WCF-Dienste hosten und Verbindungs Zugriff auf den Freigabe Dienst erhalten.</span><span class="sxs-lookup"><span data-stu-id="40c1c-123">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="40c1c-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="40c1c-124">Parent Elements</span></span>  
  
|<span data-ttu-id="40c1c-125">Element</span><span class="sxs-lookup"><span data-stu-id="40c1c-125">Element</span></span>|<span data-ttu-id="40c1c-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="40c1c-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40c1c-127">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="40c1c-127">\<system.serviceModel.activation></span></span>](system-servicemodel-activation.md)|<span data-ttu-id="40c1c-128">Enthält Konfigurationseinstellungen für den Listenerprozess SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="40c1c-128">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="40c1c-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40c1c-129">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection>
