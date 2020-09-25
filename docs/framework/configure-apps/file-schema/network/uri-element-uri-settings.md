---
title: <uri>-Element (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: 2f22d70407d10dbb38f0cb8d3a8ac74ff3fe8763
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190201"
---
# <a name="uri-element-uri-settings"></a><span data-ttu-id="d3fd4-102">\<uri>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="d3fd4-102">\<uri> Element (Uri Settings)</span></span>

<span data-ttu-id="d3fd4-103">Enthält Einstellungen, die angeben, wie die .NET Framework Webadressen verarbeitet, die mithilfe von URIs (Uniform Resource Identifier) ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="d3fd4-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<uri>**  
  
## <a name="syntax"></a><span data-ttu-id="d3fd4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d3fd4-104">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3fd4-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d3fd4-105">Attributes and Elements</span></span>  

 <span data-ttu-id="d3fd4-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d3fd4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3fd4-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="d3fd4-107">Attributes</span></span>  

 <span data-ttu-id="d3fd4-108">Keine</span><span class="sxs-lookup"><span data-stu-id="d3fd4-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d3fd4-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d3fd4-109">Child Elements</span></span>  
  
|<span data-ttu-id="d3fd4-110">**Element**</span><span class="sxs-lookup"><span data-stu-id="d3fd4-110">**Element**</span></span>|<span data-ttu-id="d3fd4-111">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d3fd4-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d3fd4-112">IDN</span><span class="sxs-lookup"><span data-stu-id="d3fd4-112">idn</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="d3fd4-113">Gibt an, ob die Analyse für internationale Domänennamen (IDN) auf den Domänennamen angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="d3fd4-113">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="d3fd4-114">IriParsing</span><span class="sxs-lookup"><span data-stu-id="d3fd4-114">iriParsing</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="d3fd4-115">Gibt an, ob die IRI-Verarbeitung (International Resource Identifier) auf angewendet wird <xref:System.Uri> und ob IRI-Erteilungs Regeln angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d3fd4-115">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="d3fd4-116">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="d3fd4-116">schemeSettings</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="d3fd4-117">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="d3fd4-117">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d3fd4-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d3fd4-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d3fd4-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="d3fd4-119">**Element**</span></span>|<span data-ttu-id="d3fd4-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d3fd4-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d3fd4-121">configuration</span><span class="sxs-lookup"><span data-stu-id="d3fd4-121">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="d3fd4-122">Enthält Einstellungen für alle Namespaces.</span><span class="sxs-lookup"><span data-stu-id="d3fd4-122">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3fd4-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d3fd4-123">Remarks</span></span>  

 <span data-ttu-id="d3fd4-124">Das- `uri` Element enthält Einstellungen für Member der-Klasse, die <xref:System.Uri> von Klassen im- <xref:System.Net> Namespace verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d3fd4-124">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="d3fd4-125">Die Einstellungen konfigurieren die Unterstützung für IRI und IDN.</span><span class="sxs-lookup"><span data-stu-id="d3fd4-125">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3fd4-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d3fd4-126">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="d3fd4-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d3fd4-127">Description</span></span>  

 <span data-ttu-id="d3fd4-128">Das folgende Beispiel zeigt eine Konfiguration, die von der- <xref:System.Uri> Klasse zur Unterstützung der IRI-Verarbeitung und IDN-Namen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d3fd4-128">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="d3fd4-129">Das Beispiel löscht außerdem alle Schema Einstellungen und fügt dann Unterstützung für die nicht-Escapezeichen für Prozent codierte Pfade für das http-Schema hinzu.</span><span class="sxs-lookup"><span data-stu-id="d3fd4-129">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d3fd4-130">Code</span><span class="sxs-lookup"><span data-stu-id="d3fd4-130">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d3fd4-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3fd4-131">See also</span></span>

- [<span data-ttu-id="d3fd4-132">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="d3fd4-132">Network Settings Schema</span></span>](index.md)
