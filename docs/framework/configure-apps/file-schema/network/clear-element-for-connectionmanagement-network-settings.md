---
title: <clear>-Element für connectionManagement (Netzwerkeinstellungen)
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
ms.openlocfilehash: 86a7a0ab402c8c40ec3b824402a1dba984412b68
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659447"
---
# <a name="clear-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="8a758-102">\<Löschen von >-Element für connectionManagement (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="8a758-102">\<clear> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="8a758-103">Löscht die Verbindungs Verwaltungsliste.</span><span class="sxs-lookup"><span data-stu-id="8a758-103">Clears the connection management list.</span></span>  
  
 <span data-ttu-id="8a758-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8a758-104">\<configuration></span></span>  
<span data-ttu-id="8a758-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="8a758-105">\<system.net></span></span>  
<span data-ttu-id="8a758-106">\<connectionManagement></span><span class="sxs-lookup"><span data-stu-id="8a758-106">\<connectionManagement></span></span>  
<span data-ttu-id="8a758-107">\<clear></span><span class="sxs-lookup"><span data-stu-id="8a758-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a758-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a758-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a758-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8a758-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8a758-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8a758-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a758-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="8a758-111">Attributes</span></span>  
 <span data-ttu-id="8a758-112">Keine</span><span class="sxs-lookup"><span data-stu-id="8a758-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8a758-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8a758-113">Child Elements</span></span>  
 <span data-ttu-id="8a758-114">Keine</span><span class="sxs-lookup"><span data-stu-id="8a758-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8a758-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8a758-115">Parent Elements</span></span>  
  
|<span data-ttu-id="8a758-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="8a758-116">**Element**</span></span>|<span data-ttu-id="8a758-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="8a758-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8a758-118">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="8a758-118">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="8a758-119">Gibt die maximale Anzahl von Verbindungen mit einem Netzwerkhost an.</span><span class="sxs-lookup"><span data-stu-id="8a758-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a758-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8a758-120">Remarks</span></span>  
 <span data-ttu-id="8a758-121">Das `clear` -Element löscht alle Einträge aus der Verbindungs Verwaltungsliste.</span><span class="sxs-lookup"><span data-stu-id="8a758-121">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8a758-122">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="8a758-122">Configuration Files</span></span>  
 <span data-ttu-id="8a758-123">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8a758-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a758-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8a758-124">Example</span></span>  
 <span data-ttu-id="8a758-125">Im folgenden Beispiel wird die Liste mit den Verbindungs Verwaltung gelöscht, und es werden neue Verbindungs Verwaltungs `www.contoso.com` Einträge für den-Server und alle anderen Netzwerk Hosts hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8a758-125">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8a758-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a758-126">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="8a758-127">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="8a758-127">Network Settings Schema</span></span>](index.md)
