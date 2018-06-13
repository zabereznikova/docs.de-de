---
title: '&lt;chunkedCookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 193b783e44fe4386d3575e180dc5baa6a7f9a8be
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758372"
---
# <a name="ltchunkedcookiehandlergt"></a><span data-ttu-id="7841e-102">&lt;chunkedCookieHandler&gt;</span><span class="sxs-lookup"><span data-stu-id="7841e-102">&lt;chunkedCookieHandler&gt;</span></span>
<span data-ttu-id="7841e-103">Konfiguriert die <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span><span class="sxs-lookup"><span data-stu-id="7841e-103">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="7841e-104">Dieses Element kann nur vorhanden sein, wenn die `mode` Attribut des der `<cookieHandler>` Element ist "Default" oder "Aufgeteilte".</span><span class="sxs-lookup"><span data-stu-id="7841e-104">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
 <span data-ttu-id="7841e-105">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="7841e-105">\<system.identityModel.services></span></span>  
<span data-ttu-id="7841e-106">\<FederationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="7841e-106">\<federationConfiguration></span></span>  
<span data-ttu-id="7841e-107">\<"cookiehandler" ></span><span class="sxs-lookup"><span data-stu-id="7841e-107">\<cookieHandler></span></span>  
<span data-ttu-id="7841e-108">\<ChunkedCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="7841e-108">\<chunkedCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7841e-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="7841e-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7841e-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7841e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7841e-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7841e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7841e-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="7841e-112">Attributes</span></span>  
  
|<span data-ttu-id="7841e-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="7841e-113">Attribute</span></span>|<span data-ttu-id="7841e-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7841e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7841e-115">chunkSize</span><span class="sxs-lookup"><span data-stu-id="7841e-115">chunkSize</span></span>|<span data-ttu-id="7841e-116">Die maximale Größe in Zeichen, die HTTP-Cookie-Daten für alle HTTP-Cookie.</span><span class="sxs-lookup"><span data-stu-id="7841e-116">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="7841e-117">Sie müssen vorsichtig Segmentgröße anpassen können.</span><span class="sxs-lookup"><span data-stu-id="7841e-117">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="7841e-118">Webbrowser haben verschiedene Grenzwerte auf die Größe des Cookies und Anzahl pro Domäne zulässig.</span><span class="sxs-lookup"><span data-stu-id="7841e-118">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="7841e-119">Die ursprünglichen Netscape-Spezifikation vorgesehenen z. B. diese Grenzwerte: 300 Cookies addieren, 4096 Bytes pro Cookie-Header (einschließlich Metadaten, nicht nur den Cookiewert) und 20 Cookies pro Domäne.</span><span class="sxs-lookup"><span data-stu-id="7841e-119">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="7841e-120">Der Standardwert ist 2000.</span><span class="sxs-lookup"><span data-stu-id="7841e-120">The default is 2000.</span></span> <span data-ttu-id="7841e-121">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7841e-121">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7841e-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7841e-122">Child Elements</span></span>  
 <span data-ttu-id="7841e-123">Keiner</span><span class="sxs-lookup"><span data-stu-id="7841e-123">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7841e-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7841e-124">Parent Elements</span></span>  
  
|<span data-ttu-id="7841e-125">Element</span><span class="sxs-lookup"><span data-stu-id="7841e-125">Element</span></span>|<span data-ttu-id="7841e-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7841e-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7841e-127">\<"cookiehandler" ></span><span class="sxs-lookup"><span data-stu-id="7841e-127">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="7841e-128">Konfiguriert die <xref:System.IdentityModel.Services.CookieHandler> , die die <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) zum Lesen und Schreiben von Cookies verwendet.</span><span class="sxs-lookup"><span data-stu-id="7841e-128">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7841e-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7841e-129">Remarks</span></span>  
 <span data-ttu-id="7841e-130">Geben Sie bei einer <xref:System.IdentityModel.Services.ChunkedCookieHandler> durch Festlegen der `mode` Attribut des der `<cookieHandler>` Element "Default" oder "Chunked", Sie können die Blockgröße, die der Cookie-Handler verwendet wird, zum Lesen und Schreiben von Cookies durch einschließen angeben eine `<chunkedCookieHandler>` untergeordnetes Element und Festlegen der `chunkSize` Attribut.</span><span class="sxs-lookup"><span data-stu-id="7841e-130">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="7841e-131">Wenn die `<chunkedCookieHandler>` -Element nicht vorhanden ist, wird die Standardblockgröße 2000 Bytes verwendet.</span><span class="sxs-lookup"><span data-stu-id="7841e-131">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="7841e-132">Dieses Element nicht angegeben, wann die `mode` -Attribut auf "Custom" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7841e-132">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="7841e-133">Die `<chunkedCookieHandler>` Element dargestellt ist, durch die <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> Klasse.</span><span class="sxs-lookup"><span data-stu-id="7841e-133">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7841e-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7841e-134">Example</span></span>  
 <span data-ttu-id="7841e-135">Das folgende Beispiel konfiguriert einen aufgeteilte Cookie-Handler, der Cookies in Abschnitten von 3000 Bytes schreibt.</span><span class="sxs-lookup"><span data-stu-id="7841e-135">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7841e-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7841e-136">See Also</span></span>  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>
