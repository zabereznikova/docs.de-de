---
title: <httpListener>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
ms.openlocfilehash: 78526559164939667eab8848bc5fd2af6749d474
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195440"
---
# <a name="httplistener-element-network-settings"></a><span data-ttu-id="92621-102">\<httpListener>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="92621-102">\<httpListener> Element (Network Settings)</span></span>

<span data-ttu-id="92621-103">Passt Parameter an, die von der-Klasse verwendet werden <xref:System.Net.HttpListener> .</span><span class="sxs-lookup"><span data-stu-id="92621-103">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpListener>**

## <a name="syntax"></a><span data-ttu-id="92621-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="92621-104">Syntax</span></span>  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a><span data-ttu-id="92621-105">Typ</span><span class="sxs-lookup"><span data-stu-id="92621-105">Type</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="92621-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="92621-106">Attributes and Elements</span></span>  

 <span data-ttu-id="92621-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="92621-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="92621-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="92621-108">Attributes</span></span>  
  
|<span data-ttu-id="92621-109">attribute</span><span class="sxs-lookup"><span data-stu-id="92621-109">Attribute</span></span>|<span data-ttu-id="92621-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92621-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="92621-111">unescaperequesturl</span><span class="sxs-lookup"><span data-stu-id="92621-111">unescapeRequestUrl</span></span>|<span data-ttu-id="92621-112">Ein boolescher Wert, der angibt, ob eine- <xref:System.Net.HttpListener> Instanz anstelle des konvertierten URIs den unformatierten URI ohne Escapezeichen verwendet.</span><span class="sxs-lookup"><span data-stu-id="92621-112">A Boolean value that indicates if a <xref:System.Net.HttpListener> instance uses the raw unescaped URI instead of the converted URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="92621-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="92621-113">Child Elements</span></span>  

 <span data-ttu-id="92621-114">Keine</span><span class="sxs-lookup"><span data-stu-id="92621-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="92621-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="92621-115">Parent Elements</span></span>  
  
|<span data-ttu-id="92621-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="92621-116">**Element**</span></span>|<span data-ttu-id="92621-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="92621-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="92621-118">settings</span><span class="sxs-lookup"><span data-stu-id="92621-118">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="92621-119">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="92621-119">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92621-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="92621-120">Remarks</span></span>  

 <span data-ttu-id="92621-121">Das **unescaperequesturl** -Attribut gibt an, ob den unformatierten URI ohne Escapezeichen <xref:System.Net.HttpListener> anstelle des konvertierten URI verwendet, bei dem alle Prozent codierten Werte konvertiert und andere normalisierungs Schritte ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="92621-121">The **unescapeRequestUrl** attribute indicates if <xref:System.Net.HttpListener> uses the raw unescaped URI instead of the converted URI where any percent-encoded values are converted and other normalization steps are taken.</span></span>  
  
 <span data-ttu-id="92621-122">Wenn eine- <xref:System.Net.HttpListener> Instanz eine Anforderung über den `http.sys` Dienst empfängt, erstellt Sie eine Instanz der von bereitgestellten URI `http.sys` -Zeichenfolge und macht Sie als- <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> Eigenschaft verfügbar.</span><span class="sxs-lookup"><span data-stu-id="92621-122">When a <xref:System.Net.HttpListener> instance receives a request through the `http.sys` service, it creates an instance of the URI string provided by `http.sys`, and exposes it as the <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="92621-123">Der Dienst macht zwei Anforderungs-URI-Zeichen folgen verfügbar `http.sys` :</span><span class="sxs-lookup"><span data-stu-id="92621-123">The `http.sys` service exposes two request URI strings:</span></span>  
  
- <span data-ttu-id="92621-124">RAW-URI</span><span class="sxs-lookup"><span data-stu-id="92621-124">Raw URI</span></span>  
  
