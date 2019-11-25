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
ms.openlocfilehash: d33dadc14510feb00e05ca557b507b0cf8fa0dd0
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087456"
---
# <a name="httpwebrequest-element-network-settings"></a><span data-ttu-id="62329-102">\<"HttpWebRequest" >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="62329-102">\<httpWebRequest> Element (Network Settings)</span></span>
<span data-ttu-id="62329-103">Passt Webanforderungs Parameter an.</span><span class="sxs-lookup"><span data-stu-id="62329-103">Customizes Web request parameters.</span></span>  

<span data-ttu-id="62329-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="62329-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="62329-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="62329-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="62329-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Einstellungen**](settings-element-network-settings.md) ></span><span class="sxs-lookup"><span data-stu-id="62329-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>\
<span data-ttu-id="62329-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<HttpWebRequest >**</span><span class="sxs-lookup"><span data-stu-id="62329-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpWebRequest>**</span></span>

## <a name="syntax"></a><span data-ttu-id="62329-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="62329-108">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62329-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="62329-109">Attributes and Elements</span></span>  
 <span data-ttu-id="62329-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="62329-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62329-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="62329-111">Attributes</span></span>  
  
|<span data-ttu-id="62329-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="62329-112">**Attribute**</span></span>|<span data-ttu-id="62329-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="62329-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="62329-114">Gibt die maximale Länge eines Antwort Headers in Kilobyte an.</span><span class="sxs-lookup"><span data-stu-id="62329-114">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="62329-115">Der Standard ist 64.</span><span class="sxs-lookup"><span data-stu-id="62329-115">The default is 64.</span></span> <span data-ttu-id="62329-116">Der Wert-1 gibt an, dass keine Größenbeschränkung für die Antwortheader festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="62329-116">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="62329-117">Gibt die maximale Länge einer Fehler Antwort in Kilobyte an.</span><span class="sxs-lookup"><span data-stu-id="62329-117">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="62329-118">Der Standard ist 64.</span><span class="sxs-lookup"><span data-stu-id="62329-118">The default is 64.</span></span> <span data-ttu-id="62329-119">Der Wert-1 gibt an, dass für die Fehler Antwort keine Größenbeschränkung festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="62329-119">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="62329-120">Gibt die maximale Länge eines Uploads als Reaktion auf einen nicht autorisierten Fehlercode in Bytes an.</span><span class="sxs-lookup"><span data-stu-id="62329-120">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="62329-121">Der Standard ist -1.</span><span class="sxs-lookup"><span data-stu-id="62329-121">The default is -1.</span></span> <span data-ttu-id="62329-122">Der Wert-1 gibt an, dass keine Größenbeschränkung für den Upload festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="62329-122">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="62329-123">Gibt an, ob die unsichere Header-Verarbeitung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="62329-123">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="62329-124">Der Standardwert ist `false`sein.</span><span class="sxs-lookup"><span data-stu-id="62329-124">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="62329-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="62329-125">Child Elements</span></span>  
 <span data-ttu-id="62329-126">Keine</span><span class="sxs-lookup"><span data-stu-id="62329-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="62329-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="62329-127">Parent Elements</span></span>  
  
|<span data-ttu-id="62329-128">**Element**</span><span class="sxs-lookup"><span data-stu-id="62329-128">**Element**</span></span>|<span data-ttu-id="62329-129">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="62329-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="62329-130">Einstellungen</span><span class="sxs-lookup"><span data-stu-id="62329-130">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="62329-131">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="62329-131">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62329-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="62329-132">Remarks</span></span>  
 <span data-ttu-id="62329-133">Standardmäßig erzwingt das .NET Framework nur RFC 2616 für die URI-Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="62329-133">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="62329-134">Einige Server Antworten können Steuerzeichen in unzulässigen Feldern enthalten, was dazu führt, dass die <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> Methode eine <xref:System.Net.WebException>auslöst.</span><span class="sxs-lookup"><span data-stu-id="62329-134">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="62329-135">Wenn **useunsafeheaderparamesing** auf **true**festgelegt ist, wird in diesem Fall <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> nicht ausgelöst. die Anwendung ist jedoch für verschiedene Formen von URI-analyseangriffen anfällig.</span><span class="sxs-lookup"><span data-stu-id="62329-135">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="62329-136">Die beste Lösung besteht darin, den Server so zu ändern, dass die Antwort keine Steuerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="62329-136">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="62329-137">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="62329-137">Configuration Files</span></span>  
 <span data-ttu-id="62329-138">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="62329-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="62329-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="62329-139">Example</span></span>  
 <span data-ttu-id="62329-140">Im folgenden Beispiel wird gezeigt, wie eine größer als normale maximale Header Länge angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="62329-140">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="62329-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62329-141">See also</span></span>

- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [<span data-ttu-id="62329-142">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="62329-142">Network Settings Schema</span></span>](index.md)
