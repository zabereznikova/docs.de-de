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
ms.openlocfilehash: 093b68d31e03094bedefa96a2f2d53eb3d84edf0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155010"
---
# <a name="add-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="8ea08-102">\<add>-Element für connectionManagement (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="8ea08-102">\<add> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="8ea08-103">Fügt der Verbindungsverwaltungsliste eine IP-Adresse oder einen DNS-Namen hinzu.</span><span class="sxs-lookup"><span data-stu-id="8ea08-103">Adds an IP address or DNS name to the connection management list.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="8ea08-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ea08-104">Syntax</span></span>  
  
```xml  
<add
  address="address expression"
  maxconnection="integer"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ea08-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8ea08-105">Attributes and Elements</span></span>  
 <span data-ttu-id="8ea08-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8ea08-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ea08-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="8ea08-107">Attributes</span></span>  
  
|<span data-ttu-id="8ea08-108">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="8ea08-108">**Attribute**</span></span>|<span data-ttu-id="8ea08-109">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="8ea08-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="8ea08-110">Eine Zeichenfolge, die eine IP-Adresse oder einen DNS-Namen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="8ea08-110">A string describing an IP address or DNS name.</span></span>|  
|`maxconnection`|<span data-ttu-id="8ea08-111">Die maximale Anzahl von Verbindungen, die für einen Server zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="8ea08-111">The maximum number of connections allowed to a server.</span></span> <span data-ttu-id="8ea08-112">Wenn keine Angabe erfolgt, wird der Standardwert "2" verwendet.</span><span class="sxs-lookup"><span data-stu-id="8ea08-112">If not supplied, the default is 2.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8ea08-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8ea08-113">Child Elements</span></span>  
 <span data-ttu-id="8ea08-114">Keine</span><span class="sxs-lookup"><span data-stu-id="8ea08-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8ea08-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8ea08-115">Parent Elements</span></span>  
  
|<span data-ttu-id="8ea08-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="8ea08-116">**Element**</span></span>|<span data-ttu-id="8ea08-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="8ea08-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8ea08-118">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="8ea08-118">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="8ea08-119">Gibt die maximale Anzahl von Verbindungen mit einem Netzwerkhost an.</span><span class="sxs-lookup"><span data-stu-id="8ea08-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ea08-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8ea08-120">Remarks</span></span>  
 <span data-ttu-id="8ea08-121">Der Wert des `address`-Attributs muss entweder ein Sternchen zur Angabe aller Verbindungen oder eine Zeichenfolge im Format `<schema>://<idn_hostname>[:<port>]` sein.</span><span class="sxs-lookup"><span data-stu-id="8ea08-121">The value of the `address` attribute should be either an asterisk to indicate all connections, or a string of the form `<schema>://<idn_hostname>[:<port>]`.</span></span>  
  
 <span data-ttu-id="8ea08-122">Enthält der an HTTP-APIs übergebene URI Unicode, wird der Name intern mit <xref:System.Uri.DnsSafeHost%2A> umgewandelt, wodurch möglicherweise eine Punycode-Zeichenfolge zurückgegeben wird (das Verhalten ist von der aktuellen IDN-Konfiguration abhängig).</span><span class="sxs-lookup"><span data-stu-id="8ea08-122">If the URI passed to any HTTP APIs contains Unicode, the name will be converted internally using <xref:System.Uri.DnsSafeHost%2A> which might return a punicode string (behavior dependent on the current IDN configuration).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8ea08-123">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="8ea08-123">Configuration Files</span></span>  
 <span data-ttu-id="8ea08-124">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8ea08-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ea08-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8ea08-125">Example</span></span>  
 <span data-ttu-id="8ea08-126">Im folgenden Beispiel wird eine Anwendung so konfiguriert, dass vier Verbindungen mit dem Server `www.contoso.com` und zwei Verbindungen mit allen anderen Servern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8ea08-126">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8ea08-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8ea08-127">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="8ea08-128">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="8ea08-128">Network Settings Schema</span></span>](index.md)
