---
title: <idn>-Element (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
ms.openlocfilehash: 533b2562f6e5c8d6c2bf452e56dff9a8bf8ab376
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "71698162"
---
# <a name="idn-element-uri-settings"></a><span data-ttu-id="84e97-102">\<idn>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="84e97-102">\<idn> Element (Uri Settings)</span></span>

<span data-ttu-id="84e97-103">Gibt an, ob die IDN (Internationalized Domain Name)-Verarbeitung auf einen Domänen Namen angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="84e97-103">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name.</span></span>
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<idn>**  
  
## <a name="syntax"></a><span data-ttu-id="84e97-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="84e97-104">Syntax</span></span>  
  
```xml
<idn
  enabled="All|AllExceptIntranet|None"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="84e97-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="84e97-105">Attributes and Elements</span></span>  
 <span data-ttu-id="84e97-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="84e97-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="84e97-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="84e97-107">Attributes</span></span>  

|<span data-ttu-id="84e97-108">**Element**</span><span class="sxs-lookup"><span data-stu-id="84e97-108">**Element**</span></span>|<span data-ttu-id="84e97-109">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="84e97-109">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="84e97-110">Gibt an, ob die IDN (Internationalized Domain Name)-Verarbeitung auf einen Domänen Namen angewendet wird. der Standardwert ist "None".</span><span class="sxs-lookup"><span data-stu-id="84e97-110">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name The default value is none.</span></span>|  

### <a name="child-elements"></a><span data-ttu-id="84e97-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="84e97-111">Child elements</span></span>

<span data-ttu-id="84e97-112">Keine</span><span class="sxs-lookup"><span data-stu-id="84e97-112">None</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="84e97-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="84e97-113">Parent elements</span></span>

|<span data-ttu-id="84e97-114">**Element**</span><span class="sxs-lookup"><span data-stu-id="84e97-114">**Element**</span></span>|<span data-ttu-id="84e97-115">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="84e97-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="84e97-116">uri</span><span class="sxs-lookup"><span data-stu-id="84e97-116">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="84e97-117">Enthält Einstellungen, die angeben, wie die .NET Framework Webadressen verarbeitet, die mithilfe von URIs (Uniform Resource Identifier) ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="84e97-117">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  

## <a name="remarks"></a><span data-ttu-id="84e97-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="84e97-118">Remarks</span></span>

<span data-ttu-id="84e97-119">Die vorhandene <xref:System.Uri> Klasse wurde in .NET Framework 3,5 erweitert.</span><span class="sxs-lookup"><span data-stu-id="84e97-119">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="84e97-120">3,0 SP1 und 2,0 SP1 mit Unterstützung für International Resource Identifier (IRI) und Internationalized Domain Names (IDN).</span><span class="sxs-lookup"><span data-stu-id="84e97-120">3.0 SP1, and 2.0 SP1 with support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="84e97-121">Aktuelle Benutzer sehen keine Änderung des Verhaltens von .NET Framework 2,0, es sei denn, Sie aktivieren speziell IRI-und IDN-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="84e97-121">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="84e97-122">Dadurch wird die Anwendungskompatibilität mit früheren Versionen von .NET Framework garantiert.</span><span class="sxs-lookup"><span data-stu-id="84e97-122">This ensures application compatibility with prior versions of the .NET Framework.</span></span>

<span data-ttu-id="84e97-123">Die folgenden beiden Änderungen sind erforderlich, um die Unterstützung für IRI zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="84e97-123">To enable support for IRI, the following two changes are required:</span></span>

1. <span data-ttu-id="84e97-124">Fügen Sie der Datei Machine. config im Verzeichnis .NET Framework 2,0 die folgende Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="84e97-124">Add the following line to the machine.config file under the .NET Framework 2.0 directory:</span></span>
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="84e97-125">Geben Sie an, ob die IDN-Verarbeitung (Internationalized Domain Name) auf den Domänen Namen angewendet werden soll und ob IRI-Regeln angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="84e97-125">Specify whether you want Internationalized Domain Name (IDN) parsing applied to the domain name and whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="84e97-126">Dies kann in der Datei „machine.config“ oder in der Datei „App.config“ durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="84e97-126">This can be done in the machine.config or in the app.config file.</span></span>

 <span data-ttu-id="84e97-127">Es gibt drei mögliche Werte für IDN, abhängig von den verwendeten DNS-Servern:</span><span class="sxs-lookup"><span data-stu-id="84e97-127">There are three possible values for IDN depending on the DNS servers that are used:</span></span>

- <span data-ttu-id="84e97-128">IDN aktiviert = alle</span><span class="sxs-lookup"><span data-stu-id="84e97-128">idn enabled = All</span></span>  

     <span data-ttu-id="84e97-129">Durch diesen Wert werden alle Unicode-Domänennamen in ihre Punycode-Entsprechungen (IDN-Namen) konvertiert.</span><span class="sxs-lookup"><span data-stu-id="84e97-129">This value will convert any Unicode domain names to their Punycode equivalents (IDN names).</span></span>

- <span data-ttu-id="84e97-130">IDN aktiviert = AllExceptIntranet</span><span class="sxs-lookup"><span data-stu-id="84e97-130">idn enabled = AllExceptIntranet</span></span>

     <span data-ttu-id="84e97-131">Dieser Wert konvertiert alle Unicode-Domänen Namen, die nicht im lokalen Intranet sind, in die Verwendung der Punycode-Entsprechungen (IDN-Namen).</span><span class="sxs-lookup"><span data-stu-id="84e97-131">This value will convert all Unicode domain names not on the local Intranet to use the Punycode equivalents (IDN names).</span></span> <span data-ttu-id="84e97-132">In diesem Fall sollten die DNS-Server, die für das Intranet verwendet werden, die Auflösung von Unicode-Namen unterstützen, um internationale Namen im lokalen Intranet zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="84e97-132">In this case to handle international names on the local Intranet, the DNS servers that are used for the Intranet should support Unicode name resolution.</span></span>

- <span data-ttu-id="84e97-133">IDN aktiviert = None</span><span class="sxs-lookup"><span data-stu-id="84e97-133">idn enabled = None</span></span>

     <span data-ttu-id="84e97-134">Durch diesen Wert werden keine Unicode-Domänennamen in ihre Punycode-Entsprechungen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="84e97-134">This value will not convert any Unicode domain names to use Punycode.</span></span> <span data-ttu-id="84e97-135">Dies ist der Standardwert, der dem .NET Framework 2.0-Verhalten entspricht.</span><span class="sxs-lookup"><span data-stu-id="84e97-135">This is the default value which is consistent with the .NET Framework 2.0 behavior.</span></span>

 <span data-ttu-id="84e97-136">Beim Aktivieren von IDN werden alle Unicode-Bezeichnungen in einem Domänennamen in ihre Punycode-Entsprechungen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="84e97-136">Enabling IDN will convert all Unicode labels in a domain name to their Punycode equivalents.</span></span> <span data-ttu-id="84e97-137">Punycode-Namen enthalten nur ASCII-Zeichen und beginnen immer mit dem Präfix „xn--“.</span><span class="sxs-lookup"><span data-stu-id="84e97-137">Punycode names contain only ASCII characters and always start with the xn-- prefix.</span></span> <span data-ttu-id="84e97-138">So werden vorhandene DNS-Server im Internet unterstützt, da die meisten DNS-Server nur ASCII-Zeichen unterstützen (siehe RFC 3940).</span><span class="sxs-lookup"><span data-stu-id="84e97-138">The reason for this is to support existing DNS servers on the Internet, since most DNS servers only support ASCII characters (see RFC 3940).</span></span>

### <a name="configuration-files"></a><span data-ttu-id="84e97-139">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="84e97-139">Configuration files</span></span>

<span data-ttu-id="84e97-140">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="84e97-140">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>

## <a name="example"></a><span data-ttu-id="84e97-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="84e97-141">Example</span></span>

<span data-ttu-id="84e97-142">Das folgende Beispiel zeigt eine Konfiguration, die von der- <xref:System.Uri> Klasse zur Unterstützung der IRI-Verarbeitung und IDN-Namen verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="84e97-142">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names:</span></span>

```xml
<configuration>
  <uri>
    <idn enabled="All" />
    <iriParsing enabled="true" />
  </uri>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="84e97-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="84e97-143">See also</span></span>

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="84e97-144">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="84e97-144">Network Settings Schema</span></span>](index.md)
