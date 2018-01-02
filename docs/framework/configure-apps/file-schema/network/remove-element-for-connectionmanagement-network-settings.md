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
ms.workload: dotnet
ms.openlocfilehash: 947150ce0ff9a5ec5fa87fef8c2e24f3ebf6b4cb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltremovegt-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="c1017-102">&lt;Entfernen Sie&gt; -Element für ConnectionManagement (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c1017-102">&lt;remove&gt; Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="c1017-103">Entfernt aus der Verbindungsverwaltungsliste eine IP-Adresse oder einen DNS-Namen.</span><span class="sxs-lookup"><span data-stu-id="c1017-103">Removes an IP address or DNS name from the connection management list.</span></span>  
  
 <span data-ttu-id="c1017-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c1017-104">\<configuration></span></span>  
<span data-ttu-id="c1017-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="c1017-105">\<system.net></span></span>  
<span data-ttu-id="c1017-106">\<ConnectionManagement ></span><span class="sxs-lookup"><span data-stu-id="c1017-106">\<connectionManagement></span></span>  
<span data-ttu-id="c1017-107">\<Entfernen ></span><span class="sxs-lookup"><span data-stu-id="c1017-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1017-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1017-108">Syntax</span></span>  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1017-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c1017-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c1017-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c1017-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1017-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="c1017-111">Attributes</span></span>  
  
|<span data-ttu-id="c1017-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="c1017-112">**Attribute**</span></span>|<span data-ttu-id="c1017-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c1017-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="c1017-114">Eine IP-Adresse oder DNS-Name.</span><span class="sxs-lookup"><span data-stu-id="c1017-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c1017-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1017-115">Child Elements</span></span>  
 <span data-ttu-id="c1017-116">Keine</span><span class="sxs-lookup"><span data-stu-id="c1017-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c1017-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1017-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c1017-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="c1017-118">**Element**</span></span>|<span data-ttu-id="c1017-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c1017-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c1017-120">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="c1017-120">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="c1017-121">Gibt die maximale Anzahl von Verbindungen mit einem Netzwerkhost an.</span><span class="sxs-lookup"><span data-stu-id="c1017-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1017-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c1017-122">Remarks</span></span>  
 <span data-ttu-id="c1017-123">Die `remove` Element entfernt den Verbindungs-Eintrag für den angegebenen Server.</span><span class="sxs-lookup"><span data-stu-id="c1017-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="c1017-124">Der Wert, der die `address` Attribut muss einen gültigen Namen von IP-Adresse oder den Hostnamen.</span><span class="sxs-lookup"><span data-stu-id="c1017-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c1017-125">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="c1017-125">Configuration Files</span></span>  
 <span data-ttu-id="c1017-126">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c1017-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1017-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c1017-127">Example</span></span>  
 <span data-ttu-id="c1017-128">Im folgenden Beispiel entfernt alle Einträge Verbindung Management Liste, für den Server www.adventure-works.com und anschließend die Anwendung für die Verwendung von vier Verbindungen mit dem Server www.contoso.com und zwei Verbindungen mit allen anderen Servern konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="c1017-128">The following example removes any connection management list entries for the server www.adventure-works.com and then configures an application to use four connections to the server www.contoso.com and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c1017-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1017-129">See Also</span></span>  
 <xref:System.Net.ServicePoint>  
 <xref:System.Net.ServicePointManager>  
 [<span data-ttu-id="c1017-130">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c1017-130">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
