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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74087456"
---
# <a name="httpwebrequest-element-network-settings"></a><span data-ttu-id="372f3-102">\<httpWebRequest>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="372f3-102">\<httpWebRequest> Element (Network Settings)</span></span>
<span data-ttu-id="372f3-103">Passt Webanforderungs Parameter an.</span><span class="sxs-lookup"><span data-stu-id="372f3-103">Customizes Web request parameters.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpWebRequest>**

## <a name="syntax"></a><span data-ttu-id="372f3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="372f3-104">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="372f3-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="372f3-105">Attributes and Elements</span></span>  
 <span data-ttu-id="372f3-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="372f3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="372f3-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="372f3-107">Attributes</span></span>  
  
|<span data-ttu-id="372f3-108">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="372f3-108">**Attribute**</span></span>|<span data-ttu-id="372f3-109">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="372f3-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="372f3-110">Gibt die maximale Länge eines Antwort Headers in Kilobyte an.</span><span class="sxs-lookup"><span data-stu-id="372f3-110">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="372f3-111">Der Standardwert ist 64.</span><span class="sxs-lookup"><span data-stu-id="372f3-111">The default is 64.</span></span> <span data-ttu-id="372f3-112">Der Wert-1 gibt an, dass keine Größenbeschränkung für die Antwortheader festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="372f3-112">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="372f3-113">Gibt die maximale Länge einer Fehler Antwort in Kilobyte an.</span><span class="sxs-lookup"><span data-stu-id="372f3-113">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="372f3-114">Der Standardwert ist 64.</span><span class="sxs-lookup"><span data-stu-id="372f3-114">The default is 64.</span></span> <span data-ttu-id="372f3-115">Der Wert-1 gibt an, dass für die Fehler Antwort keine Größenbeschränkung festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="372f3-115">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="372f3-116">Gibt die maximale Länge eines Uploads als Reaktion auf einen nicht autorisierten Fehlercode in Bytes an.</span><span class="sxs-lookup"><span data-stu-id="372f3-116">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="372f3-117">Der Standard ist -1.</span><span class="sxs-lookup"><span data-stu-id="372f3-117">The default is -1.</span></span> <span data-ttu-id="372f3-118">Der Wert -1 gibt an, dass für den Upload keine Größenbeschränkung gilt.</span><span class="sxs-lookup"><span data-stu-id="372f3-118">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="372f3-119">Gibt an, ob die unsichere Header-Verarbeitung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="372f3-119">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="372f3-120">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="372f3-120">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="372f3-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="372f3-121">Child Elements</span></span>  
 <span data-ttu-id="372f3-122">Keine</span><span class="sxs-lookup"><span data-stu-id="372f3-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="372f3-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="372f3-123">Parent Elements</span></span>  
  
|<span data-ttu-id="372f3-124">**Element**</span><span class="sxs-lookup"><span data-stu-id="372f3-124">**Element**</span></span>|<span data-ttu-id="372f3-125">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="372f3-125">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="372f3-126">settings</span><span class="sxs-lookup"><span data-stu-id="372f3-126">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="372f3-127">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="372f3-127">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="372f3-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="372f3-128">Remarks</span></span>  
 <span data-ttu-id="372f3-129">Standardmäßig erzwingt das .NET Framework nur RFC 2616 für die URI-Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="372f3-129">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="372f3-130">Einige Server Antworten können Steuerzeichen in unzulässigen Feldern enthalten, die bewirken, dass die- <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> Methode eine auslöst <xref:System.Net.WebException> .</span><span class="sxs-lookup"><span data-stu-id="372f3-130">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="372f3-131">Wenn **useunsafeheaderanalysing** auf **true**festgelegt ist, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> wird in diesem Fall nicht ausgelöst. Ihre Anwendung ist jedoch für mehrere Formen von URI-analyseangriffen anfällig.</span><span class="sxs-lookup"><span data-stu-id="372f3-131">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="372f3-132">Die beste Lösung besteht darin, den Server so zu ändern, dass die Antwort keine Steuerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="372f3-132">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="372f3-133">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="372f3-133">Configuration Files</span></span>  
 <span data-ttu-id="372f3-134">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="372f3-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="372f3-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="372f3-135">Example</span></span>  
 <span data-ttu-id="372f3-136">Im folgenden Beispiel wird gezeigt, wie eine größer als normale maximale Header Länge angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="372f3-136">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="372f3-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="372f3-137">See also</span></span>

- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [<span data-ttu-id="372f3-138">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="372f3-138">Network Settings Schema</span></span>](index.md)
