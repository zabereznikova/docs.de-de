---
title: <add>-Element für connectionManagement (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/add
helpviewer_keywords:
- <add> element, connectionManagement
- <connectionManagement>, add element
- add element, connectionManagement
- connectionManagement, add element
ms.assetid: 856bf57d-1c63-46c7-a178-03d97b0a4149
ms.openlocfilehash: 608c591b910252dd60950bf2aa7565d6df04d5fc
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664226"
---
# <a name="add-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="035dc-102">\<Add >-Element für connectionManagement (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="035dc-102">\<add> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="035dc-103">Fügt der Verbindungsverwaltungsliste eine IP-Adresse oder einen DNS-Namen hinzu.</span><span class="sxs-lookup"><span data-stu-id="035dc-103">Adds an IP address or DNS name to the connection management list.</span></span>  
  
 <span data-ttu-id="035dc-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="035dc-104">\<configuration></span></span>  
<span data-ttu-id="035dc-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="035dc-105">\<system.net></span></span>  
<span data-ttu-id="035dc-106">\<connectionManagement></span><span class="sxs-lookup"><span data-stu-id="035dc-106">\<connectionManagement></span></span>  
<span data-ttu-id="035dc-107">\<add></span><span class="sxs-lookup"><span data-stu-id="035dc-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="035dc-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="035dc-108">Syntax</span></span>  
  
```xml  
<add   
  address="address expression"   
  maxconnection="integer"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="035dc-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="035dc-109">Attributes and Elements</span></span>  
 <span data-ttu-id="035dc-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="035dc-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="035dc-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="035dc-111">Attributes</span></span>  
  
|<span data-ttu-id="035dc-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="035dc-112">**Attribute**</span></span>|<span data-ttu-id="035dc-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="035dc-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="035dc-114">Eine Zeichenfolge, die eine IP-Adresse oder einen DNS-Namen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="035dc-114">A string describing an IP address or DNS name.</span></span>|  
|`maxconnection`|<span data-ttu-id="035dc-115">Die maximale Anzahl von Verbindungen, die für einen Server zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="035dc-115">The maximum number of connections allowed to a server.</span></span> <span data-ttu-id="035dc-116">Wenn keine Angabe erfolgt, wird der Standardwert "2" verwendet.</span><span class="sxs-lookup"><span data-stu-id="035dc-116">If not supplied, the default is 2.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="035dc-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="035dc-117">Child Elements</span></span>  
 <span data-ttu-id="035dc-118">Keine</span><span class="sxs-lookup"><span data-stu-id="035dc-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="035dc-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="035dc-119">Parent Elements</span></span>  
  
|<span data-ttu-id="035dc-120">**Element**</span><span class="sxs-lookup"><span data-stu-id="035dc-120">**Element**</span></span>|<span data-ttu-id="035dc-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="035dc-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="035dc-122">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="035dc-122">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="035dc-123">Gibt die maximale Anzahl von Verbindungen mit einem Netzwerkhost an.</span><span class="sxs-lookup"><span data-stu-id="035dc-123">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="035dc-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="035dc-124">Remarks</span></span>  
 <span data-ttu-id="035dc-125">Der Wert des `address`-Attributs muss entweder ein Sternchen zur Angabe aller Verbindungen oder eine Zeichenfolge im Format `<schema>://<idn_hostname>[:<port>]` sein.</span><span class="sxs-lookup"><span data-stu-id="035dc-125">The value of the `address` attribute should be either an asterisk to indicate all connections, or a string of the form `<schema>://<idn_hostname>[:<port>]`.</span></span>  
  
 <span data-ttu-id="035dc-126">Enthält der an HTTP-APIs übergebene URI Unicode, wird der Name intern mit <xref:System.Uri.DnsSafeHost%2A> umgewandelt, wodurch möglicherweise eine Punycode-Zeichenfolge zurückgegeben wird (das Verhalten ist von der aktuellen IDN-Konfiguration abhängig).</span><span class="sxs-lookup"><span data-stu-id="035dc-126">If the URI passed to any HTTP APIs contains Unicode, the name will be converted internally using <xref:System.Uri.DnsSafeHost%2A> which might return a punicode string (behavior dependent on the current IDN configuration).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="035dc-127">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="035dc-127">Configuration Files</span></span>  
 <span data-ttu-id="035dc-128">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="035dc-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="035dc-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="035dc-129">Example</span></span>  
 <span data-ttu-id="035dc-130">Im folgenden Beispiel wird eine Anwendung so konfiguriert, dass vier Verbindungen mit dem `www.contoso.com` Server und zwei Verbindungen mit allen anderen Servern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="035dc-130">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="035dc-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="035dc-131">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="035dc-132">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="035dc-132">Network Settings Schema</span></span>](index.md)
