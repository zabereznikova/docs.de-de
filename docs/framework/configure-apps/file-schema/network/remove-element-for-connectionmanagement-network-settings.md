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
ms.openlocfilehash: 46157482d7ceb42b352c68dc9b0eab4f7688bc5c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176174"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="59863-102">\<remove>-Element für connectionManagement (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="59863-102">\<remove> Element for connectionManagement (Network Settings)</span></span>

<span data-ttu-id="59863-103">Entfernt eine IP-Adresse oder einen DNS-Namen aus der Verbindungs Verwaltungsliste.</span><span class="sxs-lookup"><span data-stu-id="59863-103">Removes an IP address or DNS name from the connection management list.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="59863-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="59863-104">Syntax</span></span>  
  
```xml  
<remove
  address="server name or IP address"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59863-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="59863-105">Attributes and Elements</span></span>  

 <span data-ttu-id="59863-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="59863-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59863-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="59863-107">Attributes</span></span>  
  
|<span data-ttu-id="59863-108">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="59863-108">**Attribute**</span></span>|<span data-ttu-id="59863-109">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="59863-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="59863-110">Eine IP-Adresse oder ein DNS-Name.</span><span class="sxs-lookup"><span data-stu-id="59863-110">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59863-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="59863-111">Child Elements</span></span>  

 <span data-ttu-id="59863-112">Keine</span><span class="sxs-lookup"><span data-stu-id="59863-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59863-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="59863-113">Parent Elements</span></span>  
  
|<span data-ttu-id="59863-114">**Element**</span><span class="sxs-lookup"><span data-stu-id="59863-114">**Element**</span></span>|<span data-ttu-id="59863-115">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="59863-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="59863-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="59863-116">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="59863-117">Gibt die maximale Anzahl von Verbindungen mit einem Netzwerkhost an.</span><span class="sxs-lookup"><span data-stu-id="59863-117">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59863-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="59863-118">Remarks</span></span>  

 <span data-ttu-id="59863-119">Das- `remove` Element entfernt den Verbindungs Verwaltungs Listeneintrag für den angegebenen Server.</span><span class="sxs-lookup"><span data-stu-id="59863-119">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="59863-120">Der Wert des `address` -Attributs muss eine gültige IP-Adresse oder ein gültiger Hostname sein.</span><span class="sxs-lookup"><span data-stu-id="59863-120">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="59863-121">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="59863-121">Configuration Files</span></span>  

 <span data-ttu-id="59863-122">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="59863-122">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="59863-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="59863-123">Example</span></span>  

 <span data-ttu-id="59863-124">Im folgenden Beispiel werden alle Verbindungs Verwaltungs Listeneinträge für den-Server entfernt `www.adventure-works.com` . Anschließend wird eine Anwendung so konfiguriert, dass vier Verbindungen mit dem Server `www.contoso.com` und zwei Verbindungen mit allen anderen Servern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="59863-124">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="59863-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="59863-125">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="59863-126">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="59863-126">Network Settings Schema</span></span>](index.md)
