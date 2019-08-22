---
title: <httpListener>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
ms.openlocfilehash: cb24dc7296e2f2f6ea292566330d3d6ae4f25f85
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664137"
---
# <a name="httplistener-element-network-settings"></a>\<HttpListener >-Element (Netzwerkeinstellungen)
Passt Parameter an, die von <xref:System.Net.HttpListener> der-Klasse verwendet werden.  
  
 \<configuration>  
\<system.net>  
\<settings>  
\<httpListener>  
  
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
|unescapeRequestUrl|Ein boolescher Wert, der angibt, <xref:System.Net.HttpListener> ob eine-Instanz anstelle des konvertierten URIs den unformatierten URI ohne Escapezeichen verwendet.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[settings](settings-element-network-settings.md)|Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.|  
  
## <a name="remarks"></a>Hinweise  
 Das **unescaperequesturl** -Attribut gibt <xref:System.Net.HttpListener> an, ob den unformatierten URI ohne Escapezeichen anstelle des konvertierten URI verwendet, bei dem alle Prozent codierten Werte konvertiert und andere normalisierungs Schritte ausgeführt werden.  
  
 Wenn eine <xref:System.Net.HttpListener> -Instanz eine Anforderung über den `http.sys` Dienst empfängt, erstellt Sie eine Instanz der von `http.sys`bereitgestellten URI-Zeichenfolge und macht Sie <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> als-Eigenschaft verfügbar.  
  
 Der `http.sys` Dienst macht zwei Anforderungs-URI-Zeichen folgen verfügbar:  
  
- RAW-URI  
  
- Konvertierter URI  
  
 Der unformatierte URI <xref:System.Uri?displayProperty=nameWithType> ist das, das in der Anforderungs Zeile einer HTTP-Anforderung bereitgestellt wird:  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 Der von `http.sys` bereitgestellte Rohdaten-URI für die oben genannte Anforderung ist "/Path/". Dies stellt die Zeichenfolge dar, die auf das HTTP-Verb folgt, wie es über das Netzwerk gesendet wurde.  
  
 Der `http.sys` Dienst erstellt einen konvertierten URI aus den Informationen, die in der Anforderung bereitgestellt werden, indem der URI in der HTTP-Anforderungs Zeile und der Host Header verwendet wird, um den Ursprungsserver zu ermitteln, an den die Anforderung weitergeleitet werden soll. Dies erfolgt durch Vergleichen der Informationen aus der Anforderung mit einem Satz von registrierten URI-Präfixen. In der HTTP-Server-SDK-Dokumentation wird dieser konvertierte URI als HTTP_COOKED_URL-Struktur bezeichnet.  
  
 Um die Anforderung mit registrierten URI-Präfixen vergleichen zu können, müssen einige Normalisierungen der Anforderung vorgenommen werden. Im obigen Beispiel würde der konvertierte URI wie folgt lauten:  
  
 `http://www.contoso.com/path/`  
  
 Der `http.sys` Dienst kombiniert den <xref:System.Uri.Host%2A?displayProperty=nameWithType> -Eigenschafts Wert und die Zeichenfolge in der Anforderungs Zeile, um einen konvertierten URI zu erstellen. Außerdem `http.sys` führt die <xref:System.Uri?displayProperty=nameWithType> -Klasse auch die folgenden Schritte aus:  
  
- Deaktiviert alle Prozent codierten Werte.  
  
- Konvertiert Prozent codierte nicht-ASCII-Zeichen in eine UTF-16-Zeichen Darstellung. Beachten Sie, dass UTF-8-und ANSI/DBCS-Zeichen sowie Unicode-Zeichen (Unicode-Codierung mit dem Format "% uXXXX") unterstützt werden.  
  
- Führt andere normalisierungs Schritte aus, z. b. Pfad Komprimierung  
  
 Da die Anforderung keine Informationen über die Codierung enthält, die für Prozent codierte Werte verwendet wird, ist es möglicherweise nicht möglich, die richtige Codierung zu ermitteln, indem Sie die Prozent codierten Werte zu ermitteln.  
  
 Stellt `http.sys` daher zwei Registrierungsschlüssel zum Ändern des Prozesses bereit:  
  
|-Registrierungsschlüssel|Standardwert|Beschreibung|  
|------------------|-------------------|-----------------|  
|EnableNonUTF8|1|Wenn 0 ( `http.sys` null), werden nur UTF-8-codierte URLs akzeptiert.<br /><br /> Wenn ungleich 0 (NULL `http.sys` ), werden auch ANSI-codierte oder DBCS-codierte URLs in Anforderungen akzeptiert.|  
|FavorUTF8|1|Wenn der Wert ungleich NULL `http.sys` ist, wird von immer versucht, eine URL als UTF-8 zu decodieren. wenn diese Konvertierung fehlschlägt und EnableNonUTF8 nicht NULL ist, versucht http. sys, Sie als ANSI oder DBCS zu decodieren.<br /><br /> Wenn NULL (und EnableNonUTF8 ungleich null) ist, versucht `http.sys` , es als ANSI oder DBCS zu decodieren. wenn dies nicht erfolgreich ist, versucht es, eine UTF-8-Konvertierung durchzusetzen.|  
  
 Wenn <xref:System.Net.HttpListener> eine Anforderung empfängt, wird der konvertierte URI von `http.sys` als Eingabe für die <xref:System.Net.HttpListenerRequest.Url%2A> -Eigenschaft verwendet.  
  
 Es besteht die Notwendigkeit, Zeichen neben Zeichen und Zahlen in URIs zu unterstützen. Ein Beispiel ist der folgende URI, der zum Abrufen von Kundeninformationen für die Kundennummer "1/3812" verwendet wird:  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 Notieren Sie sich den Prozentsatz codierten Schrägstrich im URI (% 2F). Dies ist erforderlich, da der Schrägstrich in diesem Fall Daten und kein Pfad Trennzeichen darstellt.  
  
 Wenn die Zeichenfolge an den URI-Konstruktor übergeben wird, führt dies zu folgendem URI:  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 Wenn Sie den Pfad in seine Segmente aufteilen, werden die folgenden Elemente angezeigt:  
  
 `Customer('1`  
  
 `3812')`  
  
 Dies ist nicht die Absicht des Absenders der Anforderung.  
  
 Wenn das **unescaperequesturl** -Attribut auf **false**festgelegt ist, und <xref:System.Net.HttpListener> wenn eine Anforderung empfängt, wird der unformatierte URI anstelle des konvertierten `http.sys` URI aus als Eingabe <xref:System.Net.HttpListenerRequest.Url%2A> für die-Eigenschaft verwendet.  
  
 Der Standardwert für das **unescaperequesturl** -Attribut ist " **true**".  
  
 Die <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> -Eigenschaft kann verwendet werden, um den aktuellen Wert des **unescaperequesturl** -Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie die <xref:System.Net.HttpListener> -Klasse konfiguriert wird, wenn Sie eine Anforderung zum Verwenden des RAW-URI anstelle des `http.sys` konvertierten URI von <xref:System.Net.HttpListenerRequest.Url%2A> als Eingabe für die-Eigenschaft empfängt.  
  
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
|Kann leer sein||  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Net.Configuration.HttpListenerElement>
- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpListenerRequest.Url%2A>
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](index.md)
