---
title: <clear> -Element für ConnectionManagement (Netzwerkeinstellungen)
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
ms.openlocfilehash: 733c70b0575de7e2635afaab58ad48591f035fc0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124994"
---
# <a name="clear-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="56131-102">\<clear >-Element für ConnectionManagement (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="56131-102">\<clear> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="56131-103">Löscht der Verbindungsverwaltungsliste an.</span><span class="sxs-lookup"><span data-stu-id="56131-103">Clears the connection management list.</span></span>  
  
 <span data-ttu-id="56131-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="56131-104">\<configuration></span></span>  
<span data-ttu-id="56131-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="56131-105">\<system.net></span></span>  
<span data-ttu-id="56131-106">\<connectionManagement></span><span class="sxs-lookup"><span data-stu-id="56131-106">\<connectionManagement></span></span>  
<span data-ttu-id="56131-107">\<clear></span><span class="sxs-lookup"><span data-stu-id="56131-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56131-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="56131-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56131-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="56131-109">Attributes and Elements</span></span>  
 <span data-ttu-id="56131-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="56131-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56131-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="56131-111">Attributes</span></span>  
 <span data-ttu-id="56131-112">Keine</span><span class="sxs-lookup"><span data-stu-id="56131-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="56131-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="56131-113">Child Elements</span></span>  
 <span data-ttu-id="56131-114">Keine</span><span class="sxs-lookup"><span data-stu-id="56131-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="56131-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="56131-115">Parent Elements</span></span>  
  
|**<span data-ttu-id="56131-116">Element</span><span class="sxs-lookup"><span data-stu-id="56131-116">Element</span></span>**|**<span data-ttu-id="56131-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="56131-117">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="56131-118">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="56131-118">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="56131-119">Gibt die maximale Anzahl von Verbindungen mit einem Netzwerkhost an.</span><span class="sxs-lookup"><span data-stu-id="56131-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56131-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="56131-120">Remarks</span></span>  
 <span data-ttu-id="56131-121">Die `clear` Element löscht alle Einträge aus der Verbindungsverwaltungsliste.</span><span class="sxs-lookup"><span data-stu-id="56131-121">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="56131-122">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="56131-122">Configuration Files</span></span>  
 <span data-ttu-id="56131-123">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="56131-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="56131-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="56131-124">Example</span></span>  
 <span data-ttu-id="56131-125">Im folgenden Beispiel löscht der Verbindungsverwaltungsliste und fügt dann die neue Verbindung Management-Einträge für den Server `www.contoso.com` und alle anderen Netzwerkhosts.</span><span class="sxs-lookup"><span data-stu-id="56131-125">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="56131-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56131-126">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="56131-127">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="56131-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
