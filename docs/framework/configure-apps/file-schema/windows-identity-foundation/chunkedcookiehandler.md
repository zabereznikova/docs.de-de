---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: b3b4cf0d7c2748079af7a94534622b1dbadd3ab5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941895"
---
# <a name="chunkedcookiehandler"></a><span data-ttu-id="c18c2-101">\<chunkedCookieHandler></span><span class="sxs-lookup"><span data-stu-id="c18c2-101">\<chunkedCookieHandler></span></span>
<span data-ttu-id="c18c2-102">Konfiguriert den <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span><span class="sxs-lookup"><span data-stu-id="c18c2-102">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="c18c2-103">Dieses Element kann nur vorhanden sein, wenn `mode` das-Attribut `<cookieHandler>` des-Elements "Default" oder "Chunked" ist.</span><span class="sxs-lookup"><span data-stu-id="c18c2-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
 <span data-ttu-id="c18c2-104">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="c18c2-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="c18c2-105">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="c18c2-105">\<federationConfiguration></span></span>  
<span data-ttu-id="c18c2-106">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="c18c2-106">\<cookieHandler></span></span>  
<span data-ttu-id="c18c2-107">\<chunkedCookieHandler></span><span class="sxs-lookup"><span data-stu-id="c18c2-107">\<chunkedCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c18c2-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="c18c2-108">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Chunked||Default" >  
      <chunkedCookieHandler size=xs:int >  
      </chunkedCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c18c2-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c18c2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c18c2-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c18c2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c18c2-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="c18c2-111">Attributes</span></span>  
  
|<span data-ttu-id="c18c2-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="c18c2-112">Attribute</span></span>|<span data-ttu-id="c18c2-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c18c2-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c18c2-114">chunkSize</span><span class="sxs-lookup"><span data-stu-id="c18c2-114">chunkSize</span></span>|<span data-ttu-id="c18c2-115">Die maximale Größe der HTTP-Cookie-Daten für ein beliebiges HTTP-Cookie in Zeichen.</span><span class="sxs-lookup"><span data-stu-id="c18c2-115">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="c18c2-116">Beim Anpassen der Segmentgröße müssen Sie vorsichtig sein.</span><span class="sxs-lookup"><span data-stu-id="c18c2-116">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="c18c2-117">Webbrowser haben unterschiedliche Beschränkungen hinsichtlich der Größe von Cookies und der pro Domäne zulässigen Anzahl.</span><span class="sxs-lookup"><span data-stu-id="c18c2-117">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="c18c2-118">Die ursprüngliche Netscape-Spezifikation hat z. b. diese Limits festgelegt: 300 Cookies Gesamt, 4096 Bytes pro Cookieheader (einschließlich Metadaten, nicht nur der Cookiewert) und 20 Cookies pro Domäne.</span><span class="sxs-lookup"><span data-stu-id="c18c2-118">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="c18c2-119">Der Standardwert ist 2000.</span><span class="sxs-lookup"><span data-stu-id="c18c2-119">The default is 2000.</span></span> <span data-ttu-id="c18c2-120">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c18c2-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c18c2-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c18c2-121">Child Elements</span></span>  
 <span data-ttu-id="c18c2-122">None</span><span class="sxs-lookup"><span data-stu-id="c18c2-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c18c2-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c18c2-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c18c2-124">Element</span><span class="sxs-lookup"><span data-stu-id="c18c2-124">Element</span></span>|<span data-ttu-id="c18c2-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c18c2-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c18c2-126">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="c18c2-126">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="c18c2-127">Konfiguriert den <xref:System.IdentityModel.Services.CookieHandler> , den der <xref:System.IdentityModel.Services.SessionAuthenticationModule> (Sam) zum Lesen und Schreiben von Cookies verwendet.</span><span class="sxs-lookup"><span data-stu-id="c18c2-127">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c18c2-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c18c2-128">Remarks</span></span>  
 <span data-ttu-id="c18c2-129">Wenn Sie <xref:System.IdentityModel.Services.ChunkedCookieHandler> einen angeben, indem Sie `mode` das-Attribut `<cookieHandler>` des-Elements auf "Default" oder "Chunked" festlegen, können Sie die Segmentgröße angeben, die der cookiehandler zum Lesen und Schreiben von `<chunkedCookieHandler>` Cookies verwendet, indem er ein untergeordnetes Element einschließt. Festlegen des `chunkSize` Attributs.</span><span class="sxs-lookup"><span data-stu-id="c18c2-129">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="c18c2-130">Wenn das `<chunkedCookieHandler>` -Element nicht vorhanden ist, wird die Standard Segmentgröße von 2000 Bytes verwendet.</span><span class="sxs-lookup"><span data-stu-id="c18c2-130">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="c18c2-131">Dieses Element kann nicht angegeben werden, `mode` wenn das-Attribut auf "Custom" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c18c2-131">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="c18c2-132">Das `<chunkedCookieHandler>` -Element wird durch die <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> -Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c18c2-132">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c18c2-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c18c2-133">Example</span></span>  
 <span data-ttu-id="c18c2-134">Im folgenden Beispiel wird ein segmentierter cookiehandler konfiguriert, der Cookies in Blöcken von 3000 Bytes schreibt.</span><span class="sxs-lookup"><span data-stu-id="c18c2-134">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c18c2-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c18c2-135">See also</span></span>

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
