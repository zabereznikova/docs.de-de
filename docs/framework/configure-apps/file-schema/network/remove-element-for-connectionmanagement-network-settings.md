---
title: <remove>-Element für connectionManagement (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- connectionManagement, remove element
- <remove> element, connectionManagement
- <connectionManagement>, remove element
- remove element, connectionManagement
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
ms.openlocfilehash: 39ce85c3c15a2d4bdfce801a35e9ca088bd5091b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154737"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="0cb58-102">\<Entfernen> Element für ConnectionManagement (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="0cb58-102">\<remove> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="0cb58-103">Entfernt eine IP-Adresse oder einen DNS-Namen aus der Verbindungsverwaltungsliste.</span><span class="sxs-lookup"><span data-stu-id="0cb58-103">Removes an IP address or DNS name from the connection management list.</span></span>  

<span data-ttu-id="0cb58-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0cb58-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0cb58-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="0cb58-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="0cb58-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="0cb58-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)</span></span>\
<span data-ttu-id="0cb58-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<entfernen sie>**</span><span class="sxs-lookup"><span data-stu-id="0cb58-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="0cb58-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="0cb58-108">Syntax</span></span>  
  
```xml  
<remove
  address="server name or IP address"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0cb58-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0cb58-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0cb58-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0cb58-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0cb58-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="0cb58-111">Attributes</span></span>  
  
|<span data-ttu-id="0cb58-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="0cb58-112">**Attribute**</span></span>|<span data-ttu-id="0cb58-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="0cb58-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="0cb58-114">Eine IP-Adresse oder ein DNS-Name.</span><span class="sxs-lookup"><span data-stu-id="0cb58-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0cb58-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0cb58-115">Child Elements</span></span>  
 <span data-ttu-id="0cb58-116">Keine.</span><span class="sxs-lookup"><span data-stu-id="0cb58-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0cb58-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0cb58-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0cb58-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="0cb58-118">**Element**</span></span>|<span data-ttu-id="0cb58-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="0cb58-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0cb58-120">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="0cb58-120">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="0cb58-121">Gibt die maximale Anzahl von Verbindungen mit einem Netzwerkhost an.</span><span class="sxs-lookup"><span data-stu-id="0cb58-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0cb58-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0cb58-122">Remarks</span></span>  
 <span data-ttu-id="0cb58-123">Das `remove` Element entfernt den Verbindungsverwaltungslisteneintrag für den angegebenen Server.</span><span class="sxs-lookup"><span data-stu-id="0cb58-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="0cb58-124">Der Wert `address` des Attributs sollte eine gültige IP-Adresse oder ein gültiger Hostname sein.</span><span class="sxs-lookup"><span data-stu-id="0cb58-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="0cb58-125">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="0cb58-125">Configuration Files</span></span>  
 <span data-ttu-id="0cb58-126">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0cb58-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0cb58-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0cb58-127">Example</span></span>  
 <span data-ttu-id="0cb58-128">Im folgenden Beispiel werden alle Verbindungsverwaltungslisteneinträge für den Server `www.adventure-works.com` entfernt und dann `www.contoso.com` eine Anwendung so konfiguriert, dass vier Verbindungen zum Server und zwei Verbindungen zu allen anderen Servern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0cb58-128">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0cb58-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0cb58-129">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="0cb58-130">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="0cb58-130">Network Settings Schema</span></span>](index.md)
