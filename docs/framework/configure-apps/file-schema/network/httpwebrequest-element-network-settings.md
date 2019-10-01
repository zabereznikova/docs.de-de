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
ms.openlocfilehash: fa00aed2cd1e96ec788d4bc9c1c63f20561d8d1c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698181"
---
# <a name="httpwebrequest-element-network-settings"></a><span data-ttu-id="57d07-102">\<httpwebrequest >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="57d07-102">\<httpWebRequest> Element (Network Settings)</span></span>
<span data-ttu-id="57d07-103">Passt Webanforderungs Parameter an.</span><span class="sxs-lookup"><span data-stu-id="57d07-103">Customizes Web request parameters.</span></span>  
  
[<span data-ttu-id="57d07-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="57d07-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="57d07-105">&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="57d07-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="57d07-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<settings >** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="57d07-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>  
<span data-ttu-id="57d07-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<httpwebrequest >**</span><span class="sxs-lookup"><span data-stu-id="57d07-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpWebRequest>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57d07-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="57d07-108">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="57d07-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="57d07-109">Attributes and Elements</span></span>  
 <span data-ttu-id="57d07-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="57d07-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="57d07-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="57d07-111">Attributes</span></span>  
  
|<span data-ttu-id="57d07-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="57d07-112">**Attribute**</span></span>|<span data-ttu-id="57d07-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="57d07-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="57d07-114">Gibt die maximale Länge eines Antwort Headers in Kilobyte an.</span><span class="sxs-lookup"><span data-stu-id="57d07-114">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="57d07-115">Der Standard ist 64.</span><span class="sxs-lookup"><span data-stu-id="57d07-115">The default is 64.</span></span> <span data-ttu-id="57d07-116">Der Wert-1 gibt an, dass keine Größenbeschränkung für die Antwortheader festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="57d07-116">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="57d07-117">Gibt die maximale Länge einer Fehler Antwort in Kilobyte an.</span><span class="sxs-lookup"><span data-stu-id="57d07-117">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="57d07-118">Der Standard ist 64.</span><span class="sxs-lookup"><span data-stu-id="57d07-118">The default is 64.</span></span> <span data-ttu-id="57d07-119">Der Wert-1 gibt an, dass für die Fehler Antwort keine Größenbeschränkung festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="57d07-119">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="57d07-120">Gibt die maximale Länge eines Uploads als Reaktion auf einen nicht autorisierten Fehlercode in Bytes an.</span><span class="sxs-lookup"><span data-stu-id="57d07-120">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="57d07-121">Der Standard ist -1.</span><span class="sxs-lookup"><span data-stu-id="57d07-121">The default is -1.</span></span> <span data-ttu-id="57d07-122">Der Wert-1 gibt an, dass keine Größenbeschränkung für den Upload festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="57d07-122">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="57d07-123">Gibt an, ob die unsichere Header-Verarbeitung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="57d07-123">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="57d07-124">Der Standardwert ist `false`sein.</span><span class="sxs-lookup"><span data-stu-id="57d07-124">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="57d07-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="57d07-125">Child Elements</span></span>  
 <span data-ttu-id="57d07-126">Keine</span><span class="sxs-lookup"><span data-stu-id="57d07-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="57d07-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="57d07-127">Parent Elements</span></span>  
  
|<span data-ttu-id="57d07-128">**Element**</span><span class="sxs-lookup"><span data-stu-id="57d07-128">**Element**</span></span>|<span data-ttu-id="57d07-129">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="57d07-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="57d07-130">settings</span><span class="sxs-lookup"><span data-stu-id="57d07-130">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="57d07-131">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="57d07-131">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57d07-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="57d07-132">Remarks</span></span>  
 <span data-ttu-id="57d07-133">Standardmäßig erzwingt das .NET Framework nur RFC 2616 für die URI-Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="57d07-133">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="57d07-134">Einige Server Antworten können Steuerzeichen in unzulässigen Feldern enthalten, die bewirken, dass die <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType>-Methode eine <xref:System.Net.WebException> auslöst.</span><span class="sxs-lookup"><span data-stu-id="57d07-134">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="57d07-135">Wenn **useunsafeheaderparamesing** auf **true**festgelegt ist, wird in diesem Fall nicht <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> ausgelöst. die Anwendung ist jedoch für verschiedene Formen von URI-analyseangriffen anfällig.</span><span class="sxs-lookup"><span data-stu-id="57d07-135">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="57d07-136">Die beste Lösung besteht darin, den Server so zu ändern, dass die Antwort keine Steuerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="57d07-136">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="57d07-137">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="57d07-137">Configuration Files</span></span>  
 <span data-ttu-id="57d07-138">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="57d07-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="57d07-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="57d07-139">Example</span></span>  
 <span data-ttu-id="57d07-140">Im folgenden Beispiel wird gezeigt, wie eine größer als normale maximale Header Länge angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="57d07-140">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="57d07-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57d07-141">See also</span></span>

- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [<span data-ttu-id="57d07-142">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="57d07-142">Network Settings Schema</span></span>](index.md)
