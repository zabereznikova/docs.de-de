---
title: <httpListener>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
ms.openlocfilehash: 3f75096681ab07dd6d4788fbded5ca5c4a024aef
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698197"
---
# <a name="httplistener-element-network-settings"></a><span data-ttu-id="1aa29-102">\<httplistener > Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="1aa29-102">\<httpListener> Element (Network Settings)</span></span>
<span data-ttu-id="1aa29-103">Passt die Parameter an, die von der <xref:System.Net.HttpListener>-Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1aa29-103">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>  
  
[<span data-ttu-id="1aa29-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="1aa29-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="1aa29-105">&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="1aa29-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="1aa29-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<settings >** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="1aa29-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>  
<span data-ttu-id="1aa29-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<httplistener >**</span><span class="sxs-lookup"><span data-stu-id="1aa29-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpListener>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1aa29-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="1aa29-108">Syntax</span></span>  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a><span data-ttu-id="1aa29-109">Typ</span><span class="sxs-lookup"><span data-stu-id="1aa29-109">Type</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1aa29-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1aa29-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1aa29-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1aa29-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1aa29-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="1aa29-112">Attributes</span></span>  
  
|<span data-ttu-id="1aa29-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="1aa29-113">Attribute</span></span>|<span data-ttu-id="1aa29-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1aa29-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1aa29-115">unescapeRequestUrl</span><span class="sxs-lookup"><span data-stu-id="1aa29-115">unescapeRequestUrl</span></span>|<span data-ttu-id="1aa29-116">Ein boolescher Wert, der angibt, ob eine <xref:System.Net.HttpListener>-Instanz anstelle des konvertierten URIs den unformatierten URI ohne Escapezeichen verwendet.</span><span class="sxs-lookup"><span data-stu-id="1aa29-116">A Boolean value that indicates if a <xref:System.Net.HttpListener> instance uses the raw unescaped URI instead of the converted URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1aa29-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1aa29-117">Child Elements</span></span>  
 <span data-ttu-id="1aa29-118">Keine</span><span class="sxs-lookup"><span data-stu-id="1aa29-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1aa29-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1aa29-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1aa29-120">**Element**</span><span class="sxs-lookup"><span data-stu-id="1aa29-120">**Element**</span></span>|<span data-ttu-id="1aa29-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1aa29-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1aa29-122">settings</span><span class="sxs-lookup"><span data-stu-id="1aa29-122">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="1aa29-123">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="1aa29-123">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1aa29-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1aa29-124">Remarks</span></span>  
 <span data-ttu-id="1aa29-125">Das **unescaperequesturl** -Attribut gibt an, ob <xref:System.Net.HttpListener> den unformatierten URI ohne Escapezeichen anstelle des konvertierten URI verwendet, bei dem alle Prozent codierten Werte konvertiert werden und andere normalisierungs Schritte ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1aa29-125">The **unescapeRequestUrl** attribute indicates if <xref:System.Net.HttpListener> uses the raw unescaped URI instead of the converted URI where any percent-encoded values are converted and other normalization steps are taken.</span></span>  
  
 <span data-ttu-id="1aa29-126">Wenn eine <xref:System.Net.HttpListener>-Instanz eine Anforderung über den `http.sys`-Dienst empfängt, erstellt Sie eine Instanz der von `http.sys` bereitgestellten URI-Zeichenfolge und macht Sie als <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType>-Eigenschaft verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1aa29-126">When a <xref:System.Net.HttpListener> instance receives a request through the `http.sys` service, it creates an instance of the URI string provided by `http.sys`, and exposes it as the <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="1aa29-127">Der `http.sys`-Dienst macht zwei Anforderungs-URI-Zeichen folgen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="1aa29-127">The `http.sys` service exposes two request URI strings:</span></span>  
  
- <span data-ttu-id="1aa29-128">RAW-URI</span><span class="sxs-lookup"><span data-stu-id="1aa29-128">Raw URI</span></span>  
  
- <span data-ttu-id="1aa29-129">Konvertierter URI</span><span class="sxs-lookup"><span data-stu-id="1aa29-129">Converted URI</span></span>  
  
 <span data-ttu-id="1aa29-130">Der unformatierte URI ist das <xref:System.Uri?displayProperty=nameWithType>, das in der Anforderungs Zeile einer HTTP-Anforderung bereitgestellt wird:</span><span class="sxs-lookup"><span data-stu-id="1aa29-130">The raw URI is the <xref:System.Uri?displayProperty=nameWithType> provided in the request line of a HTTP request:</span></span>  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 <span data-ttu-id="1aa29-131">Der unformatierte URI, der von `http.sys` für die oben genannte Anforderung bereitgestellt wird, ist "/Path/".</span><span class="sxs-lookup"><span data-stu-id="1aa29-131">The raw URI provided by `http.sys` for the request mentioned above, is "/path/".</span></span> <span data-ttu-id="1aa29-132">Dies stellt die Zeichenfolge dar, die auf das HTTP-Verb folgt, wie es über das Netzwerk gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="1aa29-132">This represents the string following the HTTP verb as it was sent over the network.</span></span>  
  
 <span data-ttu-id="1aa29-133">Der `http.sys`-Dienst erstellt einen konvertierten URI aus den Informationen, die in der Anforderung bereitgestellt werden, indem der URI in der HTTP-Anforderungs Zeile und der Host Header verwendet werden, um den Ursprungsserver zu ermitteln, an den die Anforderung weitergeleitet werden soll</span><span class="sxs-lookup"><span data-stu-id="1aa29-133">The `http.sys` service creates a converted URI from the information provided in the request by using the URI provided in the HTTP request line and the Host header to determine the origin server the request should be forwarded to.</span></span> <span data-ttu-id="1aa29-134">Dies erfolgt durch Vergleichen der Informationen aus der Anforderung mit einem Satz von registrierten URI-Präfixen.</span><span class="sxs-lookup"><span data-stu-id="1aa29-134">This is done by comparing the information from the request with a set of registered URI prefixes.</span></span> <span data-ttu-id="1aa29-135">In der HTTP-Server-SDK-Dokumentation wird dieser konvertierte URI als HTTP_COOKED_URL-Struktur bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="1aa29-135">The HTTP Server SDK documentation refers to this converted URI as the HTTP_COOKED_URL structure.</span></span>  
  
 <span data-ttu-id="1aa29-136">Um die Anforderung mit registrierten URI-Präfixen vergleichen zu können, müssen einige Normalisierungen der Anforderung vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="1aa29-136">In order to be able to compare the request with registered URI prefixes, some normalization to the request needs to be done.</span></span> <span data-ttu-id="1aa29-137">Im obigen Beispiel würde der konvertierte URI wie folgt lauten:</span><span class="sxs-lookup"><span data-stu-id="1aa29-137">For the sample above the converted URI would be as follows:</span></span>  
  
 `http://www.contoso.com/path/`  
  
 <span data-ttu-id="1aa29-138">Der `http.sys`-Dienst kombiniert den <xref:System.Uri.Host%2A?displayProperty=nameWithType>-Eigenschafts Wert und die Zeichenfolge in der Anforderungs Zeile, um einen konvertierten URI zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1aa29-138">The `http.sys` service combines the <xref:System.Uri.Host%2A?displayProperty=nameWithType> property value and the string in the request line to create a converted URI.</span></span> <span data-ttu-id="1aa29-139">Außerdem führt `http.sys` und die <xref:System.Uri?displayProperty=nameWithType>-Klasse auch die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="1aa29-139">In addition, `http.sys` and the <xref:System.Uri?displayProperty=nameWithType> class also does the following:</span></span>  
  
- <span data-ttu-id="1aa29-140">Deaktiviert alle Prozent codierten Werte.</span><span class="sxs-lookup"><span data-stu-id="1aa29-140">Un-escapes all percent encoded values.</span></span>  
  
- <span data-ttu-id="1aa29-141">Konvertiert Prozent codierte nicht-ASCII-Zeichen in eine UTF-16-Zeichen Darstellung.</span><span class="sxs-lookup"><span data-stu-id="1aa29-141">Converts percent-encoded non-ASCII characters into a UTF-16 character representation.</span></span> <span data-ttu-id="1aa29-142">Beachten Sie, dass UTF-8-und ANSI/DBCS-Zeichen sowie Unicode-Zeichen (Unicode-Codierung mit dem Format "% uXXXX") unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="1aa29-142">Note that UTF-8 and ANSI/DBCS characters are supported as well as Unicode characters (Unicode encoding using the %uXXXX format).</span></span>  
  
- <span data-ttu-id="1aa29-143">Führt andere normalisierungs Schritte aus, z. b. Pfad Komprimierung</span><span class="sxs-lookup"><span data-stu-id="1aa29-143">Executes other normalization steps, like path compression.</span></span>  
  
 <span data-ttu-id="1aa29-144">Da die Anforderung keine Informationen über die Codierung enthält, die für Prozent codierte Werte verwendet wird, ist es möglicherweise nicht möglich, die richtige Codierung zu ermitteln, indem Sie die Prozent codierten Werte zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="1aa29-144">Since the request doesn't contain any information about the encoding used for percent-encoded values, it may not be possible to determine the correct encoding just by parsing the percent-encoded values.</span></span>  
  
 <span data-ttu-id="1aa29-145">Daher stellt `http.sys` zwei Registrierungsschlüssel zum Ändern des Prozesses bereit:</span><span class="sxs-lookup"><span data-stu-id="1aa29-145">Therefore `http.sys` provides two registry keys for modifying the process:</span></span>  
  
|<span data-ttu-id="1aa29-146">-Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="1aa29-146">Registry Key</span></span>|<span data-ttu-id="1aa29-147">Standardwert</span><span class="sxs-lookup"><span data-stu-id="1aa29-147">Default Value</span></span>|<span data-ttu-id="1aa29-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1aa29-148">Description</span></span>|  
|------------------|-------------------|-----------------|  
|<span data-ttu-id="1aa29-149">EnableNonUTF8</span><span class="sxs-lookup"><span data-stu-id="1aa29-149">EnableNonUTF8</span></span>|<span data-ttu-id="1aa29-150">1</span><span class="sxs-lookup"><span data-stu-id="1aa29-150">1</span></span>|<span data-ttu-id="1aa29-151">Wenn 0 (null), akzeptiert `http.sys` nur UTF-8-codierte URLs.</span><span class="sxs-lookup"><span data-stu-id="1aa29-151">If zero, `http.sys` accepts only UTF-8-encoded URLs.</span></span><br /><br /> <span data-ttu-id="1aa29-152">Wenn der Wert ungleich 0 (null) ist, akzeptiert `http.sys` auch ANSI-codierte oder DBCS-codierte URLs in Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="1aa29-152">If non-zero, `http.sys` also accepts ANSI-encoded or DBCS-encoded URLs in requests.</span></span>|  
|<span data-ttu-id="1aa29-153">FavorUTF8</span><span class="sxs-lookup"><span data-stu-id="1aa29-153">FavorUTF8</span></span>|<span data-ttu-id="1aa29-154">1</span><span class="sxs-lookup"><span data-stu-id="1aa29-154">1</span></span>|<span data-ttu-id="1aa29-155">Wenn der Wert ungleich 0 (null) ist, versucht `http.sys` immer zuerst, eine URL als UTF-8 zu decodieren. Wenn diese Konvertierung fehlschlägt und EnableNonUTF8 nicht NULL ist, versucht http. sys, Sie als ANSI oder DBCS zu decodieren.</span><span class="sxs-lookup"><span data-stu-id="1aa29-155">If non-zero, `http.sys` always tries to decode a URL as UTF-8 first; if that conversion fails and EnableNonUTF8 is non-zero, Http.sys then tries to decode it as ANSI or DBCS.</span></span><br /><br /> <span data-ttu-id="1aa29-156">Wenn 0 (und EnableNonUTF8 nicht null) ist, versucht `http.sys`, Sie als ANSI oder DBCS zu decodieren. Wenn dies nicht erfolgreich ist, versucht es, eine UTF-8-Konvertierung durch zukonvertieren.</span><span class="sxs-lookup"><span data-stu-id="1aa29-156">If zero (and EnableNonUTF8 is non-zero), `http.sys` tries to decode it as ANSI or DBCS; if that is not successful, it tries a UTF-8 conversion.</span></span>|  
  
 <span data-ttu-id="1aa29-157">Wenn <xref:System.Net.HttpListener> eine Anforderung empfängt, wird der konvertierte URI von `http.sys` als Eingabe für die <xref:System.Net.HttpListenerRequest.Url%2A>-Eigenschaft verwendet.</span><span class="sxs-lookup"><span data-stu-id="1aa29-157">When <xref:System.Net.HttpListener> receives a request, it uses the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="1aa29-158">Es besteht die Notwendigkeit, Zeichen neben Zeichen und Zahlen in URIs zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1aa29-158">There is a need for supporting characters besides characters and numbers in URIs.</span></span> <span data-ttu-id="1aa29-159">Ein Beispiel ist der folgende URI, der zum Abrufen von Kundeninformationen für die Kundennummer "1/3812" verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="1aa29-159">An example is the following URI, which is used to retrieve customer information for customer number "1/3812":</span></span>  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 <span data-ttu-id="1aa29-160">Notieren Sie sich den Prozentsatz codierten Schrägstrich im URI (% 2F).</span><span class="sxs-lookup"><span data-stu-id="1aa29-160">Note the percent-encoded slash in the Uri (%2F).</span></span> <span data-ttu-id="1aa29-161">Dies ist erforderlich, da der Schrägstrich in diesem Fall Daten und kein Pfad Trennzeichen darstellt.</span><span class="sxs-lookup"><span data-stu-id="1aa29-161">This is necessary, since in this case the slash character represents data and not a path delimiter.</span></span>  
  
 <span data-ttu-id="1aa29-162">Wenn die Zeichenfolge an den URI-Konstruktor übergeben wird, führt dies zu folgendem URI:</span><span class="sxs-lookup"><span data-stu-id="1aa29-162">Passing the string to Uri constructor will lead to the following URI:</span></span>  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 <span data-ttu-id="1aa29-163">Wenn Sie den Pfad in seine Segmente aufteilen, werden die folgenden Elemente angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1aa29-163">Splitting the path into its segments would result in the following elements:</span></span>  
  
 `Customer('1`  
  
 `3812')`  
  
 <span data-ttu-id="1aa29-164">Dies ist nicht die Absicht des Absenders der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="1aa29-164">This is not the intent of the sender of the request.</span></span>  
  
 <span data-ttu-id="1aa29-165">Wenn das **unescaperequesturl** -Attribut auf **false**festgelegt ist, und wenn der <xref:System.Net.HttpListener> eine Anforderung empfängt, wird der unformatierte URI anstelle des konvertierten URI von `http.sys` als Eingabe für die <xref:System.Net.HttpListenerRequest.Url%2A>-Eigenschaft verwendet.</span><span class="sxs-lookup"><span data-stu-id="1aa29-165">If the **unescapeRequestUrl** attribute is set to **false**, then when the <xref:System.Net.HttpListener> receives a request, it uses the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="1aa29-166">Der Standardwert für das **unescaperequesturl** -Attribut ist " **true**".</span><span class="sxs-lookup"><span data-stu-id="1aa29-166">The default value for the **unescapeRequestUrl** attribute is **true**.</span></span>  
  
 <span data-ttu-id="1aa29-167">Die <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A>-Eigenschaft kann verwendet werden, um den aktuellen Wert des **unescaperequesturl** -Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1aa29-167">The <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> property can be used to get the current value of the **unescapeRequestUrl** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1aa29-168">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1aa29-168">Example</span></span>  
 <span data-ttu-id="1aa29-169">Im folgenden Beispiel wird gezeigt, wie die <xref:System.Net.HttpListener>-Klasse konfiguriert wird, wenn Sie eine Anforderung erhält, den unformatierten URI anstelle des konvertierten URI von `http.sys` als Eingabe für die <xref:System.Net.HttpListenerRequest.Url%2A>-Eigenschaft zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1aa29-169">The following example shows how to configure the <xref:System.Net.HttpListener> class when it receives a request to use the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="1aa29-170">Elementinformationen</span><span class="sxs-lookup"><span data-stu-id="1aa29-170">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="1aa29-171">Namespace</span><span class="sxs-lookup"><span data-stu-id="1aa29-171">Namespace</span></span>|<span data-ttu-id="1aa29-172">System.Net</span><span class="sxs-lookup"><span data-stu-id="1aa29-172">System.Net</span></span>|  
|<span data-ttu-id="1aa29-173">Schemaname</span><span class="sxs-lookup"><span data-stu-id="1aa29-173">Schema Name</span></span>||  
|<span data-ttu-id="1aa29-174">Validierungsdatei</span><span class="sxs-lookup"><span data-stu-id="1aa29-174">Validation File</span></span>||  
|<span data-ttu-id="1aa29-175">Kann leer sein</span><span class="sxs-lookup"><span data-stu-id="1aa29-175">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="1aa29-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1aa29-176">See also</span></span>

- <xref:System.Net.Configuration.HttpListenerElement>
- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpListenerRequest.Url%2A>
- [<span data-ttu-id="1aa29-177">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="1aa29-177">Network Settings Schema</span></span>](index.md)
