---
title: <httpListener>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
ms.openlocfilehash: b3a6d527bc1bf8210bb85424fa218fda495a2a2d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59099741"
---
# <a name="httplistener-element-network-settings"></a><span data-ttu-id="47fcd-102">\<HttpListener >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="47fcd-102">\<httpListener> Element (Network Settings)</span></span>
<span data-ttu-id="47fcd-103">Passt die Parameter ein, die die <xref:System.Net.HttpListener> Klasse.</span><span class="sxs-lookup"><span data-stu-id="47fcd-103">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>  
  
 <span data-ttu-id="47fcd-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="47fcd-104">\<configuration></span></span>  
<span data-ttu-id="47fcd-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="47fcd-105">\<system.net></span></span>  
<span data-ttu-id="47fcd-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="47fcd-106">\<settings></span></span>  
<span data-ttu-id="47fcd-107">\<httpListener></span><span class="sxs-lookup"><span data-stu-id="47fcd-107">\<httpListener></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47fcd-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="47fcd-108">Syntax</span></span>  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a><span data-ttu-id="47fcd-109">Typ</span><span class="sxs-lookup"><span data-stu-id="47fcd-109">Type</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47fcd-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="47fcd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="47fcd-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="47fcd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47fcd-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="47fcd-112">Attributes</span></span>  
  
|<span data-ttu-id="47fcd-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="47fcd-113">Attribute</span></span>|<span data-ttu-id="47fcd-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="47fcd-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="47fcd-115">unescapeRequestUrl</span><span class="sxs-lookup"><span data-stu-id="47fcd-115">unescapeRequestUrl</span></span>|<span data-ttu-id="47fcd-116">Ein boolescher Wert, der gibt an, wenn eine <xref:System.Net.HttpListener> -Instanz verwendet den unformatierten URI ohne Escapezeichen anstelle des konvertierten URI.</span><span class="sxs-lookup"><span data-stu-id="47fcd-116">A Boolean value that indicates if a <xref:System.Net.HttpListener> instance uses the raw unescaped URI instead of the converted URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="47fcd-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="47fcd-117">Child Elements</span></span>  
 <span data-ttu-id="47fcd-118">Keine</span><span class="sxs-lookup"><span data-stu-id="47fcd-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="47fcd-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="47fcd-119">Parent Elements</span></span>  
  
|<span data-ttu-id="47fcd-120">**Element**</span><span class="sxs-lookup"><span data-stu-id="47fcd-120">**Element**</span></span>|<span data-ttu-id="47fcd-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="47fcd-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="47fcd-122">settings</span><span class="sxs-lookup"><span data-stu-id="47fcd-122">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="47fcd-123">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="47fcd-123">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47fcd-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="47fcd-124">Remarks</span></span>  
 <span data-ttu-id="47fcd-125">Die **UnescapeRequestUrl** Attribut gibt an, ob <xref:System.Net.HttpListener> verwendet den unformatierten URI ohne Escapezeichen anstelle des konvertierten URI, in dem alle Werte mit Prozentzeichen codiert konvertiert und andere Normalisierung Schritte sind.</span><span class="sxs-lookup"><span data-stu-id="47fcd-125">The **unescapeRequestUrl** attribute indicates if <xref:System.Net.HttpListener> uses the raw unescaped URI instead of the converted URI where any percent-encoded values are converted and other normalization steps are taken.</span></span>  
  
 <span data-ttu-id="47fcd-126">Wenn eine <xref:System.Net.HttpListener> Instanz empfängt eine Anforderung über die `http.sys` -Dienst, erstellt er eine Instanz der URI-Zeichenfolge von bereitgestellten `http.sys`, und macht sie als verfügbar der <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="47fcd-126">When a <xref:System.Net.HttpListener> instance receives a request through the `http.sys` service, it creates an instance of the URI string provided by `http.sys`, and exposes it as the <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="47fcd-127">Die `http.sys` Dienst verfügbar macht, zwei Anfrage-URI-Zeichenfolgen:</span><span class="sxs-lookup"><span data-stu-id="47fcd-127">The `http.sys` service exposes two request URI strings:</span></span>  
  
-   <span data-ttu-id="47fcd-128">RAW-URI</span><span class="sxs-lookup"><span data-stu-id="47fcd-128">Raw URI</span></span>  
  
