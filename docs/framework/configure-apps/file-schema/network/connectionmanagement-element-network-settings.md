---
title: <connectionManagement>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement
- http://schemas.microsoft.com/.NetConfiguration/v2.0#connectionManagement
helpviewer_keywords:
- <connectionManagement> element
- connectionManagement element
ms.assetid: bedccaab-12a2-4511-8f67-e961f249aec6
ms.openlocfilehash: 9f1e382bbbaad2cb95e2c33bbbdfb4c505378c9e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154893"
---
# <a name="connectionmanagement-element-network-settings"></a><span data-ttu-id="a0d07-102">\<connectionManagement>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a0d07-102">\<connectionManagement> Element (Network Settings)</span></span>
<span data-ttu-id="a0d07-103">Gibt die maximale Anzahl von Verbindungen mit einem Netzwerkhost an.</span><span class="sxs-lookup"><span data-stu-id="a0d07-103">Specifies the maximum number of connections to a network host.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionManagement>**

## <a name="syntax"></a><span data-ttu-id="a0d07-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0d07-104">Syntax</span></span>  
  
```xml  
<connectionManagement>
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0d07-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a0d07-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a0d07-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a0d07-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0d07-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="a0d07-107">Attributes</span></span>  
 <span data-ttu-id="a0d07-108">Keine</span><span class="sxs-lookup"><span data-stu-id="a0d07-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a0d07-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a0d07-109">Child Elements</span></span>  
  
|<span data-ttu-id="a0d07-110">**Element**</span><span class="sxs-lookup"><span data-stu-id="a0d07-110">**Element**</span></span>|<span data-ttu-id="a0d07-111">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a0d07-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a0d07-112">add</span><span class="sxs-lookup"><span data-stu-id="a0d07-112">add</span></span>](add-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="a0d07-113">Fügt der Verbindungsverwaltungsliste eine IP-Adresse oder einen DNS-Namen hinzu.</span><span class="sxs-lookup"><span data-stu-id="a0d07-113">Adds an IP address or DNS name to the connection management list.</span></span>|  
|[<span data-ttu-id="a0d07-114">Löschen</span><span class="sxs-lookup"><span data-stu-id="a0d07-114">clear</span></span>](clear-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="a0d07-115">Löscht die Verbindungs Verwaltungsliste.</span><span class="sxs-lookup"><span data-stu-id="a0d07-115">Clears the connection management list.</span></span>|  
|[<span data-ttu-id="a0d07-116">remove</span><span class="sxs-lookup"><span data-stu-id="a0d07-116">remove</span></span>](remove-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="a0d07-117">Entfernt eine IP-Adresse oder einen DNS-Namen aus der Verbindungs Verwaltungsliste.</span><span class="sxs-lookup"><span data-stu-id="a0d07-117">Removes an IP address or DNS name from the connection management list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a0d07-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a0d07-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a0d07-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="a0d07-119">**Element**</span></span>|<span data-ttu-id="a0d07-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a0d07-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a0d07-121">system.net</span><span class="sxs-lookup"><span data-stu-id="a0d07-121">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="a0d07-122">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a0d07-122">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0d07-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a0d07-123">Remarks</span></span>  
 <span data-ttu-id="a0d07-124">Das- `connectionManagement` Element definiert die maximale Anzahl von Verbindungen mit einem Server oder einer Gruppe von Servern.</span><span class="sxs-lookup"><span data-stu-id="a0d07-124">The `connectionManagement` element defines the maximum number of connections to a server or group of servers.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a0d07-125">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="a0d07-125">Configuration Files</span></span>  
 <span data-ttu-id="a0d07-126">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0d07-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0d07-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a0d07-127">Example</span></span>  
 <span data-ttu-id="a0d07-128">Im folgenden Beispiel wird eine Anwendung so konfiguriert, dass vier Verbindungen mit dem Server `www.contoso.com` und zwei Verbindungen mit allen anderen Servern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0d07-128">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a0d07-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a0d07-129">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="a0d07-130">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="a0d07-130">Network Settings Schema</span></span>](index.md)
