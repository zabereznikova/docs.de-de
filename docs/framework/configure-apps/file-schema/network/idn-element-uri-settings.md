---
title: <idn>-Element (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
ms.openlocfilehash: 2d2729f9120d6b6fe673904ad2bf6d005ddf5469
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705107"
---
# <a name="idn-element-uri-settings"></a><span data-ttu-id="0e2c3-102">\<IDN >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="0e2c3-102">\<idn> Element (Uri Settings)</span></span>
<span data-ttu-id="0e2c3-103">Gibt an, ob es sich bei Analyse Internationalized Domain Name (IDN) an den Domänennamen angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="0e2c3-103">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="0e2c3-104">Schemahierarchie</span><span class="sxs-lookup"><span data-stu-id="0e2c3-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="0e2c3-105">\<configuration> Element</span><span class="sxs-lookup"><span data-stu-id="0e2c3-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="0e2c3-106">\<URI >-Elements (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="0e2c3-106">\<Uri> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [<span data-ttu-id="0e2c3-107">\<idn></span><span class="sxs-lookup"><span data-stu-id="0e2c3-107">\<idn></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="0e2c3-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e2c3-108">Syntax</span></span>  
  
```xml  
<idn  
  enabled="All|AllExceptIntranet|None"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e2c3-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0e2c3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0e2c3-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0e2c3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e2c3-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="0e2c3-111">Attributes</span></span>  
  
|<span data-ttu-id="0e2c3-112">**Element**</span><span class="sxs-lookup"><span data-stu-id="0e2c3-112">**Element**</span></span>|<span data-ttu-id="0e2c3-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="0e2c3-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="0e2c3-114">Gibt an, wenn Internationalized Domain Name (IDN) Analyse an den Domänennamen angewendet wird der Standardwert none ist.</span><span class="sxs-lookup"><span data-stu-id="0e2c3-114">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name The default value is none.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e2c3-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0e2c3-115">Child Elements</span></span>  
 <span data-ttu-id="0e2c3-116">Keiner</span><span class="sxs-lookup"><span data-stu-id="0e2c3-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0e2c3-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0e2c3-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0e2c3-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="0e2c3-118">**Element**</span></span>|<span data-ttu-id="0e2c3-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="0e2c3-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0e2c3-120">uri</span><span class="sxs-lookup"><span data-stu-id="0e2c3-120">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="0e2c3-121">Enthält Einstellungen, die angeben, wie .NET Framework Webadressen, die mithilfe von uniform Resource Identifier (URIs) ausgedrückt verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="0e2c3-121">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e2c3-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0e2c3-122">Remarks</span></span>  
 <span data-ttu-id="0e2c3-123">Die vorhandene <xref:System.Uri> Klasse in .NET Framework 3.5 erweitert wurde.</span><span class="sxs-lookup"><span data-stu-id="0e2c3-123">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="0e2c3-124">3.0 SP1 und 2.0 SP1 mit Unterstützung von International Resource Identifiers (IRI) und internationale Domänennamen (IDN).</span><span class="sxs-lookup"><span data-stu-id="0e2c3-124">3.0 SP1, and 2.0 SP1 with support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="0e2c3-125">Derzeitige Benutzer werden keine Änderung gegenüber dem .NET Framework 2.0-Verhalten feststellen, es sei denn, sie IRI und IDN explizit aktivieren unterstützen.</span><span class="sxs-lookup"><span data-stu-id="0e2c3-125">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="0e2c3-126">Dadurch wird die Anwendungskompatibilität mit früheren Versionen von .NET Framework garantiert.</span><span class="sxs-lookup"><span data-stu-id="0e2c3-126">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="0e2c3-127">Um die IRI-Unterstützung aktivieren, müssen die folgenden beiden Änderungen vornehmen:</span><span class="sxs-lookup"><span data-stu-id="0e2c3-127">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="0e2c3-128">Fügen Sie die folgende Zeile in die Datei "Machine.config" im .NET Framework 2.0-Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="0e2c3-128">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="0e2c3-129">Geben Sie, ob Sie möchten, dass Internationalized Domain Name (IDN) zu analysieren, die für den Domänennamen angewendet und gibt an, ob die IRI-Analyseregeln angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0e2c3-129">Specify whether you want Internationalized Domain Name (IDN) parsing applied to the domain name and whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="0e2c3-130">Dies kann in der Datei „machine.config“ oder in der Datei „App.config“ durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0e2c3-130">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="0e2c3-131">Es gibt drei mögliche Werte für IDN, die abhängig von den DNS-Servern, die verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="0e2c3-131">There are three possible values for IDN depending on the DNS servers that are used:</span></span>  
  
- <span data-ttu-id="0e2c3-132">IDN aktiviert = All</span><span class="sxs-lookup"><span data-stu-id="0e2c3-132">idn enabled = All</span></span>  
  
     <span data-ttu-id="0e2c3-133">Dieser Wert werden alle Unicode-Domänennamen in ihre Punycode-Entsprechungen (IDN-Namen) konvertiert.</span><span class="sxs-lookup"><span data-stu-id="0e2c3-133">This value will convert any Unicode domain names to their Punycode equivalents (IDN names).</span></span>  
  
- <span data-ttu-id="0e2c3-134">IDN aktiviert = AllExceptIntranet</span><span class="sxs-lookup"><span data-stu-id="0e2c3-134">idn enabled = AllExceptIntranet</span></span>  
  
     <span data-ttu-id="0e2c3-135">Diesen Wert werden alle Unicode-Domänennamen nicht auf dem lokalen Intranet verwenden Sie die Punycode-Entsprechungen (IDN-Namen) konvertiert.</span><span class="sxs-lookup"><span data-stu-id="0e2c3-135">This value will convert all Unicode domain names not on the local Intranet to use the Punycode equivalents (IDN names).</span></span> <span data-ttu-id="0e2c3-136">In diesem Fall sollte Wenn internationale Namen im lokalen Intranet verarbeitet, unterstützen die DNS-Server, die für das Intranet verwendet werden Unicode-namensauflösung.</span><span class="sxs-lookup"><span data-stu-id="0e2c3-136">In this case to handle international names on the local Intranet, the DNS servers that are used for the Intranet should support Unicode name resolution.</span></span>  
  
- <span data-ttu-id="0e2c3-137">IDN aktiviert = keine</span><span class="sxs-lookup"><span data-stu-id="0e2c3-137">idn enabled = None</span></span>  
  
     <span data-ttu-id="0e2c3-138">Dieser Wert wird nicht auf Unicode-Domänennamen auf Ihre Punycode-Entsprechungen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="0e2c3-138">This value will not convert any Unicode domain names to use Punycode.</span></span> <span data-ttu-id="0e2c3-139">Dies ist der Standardwert, der das .NET Framework 2.0-Verhalten entspricht.</span><span class="sxs-lookup"><span data-stu-id="0e2c3-139">This is the default value which is consistent with the .NET Framework 2.0 behaviour.</span></span>  
  
 <span data-ttu-id="0e2c3-140">Beim Aktivieren von IDN werden alle Unicode-Bezeichnungen in einem Domänennamen in ihre Punycode-Entsprechungen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="0e2c3-140">Enabling IDN will convert all Unicode labels in a domain name to their Punycode equivalents.</span></span> <span data-ttu-id="0e2c3-141">Punycode-Namen enthalten nur ASCII-Zeichen und beginnen immer mit dem Präfix „xn--“.</span><span class="sxs-lookup"><span data-stu-id="0e2c3-141">Punycode names contain only ASCII characters and always start with the xn-- prefix.</span></span> <span data-ttu-id="0e2c3-142">So werden vorhandene DNS-Server im Internet unterstützt, da die meisten DNS-Server nur ASCII-Zeichen unterstützen (siehe RFC 3940).</span><span class="sxs-lookup"><span data-stu-id="0e2c3-142">The reason for this is to support existing DNS servers on the Internet, since most DNS servers only support ASCII characters (see RFC 3940).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="0e2c3-143">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="0e2c3-143">Configuration Files</span></span>  
 <span data-ttu-id="0e2c3-144">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0e2c3-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e2c3-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0e2c3-145">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="0e2c3-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e2c3-146">Description</span></span>  
 <span data-ttu-id="0e2c3-147">Das folgende Beispiel zeigt eine Konfiguration, die von verwendet die <xref:System.Uri> Klasse Analysieren von IRI und IDN-Namen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0e2c3-147">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="0e2c3-148">Code</span><span class="sxs-lookup"><span data-stu-id="0e2c3-148">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0e2c3-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e2c3-149">See also</span></span>

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="0e2c3-150">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="0e2c3-150">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
