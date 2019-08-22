---
title: <httpWebRequest>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
ms.openlocfilehash: de5672e5c6762b1e0742e717a3d499a4f93ee8ec
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659343"
---
# <a name="httpwebrequest-element-network-settings"></a><span data-ttu-id="e29d7-102">\<HttpWebRequest >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="e29d7-102">\<httpWebRequest> Element (Network Settings)</span></span>
<span data-ttu-id="e29d7-103">Passt Webanforderungs Parameter an.</span><span class="sxs-lookup"><span data-stu-id="e29d7-103">Customizes Web request parameters.</span></span>  
  
 <span data-ttu-id="e29d7-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e29d7-104">\<configuration></span></span>  
<span data-ttu-id="e29d7-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="e29d7-105">\<system.net></span></span>  
<span data-ttu-id="e29d7-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="e29d7-106">\<settings></span></span>  
<span data-ttu-id="e29d7-107">\<httpWebRequest></span><span class="sxs-lookup"><span data-stu-id="e29d7-107">\<httpWebRequest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e29d7-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="e29d7-108">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e29d7-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e29d7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e29d7-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e29d7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e29d7-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="e29d7-111">Attributes</span></span>  
  
|<span data-ttu-id="e29d7-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="e29d7-112">**Attribute**</span></span>|<span data-ttu-id="e29d7-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e29d7-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="e29d7-114">Gibt die maximale Länge eines Antwort Headers in Kilobyte an.</span><span class="sxs-lookup"><span data-stu-id="e29d7-114">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="e29d7-115">Der Standard ist 64.</span><span class="sxs-lookup"><span data-stu-id="e29d7-115">The default is 64.</span></span> <span data-ttu-id="e29d7-116">Der Wert-1 gibt an, dass keine Größenbeschränkung für die Antwortheader festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="e29d7-116">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="e29d7-117">Gibt die maximale Länge einer Fehler Antwort in Kilobyte an.</span><span class="sxs-lookup"><span data-stu-id="e29d7-117">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="e29d7-118">Der Standard ist 64.</span><span class="sxs-lookup"><span data-stu-id="e29d7-118">The default is 64.</span></span> <span data-ttu-id="e29d7-119">Der Wert-1 gibt an, dass für die Fehler Antwort keine Größenbeschränkung festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="e29d7-119">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="e29d7-120">Gibt die maximale Länge eines Uploads als Reaktion auf einen nicht autorisierten Fehlercode in Bytes an.</span><span class="sxs-lookup"><span data-stu-id="e29d7-120">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="e29d7-121">Der Standard ist -1.</span><span class="sxs-lookup"><span data-stu-id="e29d7-121">The default is -1.</span></span> <span data-ttu-id="e29d7-122">Der Wert-1 gibt an, dass keine Größenbeschränkung für den Upload festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="e29d7-122">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="e29d7-123">Gibt an, ob die unsichere Header-Verarbeitung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e29d7-123">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="e29d7-124">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="e29d7-124">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e29d7-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e29d7-125">Child Elements</span></span>  
 <span data-ttu-id="e29d7-126">Keine</span><span class="sxs-lookup"><span data-stu-id="e29d7-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e29d7-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e29d7-127">Parent Elements</span></span>  
  
|<span data-ttu-id="e29d7-128">**Element**</span><span class="sxs-lookup"><span data-stu-id="e29d7-128">**Element**</span></span>|<span data-ttu-id="e29d7-129">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e29d7-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e29d7-130">settings</span><span class="sxs-lookup"><span data-stu-id="e29d7-130">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="e29d7-131">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="e29d7-131">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e29d7-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e29d7-132">Remarks</span></span>  
 <span data-ttu-id="e29d7-133">Standardmäßig erzwingt das .NET Framework nur RFC 2616 für die URI-Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="e29d7-133">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="e29d7-134">Einige Server Antworten können Steuerzeichen in unzulässigen Feldern enthalten, die bewirken, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> dass die-Methode <xref:System.Net.WebException>eine auslöst.</span><span class="sxs-lookup"><span data-stu-id="e29d7-134">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="e29d7-135">Wenn **useunsafeheaderanalysing** auf **true**festgelegt ist <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> , wird in diesem Fall nicht ausgelöst. Ihre Anwendung ist jedoch für mehrere Formen von URI-analyseangriffen anfällig.</span><span class="sxs-lookup"><span data-stu-id="e29d7-135">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="e29d7-136">Die beste Lösung besteht darin, den Server so zu ändern, dass die Antwort keine Steuerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="e29d7-136">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e29d7-137">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="e29d7-137">Configuration Files</span></span>  
 <span data-ttu-id="e29d7-138">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e29d7-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e29d7-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e29d7-139">Example</span></span>  
 <span data-ttu-id="e29d7-140">Im folgenden Beispiel wird gezeigt, wie eine größer als normale maximale Header Länge angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e29d7-140">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpWebRequest  
        maximumResponseHeadersLength="128"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e29d7-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e29d7-141">See also</span></span>

- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [<span data-ttu-id="e29d7-142">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="e29d7-142">Network Settings Schema</span></span>](index.md)
