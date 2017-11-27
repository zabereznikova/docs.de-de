---
title: "&lt;Entfernen Sie&gt; -Element für ConnectionManagement (Netzwerkeinstellungen)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- connectionManagement, remove element
- <remove> element, connectionManagement
- <connectionManagement>, remove element
- remove element, connectionManagement
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 92536ad7605211f3a7f606920b054a217427c8f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltremovegt-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="984bd-102">&lt;Entfernen Sie&gt; -Element für ConnectionManagement (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="984bd-102">&lt;remove&gt; Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="984bd-103">Entfernt aus der Verbindungsverwaltungsliste eine IP-Adresse oder einen DNS-Namen.</span><span class="sxs-lookup"><span data-stu-id="984bd-103">Removes an IP address or DNS name from the connection management list.</span></span>  
  
 <span data-ttu-id="984bd-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="984bd-104">\<configuration></span></span>  
<span data-ttu-id="984bd-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="984bd-105">\<system.net></span></span>  
<span data-ttu-id="984bd-106">\<ConnectionManagement ></span><span class="sxs-lookup"><span data-stu-id="984bd-106">\<connectionManagement></span></span>  
<span data-ttu-id="984bd-107">\<Entfernen ></span><span class="sxs-lookup"><span data-stu-id="984bd-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="984bd-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="984bd-108">Syntax</span></span>  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="984bd-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="984bd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="984bd-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="984bd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="984bd-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="984bd-111">Attributes</span></span>  
  
|<span data-ttu-id="984bd-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="984bd-112">**Attribute**</span></span>|<span data-ttu-id="984bd-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="984bd-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="984bd-114">Eine IP-Adresse oder DNS-Name.</span><span class="sxs-lookup"><span data-stu-id="984bd-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="984bd-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="984bd-115">Child Elements</span></span>  
 <span data-ttu-id="984bd-116">Keine</span><span class="sxs-lookup"><span data-stu-id="984bd-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="984bd-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="984bd-117">Parent Elements</span></span>  
  
|<span data-ttu-id="984bd-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="984bd-118">**Element**</span></span>|<span data-ttu-id="984bd-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="984bd-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="984bd-120">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="984bd-120">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="984bd-121">Gibt die maximale Anzahl von Verbindungen mit einem Netzwerkhost an.</span><span class="sxs-lookup"><span data-stu-id="984bd-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="984bd-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="984bd-122">Remarks</span></span>  
 <span data-ttu-id="984bd-123">Die `remove` Element entfernt den Verbindungs-Eintrag für den angegebenen Server.</span><span class="sxs-lookup"><span data-stu-id="984bd-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="984bd-124">Der Wert, der die `address` Attribut muss einen gültigen Namen von IP-Adresse oder den Hostnamen.</span><span class="sxs-lookup"><span data-stu-id="984bd-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="984bd-125">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="984bd-125">Configuration Files</span></span>  
 <span data-ttu-id="984bd-126">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="984bd-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="984bd-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="984bd-127">Example</span></span>  
 <span data-ttu-id="984bd-128">Im folgenden Beispiel entfernt alle Einträge Verbindung Management Liste, für den Server www.adventure-works.com und anschließend die Anwendung für die Verwendung von vier Verbindungen mit dem Server www.contoso.com und zwei Verbindungen mit allen anderen Servern konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="984bd-128">The following example removes any connection management list entries for the server www.adventure-works.com and then configures an application to use four connections to the server www.contoso.com and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <remove address="http://www.adventure-works.com" />  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="984bd-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="984bd-129">See Also</span></span>  
 <xref:System.Net.ServicePoint>  
 <xref:System.Net.ServicePointManager>  
 [<span data-ttu-id="984bd-130">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="984bd-130">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
