---
title: <uri>-Element (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: a492baf9951466383ca0277a2927b8554e5bb332
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697437"
---
# <a name="uri-element-uri-settings"></a><span data-ttu-id="1de96-102">\<URI-> Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="1de96-102">\<uri> Element (Uri Settings)</span></span>
<span data-ttu-id="1de96-103">Enthält Einstellungen, die angeben, wie die .NET Framework Webadressen verarbeitet, die mithilfe von URIs (Uniform Resource Identifier) ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="1de96-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
[<span data-ttu-id="1de96-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="1de96-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="1de96-105">&nbsp;&nbsp; **\<-URI >**</span><span class="sxs-lookup"><span data-stu-id="1de96-105">&nbsp;&nbsp;**\<uri>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1de96-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="1de96-106">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1de96-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1de96-107">Attributes and Elements</span></span>  
 <span data-ttu-id="1de96-108">In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1de96-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1de96-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="1de96-109">Attributes</span></span>  
 <span data-ttu-id="1de96-110">None.</span><span class="sxs-lookup"><span data-stu-id="1de96-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1de96-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1de96-111">Child Elements</span></span>  
  
|<span data-ttu-id="1de96-112">**Element**</span><span class="sxs-lookup"><span data-stu-id="1de96-112">**Element**</span></span>|<span data-ttu-id="1de96-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1de96-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1de96-114">idn</span><span class="sxs-lookup"><span data-stu-id="1de96-114">idn</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="1de96-115">Gibt an, ob die Analyse für internationale Domänennamen (IDN) auf den Domänennamen angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="1de96-115">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="1de96-116">iriParsing</span><span class="sxs-lookup"><span data-stu-id="1de96-116">iriParsing</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="1de96-117">Gibt an, ob die IRI-Verarbeitung (International Resource Identifier) auf <xref:System.Uri> angewendet wird und ob IRI-Erteilungs Regeln angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1de96-117">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="1de96-118">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="1de96-118">schemeSettings</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="1de96-119">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="1de96-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1de96-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1de96-120">Parent Elements</span></span>  
  
|<span data-ttu-id="1de96-121">**Element**</span><span class="sxs-lookup"><span data-stu-id="1de96-121">**Element**</span></span>|<span data-ttu-id="1de96-122">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1de96-122">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1de96-123">configuration</span><span class="sxs-lookup"><span data-stu-id="1de96-123">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="1de96-124">Enthält Einstellungen für alle Namespaces.</span><span class="sxs-lookup"><span data-stu-id="1de96-124">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1de96-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1de96-125">Remarks</span></span>  
 <span data-ttu-id="1de96-126">Das `uri`-Element enthält Einstellungen für Member der <xref:System.Uri> Klasse, die von Klassen im <xref:System.Net>-Namespace verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1de96-126">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="1de96-127">Die Einstellungen konfigurieren die Unterstützung für IRI und IDN.</span><span class="sxs-lookup"><span data-stu-id="1de96-127">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1de96-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1de96-128">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="1de96-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1de96-129">Description</span></span>  
 <span data-ttu-id="1de96-130">Das folgende Beispiel zeigt eine Konfiguration, die von der <xref:System.Uri>-Klasse zur Unterstützung der IRI-Verarbeitung und IDN-Namen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1de96-130">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="1de96-131">Das Beispiel löscht außerdem alle Schema Einstellungen und fügt dann Unterstützung für die nicht-Escapezeichen für Prozent codierte Pfade für das http-Schema hinzu.</span><span class="sxs-lookup"><span data-stu-id="1de96-131">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="1de96-132">Code</span><span class="sxs-lookup"><span data-stu-id="1de96-132">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1de96-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1de96-133">See also</span></span>

- [<span data-ttu-id="1de96-134">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="1de96-134">Network Settings Schema</span></span>](index.md)
