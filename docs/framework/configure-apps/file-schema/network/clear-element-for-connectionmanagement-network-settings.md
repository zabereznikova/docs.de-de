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
ms.openlocfilehash: 17b380b12977423669fd413132d69a3082daca41
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698360"
---
# <a name="clear-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="b0d49-102">\<clear >-Element für connectionManagement (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b0d49-102">\<clear> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="b0d49-103">Löscht die Verbindungs Verwaltungsliste.</span><span class="sxs-lookup"><span data-stu-id="b0d49-103">Clears the connection management list.</span></span>  
  
[<span data-ttu-id="b0d49-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="b0d49-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="b0d49-105">&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b0d49-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="b0d49-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<connectionmanagement >** ](connectionmanagement-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b0d49-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)</span></span>  
<span data-ttu-id="b0d49-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="b0d49-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0d49-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="b0d49-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0d49-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b0d49-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b0d49-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b0d49-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0d49-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="b0d49-111">Attributes</span></span>  
 <span data-ttu-id="b0d49-112">Keine</span><span class="sxs-lookup"><span data-stu-id="b0d49-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b0d49-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b0d49-113">Child Elements</span></span>  
 <span data-ttu-id="b0d49-114">Keine</span><span class="sxs-lookup"><span data-stu-id="b0d49-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b0d49-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b0d49-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b0d49-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="b0d49-116">**Element**</span></span>|<span data-ttu-id="b0d49-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b0d49-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b0d49-118">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="b0d49-118">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="b0d49-119">Gibt die maximale Anzahl von Verbindungen mit einem Netzwerkhost an.</span><span class="sxs-lookup"><span data-stu-id="b0d49-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0d49-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b0d49-120">Remarks</span></span>  
 <span data-ttu-id="b0d49-121">Das `clear`-Element löscht alle Einträge aus der Verbindungs Verwaltungsliste.</span><span class="sxs-lookup"><span data-stu-id="b0d49-121">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b0d49-122">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="b0d49-122">Configuration Files</span></span>  
 <span data-ttu-id="b0d49-123">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b0d49-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0d49-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b0d49-124">Example</span></span>  
 <span data-ttu-id="b0d49-125">Im folgenden Beispiel wird die Liste mit den Verbindungs Verwaltung gelöscht, und es werden neue Verbindungs Verwaltungs Einträge für den Server `www.contoso.com` und alle anderen Netzwerk Hosts hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b0d49-125">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b0d49-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0d49-126">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="b0d49-127">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b0d49-127">Network Settings Schema</span></span>](index.md)
