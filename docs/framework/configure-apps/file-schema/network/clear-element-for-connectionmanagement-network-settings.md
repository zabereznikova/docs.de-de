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
ms.openlocfilehash: a76df48a9de084e1121a5e96b22edf7aa3acba23
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088485"
---
# <a name="clear-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="340ad-102">\<clear>-Element für connectionManagement (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="340ad-102">\<clear> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="340ad-103">Löscht die Verbindungs Verwaltungsliste.</span><span class="sxs-lookup"><span data-stu-id="340ad-103">Clears the connection management list.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="340ad-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="340ad-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="340ad-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="340ad-105">Attributes and Elements</span></span>  
 <span data-ttu-id="340ad-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="340ad-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="340ad-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="340ad-107">Attributes</span></span>  
 <span data-ttu-id="340ad-108">Keine</span><span class="sxs-lookup"><span data-stu-id="340ad-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="340ad-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="340ad-109">Child Elements</span></span>  
 <span data-ttu-id="340ad-110">Keine.</span><span class="sxs-lookup"><span data-stu-id="340ad-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="340ad-111">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="340ad-111">Parent Elements</span></span>  
  
|<span data-ttu-id="340ad-112">**Element**</span><span class="sxs-lookup"><span data-stu-id="340ad-112">**Element**</span></span>|<span data-ttu-id="340ad-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="340ad-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="340ad-114">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="340ad-114">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="340ad-115">Gibt die maximale Anzahl von Verbindungen mit einem Netzwerkhost an.</span><span class="sxs-lookup"><span data-stu-id="340ad-115">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="340ad-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="340ad-116">Remarks</span></span>  
 <span data-ttu-id="340ad-117">Das- `clear` Element löscht alle Einträge aus der Verbindungs Verwaltungsliste.</span><span class="sxs-lookup"><span data-stu-id="340ad-117">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="340ad-118">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="340ad-118">Configuration Files</span></span>  
 <span data-ttu-id="340ad-119">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="340ad-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="340ad-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="340ad-120">Example</span></span>  
 <span data-ttu-id="340ad-121">Im folgenden Beispiel wird die Liste mit den Verbindungs Verwaltung gelöscht, und es werden neue Verbindungs Verwaltungs Einträge für den `www.contoso.com` -Server und alle anderen Netzwerk Hosts hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="340ad-121">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="340ad-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="340ad-122">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="340ad-123">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="340ad-123">Network Settings Schema</span></span>](index.md)