-   <span data-ttu-id="47fcd-129">Konvertierten URI</span><span class="sxs-lookup"><span data-stu-id="47fcd-129">Converted URI</span></span>  
  
 <span data-ttu-id="47fcd-130">Der raw-URI ist die <xref:System.Uri?displayProperty=nameWithType> bereitgestellt, in der Anforderungszeile einer HTTP-Anforderung:</span><span class="sxs-lookup"><span data-stu-id="47fcd-130">The raw URI is the <xref:System.Uri?displayProperty=nameWithType> provided in the request line of a HTTP request:</span></span>  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 <span data-ttu-id="47fcd-131">Den unformatierten URI gebotenen `http.sys` für die oben genannte Anforderung ist "/ Path /".</span><span class="sxs-lookup"><span data-stu-id="47fcd-131">The raw URI provided by `http.sys` for the request mentioned above, is "/path/".</span></span> <span data-ttu-id="47fcd-132">Dies stellt die Zeichenfolge, die das HTTP-Verb folgt, wie sie über das Netzwerk gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="47fcd-132">This represents the string following the HTTP verb as it was sent over the network.</span></span>  
  
 <span data-ttu-id="47fcd-133">Die `http.sys` -Dienst erstellt einen konvertierten URI aus den Informationen in der Anforderung bereitgestellt werden, mithilfe den URI aus der HTTP-Anforderungszeilen und der Host-Header, um zu bestimmen, den Ursprungsserver die Anforderung weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="47fcd-133">The `http.sys` service creates a converted URI from the information provided in the request by using the URI provided in the HTTP request line and the Host header to determine the origin server the request should be forwarded to.</span></span> <span data-ttu-id="47fcd-134">Dies erfolgt durch Vergleichen der Informationen aus der Anforderung mit einem Satz von URI-Präfixe registriert.</span><span class="sxs-lookup"><span data-stu-id="47fcd-134">This is done by comparing the information from the request with a set of registered URI prefixes.</span></span> <span data-ttu-id="47fcd-135">Die HTTP-Server SDK-Dokumentation, die auf diesen konvertierten URI als HTTP_COOKED_URL-Struktur bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="47fcd-135">The HTTP Server SDK documentation refers to this converted URI as the HTTP_COOKED_URL structure.</span></span>  
  
 <span data-ttu-id="47fcd-136">Um die Anforderung mit URI-Präfixe, die registrierten vergleichen zu können, muss eine Normalisierung der Anforderung erfolgen.</span><span class="sxs-lookup"><span data-stu-id="47fcd-136">In order to be able to compare the request with registered URI prefixes, some normalization to the request needs to be done.</span></span> <span data-ttu-id="47fcd-137">Für das Beispiel oben des konvertierten URI würde wie folgt lauten:</span><span class="sxs-lookup"><span data-stu-id="47fcd-137">For the sample above the converted URI would be as follows:</span></span>  
  
 `http://www.contoso.com/path/`  
  
 <span data-ttu-id="47fcd-138">Die `http.sys` service kombiniert die <xref:System.Uri.Host%2A?displayProperty=nameWithType> Eigenschaftswert und die Zeichenfolge in der Anforderungszeile auf einen konvertierten URI zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="47fcd-138">The `http.sys` service combines the <xref:System.Uri.Host%2A?displayProperty=nameWithType> property value and the string in the request line to create a converted URI.</span></span> <span data-ttu-id="47fcd-139">Darüber hinaus `http.sys` und <xref:System.Uri?displayProperty=nameWithType> Klasse wird außerdem Folgendes:</span><span class="sxs-lookup"><span data-stu-id="47fcd-139">In addition, `http.sys` and the <xref:System.Uri?displayProperty=nameWithType> class also does the following:</span></span>  
  
-   <span data-ttu-id="47fcd-140">Un-Escapezeichen alle als Prozentwert codierte Werte.</span><span class="sxs-lookup"><span data-stu-id="47fcd-140">Un-escapes all percent encoded values.</span></span>  
  
-   <span data-ttu-id="47fcd-141">Prozentwert codiert konvertiert nicht-ASCII-Zeichen in eine UTF-16-Zeichen-Darstellung.</span><span class="sxs-lookup"><span data-stu-id="47fcd-141">Converts percent-encoded non-ASCII characters into a UTF-16 character representation.</span></span> <span data-ttu-id="47fcd-142">Beachten Sie, dass UTF-8 und ANSI/DBCS-Zeichen sowie Unicode-Zeichen (Unicode-Codierung mit dem % uXXXX-Format) unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="47fcd-142">Note that UTF-8 and ANSI/DBCS characters are supported as well as Unicode characters (Unicode encoding using the %uXXXX format).</span></span>  
  
