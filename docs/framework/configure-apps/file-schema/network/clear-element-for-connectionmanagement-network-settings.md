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
manager: markl
ms.openlocfilehash: 5bcd17cfe1f3bd7531453b62552a4907df5b96bc
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltcleargt-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="ec48b-102">&lt;Deaktivieren Sie&gt; -Element für ConnectionManagement (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ec48b-102">&lt;clear&gt; Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="ec48b-103">Löscht die Verbindungsverwaltungsliste.</span><span class="sxs-lookup"><span data-stu-id="ec48b-103">Clears the connection management list.</span></span>  
  
 <span data-ttu-id="ec48b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ec48b-104">\<configuration></span></span>  
<span data-ttu-id="ec48b-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="ec48b-105">\<system.net></span></span>  
<span data-ttu-id="ec48b-106">\<ConnectionManagement ></span><span class="sxs-lookup"><span data-stu-id="ec48b-106">\<connectionManagement></span></span>  
<span data-ttu-id="ec48b-107">\<Deaktivieren Sie ></span><span class="sxs-lookup"><span data-stu-id="ec48b-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec48b-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec48b-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec48b-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ec48b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ec48b-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ec48b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec48b-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="ec48b-111">Attributes</span></span>  
 <span data-ttu-id="ec48b-112">Keine</span><span class="sxs-lookup"><span data-stu-id="ec48b-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ec48b-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ec48b-113">Child Elements</span></span>  
 <span data-ttu-id="ec48b-114">Keine</span><span class="sxs-lookup"><span data-stu-id="ec48b-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ec48b-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ec48b-115">Parent Elements</span></span>  
  
|<span data-ttu-id="ec48b-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="ec48b-116">**Element**</span></span>|<span data-ttu-id="ec48b-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ec48b-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ec48b-118">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="ec48b-118">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="ec48b-119">Gibt die maximale Anzahl von Verbindungen mit einem Netzwerkhost an.</span><span class="sxs-lookup"><span data-stu-id="ec48b-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec48b-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ec48b-120">Remarks</span></span>  
 <span data-ttu-id="ec48b-121">Die `clear` -Element löscht alle Einträge aus der Verbindungsverwaltungsliste.</span><span class="sxs-lookup"><span data-stu-id="ec48b-121">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ec48b-122">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="ec48b-122">Configuration Files</span></span>  
 <span data-ttu-id="ec48b-123">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ec48b-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec48b-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ec48b-124">Example</span></span>  
 <span data-ttu-id="ec48b-125">Im folgenden Beispiel löscht die Verbindungsverwaltungsliste und fügt dann die neue Verbindung Management-Einträge für den Server www.contoso.com und alle anderen Netzwerkhosts hinzu.</span><span class="sxs-lookup"><span data-stu-id="ec48b-125">The following example clears the connection management list and then adds new connection management entries for the server www.contoso.com and all other network hosts.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ec48b-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec48b-126">See Also</span></span>  
 <xref:System.Net.ServicePoint>  
 <xref:System.Net.ServicePointManager>  
 [<span data-ttu-id="ec48b-127">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ec48b-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
