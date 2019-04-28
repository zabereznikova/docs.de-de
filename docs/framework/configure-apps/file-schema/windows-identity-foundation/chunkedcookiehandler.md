---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: d9c81d5de7bea343f0d67fa00037763fbae7b8c5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667339"
---
# <a name="chunkedcookiehandler"></a><span data-ttu-id="7ecb7-101">\<chunkedCookieHandler></span><span class="sxs-lookup"><span data-stu-id="7ecb7-101">\<chunkedCookieHandler></span></span>
<span data-ttu-id="7ecb7-102">Konfiguriert die <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span><span class="sxs-lookup"><span data-stu-id="7ecb7-102">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="7ecb7-103">Dieses Element kann nur vorhanden sein, wenn die `mode` Attribut der `<cookieHandler>` -Element ist "Default" oder "Aufgeteilte".</span><span class="sxs-lookup"><span data-stu-id="7ecb7-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
 <span data-ttu-id="7ecb7-104">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="7ecb7-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="7ecb7-105">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="7ecb7-105">\<federationConfiguration></span></span>  
<span data-ttu-id="7ecb7-106">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="7ecb7-106">\<cookieHandler></span></span>  
<span data-ttu-id="7ecb7-107">\<chunkedCookieHandler></span><span class="sxs-lookup"><span data-stu-id="7ecb7-107">\<chunkedCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ecb7-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ecb7-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ecb7-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7ecb7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7ecb7-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7ecb7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ecb7-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="7ecb7-111">Attributes</span></span>  
  
|<span data-ttu-id="7ecb7-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="7ecb7-112">Attribute</span></span>|<span data-ttu-id="7ecb7-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ecb7-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7ecb7-114">ChunkSize</span><span class="sxs-lookup"><span data-stu-id="7ecb7-114">chunkSize</span></span>|<span data-ttu-id="7ecb7-115">Die maximale Größe in Zeichen, die HTTP-Cookie-Daten für alle eine HTTP-Cookie.</span><span class="sxs-lookup"><span data-stu-id="7ecb7-115">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="7ecb7-116">Sie müssen Sie vorsichtig, wenn die Blockgröße anpassen können.</span><span class="sxs-lookup"><span data-stu-id="7ecb7-116">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="7ecb7-117">Webbrowser haben verschiedene Grenzwerte auf der Größe des Cookies und die Anzahl der pro Domäne zulässig.</span><span class="sxs-lookup"><span data-stu-id="7ecb7-117">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="7ecb7-118">Die ursprüngliche Netscape-Spezifikation senkendatenquelle z. B. diese Grenzwerte: 300 Cookies insgesamt maximal 4096 Bytes pro Cookie-Header (einschließlich Metadaten, nicht nur den Cookiewert) und 20 Cookies pro Domäne.</span><span class="sxs-lookup"><span data-stu-id="7ecb7-118">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="7ecb7-119">Der Standardwert ist 2000.</span><span class="sxs-lookup"><span data-stu-id="7ecb7-119">The default is 2000.</span></span> <span data-ttu-id="7ecb7-120">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7ecb7-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7ecb7-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7ecb7-121">Child Elements</span></span>  
 <span data-ttu-id="7ecb7-122">Keiner</span><span class="sxs-lookup"><span data-stu-id="7ecb7-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7ecb7-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7ecb7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7ecb7-124">Element</span><span class="sxs-lookup"><span data-stu-id="7ecb7-124">Element</span></span>|<span data-ttu-id="7ecb7-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ecb7-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7ecb7-126">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="7ecb7-126">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="7ecb7-127">Konfiguriert die <xref:System.IdentityModel.Services.CookieHandler> , die die <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) zum Lesen und Schreiben von Cookies verwendet.</span><span class="sxs-lookup"><span data-stu-id="7ecb7-127">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ecb7-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7ecb7-128">Remarks</span></span>  
 <span data-ttu-id="7ecb7-129">Beim Angeben von eine <xref:System.IdentityModel.Services.ChunkedCookieHandler> durch Festlegen der `mode` Attribut der `<cookieHandler>` "Default" oder "Chunked"-Element geben Sie die Blockgröße, die der cookiehandler verwendet wird, zum Lesen und Schreiben von Cookies durch Einschließen einer `<chunkedCookieHandler>` untergeordnetes Element und Festlegen der `chunkSize` Attribut.</span><span class="sxs-lookup"><span data-stu-id="7ecb7-129">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="7ecb7-130">Wenn die `<chunkedCookieHandler>` Element ist nicht vorhanden, wird die standardmäßige Segmentgröße von 2000 Bytes verwendet.</span><span class="sxs-lookup"><span data-stu-id="7ecb7-130">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="7ecb7-131">Dieses Element nicht angegeben, wenn die `mode` -Attribut auf "Custom" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7ecb7-131">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="7ecb7-132">Die `<chunkedCookieHandler>` Element wird dargestellt, durch die <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> Klasse.</span><span class="sxs-lookup"><span data-stu-id="7ecb7-132">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ecb7-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7ecb7-133">Example</span></span>  
 <span data-ttu-id="7ecb7-134">Im folgenden Beispiel wird einen segmentierten cookiehandler, der Cookies in Blöcken von 3000 Bytes schreibt.</span><span class="sxs-lookup"><span data-stu-id="7ecb7-134">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7ecb7-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ecb7-135">See also</span></span>

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
