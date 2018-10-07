---
title: '&lt;Deaktivieren Sie&gt; -Element für ConnectionManagement (Netzwerkeinstellungen)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, connectionManagement
- connectionManagement, clear element
- clear element, connectionManagement
- <connectionManagement>, clear element
ms.assetid: fb259282-84c4-4dc4-a226-78d904a6edc3
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 9542332085d0b0319c55db63fd98c9dd8eb3f576
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2018
ms.locfileid: "48839467"
---
# <a name="ltcleargt-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="35ed8-102">&lt;Deaktivieren Sie&gt; -Element für ConnectionManagement (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="35ed8-102">&lt;clear&gt; Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="35ed8-103">Löscht der Verbindungsverwaltungsliste an.</span><span class="sxs-lookup"><span data-stu-id="35ed8-103">Clears the connection management list.</span></span>  
  
 <span data-ttu-id="35ed8-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="35ed8-104">\<configuration></span></span>  
<span data-ttu-id="35ed8-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="35ed8-105">\<system.net></span></span>  
<span data-ttu-id="35ed8-106">\<ConnectionManagement ></span><span class="sxs-lookup"><span data-stu-id="35ed8-106">\<connectionManagement></span></span>  
<span data-ttu-id="35ed8-107">\<Deaktivieren Sie ></span><span class="sxs-lookup"><span data-stu-id="35ed8-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35ed8-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="35ed8-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35ed8-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="35ed8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="35ed8-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="35ed8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35ed8-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="35ed8-111">Attributes</span></span>  
 <span data-ttu-id="35ed8-112">Keine</span><span class="sxs-lookup"><span data-stu-id="35ed8-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="35ed8-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="35ed8-113">Child Elements</span></span>  
 <span data-ttu-id="35ed8-114">Keine</span><span class="sxs-lookup"><span data-stu-id="35ed8-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="35ed8-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="35ed8-115">Parent Elements</span></span>  
  
|<span data-ttu-id="35ed8-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="35ed8-116">**Element**</span></span>|<span data-ttu-id="35ed8-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="35ed8-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="35ed8-118">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="35ed8-118">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="35ed8-119">Gibt die maximale Anzahl von Verbindungen mit einem Netzwerkhost an.</span><span class="sxs-lookup"><span data-stu-id="35ed8-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35ed8-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="35ed8-120">Remarks</span></span>  
 <span data-ttu-id="35ed8-121">Die `clear` Element löscht alle Einträge aus der Verbindungsverwaltungsliste.</span><span class="sxs-lookup"><span data-stu-id="35ed8-121">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="35ed8-122">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="35ed8-122">Configuration Files</span></span>  
 <span data-ttu-id="35ed8-123">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="35ed8-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="35ed8-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="35ed8-124">Example</span></span>  
 <span data-ttu-id="35ed8-125">Das folgende Beispiel löscht der Verbindungsverwaltungsliste und fügt dann die neue Verbindung Management-Einträge für den Server www.contoso.com und alle anderen Netzwerkhosts hinzu.</span><span class="sxs-lookup"><span data-stu-id="35ed8-125">The following example clears the connection management list and then adds new connection management entries for the server www.contoso.com and all other network hosts.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <clear/>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="35ed8-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35ed8-126">See Also</span></span>  
 <xref:System.Net.ServicePoint>  
 <xref:System.Net.ServicePointManager>  
 [<span data-ttu-id="35ed8-127">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="35ed8-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
