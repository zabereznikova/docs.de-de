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
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 1736dd8fcb308bceee5f100149919ff9ec45510d
ms.sourcegitcommit: d88024e6d6d8b242feae5f4007a709379355aa24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2018
ms.locfileid: "49316323"
---
# <a name="ltconnectionmanagementgt-element-network-settings"></a><span data-ttu-id="8eccd-102">&lt;ConnectionManagement&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="8eccd-102">&lt;connectionManagement&gt; Element (Network Settings)</span></span>
<span data-ttu-id="8eccd-103">Gibt die maximale Anzahl von Verbindungen mit einem Netzwerkhost an.</span><span class="sxs-lookup"><span data-stu-id="8eccd-103">Specifies the maximum number of connections to a network host.</span></span>  
  
 <span data-ttu-id="8eccd-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8eccd-104">\<configuration></span></span>  
<span data-ttu-id="8eccd-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="8eccd-105">\<system.net></span></span>  
<span data-ttu-id="8eccd-106">\<ConnectionManagement ></span><span class="sxs-lookup"><span data-stu-id="8eccd-106">\<connectionManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8eccd-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="8eccd-107">Syntax</span></span>  
  
```xml  
<connectionManagement>   
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8eccd-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8eccd-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8eccd-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8eccd-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8eccd-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="8eccd-110">Attributes</span></span>  
 <span data-ttu-id="8eccd-111">Keine</span><span class="sxs-lookup"><span data-stu-id="8eccd-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8eccd-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8eccd-112">Child Elements</span></span>  
  
|<span data-ttu-id="8eccd-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="8eccd-113">**Element**</span></span>|<span data-ttu-id="8eccd-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="8eccd-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8eccd-115">add</span><span class="sxs-lookup"><span data-stu-id="8eccd-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="8eccd-116">Fügt der Verbindungsverwaltungsliste eine IP-Adresse oder einen DNS-Namen hinzu.</span><span class="sxs-lookup"><span data-stu-id="8eccd-116">Adds an IP address or DNS name to the connection management list.</span></span>|  
|[<span data-ttu-id="8eccd-117">clear</span><span class="sxs-lookup"><span data-stu-id="8eccd-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="8eccd-118">Löscht der Verbindungsverwaltungsliste an.</span><span class="sxs-lookup"><span data-stu-id="8eccd-118">Clears the connection management list.</span></span>|  
|[<span data-ttu-id="8eccd-119">remove</span><span class="sxs-lookup"><span data-stu-id="8eccd-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="8eccd-120">Entfernt aus der Verbindungsverwaltungsliste eine IP-Adresse oder DNS-Namen.</span><span class="sxs-lookup"><span data-stu-id="8eccd-120">Removes an IP address or DNS name from the connection management list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8eccd-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8eccd-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8eccd-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="8eccd-122">**Element**</span></span>|<span data-ttu-id="8eccd-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="8eccd-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8eccd-124">System.NET</span><span class="sxs-lookup"><span data-stu-id="8eccd-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="8eccd-125">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8eccd-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8eccd-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8eccd-126">Remarks</span></span>  
 <span data-ttu-id="8eccd-127">Die `connectionManagement` Element definiert die maximale Anzahl von Verbindungen mit einem Server oder eine Gruppe von Servern.</span><span class="sxs-lookup"><span data-stu-id="8eccd-127">The `connectionManagement` element defines the maximum number of connections to a server or group of servers.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8eccd-128">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="8eccd-128">Configuration Files</span></span>  
 <span data-ttu-id="8eccd-129">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8eccd-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8eccd-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8eccd-130">Example</span></span>  
 <span data-ttu-id="8eccd-131">Im folgenden Beispiel wird eine Anwendung für die Verwendung von vier Verbindungen mit dem Server `www.contoso.com` und zwei Verbindungen mit allen anderen Servern.</span><span class="sxs-lookup"><span data-stu-id="8eccd-131">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8eccd-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8eccd-132">See Also</span></span>  
 <xref:System.Net.ServicePoint>  
 <xref:System.Net.ServicePointManager>  
 [<span data-ttu-id="8eccd-133">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="8eccd-133">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
