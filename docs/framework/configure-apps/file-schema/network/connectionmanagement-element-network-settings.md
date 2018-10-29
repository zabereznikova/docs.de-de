---
title: '&lt;ConnectionManagement&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement
- http://schemas.microsoft.com/.NetConfiguration/v2.0#connectionManagement
helpviewer_keywords:
- <connectionManagement> element
- connectionManagement element
ms.assetid: bedccaab-12a2-4511-8f67-e961f249aec6
ms.openlocfilehash: 7cc5f2a37c0520ee48a10afeb4b9bc83ffd61033
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2018
ms.locfileid: "50201542"
---
# <a name="ltconnectionmanagementgt-element-network-settings"></a><span data-ttu-id="a7762-102">&lt;ConnectionManagement&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a7762-102">&lt;connectionManagement&gt; Element (Network Settings)</span></span>
<span data-ttu-id="a7762-103">Gibt die maximale Anzahl von Verbindungen mit einem Netzwerkhost an.</span><span class="sxs-lookup"><span data-stu-id="a7762-103">Specifies the maximum number of connections to a network host.</span></span>  
  
 <span data-ttu-id="a7762-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a7762-104">\<configuration></span></span>  
<span data-ttu-id="a7762-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="a7762-105">\<system.net></span></span>  
<span data-ttu-id="a7762-106">\<ConnectionManagement ></span><span class="sxs-lookup"><span data-stu-id="a7762-106">\<connectionManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7762-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7762-107">Syntax</span></span>  
  
```xml  
<connectionManagement>   
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7762-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a7762-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a7762-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a7762-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7762-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="a7762-110">Attributes</span></span>  
 <span data-ttu-id="a7762-111">Keine</span><span class="sxs-lookup"><span data-stu-id="a7762-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a7762-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a7762-112">Child Elements</span></span>  
  
|<span data-ttu-id="a7762-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="a7762-113">**Element**</span></span>|<span data-ttu-id="a7762-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a7762-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a7762-115">add</span><span class="sxs-lookup"><span data-stu-id="a7762-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="a7762-116">Fügt der Verbindungsverwaltungsliste eine IP-Adresse oder einen DNS-Namen hinzu.</span><span class="sxs-lookup"><span data-stu-id="a7762-116">Adds an IP address or DNS name to the connection management list.</span></span>|  
|[<span data-ttu-id="a7762-117">clear</span><span class="sxs-lookup"><span data-stu-id="a7762-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="a7762-118">Löscht der Verbindungsverwaltungsliste an.</span><span class="sxs-lookup"><span data-stu-id="a7762-118">Clears the connection management list.</span></span>|  
|[<span data-ttu-id="a7762-119">remove</span><span class="sxs-lookup"><span data-stu-id="a7762-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="a7762-120">Entfernt aus der Verbindungsverwaltungsliste eine IP-Adresse oder DNS-Namen.</span><span class="sxs-lookup"><span data-stu-id="a7762-120">Removes an IP address or DNS name from the connection management list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a7762-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a7762-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a7762-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="a7762-122">**Element**</span></span>|<span data-ttu-id="a7762-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a7762-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a7762-124">System.NET</span><span class="sxs-lookup"><span data-stu-id="a7762-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="a7762-125">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a7762-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7762-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a7762-126">Remarks</span></span>  
 <span data-ttu-id="a7762-127">Die `connectionManagement` Element definiert die maximale Anzahl von Verbindungen mit einem Server oder eine Gruppe von Servern.</span><span class="sxs-lookup"><span data-stu-id="a7762-127">The `connectionManagement` element defines the maximum number of connections to a server or group of servers.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a7762-128">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="a7762-128">Configuration Files</span></span>  
 <span data-ttu-id="a7762-129">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a7762-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7762-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a7762-130">Example</span></span>  
 <span data-ttu-id="a7762-131">Im folgenden Beispiel wird eine Anwendung für die Verwendung von vier Verbindungen mit dem Server `www.contoso.com` und zwei Verbindungen mit allen anderen Servern.</span><span class="sxs-lookup"><span data-stu-id="a7762-131">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a7762-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7762-132">See Also</span></span>  
- <xref:System.Net.ServicePoint>  
- <xref:System.Net.ServicePointManager>  
- [<span data-ttu-id="a7762-133">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a7762-133">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
