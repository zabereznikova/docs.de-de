---
title: '&lt;URI&gt; Element (Uri-Einstellungen)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 735a6596b22e6d6fdcff776dd79224230db5b7b3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="lturigt-element-uri-settings"></a><span data-ttu-id="b52c2-102">&lt;URI&gt; Element (Uri-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="b52c2-102">&lt;Uri&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="b52c2-103">Enthält Einstellungen, die angeben, wie .NET Framework Webadressen ausgedrückt mit uniform Resource Identifier (URIs) behandelt.</span><span class="sxs-lookup"><span data-stu-id="b52c2-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="b52c2-104">Schemahierarchie</span><span class="sxs-lookup"><span data-stu-id="b52c2-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="b52c2-105">\<configuration> Element</span><span class="sxs-lookup"><span data-stu-id="b52c2-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="b52c2-106">\<URI ></span><span class="sxs-lookup"><span data-stu-id="b52c2-106">\<uri></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="b52c2-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="b52c2-107">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b52c2-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b52c2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b52c2-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b52c2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b52c2-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="b52c2-110">Attributes</span></span>  
 <span data-ttu-id="b52c2-111">Keine</span><span class="sxs-lookup"><span data-stu-id="b52c2-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b52c2-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b52c2-112">Child Elements</span></span>  
  
|<span data-ttu-id="b52c2-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="b52c2-113">**Element**</span></span>|<span data-ttu-id="b52c2-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b52c2-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b52c2-115">IDN</span><span class="sxs-lookup"><span data-stu-id="b52c2-115">idn</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|<span data-ttu-id="b52c2-116">Gibt an, ob die Analyse für internationale Domänennamen (IDN) auf den Domänennamen angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="b52c2-116">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="b52c2-117">iriParsing</span><span class="sxs-lookup"><span data-stu-id="b52c2-117">iriParsing</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|<span data-ttu-id="b52c2-118">Gibt an, ob auf die Analyse von International Resource Identifier (IRI) angewendet wird <xref:System.Uri> und gibt an, ob die IRI-Analyse Regeln angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b52c2-118">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="b52c2-119">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="b52c2-119">schemeSettings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="b52c2-120">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="b52c2-120">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b52c2-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b52c2-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b52c2-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="b52c2-122">**Element**</span></span>|<span data-ttu-id="b52c2-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b52c2-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b52c2-124">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="b52c2-124">configuration</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="b52c2-125">Enthält Einstellungen für alle Namespaces.</span><span class="sxs-lookup"><span data-stu-id="b52c2-125">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b52c2-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b52c2-126">Remarks</span></span>  
 <span data-ttu-id="b52c2-127">Die `uri` Element enthält die Einstellungen für Mitglieder der der <xref:System.Uri> Klasse, die vom Klassen in der <xref:System.Net> Namespace.</span><span class="sxs-lookup"><span data-stu-id="b52c2-127">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="b52c2-128">Die Unterstützung für IRI und IDN zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b52c2-128">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b52c2-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b52c2-129">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b52c2-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b52c2-130">Description</span></span>  
 <span data-ttu-id="b52c2-131">Das folgende Beispiel zeigt eine Konfiguration von verwendet die <xref:System.Uri> Klasse IRI-Analyse und IDN-Namen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b52c2-131">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="b52c2-132">Im Beispiel löscht auch alle Schema-Einstellungen, und klicken Sie dann bietet Unterstützung für Escapezeichen nicht Prozentzeichen codiert Pfadtrennzeichen für das HTTP-Schema.</span><span class="sxs-lookup"><span data-stu-id="b52c2-132">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b52c2-133">Code</span><span class="sxs-lookup"><span data-stu-id="b52c2-133">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b52c2-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b52c2-134">See Also</span></span>  
 [<span data-ttu-id="b52c2-135">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b52c2-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