-   <span data-ttu-id="47fcd-143">Führt andere Normalisierungsschritte, ebenso wie die pfadkomprimierung an.</span><span class="sxs-lookup"><span data-stu-id="47fcd-143">Executes other normalization steps, like path compression.</span></span>  
  
 <span data-ttu-id="47fcd-144">Da die Anforderung keine Informationen über die Codierung für prozentcodiert Werte verwendet wird, es möglich, zu bestimmen, die richtige Codierung nur durch Analysieren der prozentcodiert Werte möglicherweise nicht.</span><span class="sxs-lookup"><span data-stu-id="47fcd-144">Since the request doesn't contain any information about the encoding used for percent-encoded values, it may not be possible to determine the correct encoding just by parsing the percent-encoded values.</span></span>  
  
 <span data-ttu-id="47fcd-145">Aus diesem Grund `http.sys` stellt zwei Registrierungsschlüssel zum Ändern des Prozesses:</span><span class="sxs-lookup"><span data-stu-id="47fcd-145">Therefore `http.sys` provides two registry keys for modifying the process:</span></span>  
  
|<span data-ttu-id="47fcd-146">-Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="47fcd-146">Registry Key</span></span>|<span data-ttu-id="47fcd-147">Standardwert</span><span class="sxs-lookup"><span data-stu-id="47fcd-147">Default Value</span></span>|<span data-ttu-id="47fcd-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="47fcd-148">Description</span></span>|  
|------------------|-------------------|-----------------|  
|<span data-ttu-id="47fcd-149">EnableNonUTF8</span><span class="sxs-lookup"><span data-stu-id="47fcd-149">EnableNonUTF8</span></span>|<span data-ttu-id="47fcd-150">1</span><span class="sxs-lookup"><span data-stu-id="47fcd-150">1</span></span>|<span data-ttu-id="47fcd-151">Wenn NULL, `http.sys` akzeptiert nur UTF-8-codierte URLs.</span><span class="sxs-lookup"><span data-stu-id="47fcd-151">If zero, `http.sys` accepts only UTF-8-encoded URLs.</span></span><br /><br /> <span data-ttu-id="47fcd-152">Wenn ungleich NULL ist, `http.sys` akzeptiert auch ANSI-codiert oder DBCS-codierte URLs in Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="47fcd-152">If non-zero, `http.sys` also accepts ANSI-encoded or DBCS-encoded URLs in requests.</span></span>|  
|<span data-ttu-id="47fcd-153">FavorUTF8</span><span class="sxs-lookup"><span data-stu-id="47fcd-153">FavorUTF8</span></span>|<span data-ttu-id="47fcd-154">1</span><span class="sxs-lookup"><span data-stu-id="47fcd-154">1</span></span>|<span data-ttu-id="47fcd-155">Wenn ungleich NULL ist, `http.sys` immer versucht, eine URL als UTF-8 zuerst decodieren, wenn diese Konvertierung schlägt fehl, und EnableNonUTF8 ungleich NULL, "http.sys" und dann versucht, die als ANSI oder DBCS decodiert werden.</span><span class="sxs-lookup"><span data-stu-id="47fcd-155">If non-zero, `http.sys` always tries to decode a URL as UTF-8 first; if that conversion fails and EnableNonUTF8 is non-zero, Http.sys then tries to decode it as ANSI or DBCS.</span></span><br /><br /> <span data-ttu-id="47fcd-156">Wenn der Wert 0 (und EnableNonUTF8 ungleich null), `http.sys` versucht, es als ANSI oder DBCS; Wenn das Decodieren nicht erfolgreich ist, versucht eine UTF-8-Konvertierung.</span><span class="sxs-lookup"><span data-stu-id="47fcd-156">If zero (and EnableNonUTF8 is non-zero), `http.sys` tries to decode it as ANSI or DBCS; if that is not successful, it tries a UTF-8 conversion.</span></span>|  
  
 <span data-ttu-id="47fcd-157">Wenn <xref:System.Net.HttpListener> eine Anforderung empfängt, verwendet es den konvertierten URI aus `http.sys` als Eingabe für die <xref:System.Net.HttpListenerRequest.Url%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="47fcd-157">When <xref:System.Net.HttpListener> receives a request, it uses the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="47fcd-158">Besteht die Notwendigkeit für die Unterstützung von Zeichen als Buchstaben und Zahlen in URIs.</span><span class="sxs-lookup"><span data-stu-id="47fcd-158">There is a need for supporting characters besides characters and numbers in URIs.</span></span> <span data-ttu-id="47fcd-159">Ein Beispiel ist der folgende URI, dient zum Abrufen von Kundeninformationen für Kunden Zahl "1/3812":</span><span class="sxs-lookup"><span data-stu-id="47fcd-159">An example is the following URI, which is used to retrieve customer information for customer number "1/3812":</span></span>  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 <span data-ttu-id="47fcd-160">Beachten Sie den Prozentwert codiert Schrägstrich im Uri (% 2F).</span><span class="sxs-lookup"><span data-stu-id="47fcd-160">Note the percent-encoded slash in the Uri (%2F).</span></span> <span data-ttu-id="47fcd-161">Dies ist erforderlich, da in diesem Fall der Schrägstrich Daten und kein Pfadtrennzeichen darstellt.</span><span class="sxs-lookup"><span data-stu-id="47fcd-161">This is necessary, since in this case the slash character represents data and not a path delimiter.</span></span>  
  
 <span data-ttu-id="47fcd-162">Die Zeichenfolge an den Uri-Konstruktor übergeben, führt der folgende URI:</span><span class="sxs-lookup"><span data-stu-id="47fcd-162">Passing the string to Uri constructor will lead to the following URI:</span></span>  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 <span data-ttu-id="47fcd-163">Den Pfad in seine Segmente aufgeteilt werden, würde in den folgenden Elementen:</span><span class="sxs-lookup"><span data-stu-id="47fcd-163">Splitting the path into its segments would result in the following elements:</span></span>  
  
 `Customer('1`  
  
 `3812')`  
  
 <span data-ttu-id="47fcd-164">Dies ist nicht die Absicht des Absenders der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="47fcd-164">This is not the intent of the sender of the request.</span></span>  
  
 <span data-ttu-id="47fcd-165">Wenn die **UnescapeRequestUrl** -Attributsatz auf **"false"**, wenn dann der <xref:System.Net.HttpListener> eine Anforderung empfängt, anstelle des konvertierten URI aus den unformatierten URI verwendet `http.sys` als Eingabe für die <xref:System.Net.HttpListenerRequest.Url%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="47fcd-165">If the **unescapeRequestUrl** attribute is set to **false**, then when the <xref:System.Net.HttpListener> receives a request, it uses the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="47fcd-166">Der Standardwert für die **UnescapeRequestUrl** Attribut **"true"**.</span><span class="sxs-lookup"><span data-stu-id="47fcd-166">The default value for the **unescapeRequestUrl** attribute is **true**.</span></span>  
  
 <span data-ttu-id="47fcd-167">Die <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> Eigenschaft kann verwendet werden, um den aktuellen Wert der erhalten die **UnescapeRequestUrl** Attribut aus anwendbaren Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="47fcd-167">The <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> property can be used to get the current value of the **unescapeRequestUrl** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47fcd-168">Beispiel</span><span class="sxs-lookup"><span data-stu-id="47fcd-168">Example</span></span>  
 <span data-ttu-id="47fcd-169">Das folgende Beispiel zeigt, wie Sie konfigurieren die <xref:System.Net.HttpListener> Klasse bei Empfang einer Anforderung mit den unformatierten URI anstelle des konvertierten URI aus `http.sys` als Eingabe für die <xref:System.Net.HttpListenerRequest.Url%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="47fcd-169">The following example shows how to configure the <xref:System.Net.HttpListener> class when it receives a request to use the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="47fcd-170">Elementinformationen</span><span class="sxs-lookup"><span data-stu-id="47fcd-170">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="47fcd-171">Namespace</span><span class="sxs-lookup"><span data-stu-id="47fcd-171">Namespace</span></span>|<span data-ttu-id="47fcd-172">System.Net</span><span class="sxs-lookup"><span data-stu-id="47fcd-172">System.Net</span></span>|  
|<span data-ttu-id="47fcd-173">Schemaname</span><span class="sxs-lookup"><span data-stu-id="47fcd-173">Schema Name</span></span>||  
|<span data-ttu-id="47fcd-174">Validierungsdatei</span><span class="sxs-lookup"><span data-stu-id="47fcd-174">Validation File</span></span>||  
|<span data-ttu-id="47fcd-175">Leer kann sein</span><span class="sxs-lookup"><span data-stu-id="47fcd-175">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="47fcd-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47fcd-176">See also</span></span>

- <xref:System.Net.Configuration.HttpListenerElement>
- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpListenerRequest.Url%2A>
- [<span data-ttu-id="47fcd-177">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="47fcd-177">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
