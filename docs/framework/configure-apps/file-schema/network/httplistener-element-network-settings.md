---
title: "&lt;httpListener&gt;-Element (Netzwerkeinstellungen) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# &lt;httpListener&gt;-Element (Netzwerkeinstellungen)
Passt die von der <xref:System.Net.HttpListener>\-Klasse verwendeten Parameter an.  
  
## Syntax  
  
```  
  
      <httpListener  
  unescapeRequestUrl ="true|false"  
/>  
```  
  
## Typ  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|unescapeRequestUrl|Ein boolescher Wert, der angibt, ob eine <xref:System.Net.HttpListener>\-Instanz den unformatierten URI ohne Escapezeichen anstelle des konvertierten URI verwendet.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>\-Namespace.|  
  
## Hinweise  
 Das **unescapeRequestUrl**\-Attribut gibt an, ob <xref:System.Net.HttpListener> den unformatierten URI ohne Escapezeichen anstelle des konvertierten URIs verwendet, wobei alle mit Prozentzeichen codierten Werte konvertiert und andere Normalisierungsschritte unternommen werden.  
  
 Wenn eine <xref:System.Net.HttpListener>\-Instanz durch den `http.sys`\-Dienst eine Anforderung empfängt, erstellt sie eine Instanz der URI\-Zeichenfolge, die von `http.sys` bereitgestellt wurde, und macht sie als <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=fullName>\-Eigenschaft verfügbar.  
  
 Der `http.sys`\-Dienst macht zwei Anforderungs\-URI\-Zeichenfolgen verfügbar:  
  
-   Unformatierter URI  
  
-   Konvertierter URI  
  
 Der unformatierte URI ist der in der Anforderungszeile einer HTTP\-Anforderung bereitgestellte <xref:System.Uri?displayProperty=fullName>:  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 Der unformatierte URI, der von `http.sys` für die oben genannte Anforderung angegeben wird, ist "\/path\/".  Dies stellt die Zeichenfolge dar, die auf das HTTP\-Verb folgt, wie es über das Netzwerk gesendet wurde.  
  
 Der `http.sys`\-Dienst erstellt einen konvertierten URI aus den in der Anforderung bereitgestellten Informationen, indem der URI aus der HTTP\-Anforderungszeile und der Host\-Header verwendet werden, um den Ursprungsserver zu bestimmen, an den die Anforderung weitergeleitet werden soll.  Dies geschieht durch Vergleichen der Informationen aus der Anforderung mit einem Satz registrierter URI\-Präfixe.  Die HTTP\-Server\-SDK\-Dokumentation verweist auf diesen konvertierten URI als HTTP\_COOKED\_URL\-Struktur.  
  
 Um in der Lage zu sein, die Anforderung mit registrierten URI\-Präfixen zu vergleichen, muss eine Normalisierung der Anforderung ausgeführt werden.  Für das Beispiel oben würde der konvertierte URI wie folgt lauten:  
  
 `http://www.contoso.com/path/`  
  
 Der `http.sys`\-Dienst kombiniert den <xref:System.Uri.Host%2A?displayProperty=fullName>\-Eigenschaftswert und die Zeichenfolge in der Anforderungszeile, um einen konvertierten URI zu erstellen.  Darüber hinaus führen `http.sys` und die <xref:System.Uri?displayProperty=fullName>\-Klasse Folgendes aus:  
  
-   Entfernt alle als Prozentwert codierten Werte.  
  
-   Konvertiert mit Prozentzeichen kodierte Nicht\-ASCII\-Zeichen in eine UTF\-16\-Zeichendarstellung.  Beachten Sie, dass UTF\-8 und ANSI\-\/DBCSs\-Zeichen sowie Unicode\-Zeichen \(Unicode\-Codierung, die das %uXXXX\-Format verwendet\) unterstützt werden.  
  
