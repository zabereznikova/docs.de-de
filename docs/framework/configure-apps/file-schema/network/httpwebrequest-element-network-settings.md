---
title: '&lt;"HttpWebRequest"&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
ms.openlocfilehash: 586b3e7219c72b6cd00653d6d0be3a74f6359709
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50048982"
---
# <a name="lthttpwebrequestgt-element-network-settings"></a><span data-ttu-id="90940-102">&lt;"HttpWebRequest"&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="90940-102">&lt;httpWebRequest&gt; Element (Network Settings)</span></span>
<span data-ttu-id="90940-103">Passt die Web-Anforderungsparameter.</span><span class="sxs-lookup"><span data-stu-id="90940-103">Customizes Web request parameters.</span></span>  
  
 <span data-ttu-id="90940-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="90940-104">\<configuration></span></span>  
<span data-ttu-id="90940-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="90940-105">\<system.net></span></span>  
<span data-ttu-id="90940-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="90940-106">\<settings></span></span>  
<span data-ttu-id="90940-107">\<"HttpWebRequest" ></span><span class="sxs-lookup"><span data-stu-id="90940-107">\<httpWebRequest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90940-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="90940-108">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90940-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="90940-109">Attributes and Elements</span></span>  
 <span data-ttu-id="90940-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="90940-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90940-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="90940-111">Attributes</span></span>  
  
|<span data-ttu-id="90940-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="90940-112">**Attribute**</span></span>|<span data-ttu-id="90940-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="90940-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="90940-114">Gibt die maximale Länge des Antwortheaders in Kilobyte an.</span><span class="sxs-lookup"><span data-stu-id="90940-114">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="90940-115">Der Standard ist 64.</span><span class="sxs-lookup"><span data-stu-id="90940-115">The default is 64.</span></span> <span data-ttu-id="90940-116">Der Wert-1 gibt an, dass keine größenbeschränkung für die Header der Antwort festgelegt werden, wird.</span><span class="sxs-lookup"><span data-stu-id="90940-116">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="90940-117">Gibt die maximale Länge einer Fehlerantwort in Kilobyte an.</span><span class="sxs-lookup"><span data-stu-id="90940-117">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="90940-118">Der Standard ist 64.</span><span class="sxs-lookup"><span data-stu-id="90940-118">The default is 64.</span></span> <span data-ttu-id="90940-119">Der Wert-1 gibt an, dass keine größenbeschränkung für die Fehlerantwort verhängt wird.</span><span class="sxs-lookup"><span data-stu-id="90940-119">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="90940-120">Gibt die maximale Länge eines Uploads als Antwort auf einen nicht autorisierten Fehlercode in Byte an.</span><span class="sxs-lookup"><span data-stu-id="90940-120">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="90940-121">Der Standard ist -1.</span><span class="sxs-lookup"><span data-stu-id="90940-121">The default is -1.</span></span> <span data-ttu-id="90940-122">Der Wert-1 gibt an, dass für den Upload keine größenbeschränkung festgelegt werden wird.</span><span class="sxs-lookup"><span data-stu-id="90940-122">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="90940-123">Gibt an, ob unsichere Headeranalyse aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="90940-123">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="90940-124">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="90940-124">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="90940-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="90940-125">Child Elements</span></span>  
 <span data-ttu-id="90940-126">Keine</span><span class="sxs-lookup"><span data-stu-id="90940-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="90940-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="90940-127">Parent Elements</span></span>  
  
|<span data-ttu-id="90940-128">**Element**</span><span class="sxs-lookup"><span data-stu-id="90940-128">**Element**</span></span>|<span data-ttu-id="90940-129">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="90940-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="90940-130">settings</span><span class="sxs-lookup"><span data-stu-id="90940-130">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="90940-131">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="90940-131">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90940-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90940-132">Remarks</span></span>  
 <span data-ttu-id="90940-133">Standardmäßig erzwingt .NET Framework RFC 2616 ausschließlich für die URI-Analyse.</span><span class="sxs-lookup"><span data-stu-id="90940-133">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="90940-134">Einige Serverantworten können Steuerzeichen enthalten, in einem Feld unzulässigen, dadurch wird die <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> Methode zum Auslösen einer <xref:System.Net.WebException>.</span><span class="sxs-lookup"><span data-stu-id="90940-134">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="90940-135">Wenn **UseUnsafeHeaderParsing** nastaven NA hodnotu **"true"**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> in diesem Fall jedoch keine Ausnahme auslöst, wird Ihre Anwendung verschiedene Formen des URI-Analyse-Angriffe anfällig.</span><span class="sxs-lookup"><span data-stu-id="90940-135">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="90940-136">Die beste Lösung ist zum Ändern des Servers, damit die Antwort keine Steuerzeichen berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="90940-136">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="90940-137">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="90940-137">Configuration Files</span></span>  
 <span data-ttu-id="90940-138">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="90940-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="90940-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90940-139">Example</span></span>  
 <span data-ttu-id="90940-140">Das folgende Beispiel zeigt, wie Sie einen größeren angeben als die normale maximale Headerlänge.</span><span class="sxs-lookup"><span data-stu-id="90940-140">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="90940-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90940-141">See Also</span></span>  
 <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>  
 [<span data-ttu-id="90940-142">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="90940-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