- <span data-ttu-id="92621-125">Konvertierter URI</span><span class="sxs-lookup"><span data-stu-id="92621-125">Converted URI</span></span>  
  
 <span data-ttu-id="92621-126">Der unformatierte URI ist das, das <xref:System.Uri?displayProperty=nameWithType> in der Anforderungs Zeile einer HTTP-Anforderung bereitgestellt wird:</span><span class="sxs-lookup"><span data-stu-id="92621-126">The raw URI is the <xref:System.Uri?displayProperty=nameWithType> provided in the request line of a HTTP request:</span></span>  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 <span data-ttu-id="92621-127">Der von bereitgestellte Rohdaten-URI `http.sys` für die oben genannte Anforderung ist "/Path/".</span><span class="sxs-lookup"><span data-stu-id="92621-127">The raw URI provided by `http.sys` for the request mentioned above, is "/path/".</span></span> <span data-ttu-id="92621-128">Dies stellt die Zeichenfolge dar, die auf das HTTP-Verb folgt, wie es über das Netzwerk gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="92621-128">This represents the string following the HTTP verb as it was sent over the network.</span></span>  
  
 <span data-ttu-id="92621-129">Der `http.sys` Dienst erstellt einen konvertierten URI aus den Informationen, die in der Anforderung bereitgestellt werden, indem der URI in der HTTP-Anforderungs Zeile und der Host Header verwendet wird, um den Ursprungsserver zu ermitteln, an den die Anforderung weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="92621-129">The `http.sys` service creates a converted URI from the information provided in the request by using the URI provided in the HTTP request line and the Host header to determine the origin server the request should be forwarded to.</span></span> <span data-ttu-id="92621-130">Dies erfolgt durch Vergleichen der Informationen aus der Anforderung mit einem Satz von registrierten URI-Präfixen.</span><span class="sxs-lookup"><span data-stu-id="92621-130">This is done by comparing the information from the request with a set of registered URI prefixes.</span></span> <span data-ttu-id="92621-131">In der HTTP-Server-SDK-Dokumentation wird dieser konvertierte URI als HTTP_COOKED_URL Struktur bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="92621-131">The HTTP Server SDK documentation refers to this converted URI as the HTTP_COOKED_URL structure.</span></span>  
  
 <span data-ttu-id="92621-132">Um die Anforderung mit registrierten URI-Präfixen vergleichen zu können, müssen einige Normalisierungen der Anforderung vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="92621-132">In order to be able to compare the request with registered URI prefixes, some normalization to the request needs to be done.</span></span> <span data-ttu-id="92621-133">Im obigen Beispiel würde der konvertierte URI wie folgt lauten:</span><span class="sxs-lookup"><span data-stu-id="92621-133">For the sample above the converted URI would be as follows:</span></span>  
  
 `http://www.contoso.com/path/`  
  
 <span data-ttu-id="92621-134">Der `http.sys` Dienst kombiniert den <xref:System.Uri.Host%2A?displayProperty=nameWithType> -Eigenschafts Wert und die Zeichenfolge in der Anforderungs Zeile, um einen konvertierten URI zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="92621-134">The `http.sys` service combines the <xref:System.Uri.Host%2A?displayProperty=nameWithType> property value and the string in the request line to create a converted URI.</span></span> <span data-ttu-id="92621-135">Außerdem `http.sys` führt die- <xref:System.Uri?displayProperty=nameWithType> Klasse auch die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="92621-135">In addition, `http.sys` and the <xref:System.Uri?displayProperty=nameWithType> class also does the following:</span></span>  
  
- <span data-ttu-id="92621-136">Deaktiviert alle Prozent codierten Werte.</span><span class="sxs-lookup"><span data-stu-id="92621-136">Un-escapes all percent encoded values.</span></span>  
  
- <span data-ttu-id="92621-137">Konvertiert Prozent codierte nicht-ASCII-Zeichen in eine UTF-16-Zeichen Darstellung.</span><span class="sxs-lookup"><span data-stu-id="92621-137">Converts percent-encoded non-ASCII characters into a UTF-16 character representation.</span></span> <span data-ttu-id="92621-138">Beachten Sie, dass UTF-8-und ANSI/DBCS-Zeichen sowie Unicode-Zeichen (Unicode-Codierung mit dem Format "% uXXXX") unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="92621-138">Note that UTF-8 and ANSI/DBCS characters are supported as well as Unicode characters (Unicode encoding using the %uXXXX format).</span></span>  
  
