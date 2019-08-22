---
title: <idn>-Element (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
ms.openlocfilehash: 5fe2eafee702be96bfdca80a06af4a040d9ef0f6
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664121"
---
# <a name="idn-element-uri-settings"></a><span data-ttu-id="e6a8c-102">\<IDN-> Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="e6a8c-102">\<idn> Element (Uri Settings)</span></span>
<span data-ttu-id="e6a8c-103">Gibt an, ob die IDN (Internationalized Domain Name)-Verarbeitung auf einen Domänen Namen angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="e6a8c-103">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="e6a8c-104">Schemahierarchie</span><span class="sxs-lookup"><span data-stu-id="e6a8c-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="e6a8c-105">\<configuration> Element</span><span class="sxs-lookup"><span data-stu-id="e6a8c-105">\<configuration> Element</span></span>](../configuration-element.md)  
  
 [<span data-ttu-id="e6a8c-106">\<URI-> Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="e6a8c-106">\<Uri> Element (Uri Settings)</span></span>](uri-element-uri-settings.md)  
  
 [<span data-ttu-id="e6a8c-107">\<idn></span><span class="sxs-lookup"><span data-stu-id="e6a8c-107">\<idn></span></span>](idn-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="e6a8c-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6a8c-108">Syntax</span></span>  
  
```xml  
<idn  
  enabled="All|AllExceptIntranet|None"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6a8c-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e6a8c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e6a8c-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e6a8c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6a8c-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="e6a8c-111">Attributes</span></span>  
  
|<span data-ttu-id="e6a8c-112">**Element**</span><span class="sxs-lookup"><span data-stu-id="e6a8c-112">**Element**</span></span>|<span data-ttu-id="e6a8c-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e6a8c-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="e6a8c-114">Gibt an, ob die IDN (Internationalized Domain Name)-Verarbeitung auf einen Domänen Namen angewendet wird. der Standardwert ist "None".</span><span class="sxs-lookup"><span data-stu-id="e6a8c-114">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name The default value is none.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e6a8c-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e6a8c-115">Child Elements</span></span>  
 <span data-ttu-id="e6a8c-116">None</span><span class="sxs-lookup"><span data-stu-id="e6a8c-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e6a8c-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e6a8c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e6a8c-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="e6a8c-118">**Element**</span></span>|<span data-ttu-id="e6a8c-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e6a8c-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e6a8c-120">uri</span><span class="sxs-lookup"><span data-stu-id="e6a8c-120">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="e6a8c-121">Enthält Einstellungen, die angeben, wie die .NET Framework Webadressen verarbeitet, die mithilfe von URIs (Uniform Resource Identifier) ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="e6a8c-121">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6a8c-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e6a8c-122">Remarks</span></span>  
 <span data-ttu-id="e6a8c-123">Die vorhandene <xref:System.Uri> Klasse wurde in .NET Framework 3,5 erweitert.</span><span class="sxs-lookup"><span data-stu-id="e6a8c-123">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="e6a8c-124">3,0 SP1 und 2,0 SP1 mit Unterstützung für International Resource Identifier (IRI) und Internationalized Domain Names (IDN).</span><span class="sxs-lookup"><span data-stu-id="e6a8c-124">3.0 SP1, and 2.0 SP1 with support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="e6a8c-125">Aktuelle Benutzer sehen keine Änderung des Verhaltens von .NET Framework 2,0, es sei denn, Sie aktivieren speziell IRI-und IDN-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="e6a8c-125">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="e6a8c-126">Dadurch wird die Anwendungskompatibilität mit früheren Versionen von .NET Framework garantiert.</span><span class="sxs-lookup"><span data-stu-id="e6a8c-126">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="e6a8c-127">Die folgenden beiden Änderungen sind erforderlich, um die Unterstützung für IRI zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="e6a8c-127">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="e6a8c-128">Fügen Sie der Datei Machine. config im Verzeichnis .NET Framework 2,0 die folgende Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="e6a8c-128">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="e6a8c-129">Geben Sie an, ob die IDN-Verarbeitung (Internationalized Domain Name) auf den Domänen Namen angewendet werden soll und ob IRI-Regeln angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e6a8c-129">Specify whether you want Internationalized Domain Name (IDN) parsing applied to the domain name and whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="e6a8c-130">Dies kann in der Datei „machine.config“ oder in der Datei „App.config“ durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e6a8c-130">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="e6a8c-131">Es gibt drei mögliche Werte für IDN, abhängig von den verwendeten DNS-Servern:</span><span class="sxs-lookup"><span data-stu-id="e6a8c-131">There are three possible values for IDN depending on the DNS servers that are used:</span></span>  
  
- <span data-ttu-id="e6a8c-132">IDN aktiviert = alle</span><span class="sxs-lookup"><span data-stu-id="e6a8c-132">idn enabled = All</span></span>  
  
     <span data-ttu-id="e6a8c-133">Mit diesem Wert werden alle Unicode-Domänen Namen in Ihre Punycode-Entsprechungen (IDN-Namen) konvertiert.</span><span class="sxs-lookup"><span data-stu-id="e6a8c-133">This value will convert any Unicode domain names to their Punycode equivalents (IDN names).</span></span>  
  
- <span data-ttu-id="e6a8c-134">IDN aktiviert = AllExceptIntranet</span><span class="sxs-lookup"><span data-stu-id="e6a8c-134">idn enabled = AllExceptIntranet</span></span>  
  
     <span data-ttu-id="e6a8c-135">Dieser Wert konvertiert alle Unicode-Domänen Namen, die nicht im lokalen Intranet sind, in die Verwendung der Punycode-Entsprechungen (IDN-Namen).</span><span class="sxs-lookup"><span data-stu-id="e6a8c-135">This value will convert all Unicode domain names not on the local Intranet to use the Punycode equivalents (IDN names).</span></span> <span data-ttu-id="e6a8c-136">In diesem Fall sollten die DNS-Server, die für das Intranet verwendet werden, die Auflösung von Unicode-Namen unterstützen, um internationale Namen im lokalen Intranet zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e6a8c-136">In this case to handle international names on the local Intranet, the DNS servers that are used for the Intranet should support Unicode name resolution.</span></span>  
  
- <span data-ttu-id="e6a8c-137">IDN aktiviert = None</span><span class="sxs-lookup"><span data-stu-id="e6a8c-137">idn enabled = None</span></span>  
  
     <span data-ttu-id="e6a8c-138">Mit diesem Wert werden keine Unicode-Domänen Namen in Punycode konvertiert.</span><span class="sxs-lookup"><span data-stu-id="e6a8c-138">This value will not convert any Unicode domain names to use Punycode.</span></span> <span data-ttu-id="e6a8c-139">Dies ist der Standardwert, der mit dem .NET Framework 2,0-Verhalten konsistent ist.</span><span class="sxs-lookup"><span data-stu-id="e6a8c-139">This is the default value which is consistent with the .NET Framework 2.0 behaviour.</span></span>  
  
 <span data-ttu-id="e6a8c-140">Beim Aktivieren von IDN werden alle Unicode-Bezeichnungen in einem Domänennamen in ihre Punycode-Entsprechungen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="e6a8c-140">Enabling IDN will convert all Unicode labels in a domain name to their Punycode equivalents.</span></span> <span data-ttu-id="e6a8c-141">Punycode-Namen enthalten nur ASCII-Zeichen und beginnen immer mit dem Präfix „xn--“.</span><span class="sxs-lookup"><span data-stu-id="e6a8c-141">Punycode names contain only ASCII characters and always start with the xn-- prefix.</span></span> <span data-ttu-id="e6a8c-142">So werden vorhandene DNS-Server im Internet unterstützt, da die meisten DNS-Server nur ASCII-Zeichen unterstützen (siehe RFC 3940).</span><span class="sxs-lookup"><span data-stu-id="e6a8c-142">The reason for this is to support existing DNS servers on the Internet, since most DNS servers only support ASCII characters (see RFC 3940).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="e6a8c-143">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="e6a8c-143">Configuration Files</span></span>  
 <span data-ttu-id="e6a8c-144">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e6a8c-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6a8c-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e6a8c-145">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="e6a8c-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6a8c-146">Description</span></span>  
 <span data-ttu-id="e6a8c-147">Das folgende Beispiel zeigt eine Konfiguration, die von <xref:System.Uri> der-Klasse zur Unterstützung der IRI-Verarbeitung und IDN-Namen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e6a8c-147">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e6a8c-148">Code</span><span class="sxs-lookup"><span data-stu-id="e6a8c-148">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6a8c-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6a8c-149">See also</span></span>

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="e6a8c-150">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="e6a8c-150">Network Settings Schema</span></span>](index.md)
