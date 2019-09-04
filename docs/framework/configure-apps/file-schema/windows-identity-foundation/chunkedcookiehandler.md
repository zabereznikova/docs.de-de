---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: 6aad95033b99f1472284f838f3ede2e74ea8324c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252108"
---
# <a name="chunkedcookiehandler"></a><span data-ttu-id="6bec4-101">\<chunkedCookieHandler></span><span class="sxs-lookup"><span data-stu-id="6bec4-101">\<chunkedCookieHandler></span></span>
<span data-ttu-id="6bec4-102">Konfiguriert den <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span><span class="sxs-lookup"><span data-stu-id="6bec4-102">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="6bec4-103">Dieses Element kann nur vorhanden sein, wenn `mode` das-Attribut `<cookieHandler>` des-Elements "Default" oder "Chunked" ist.</span><span class="sxs-lookup"><span data-stu-id="6bec4-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
<span data-ttu-id="6bec4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6bec4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6bec4-105">&nbsp;&nbsp;[ **\<System. IdentityModel. Services->** ](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="6bec4-105">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="6bec4-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<federationconfiguration->** ](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="6bec4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="6bec4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cookiehandler->** ](cookiehandler.md)</span><span class="sxs-lookup"><span data-stu-id="6bec4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)</span></span>\
<span data-ttu-id="6bec4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> von "chunkedcookiehandler"**</span><span class="sxs-lookup"><span data-stu-id="6bec4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<chunkedCookieHandler>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bec4-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="6bec4-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6bec4-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6bec4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6bec4-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6bec4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6bec4-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="6bec4-112">Attributes</span></span>  
  
|<span data-ttu-id="6bec4-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="6bec4-113">Attribute</span></span>|<span data-ttu-id="6bec4-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6bec4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6bec4-115">chunkSize</span><span class="sxs-lookup"><span data-stu-id="6bec4-115">chunkSize</span></span>|<span data-ttu-id="6bec4-116">Die maximale Größe der HTTP-Cookie-Daten für ein beliebiges HTTP-Cookie in Zeichen.</span><span class="sxs-lookup"><span data-stu-id="6bec4-116">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="6bec4-117">Beim Anpassen der Segmentgröße müssen Sie vorsichtig sein.</span><span class="sxs-lookup"><span data-stu-id="6bec4-117">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="6bec4-118">Webbrowser haben unterschiedliche Beschränkungen hinsichtlich der Größe von Cookies und der pro Domäne zulässigen Anzahl.</span><span class="sxs-lookup"><span data-stu-id="6bec4-118">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="6bec4-119">Die ursprüngliche Netscape-Spezifikation hat z. b. diese Limits festgelegt: 300 Cookies Gesamt, 4096 Bytes pro Cookieheader (einschließlich Metadaten, nicht nur der Cookiewert) und 20 Cookies pro Domäne.</span><span class="sxs-lookup"><span data-stu-id="6bec4-119">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="6bec4-120">Der Standardwert ist 2000.</span><span class="sxs-lookup"><span data-stu-id="6bec4-120">The default is 2000.</span></span> <span data-ttu-id="6bec4-121">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6bec4-121">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6bec4-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6bec4-122">Child Elements</span></span>  
 <span data-ttu-id="6bec4-123">None</span><span class="sxs-lookup"><span data-stu-id="6bec4-123">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6bec4-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6bec4-124">Parent Elements</span></span>  
  
|<span data-ttu-id="6bec4-125">Element</span><span class="sxs-lookup"><span data-stu-id="6bec4-125">Element</span></span>|<span data-ttu-id="6bec4-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6bec4-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6bec4-127">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="6bec4-127">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="6bec4-128">Konfiguriert den <xref:System.IdentityModel.Services.CookieHandler> , den der <xref:System.IdentityModel.Services.SessionAuthenticationModule> (Sam) zum Lesen und Schreiben von Cookies verwendet.</span><span class="sxs-lookup"><span data-stu-id="6bec4-128">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6bec4-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6bec4-129">Remarks</span></span>  
 <span data-ttu-id="6bec4-130">Wenn Sie <xref:System.IdentityModel.Services.ChunkedCookieHandler> einen angeben, indem Sie `mode` das-Attribut `<cookieHandler>` des-Elements auf "Default" oder "Chunked" festlegen, können Sie die Segmentgröße angeben, die der cookiehandler zum Lesen und Schreiben von `<chunkedCookieHandler>` Cookies verwendet, indem er ein untergeordnetes Element einschließt. Festlegen des `chunkSize` Attributs.</span><span class="sxs-lookup"><span data-stu-id="6bec4-130">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="6bec4-131">Wenn das `<chunkedCookieHandler>` -Element nicht vorhanden ist, wird die Standard Segmentgröße von 2000 Bytes verwendet.</span><span class="sxs-lookup"><span data-stu-id="6bec4-131">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="6bec4-132">Dieses Element kann nicht angegeben werden, `mode` wenn das-Attribut auf "Custom" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="6bec4-132">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="6bec4-133">Das `<chunkedCookieHandler>` -Element wird durch die <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> -Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6bec4-133">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6bec4-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6bec4-134">Example</span></span>  
 <span data-ttu-id="6bec4-135">Im folgenden Beispiel wird ein segmentierter cookiehandler konfiguriert, der Cookies in Blöcken von 3000 Bytes schreibt.</span><span class="sxs-lookup"><span data-stu-id="6bec4-135">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6bec4-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6bec4-136">See also</span></span>

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
