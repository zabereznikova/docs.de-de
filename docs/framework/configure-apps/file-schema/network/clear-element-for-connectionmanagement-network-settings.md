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
ms.openlocfilehash: 446bec116118ee8b604ef3664a6eb0452e6d5a38
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91184104"
---
# <a name="clear-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="eab3d-102">\<clear>-Element für connectionManagement (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="eab3d-102">\<clear> Element for connectionManagement (Network Settings)</span></span>

<span data-ttu-id="eab3d-103">Löscht die Verbindungs Verwaltungsliste.</span><span class="sxs-lookup"><span data-stu-id="eab3d-103">Clears the connection management list.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="eab3d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eab3d-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eab3d-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="eab3d-105">Attributes and Elements</span></span>  

 <span data-ttu-id="eab3d-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eab3d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eab3d-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="eab3d-107">Attributes</span></span>  

 <span data-ttu-id="eab3d-108">Keine</span><span class="sxs-lookup"><span data-stu-id="eab3d-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="eab3d-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eab3d-109">Child Elements</span></span>  

 <span data-ttu-id="eab3d-110">Keine</span><span class="sxs-lookup"><span data-stu-id="eab3d-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eab3d-111">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eab3d-111">Parent Elements</span></span>  
  
|<span data-ttu-id="eab3d-112">**Element**</span><span class="sxs-lookup"><span data-stu-id="eab3d-112">**Element**</span></span>|<span data-ttu-id="eab3d-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="eab3d-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="eab3d-114">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="eab3d-114">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="eab3d-115">Gibt die maximale Anzahl von Verbindungen mit einem Netzwerkhost an.</span><span class="sxs-lookup"><span data-stu-id="eab3d-115">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eab3d-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="eab3d-116">Remarks</span></span>  

 <span data-ttu-id="eab3d-117">Das- `clear` Element löscht alle Einträge aus der Verbindungs Verwaltungsliste.</span><span class="sxs-lookup"><span data-stu-id="eab3d-117">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="eab3d-118">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="eab3d-118">Configuration Files</span></span>  

 <span data-ttu-id="eab3d-119">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eab3d-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eab3d-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eab3d-120">Example</span></span>  

 <span data-ttu-id="eab3d-121">Im folgenden Beispiel wird die Liste mit den Verbindungs Verwaltung gelöscht, und es werden neue Verbindungs Verwaltungs Einträge für den `www.contoso.com` -Server und alle anderen Netzwerk Hosts hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="eab3d-121">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="eab3d-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eab3d-122">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="eab3d-123">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="eab3d-123">Network Settings Schema</span></span>](index.md)
