---
title: '&lt;HttpListener&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
ms.openlocfilehash: 58228eed71dd6a5f5af8e26c02db9633da6ceef6
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2018
ms.locfileid: "50197781"
---
# <a name="lthttplistenergt-element-network-settings"></a>&lt;HttpListener&gt; -Element (Netzwerkeinstellungen)
Passt die Parameter ein, die die <xref:System.Net.HttpListener> Klasse.  
  
 \<configuration>  
\<system.net>  
\<settings>  
\<HttpListener >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a>Typ  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|unescapeRequestUrl|Ein boolescher Wert, der gibt an, wenn eine <xref:System.Net.HttpListener> -Instanz verwendet den unformatierten URI ohne Escapezeichen anstelle des konvertierten URI.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.|  
  
## <a name="remarks"></a>Hinweise  
 Die **UnescapeRequestUrl** Attribut gibt an, ob <xref:System.Net.HttpListener> verwendet den unformatierten URI ohne Escapezeichen anstelle des konvertierten URI, in dem alle Werte mit Prozentzeichen codiert konvertiert und andere Normalisierung Schritte sind.  
  
 Wenn eine <xref:System.Net.HttpListener> Instanz empfängt eine Anforderung über die `http.sys` -Dienst, erstellt er eine Instanz der URI-Zeichenfolge von bereitgestellten `http.sys`, und macht sie als verfügbar der <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> Eigenschaft.  
  
 Die `http.sys` Dienst verfügbar macht, zwei Anfrage-URI-Zeichenfolgen:  
  
-   RAW-URI  
  
-   Konvertierten URI  
  
 Der raw-URI ist die <xref:System.Uri?displayProperty=nameWithType> bereitgestellt, in der Anforderungszeile einer HTTP-Anforderung:  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 Den unformatierten URI gebotenen `http.sys` für die oben genannte Anforderung ist "/ Path /". Dies stellt die Zeichenfolge, die das HTTP-Verb folgt, wie sie über das Netzwerk gesendet wurde.  
  
 Die `http.sys` -Dienst erstellt einen konvertierten URI aus den Informationen in der Anforderung bereitgestellt werden, mithilfe den URI aus der HTTP-Anforderungszeilen und der Host-Header, um zu bestimmen, den Ursprungsserver die Anforderung weitergeleitet werden soll. Dies erfolgt durch Vergleichen der Informationen aus der Anforderung mit einem Satz von URI-Präfixe registriert. Die HTTP-Server SDK-Dokumentation, die auf diesen konvertierten URI als HTTP_COOKED_URL-Struktur bezeichnet wird.  
  
 Um die Anforderung mit URI-Präfixe, die registrierten vergleichen zu können, muss eine Normalisierung der Anforderung erfolgen. Für das Beispiel oben des konvertierten URI würde wie folgt lauten:  
  
 `http://www.contoso.com/path/`  
  
 Die `http.sys` service kombiniert die <xref:System.Uri.Host%2A?displayProperty=nameWithType> Eigenschaftswert und die Zeichenfolge in der Anforderungszeile auf einen konvertierten URI zu erstellen. Darüber hinaus `http.sys` und <xref:System.Uri?displayProperty=nameWithType> Klasse wird außerdem Folgendes:  
  
-   Un-Escapezeichen alle als Prozentwert codierte Werte.  
  
-   Prozentwert codiert konvertiert nicht-ASCII-Zeichen in eine UTF-16-Zeichen-Darstellung. Beachten Sie, dass UTF-8 und ANSI/DBCS-Zeichen sowie Unicode-Zeichen (Unicode-Codierung mit dem % uXXXX-Format) unterstützt werden.  
  
-   Führt andere Normalisierungsschritte, ebenso wie die pfadkomprimierung an.  
  
 Da die Anforderung keine Informationen über die Codierung für prozentcodiert Werte verwendet wird, es möglich, zu bestimmen, die richtige Codierung nur durch Analysieren der prozentcodiert Werte möglicherweise nicht.  
  
 Aus diesem Grund `http.sys` stellt zwei Registrierungsschlüssel zum Ändern des Prozesses:  
  
|-Registrierungsschlüssel|Standardwert|Beschreibung|  
|------------------|-------------------|-----------------|  
|EnableNonUTF8|1|Wenn NULL, `http.sys` akzeptiert nur UTF-8-codierte URLs.<br /><br /> Wenn ungleich NULL ist, `http.sys` akzeptiert auch ANSI-codiert oder DBCS-codierte URLs in Anforderungen.|  
|FavorUTF8|1|Wenn ungleich NULL ist, `http.sys` immer versucht, eine URL als UTF-8 zuerst decodieren, wenn diese Konvertierung schlägt fehl, und EnableNonUTF8 ungleich NULL, "http.sys" und dann versucht, die als ANSI oder DBCS decodiert werden.<br /><br /> Wenn der Wert 0 (und EnableNonUTF8 ungleich null), `http.sys` versucht, es als ANSI oder DBCS; Wenn das Decodieren nicht erfolgreich ist, versucht eine UTF-8-Konvertierung.|  
  
 Wenn <xref:System.Net.HttpListener> eine Anforderung empfängt, verwendet es den konvertierten URI aus `http.sys` als Eingabe für die <xref:System.Net.HttpListenerRequest.Url%2A> Eigenschaft.  
  
 Besteht die Notwendigkeit für die Unterstützung von Zeichen als Buchstaben und Zahlen in URIs. Ein Beispiel ist der folgende URI, dient zum Abrufen von Kundeninformationen für Kunden Zahl "1/3812":  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 Beachten Sie den Prozentwert codiert Schrägstrich im Uri (% 2F). Dies ist erforderlich, da in diesem Fall der Schrägstrich Daten und kein Pfadtrennzeichen darstellt.  
  
 Die Zeichenfolge an den Uri-Konstruktor übergeben, führt der folgende URI:  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 Den Pfad in seine Segmente aufgeteilt werden, würde in den folgenden Elementen:  
  
 `Customer('1`  
  
 `3812')`  
  
 Dies ist nicht die Absicht des Absenders der Anforderung.  
  
 Wenn die **UnescapeRequestUrl** -Attributsatz auf **"false"**, wenn dann der <xref:System.Net.HttpListener> eine Anforderung empfängt, anstelle des konvertierten URI aus den unformatierten URI verwendet `http.sys` als Eingabe für die <xref:System.Net.HttpListenerRequest.Url%2A> Eigenschaft.  
  
 Der Standardwert für die **UnescapeRequestUrl** Attribut **"true"**.  
  
 Die <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> Eigenschaft kann verwendet werden, um den aktuellen Wert der erhalten die **UnescapeRequestUrl** Attribut aus anwendbaren Konfigurationsdateien.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie konfigurieren die <xref:System.Net.HttpListener> Klasse bei Empfang einer Anforderung mit den unformatierten URI anstelle des konvertierten URI aus `http.sys` als Eingabe für die <xref:System.Net.HttpListenerRequest.Url%2A> Eigenschaft.  
  
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
  
## <a name="element-information"></a>Elementinformationen  
  
|||
|-|-|  
|Namespace|System.Net|  
|Schemaname||  
|Validierungsdatei||  
|Leer kann sein||  
  
## <a name="see-also"></a>Siehe auch  
- <xref:System.Net.Configuration.HttpListenerElement>  
- <xref:System.Net.HttpListener>  
- <xref:System.Net.HttpListenerRequest.Url%2A>  
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
