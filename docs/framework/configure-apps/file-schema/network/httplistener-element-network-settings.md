---
title: '&lt;HttpListener&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a327f757f26c815d5b2cffe179af68bbe3d152eb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="lthttplistenergt-element-network-settings"></a>&lt;HttpListener&gt; -Element (Netzwerkeinstellungen)
Passt die vom verwendeten Parameter an die <xref:System.Net.HttpListener> Klasse.  
  
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
|unescapeRequestUrl|Ein boolescher Wert, der gibt an, wenn eine <xref:System.Net.HttpListener> Instanz verwendet den unformatierten URI ohne Escapezeichen anstelle des konvertierten URI.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.|  
  
## <a name="remarks"></a>Hinweise  
 Die **UnescapeRequestUrl** Attribut gibt an, ob <xref:System.Net.HttpListener> verwendet den unformatierten URI ohne Escapezeichen anstelle des konvertierten URI, in dem alle Prozentzeichen codiert Werte konvertiert und andere Normalisierungsschritte unternommen werden.  
  
 Wenn eine <xref:System.Net.HttpListener> Instanz empfängt eine Anforderung über die `http.sys` Service, erstellt er eine Instanz der URI-Zeichenfolge, die von bereitgestellte `http.sys`, und verfügbar gemacht wird, als die <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> Eigenschaft.  
  
 Die `http.sys` Dienst macht zwei Zeichenfolgen der Anfrage-URI:  
  
-   RAW-URI  
  
-   Konvertierte URI  
  
 Der unformatierte URI ist der <xref:System.Uri?displayProperty=nameWithType> in der Anforderungszeile einer HTTP-Anforderung bereitgestellt:  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 Der unformatierte URI gebotenen `http.sys` für die oben genannte Anforderung ist "/ Path /". Dies stellt die Zeichenfolge, die das HTTP-Verb folgt, da sie über das Netzwerk gesendet wurden.  
  
 Die `http.sys` Dienst erstellt einen konvertierten URI aus der Informationen in der Anforderung mithilfe den in der Anforderungszeile HTTP-URI und der Hostheader, um zu bestimmen, den Ursprungsserver die Anforderung weitergeleitet werden sollen. Dies erfolgt durch Vergleichen der Informationen aus der Anforderung mit einem Satz von registrierten URI-Präfixen. Die HTTP-Server-SDK-Dokumentation verweist auf diesen konvertierten URI als HTTP_COOKED_URL-Struktur.  
  
 Damit die Anforderung mit registrierten URI-Präfixe verglichen werden können, muss eine Normalisierung der Anforderung erfolgen. Für das Beispiel oben des konvertierten URI würde wie folgt lauten:  
  
 `http://www.contoso.com/path/`  
  
 Die `http.sys` service kombiniert die <xref:System.Uri.Host%2A?displayProperty=nameWithType> Eigenschaftswert und die Zeichenfolge in der Anforderungszeile, um einen konvertierten URI zu erstellen. Darüber hinaus `http.sys` und die <xref:System.Uri?displayProperty=nameWithType> Klasse wird auch Folgendes:  
  
-   Alle Prozentangaben codierte un-Escapezeichen.  
  
-   Konvertiert Prozentzeichen codiert nicht-ASCII-Zeichen in eine UTF-16-Zeichen-Darstellung. Beachten Sie, dass UTF-8 und ANSI/DBCS-Zeichen sowie Unicode-Zeichen (Unicode-Codierung mit dem % uXXXX-Format) unterstützt werden.  
  
-   Führt andere Normalisierungsschritte, ebenso wie die Pfad-Komprimierung an.  
  
 Da die Anforderung keine Informationen enthält über die Codierung für Werte Prozentzeichen codiert möglich, Bestimmen der richtigen Codierung nur durch das Analysieren der Prozentzeichen codiert Werte möglicherweise nicht.  
  
 Aus diesem Grund `http.sys` bietet zwei Registrierungsschlüssel zum Ändern des Prozesses:  
  
|-Registrierungsschlüssel|Standardwert|Beschreibung|  
|------------------|-------------------|-----------------|  
|EnableNonUTF8|1|Wenn der Wert 0, `http.sys` akzeptiert nur UTF-8-codierte URLs.<br /><br /> Wenn ungleich 0 (null), `http.sys` auch ANSI-codiert oder DBCS-codierte URLs in Anforderungen akzeptiert.|  
|FavorUTF8|1|Wenn ungleich 0 (null), `http.sys` immer versucht, eine URL als UTF-8 zuerst decodiert werden, wenn dieser Konvertierung ein Fehler auftritt und EnableNonUTF8 ungleich NULL ist, "http.sys" und dann versucht, die als ANSI oder DBCS decodiert werden.<br /><br /> Wenn der Wert 0 (und EnableNonUTF8 ist ungleich null), `http.sys` versucht, die als ANSI oder DBCS; Wenn für das decodiert nicht erfolgreich ist, versucht eine UTF-8-Konvertierung.|  
  
 Wenn <xref:System.Net.HttpListener> eine Anforderung empfängt, verwendet es den konvertierten URI aus `http.sys` als Eingabe in die <xref:System.Net.HttpListenerRequest.Url%2A> Eigenschaft.  
  
 Es ist erforderlich für die Unterstützung von Zeichen als Buchstaben und Zahlen in URIs. Ein Beispiel ist der folgende URI, die verwendet wird, um Kundeninformationen für Kunden abrufen Nummer "1/3812":  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 Beachten Sie das Prozentzeichen codiert Schrägstrich in der Uri (% 2F). Dies ist erforderlich, da in diesem Fall die Schrägstrich Daten und kein Pfadtrennzeichen darstellt.  
  
 Die Zeichenfolge an den Uri-Konstruktor übergeben wird, führen zu den folgenden URI:  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 Aufteilen des Pfads in seine Segmente würde dazu führen, dass die folgenden Elemente:  
  
 `Customer('1`  
  
 `3812')`  
  
 Dies ist nicht die Absicht des Absenders der Anforderung.  
  
 Wenn die **UnescapeRequestUrl** -Attributsatz zur **"false"**, bei der <xref:System.Net.HttpListener> eine Anforderung empfängt, verwendet es den unformatierten URI anstelle des konvertierten URI von `http.sys` als Eingabe für die <xref:System.Net.HttpListenerRequest.Url%2A> Eigenschaft.  
  
 Der Standardwert für die **UnescapeRequestUrl** -Attribut ist **"true"**.  
  
 Die <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> Eigenschaft kann verwendet werden, den aktuellen Wert der abzurufenden der **UnescapeRequestUrl** Attribut aus anwendbaren Konfigurationsdateien.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie konfigurieren die <xref:System.Net.HttpListener> Klasse, wenn er eine Anforderung, den unformatierten URI anstelle des konvertierten URI von empfängt `http.sys` als Eingabe in die <xref:System.Net.HttpListenerRequest.Url%2A> Eigenschaft.  
  
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
 <xref:System.Net.Configuration.HttpListenerElement>  
 <xref:System.Net.HttpListener>  
 <xref:System.Net.HttpListenerRequest.Url%2A>  
 [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
