---
title: <remove>-Element für schemeSettings (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: 4095ba51-de20-4f87-b562-018abe422c91
ms.openlocfilehash: 018a08693a39bb297bdaa468ba59d4bf097f6922
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151388"
---
# <a name="remove-element-for-schemesettings-uri-settings"></a><span data-ttu-id="70746-102">\<remove>-Element für schemeSettings (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="70746-102">\<remove> Element for schemeSettings (Uri Settings)</span></span>

<span data-ttu-id="70746-103">Entfernt eine Schema Einstellung für einen Schema Namen.</span><span class="sxs-lookup"><span data-stu-id="70746-103">Removes a scheme setting for a scheme name.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="70746-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="70746-104">Syntax</span></span>  
  
```xml  
<remove
  name="http|https"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70746-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="70746-105">Attributes and Elements</span></span>  

 <span data-ttu-id="70746-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="70746-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70746-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="70746-107">Attributes</span></span>  
  
|<span data-ttu-id="70746-108">attribute</span><span class="sxs-lookup"><span data-stu-id="70746-108">Attribute</span></span>|<span data-ttu-id="70746-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70746-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="70746-110">name</span><span class="sxs-lookup"><span data-stu-id="70746-110">name</span></span>|<span data-ttu-id="70746-111">Der Name des Schemas, für das diese Einstellung gilt.</span><span class="sxs-lookup"><span data-stu-id="70746-111">The scheme name for which this setting applies.</span></span> <span data-ttu-id="70746-112">Die einzigen unterstützten Werte sind Name = "http" und Name = "https".</span><span class="sxs-lookup"><span data-stu-id="70746-112">The only supported values are name="http" and name="https".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="70746-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="70746-113">Child Elements</span></span>  

 <span data-ttu-id="70746-114">Keine</span><span class="sxs-lookup"><span data-stu-id="70746-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="70746-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="70746-115">Parent Elements</span></span>  
  
|<span data-ttu-id="70746-116">Element</span><span class="sxs-lookup"><span data-stu-id="70746-116">Element</span></span>|<span data-ttu-id="70746-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70746-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="70746-118">\<schemeSettings> -Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="70746-118">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="70746-119">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="70746-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70746-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="70746-120">Remarks</span></span>  

 <span data-ttu-id="70746-121">Standardmäßig werden von der- <xref:System.Uri?displayProperty=nameWithType> Klasse in Prozent codierte Pfad Trennzeichen vor dem Ausführen der Pfad Komprimierung aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="70746-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="70746-122">Dies wurde als Sicherheitsmechanismus gegen Angriffe wie die folgende implementiert:</span><span class="sxs-lookup"><span data-stu-id="70746-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="70746-123">Wenn dieser URI an Module übermittelt wird, die Prozent codierte Zeichen nicht ordnungsgemäß verarbeiten, kann dies dazu führen, dass der folgende Befehl vom Server ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="70746-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="70746-124">Aus diesem Grund werden von der-Klasse zuerst Pfad Trennzeichen aufgehoben, <xref:System.Uri?displayProperty=nameWithType> und anschließend wird die Pfad Komprimierung angewendet.</span><span class="sxs-lookup"><span data-stu-id="70746-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="70746-125">Das Ergebnis der Übergabe der obigen bösartigen URL an den <xref:System.Uri?displayProperty=nameWithType> Klassenkonstruktor führt zum folgenden URI:</span><span class="sxs-lookup"><span data-stu-id="70746-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="70746-126">Dieses Standardverhalten kann so geändert werden, dass keine Escapezeichen für Prozent codierte Pfad Trennzeichen verwendet werden, indem die SchemeSettings-Konfigurationsoption für ein bestimmtes Schema verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="70746-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="70746-127">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="70746-127">Configuration Files</span></span>  

 <span data-ttu-id="70746-128">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="70746-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="70746-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="70746-129">Example</span></span>  

 <span data-ttu-id="70746-130">Das folgende Beispiel zeigt eine Konfiguration, die von der-Klasse verwendet wird, mit der <xref:System.Uri> alle Schema Einstellungen für das http-Schema entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="70746-130">The following example shows a configuration used by the <xref:System.Uri> class that removes any scheme settings for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <remove name="http"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="70746-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="70746-131">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="70746-132">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="70746-132">Network Settings Schema</span></span>](index.md)
