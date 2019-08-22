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
ms.openlocfilehash: 8ab7a43fbb3e8df5bb0c99b5947f2fafb362399a
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664033"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="b8008-102">\<Entfernen von >-Element für connectionManagement (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b8008-102">\<remove> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="b8008-103">Entfernt eine IP-Adresse oder einen DNS-Namen aus der Verbindungs Verwaltungsliste.</span><span class="sxs-lookup"><span data-stu-id="b8008-103">Removes an IP address or DNS name from the connection management list.</span></span>  
  
 <span data-ttu-id="b8008-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b8008-104">\<configuration></span></span>  
<span data-ttu-id="b8008-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="b8008-105">\<system.net></span></span>  
<span data-ttu-id="b8008-106">\<connectionManagement></span><span class="sxs-lookup"><span data-stu-id="b8008-106">\<connectionManagement></span></span>  
<span data-ttu-id="b8008-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="b8008-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8008-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8008-108">Syntax</span></span>  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8008-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b8008-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b8008-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b8008-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8008-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="b8008-111">Attributes</span></span>  
  
|<span data-ttu-id="b8008-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="b8008-112">**Attribute**</span></span>|<span data-ttu-id="b8008-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b8008-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="b8008-114">Eine IP-Adresse oder ein DNS-Name.</span><span class="sxs-lookup"><span data-stu-id="b8008-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b8008-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b8008-115">Child Elements</span></span>  
 <span data-ttu-id="b8008-116">Keine</span><span class="sxs-lookup"><span data-stu-id="b8008-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b8008-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b8008-117">Parent Elements</span></span>  
  
|<span data-ttu-id="b8008-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="b8008-118">**Element**</span></span>|<span data-ttu-id="b8008-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b8008-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b8008-120">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="b8008-120">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="b8008-121">Gibt die maximale Anzahl von Verbindungen mit einem Netzwerkhost an.</span><span class="sxs-lookup"><span data-stu-id="b8008-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8008-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b8008-122">Remarks</span></span>  
 <span data-ttu-id="b8008-123">Das `remove` -Element entfernt den Verbindungs Verwaltungs Listeneintrag für den angegebenen Server.</span><span class="sxs-lookup"><span data-stu-id="b8008-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="b8008-124">Der Wert des `address` -Attributs muss eine gültige IP-Adresse oder ein gültiger Hostname sein.</span><span class="sxs-lookup"><span data-stu-id="b8008-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b8008-125">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="b8008-125">Configuration Files</span></span>  
 <span data-ttu-id="b8008-126">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b8008-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8008-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b8008-127">Example</span></span>  
 <span data-ttu-id="b8008-128">Im folgenden Beispiel werden alle Verbindungs Verwaltungs Listeneinträge für den- `www.adventure-works.com` Server entfernt. Anschließend wird eine Anwendung so konfiguriert, dass vier Verbindungen `www.contoso.com` mit dem Server und zwei Verbindungen mit allen anderen Servern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b8008-128">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b8008-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8008-129">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="b8008-130">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b8008-130">Network Settings Schema</span></span>](index.md)
