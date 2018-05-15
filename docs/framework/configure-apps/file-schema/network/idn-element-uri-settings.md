---
title: '&lt;IDN&gt; Element (Uri-Einstellungen)'
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 17f68fbb92797928be911e530232e8638793687f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltidngt-element-uri-settings"></a><span data-ttu-id="5d089-102">&lt;IDN&gt; Element (Uri-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="5d089-102">&lt;idn&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="5d089-103">Gibt an, ob Internationalized Domain Name (IDN) Analyse an den Domänennamen angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="5d089-103">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="5d089-104">Schemahierarchie</span><span class="sxs-lookup"><span data-stu-id="5d089-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="5d089-105">\<configuration> Element</span><span class="sxs-lookup"><span data-stu-id="5d089-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="5d089-106">\<URI >-Element (Uri-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="5d089-106">\<Uri> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [<span data-ttu-id="5d089-107">\<IDN ></span><span class="sxs-lookup"><span data-stu-id="5d089-107">\<idn></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="5d089-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d089-108">Syntax</span></span>  
  
```xml  
<idn  
  enabled="All|AllExceptIntranet|None"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d089-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5d089-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5d089-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5d089-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d089-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="5d089-111">Attributes</span></span>  
  
|<span data-ttu-id="5d089-112">**Element**</span><span class="sxs-lookup"><span data-stu-id="5d089-112">**Element**</span></span>|<span data-ttu-id="5d089-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="5d089-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="5d089-114">Gibt bei Anwendung auf einen Domänennamen Internationalized Domain Name (IDN) Analyse der Standardwert none ist.</span><span class="sxs-lookup"><span data-stu-id="5d089-114">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name The default value is none.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d089-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5d089-115">Child Elements</span></span>  
 <span data-ttu-id="5d089-116">Keiner</span><span class="sxs-lookup"><span data-stu-id="5d089-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5d089-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5d089-117">Parent Elements</span></span>  
  
|<span data-ttu-id="5d089-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="5d089-118">**Element**</span></span>|<span data-ttu-id="5d089-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="5d089-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="5d089-120">URI</span><span class="sxs-lookup"><span data-stu-id="5d089-120">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="5d089-121">Enthält Einstellungen, die angeben, wie .NET Framework Webadressen ausgedrückt mit uniform Resource Identifier (URIs) behandelt.</span><span class="sxs-lookup"><span data-stu-id="5d089-121">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d089-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5d089-122">Remarks</span></span>  
 <span data-ttu-id="5d089-123">Die vorhandene <xref:System.Uri> Klasse in .NET Framework 3.5 erweitert wurde.</span><span class="sxs-lookup"><span data-stu-id="5d089-123">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="5d089-124">3.0 SP1 und 2.0 SP1 mit Unterstützung für International Resource Identifiers (IRI) und internationale Domänennamen (IDN).</span><span class="sxs-lookup"><span data-stu-id="5d089-124">3.0 SP1, and 2.0 SP1 with support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="5d089-125">Aktuellen Benutzer sehen keine Änderungen des Verhaltens gegenüber den .NET Framework 2.0, es sei denn, sie explizit IRI und IDN aktivieren unterstützen.</span><span class="sxs-lookup"><span data-stu-id="5d089-125">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="5d089-126">Dadurch wird die Anwendungskompatibilität mit früheren Versionen von .NET Framework garantiert.</span><span class="sxs-lookup"><span data-stu-id="5d089-126">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="5d089-127">Um die Unterstützung für IRI aktivieren, sind die folgenden zwei Änderungen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="5d089-127">To enable support for IRI, the following two changes are required:</span></span>  
  
1.  <span data-ttu-id="5d089-128">Fügen Sie die folgende Zeile auf die Datei "Machine.config" im .NET Framework 2.0-Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="5d089-128">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  <span data-ttu-id="5d089-129">Geben Sie, ob Sie, dass Internationalized Domain Name (IDN) zu analysieren, die auf den Domänennamen angewendet und gibt an, ob die IRI-Analyse Regeln angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5d089-129">Specify whether you want Internationalized Domain Name (IDN) parsing applied to the domain name and whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="5d089-130">Dies kann in der Datei „machine.config“ oder in der Datei „App.config“ durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5d089-130">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="5d089-131">Es gibt drei mögliche Werte für IDN abhängig von den DNS-Servern, die verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="5d089-131">There are three possible values for IDN depending on the DNS servers that are used:</span></span>  
  
-   <span data-ttu-id="5d089-132">IDN aktiviert = All</span><span class="sxs-lookup"><span data-stu-id="5d089-132">idn enabled = All</span></span>  
  
     <span data-ttu-id="5d089-133">Dieser Wert wird alle Unicode-Domänennamen in ihre Punycode-Entsprechungen (IDN-Namen) konvertiert.</span><span class="sxs-lookup"><span data-stu-id="5d089-133">This value will convert any Unicode domain names to their Punycode equivalents (IDN names).</span></span>  
  
-   <span data-ttu-id="5d089-134">IDN aktiviert = AllExceptIntranet</span><span class="sxs-lookup"><span data-stu-id="5d089-134">idn enabled = AllExceptIntranet</span></span>  
  
     <span data-ttu-id="5d089-135">Dieser Wert wird allen Unicode-Domänennamen nicht auf dem lokalen Intranet verwenden Sie die Punycode-Entsprechungen (IDN-Namen) konvertiert.</span><span class="sxs-lookup"><span data-stu-id="5d089-135">This value will convert all Unicode domain names not on the local Intranet to use the Punycode equivalents (IDN names).</span></span> <span data-ttu-id="5d089-136">In diesem Fall sollte die DNS-Server, die für das Intranet verwendet werden um internationale Namen im lokalen Intranet zu behandeln, Unicode-namensauflösung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="5d089-136">In this case to handle international names on the local Intranet, the DNS servers that are used for the Intranet should support Unicode name resolution.</span></span>  
  
-   <span data-ttu-id="5d089-137">IDN aktiviert = keine</span><span class="sxs-lookup"><span data-stu-id="5d089-137">idn enabled = None</span></span>  
  
     <span data-ttu-id="5d089-138">Dieser Wert keine Unicode-Domänennamen mit Punycode konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="5d089-138">This value will not convert any Unicode domain names to use Punycode.</span></span> <span data-ttu-id="5d089-139">Dies ist der Standardwert, der mit dem .NET Framework 2.0-Verhalten konsistent ist.</span><span class="sxs-lookup"><span data-stu-id="5d089-139">This is the default value which is consistent with the .NET Framework 2.0 behaviour.</span></span>  
  
 <span data-ttu-id="5d089-140">Beim Aktivieren von IDN werden alle Unicode-Bezeichnungen in einem Domänennamen in ihre Punycode-Entsprechungen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="5d089-140">Enabling IDN will convert all Unicode labels in a domain name to their Punycode equivalents.</span></span> <span data-ttu-id="5d089-141">Punycode-Namen enthalten nur ASCII-Zeichen und beginnen immer mit dem Präfix „xn--“.</span><span class="sxs-lookup"><span data-stu-id="5d089-141">Punycode names contain only ASCII characters and always start with the xn-- prefix.</span></span> <span data-ttu-id="5d089-142">So werden vorhandene DNS-Server im Internet unterstützt, da die meisten DNS-Server nur ASCII-Zeichen unterstützen (siehe RFC 3940).</span><span class="sxs-lookup"><span data-stu-id="5d089-142">The reason for this is to support existing DNS servers on the Internet, since most DNS servers only support ASCII characters (see RFC 3940).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="5d089-143">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="5d089-143">Configuration Files</span></span>  
 <span data-ttu-id="5d089-144">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5d089-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d089-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5d089-145">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="5d089-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d089-146">Description</span></span>  
 <span data-ttu-id="5d089-147">Das folgende Beispiel zeigt eine Konfiguration von verwendet die <xref:System.Uri> Klasse IRI-Analyse und IDN-Namen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5d089-147">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="5d089-148">Code</span><span class="sxs-lookup"><span data-stu-id="5d089-148">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5d089-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d089-149">See Also</span></span>  
 <xref:System.Configuration.IdnElement?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 [<span data-ttu-id="5d089-150">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="5d089-150">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
