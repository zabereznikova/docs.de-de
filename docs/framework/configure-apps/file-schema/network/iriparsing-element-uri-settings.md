---
title: <iriParsing>-Element (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: fd617d1b4ac8e532c6f9aeaa01465e9866b059e9
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698093"
---
# <a name="iriparsing-element-uri-settings"></a><span data-ttu-id="07394-102">\<iriising >-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="07394-102">\<iriParsing> Element (Uri Settings)</span></span>
<span data-ttu-id="07394-103">Gibt an, ob die Analyse für internationale Ressourcenbezeichner (International Resource Identifier, IRI) auf <xref:System.Uri> angewendet wird und ob die IRI-Analyseregeln angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="07394-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
[<span data-ttu-id="07394-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="07394-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="07394-105">&nbsp;&nbsp;[ **\<-URI >** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="07394-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="07394-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<IRI >**</span><span class="sxs-lookup"><span data-stu-id="07394-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<iriParsing>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07394-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="07394-107">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07394-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="07394-108">Attributes and Elements</span></span>  
 <span data-ttu-id="07394-109">In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="07394-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07394-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="07394-110">Attributes</span></span>  
  
|<span data-ttu-id="07394-111">**Element**</span><span class="sxs-lookup"><span data-stu-id="07394-111">**Element**</span></span>|<span data-ttu-id="07394-112">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="07394-112">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="07394-113">Gibt an, ob die IRI-Verarbeitung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="07394-113">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="07394-114">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="07394-114">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="07394-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="07394-115">Child Elements</span></span>  
 <span data-ttu-id="07394-116">Keine</span><span class="sxs-lookup"><span data-stu-id="07394-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="07394-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="07394-117">Parent Elements</span></span>  
  
|<span data-ttu-id="07394-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="07394-118">**Element**</span></span>|<span data-ttu-id="07394-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="07394-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="07394-120">uri</span><span class="sxs-lookup"><span data-stu-id="07394-120">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="07394-121">Enthält Einstellungen, die angeben, wie die .NET Framework Webadressen verarbeitet, die mithilfe von URIs (Uniform Resource Identifier) ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="07394-121">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07394-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="07394-122">Remarks</span></span>  
 <span data-ttu-id="07394-123">Die vorhandene <xref:System.Uri> Klasse wurde in .NET Framework 3,5 erweitert.</span><span class="sxs-lookup"><span data-stu-id="07394-123">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="07394-124">3,0 SP1 und 2,0 SP1 zur Unterstützung von International Resource Identifier (IRI) und internationalisierten Domänen Namen (IDN).</span><span class="sxs-lookup"><span data-stu-id="07394-124">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="07394-125">Aktuelle Benutzer sehen keine Änderung des Verhaltens von .NET Framework 2,0, es sei denn, Sie aktivieren speziell IRI-und IDN-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="07394-125">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="07394-126">Dadurch wird die Anwendungskompatibilität mit früheren Versionen von .NET Framework garantiert.</span><span class="sxs-lookup"><span data-stu-id="07394-126">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="07394-127">Die folgenden beiden Änderungen sind erforderlich, um die Unterstützung für IRI zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="07394-127">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="07394-128">Fügen Sie der Datei Machine. config im Verzeichnis .NET Framework 2,0 die folgende Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="07394-128">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="07394-129">Geben Sie an, ob die IRI-Verarbeitungs Regeln angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="07394-129">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="07394-130">Dies kann in der Datei „machine.config“ oder in der Datei „App.config“ durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="07394-130">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="07394-131">Durch das Aktivieren der IRI-Verarbeitung (iriising aktiviert = `true`) erfolgt die Normalisierung und Zeichen Überprüfung gemäß den neuesten IRI-Regeln in RFC 3987.</span><span class="sxs-lookup"><span data-stu-id="07394-131">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="07394-132">Der Standardwert ist `false` und führt eine Normalisierung und Zeichen Überprüfung gemäß RFC 2396 und RFC 3986 durch (für IPv6-Literale).</span><span class="sxs-lookup"><span data-stu-id="07394-132">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="07394-133">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="07394-133">Configuration Files</span></span>  
 <span data-ttu-id="07394-134">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="07394-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="07394-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07394-135">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="07394-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07394-136">Description</span></span>  
 <span data-ttu-id="07394-137">Das folgende Beispiel zeigt eine Konfiguration, die von der <xref:System.Uri>-Klasse zur Unterstützung der IRI-Verarbeitung und IDN-Namen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="07394-137">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="07394-138">Code</span><span class="sxs-lookup"><span data-stu-id="07394-138">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="07394-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07394-139">See also</span></span>

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="07394-140">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="07394-140">Network Settings Schema</span></span>](index.md)