- <span data-ttu-id="92621-139">Führt andere normalisierungs Schritte aus, z. b. Pfad Komprimierung</span><span class="sxs-lookup"><span data-stu-id="92621-139">Executes other normalization steps, like path compression.</span></span>  
  
 <span data-ttu-id="92621-140">Da die Anforderung keine Informationen über die Codierung enthält, die für Prozent codierte Werte verwendet wird, ist es möglicherweise nicht möglich, die richtige Codierung zu ermitteln, indem Sie die Prozent codierten Werte zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="92621-140">Since the request doesn't contain any information about the encoding used for percent-encoded values, it may not be possible to determine the correct encoding just by parsing the percent-encoded values.</span></span>  
  
 <span data-ttu-id="92621-141">`http.sys`Stellt daher zwei Registrierungsschlüssel zum Ändern des Prozesses bereit:</span><span class="sxs-lookup"><span data-stu-id="92621-141">Therefore `http.sys` provides two registry keys for modifying the process:</span></span>  
  
|<span data-ttu-id="92621-142">-Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="92621-142">Registry Key</span></span>|<span data-ttu-id="92621-143">Standardwert</span><span class="sxs-lookup"><span data-stu-id="92621-143">Default Value</span></span>|<span data-ttu-id="92621-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92621-144">Description</span></span>|  
|------------------|-------------------|-----------------|  
|<span data-ttu-id="92621-145">EnableNonUTF8</span><span class="sxs-lookup"><span data-stu-id="92621-145">EnableNonUTF8</span></span>|<span data-ttu-id="92621-146">1</span><span class="sxs-lookup"><span data-stu-id="92621-146">1</span></span>|<span data-ttu-id="92621-147">Wenn 0 (null), werden `http.sys` nur UTF-8-codierte URLs akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="92621-147">If zero, `http.sys` accepts only UTF-8-encoded URLs.</span></span><br /><br /> <span data-ttu-id="92621-148">Wenn ungleich 0 (null), werden `http.sys` auch ANSI-codierte oder DBCS-codierte URLs in Anforderungen akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="92621-148">If non-zero, `http.sys` also accepts ANSI-encoded or DBCS-encoded URLs in requests.</span></span>|  
|<span data-ttu-id="92621-149">FavorUTF8</span><span class="sxs-lookup"><span data-stu-id="92621-149">FavorUTF8</span></span>|<span data-ttu-id="92621-150">1</span><span class="sxs-lookup"><span data-stu-id="92621-150">1</span></span>|<span data-ttu-id="92621-151">Wenn der Wert ungleich 0 (null) ist, wird `http.sys` von immer versucht, eine URL als UTF-8 zu decodieren. wenn diese Konvertierung fehlschlägt und EnableNonUTF8 ungleich NULL ist, versucht Http.sys, Sie als ANSI oder DBCS zu decodieren.</span><span class="sxs-lookup"><span data-stu-id="92621-151">If non-zero, `http.sys` always tries to decode a URL as UTF-8 first; if that conversion fails and EnableNonUTF8 is non-zero, Http.sys then tries to decode it as ANSI or DBCS.</span></span><br /><br /> <span data-ttu-id="92621-152">Wenn NULL (und EnableNonUTF8 ungleich null) ist, `http.sys` versucht, es als ANSI oder DBCS zu decodieren. wenn dies nicht erfolgreich ist, versucht es, eine UTF-8-Konvertierung durchzusetzen.</span><span class="sxs-lookup"><span data-stu-id="92621-152">If zero (and EnableNonUTF8 is non-zero), `http.sys` tries to decode it as ANSI or DBCS; if that is not successful, it tries a UTF-8 conversion.</span></span>|  
  
 <span data-ttu-id="92621-153">Wenn <xref:System.Net.HttpListener> eine Anforderung empfängt, wird der konvertierte URI von `http.sys` als Eingabe für die- <xref:System.Net.HttpListenerRequest.Url%2A> Eigenschaft verwendet.</span><span class="sxs-lookup"><span data-stu-id="92621-153">When <xref:System.Net.HttpListener> receives a request, it uses the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="92621-154">Es besteht die Notwendigkeit, Zeichen neben Zeichen und Zahlen in URIs zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="92621-154">There is a need for supporting characters besides characters and numbers in URIs.</span></span> <span data-ttu-id="92621-155">Ein Beispiel ist der folgende URI, der zum Abrufen von Kundeninformationen für die Kundennummer "1/3812" verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="92621-155">An example is the following URI, which is used to retrieve customer information for customer number "1/3812":</span></span>  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 <span data-ttu-id="92621-156">Notieren Sie sich den Prozentsatz codierten Schrägstrich im URI (% 2F).</span><span class="sxs-lookup"><span data-stu-id="92621-156">Note the percent-encoded slash in the Uri (%2F).</span></span> <span data-ttu-id="92621-157">Dies ist erforderlich, da der Schrägstrich in diesem Fall Daten und kein Pfad Trennzeichen darstellt.</span><span class="sxs-lookup"><span data-stu-id="92621-157">This is necessary, since in this case the slash character represents data and not a path delimiter.</span></span>  
  
 <span data-ttu-id="92621-158">Wenn die Zeichenfolge an den URI-Konstruktor übergeben wird, führt dies zu folgendem URI:</span><span class="sxs-lookup"><span data-stu-id="92621-158">Passing the string to Uri constructor will lead to the following URI:</span></span>  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 <span data-ttu-id="92621-159">Wenn Sie den Pfad in seine Segmente aufteilen, werden die folgenden Elemente angezeigt:</span><span class="sxs-lookup"><span data-stu-id="92621-159">Splitting the path into its segments would result in the following elements:</span></span>  
  
 `Customer('1`  
  
 `3812')`  
  
 <span data-ttu-id="92621-160">Dies ist nicht die Absicht des Absenders der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="92621-160">This is not the intent of the sender of the request.</span></span>  
  
 <span data-ttu-id="92621-161">Wenn das **unescaperequesturl** -Attribut auf **false**festgelegt ist, und wenn <xref:System.Net.HttpListener> eine Anforderung empfängt, wird der unformatierte URI anstelle des konvertierten URI aus `http.sys` als Eingabe für die- <xref:System.Net.HttpListenerRequest.Url%2A> Eigenschaft verwendet.</span><span class="sxs-lookup"><span data-stu-id="92621-161">If the **unescapeRequestUrl** attribute is set to **false**, then when the <xref:System.Net.HttpListener> receives a request, it uses the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="92621-162">Der Standardwert für das **unescaperequesturl** -Attribut ist " **true**".</span><span class="sxs-lookup"><span data-stu-id="92621-162">The default value for the **unescapeRequestUrl** attribute is **true**.</span></span>  
  
 <span data-ttu-id="92621-163">Die- <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> Eigenschaft kann verwendet werden, um den aktuellen Wert des **unescaperequesturl** -Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="92621-163">The <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> property can be used to get the current value of the **unescapeRequestUrl** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92621-164">Beispiel</span><span class="sxs-lookup"><span data-stu-id="92621-164">Example</span></span>  

 <span data-ttu-id="92621-165">Im folgenden Beispiel wird gezeigt, wie die-Klasse konfiguriert wird, <xref:System.Net.HttpListener> Wenn Sie eine Anforderung zum Verwenden des RAW-URI anstelle des konvertierten URI von `http.sys` als Eingabe für die- <xref:System.Net.HttpListenerRequest.Url%2A> Eigenschaft empfängt.</span><span class="sxs-lookup"><span data-stu-id="92621-165">The following example shows how to configure the <xref:System.Net.HttpListener> class when it receives a request to use the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpListener  
        unescapeRequestUrl="false"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="92621-166">Elementinformationen</span><span class="sxs-lookup"><span data-stu-id="92621-166">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="92621-167">Namespace</span><span class="sxs-lookup"><span data-stu-id="92621-167">Namespace</span></span>|<span data-ttu-id="92621-168">System.Net</span><span class="sxs-lookup"><span data-stu-id="92621-168">System.Net</span></span>|  
|<span data-ttu-id="92621-169">Name des Schemas</span><span class="sxs-lookup"><span data-stu-id="92621-169">Schema Name</span></span>||  
|<span data-ttu-id="92621-170">Validierungsdatei</span><span class="sxs-lookup"><span data-stu-id="92621-170">Validation File</span></span>||  
|<span data-ttu-id="92621-171">Kann leer sein</span><span class="sxs-lookup"><span data-stu-id="92621-171">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="92621-172">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="92621-172">See also</span></span>

- <xref:System.Net.Configuration.HttpListenerElement>
- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpListenerRequest.Url%2A>
- [<span data-ttu-id="92621-173">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="92621-173">Network Settings Schema</span></span>](index.md)
