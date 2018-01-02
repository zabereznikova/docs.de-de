---
title: '&lt;HttpWebRequest&gt; -Element (Netzwerkeinstellungen)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
caps.latest.revision: "18"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: dadb2d7635f132b44d6fca8c56f53b847ffb1ff9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="lthttpwebrequestgt-element-network-settings"></a><span data-ttu-id="0c8da-102">&lt;HttpWebRequest&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="0c8da-102">&lt;httpWebRequest&gt; Element (Network Settings)</span></span>
<span data-ttu-id="0c8da-103">Passt die Anforderungsparameter werden Web an.</span><span class="sxs-lookup"><span data-stu-id="0c8da-103">Customizes Web request parameters.</span></span>  
  
 <span data-ttu-id="0c8da-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0c8da-104">\<configuration></span></span>  
<span data-ttu-id="0c8da-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="0c8da-105">\<system.net></span></span>  
<span data-ttu-id="0c8da-106">\<Einstellungen ></span><span class="sxs-lookup"><span data-stu-id="0c8da-106">\<settings></span></span>  
<span data-ttu-id="0c8da-107">\<HttpWebRequest ></span><span class="sxs-lookup"><span data-stu-id="0c8da-107">\<httpWebRequest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c8da-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="0c8da-108">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c8da-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0c8da-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0c8da-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0c8da-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c8da-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="0c8da-111">Attributes</span></span>  
  
|<span data-ttu-id="0c8da-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="0c8da-112">**Attribute**</span></span>|<span data-ttu-id="0c8da-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="0c8da-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="0c8da-114">Gibt die maximale Länge des Antwortheaders in Kilobyte an.</span><span class="sxs-lookup"><span data-stu-id="0c8da-114">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="0c8da-115">Der Standard ist 64.</span><span class="sxs-lookup"><span data-stu-id="0c8da-115">The default is 64.</span></span> <span data-ttu-id="0c8da-116">Der Wert-1 gibt an, dass keine größenbeschränkung für die Antwortheader auferlegt werden wird.</span><span class="sxs-lookup"><span data-stu-id="0c8da-116">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="0c8da-117">Gibt die maximale Länge einer Fehlerantwort in Kilobyte an.</span><span class="sxs-lookup"><span data-stu-id="0c8da-117">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="0c8da-118">Der Standard ist 64.</span><span class="sxs-lookup"><span data-stu-id="0c8da-118">The default is 64.</span></span> <span data-ttu-id="0c8da-119">Der Wert-1 gibt an, dass keine größenbeschränkung für die Fehlerantwort auferlegt werden wird.</span><span class="sxs-lookup"><span data-stu-id="0c8da-119">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="0c8da-120">Gibt die maximale Länge eines Uploads als Antwort auf einen nicht autorisierten Fehlercode in Bytes an.</span><span class="sxs-lookup"><span data-stu-id="0c8da-120">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="0c8da-121">Der Standard ist -1.</span><span class="sxs-lookup"><span data-stu-id="0c8da-121">The default is -1.</span></span> <span data-ttu-id="0c8da-122">Der Wert-1 gibt an, dass keine größenbeschränkung für den Upload auferlegt werden wird.</span><span class="sxs-lookup"><span data-stu-id="0c8da-122">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="0c8da-123">Gibt an, ob unsichere Headeranalyse aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="0c8da-123">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="0c8da-124">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="0c8da-124">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0c8da-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0c8da-125">Child Elements</span></span>  
 <span data-ttu-id="0c8da-126">Keine</span><span class="sxs-lookup"><span data-stu-id="0c8da-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0c8da-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0c8da-127">Parent Elements</span></span>  
  
|<span data-ttu-id="0c8da-128">**Element**</span><span class="sxs-lookup"><span data-stu-id="0c8da-128">**Element**</span></span>|<span data-ttu-id="0c8da-129">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="0c8da-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0c8da-130">Einstellungen</span><span class="sxs-lookup"><span data-stu-id="0c8da-130">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="0c8da-131">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="0c8da-131">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c8da-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0c8da-132">Remarks</span></span>  
 <span data-ttu-id="0c8da-133">Standardmäßig setzt .NET Framework RFC 2616 streng für die Analyse von URI.</span><span class="sxs-lookup"><span data-stu-id="0c8da-133">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="0c8da-134">Einige Serverantworten enthalten möglicherweise Steuerzeichen in unzulässigen Feldern, wodurch die <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> Methode zum Auslösen einer <xref:System.Net.WebException>.</span><span class="sxs-lookup"><span data-stu-id="0c8da-134">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="0c8da-135">Wenn **UseUnsafeHeaderParsing** festgelegt ist, um **"true"**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> in diesem Fall jedoch keine Ausnahme auslöst, wird Ihre Anwendung mehrere Typen von URI Analyse Angriffe anfällig sein.</span><span class="sxs-lookup"><span data-stu-id="0c8da-135">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="0c8da-136">Die beste Lösung ist auf den Server ändern, sodass die Antwort keine Steuerzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="0c8da-136">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="0c8da-137">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="0c8da-137">Configuration Files</span></span>  
 <span data-ttu-id="0c8da-138">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0c8da-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c8da-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0c8da-139">Example</span></span>  
 <span data-ttu-id="0c8da-140">Im folgende Beispiel wird gezeigt, wie eine größere als normale maximale Headergröße Länge.</span><span class="sxs-lookup"><span data-stu-id="0c8da-140">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0c8da-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c8da-141">See Also</span></span>  
 <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>  
 [<span data-ttu-id="0c8da-142">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="0c8da-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