-   Führt andere Normalisierungsschritte aus, wie etwa Pfadkomprimierung.  
  
 Da die Anforderung keine Informationen über die Codierung enthält, die für Prozentzeichen kodierte Werte verwendet wird, ist es eventuell nicht möglich, die richtige Codierung nur durch das Analysieren der mit Prozentzeichen codierten Werte zu bestimmen.  
  
 Daher stellt `http.sys` zwei Registrierungsschlüssel zum Ändern des Prozesses bereit:  
  
|\-Registrierungsschlüssel|Standardwert|**Beschreibung**|  
|-------------------------------|------------------|----------------------|  
|EnableNonUTF8|1|Falls 0 \(null\), akzeptiert `http.sys` nur UTF 8\-codierte URLs.<br /><br /> Falls ungleich 0 \(null\) akzeptiert `http.sys` auch ANSI\-codiert oder DBCS\-codierte URLs in Anforderungen.|  
|FavorUTF8|1|Falls ungleich 0 \(null\) versucht `http.sys` immer, zuerst eine URL als UTF\-8 zu decodieren; wenn diese Konvertierung fehlschlägt, und EnableNonUTF8 ist ungleich 0 \(null\), versucht Http.sys dann, es als ANSI oder DBCS zu decodieren.<br /><br /> Falls der Wert 0 \(null\) beträgt \(und EnableNonUTF8 ungleich 0 \(null\) ist\), versucht `http.sys`, es als ANSI oder DBCS zu decodieren; wenn das nicht erfolgreich ist, versucht es eine UTF\-8\-Konvertierung.|  
  
 Wenn das <xref:System.Net.HttpListener>\-Objekt eine Anforderung empfängt, verwendet es den konvertierten URI von `http.sys` als Eingabe für <xref:System.Net.HttpListenerRequest.Url%2A>\-Eigenschaft.  
  
 In URIs müssen auch andere Zeichen als Buchstaben und Zahlen unterstützt werden.  Ein Beispiel ist der folgende URI, der verwendet wird, um Kundeninformationen für Kunde Nummer "1\/3812" abzurufen:  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 Beachten Sie den mit Prozentzeichen codierten Schrägstrich in der URI \(% 2F\).  Dies ist notwendig, da das Schrägstrichzeichen in diesem Fall Daten und kein Pfadtrennzeichen darstellt.  
  
 Das Übergeben der Zeichenfolge an den URI\-Konstruktor führt zur folgenden URI:  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 Das Aufteilen des Pfads in seine Segmente würde zu den folgenden Elementen führen:  
  
 `Customer('1`  
  
 `3812')`  
  
 Dies ist nicht die Absicht des Absenders der Anforderung.  
  
 Wenn das **unescapeRequestUrl**\-Attribut auf **false** festgelegt wird, wenn der <xref:System.Net.HttpListener> eine Anforderung empfängt, verwendet es den unformatierten URI statt des konvertierten URIs von `http.sys` als Eingabe für die <xref:System.Net.HttpListenerRequest.Url%2A>\-Eigenschaft.  
  
 Der Standardwert für das **unescapeRequestUrl**\-Attribut ist **true**.  
  
 Die <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A>\-Eigenschaft kann verwendet werden, um den aktuellen Wert des **unescapeRequestUrl**\-Attributs aus anwendbaren Konfigurationsdateien abzurufen.  
  
## Beispiel  
 Im folgenden Codebeispiel wird gezeigt, wie die <xref:System.Net.HttpListener>\-Klasse konfiguriert wird, wenn sie eine Anforderung zur Verwendung des unformatierten URI statt des konvertierten URI von `http.sys` als Eingabe für die <xref:System.Net.HttpListenerRequest.Url%2A>\-Eigenschaft empfängt.  
  
```  
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
  
## Elementinformationen  
  
|||  
|-|-|  
|Namespace|System.Net|  
|Schemaname||  
|Validierungsdatei||  
|Kann leer sein||  
  
## Siehe auch  
 <xref:System.Net.Configuration.HttpListenerElement>   
 <xref:System.Net.HttpListener>   
 <xref:System.Net.HttpListenerRequest.Url%2A>   
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)