---
title: Überblick über WCF-Web-HTTP-Programmiermodelle
ms.date: 03/30/2017
ms.assetid: 381fdc3a-6e6c-4890-87fe-91cca6f4b476
ms.openlocfilehash: 8a4b4ff6c0482ed8a09fe30b7d03afc1f84db581
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739900"
---
# <a name="wcf-web-http-programming-model-overview"></a>Überblick über WCF-Web-HTTP-Programmiermodelle
Das Windows Communication Foundation (WCF)-Web-HTTP-Programmiermodell stellt die grundlegenden Elemente bereit, die zum Erstellen von Web-http-Diensten mit WCF Die WCF-Web-HTTP-Dienste sind so konzipiert, dass Sie von den verschiedensten möglichen Clients, einschließlich Webbrowsern, zugänglich sind und die folgenden besonderen Anforderungen erfüllen:  
  
- **URIs und URI-Verarbeitung** URIs spielen eine zentrale Rolle beim Entwerfen von Web-http-Diensten. Das WCF-Web-HTTP-Programmiermodell verwendet die Klassen <xref:System.UriTemplate> und <xref:System.UriTemplateTable>, um URI-Verarbeitungsfunktionen bereitzustellen.  
  
- **Unterstützung für Get-und Post-Vorgänge** Web-HTTP-Dienste nutzen das Get-Verb für den Datenabruf, zusätzlich zu den verschiedenen Aufruf Verben für die Datenänderung und den Remote Aufruf. Das WCF-Web-HTTP-Programmiermodell verwendet die <xref:System.ServiceModel.Web.WebGetAttribute> und <xref:System.ServiceModel.Web.WebInvokeAttribute>, um Dienst Vorgänge sowohl Get-als auch anderen HTTP-Verben wie Put, Post und DELETE zuzuordnen.  
  
- **Mehrere Datenformate** Webdienste verarbeiten viele Arten von Daten zusätzlich zu SOAP-Nachrichten. Das WCF-Web-HTTP-Programmiermodell verwendet die <xref:System.ServiceModel.WebHttpBinding> und <xref:System.ServiceModel.Description.WebHttpBehavior>, um viele verschiedene Datenformate zu unterstützen, z. b. XML-Dokumente, JSON-Datenobjekte und Streams von Binär Inhalten wie Bildern, Videodateien oder nur-Text.  
  
 Das WCF-Web-HTTP-Programmiermodell erweitert die Reichweite von WCF auf Szenarien im Webstil, die Web-HTTP-Dienste, AJAX-und JSON-Dienste sowie Syndikation-Feeds (Atom/RSS) enthalten. Weitere Informationen zu AJAX-und JSON-Diensten finden Sie [unter AJAX-Integration und JSON-Unterstützung](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md). Weitere Informationen zur Syndizierung finden Sie unter [Übersicht über die WCF-Syndizierung](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md).  
  
 Es gibt keine zusätzlichen Einschränkungen bei den Datentypen, die von einem WEB-HTTP-Dienst zurückgegeben werden können. Jeder serialisierbare Typ kann von einem WEB-HTTP-Dienstvorgang zurückgegeben werden. Da WEB-HTTP-Dienstvorgänge durch einen Webbrowser aufgerufen werden können, gibt es eine Einschränkung in Bezug auf Datentypen, die in einer URL angegeben werden können. Weitere Informationen zu den standardmäßig unterstützten Typen finden Sie unten im Abschnitt " **UriTemplate-Abfrage Zeichenfolgen-Parameter und-URLs** ". Das Standardverhalten kann geändert werden, indem eine eigene T:System.ServiceModel.Dispatcher.QueryStringConverter-Implementierung bereitgestellt wird, die angibt, wie die in einer URL angegebenen Parameter in den tatsächlichen Parametertyp konvertiert werden. Weitere Informationen finden Sie unter <xref:System.ServiceModel.Dispatcher.QueryStringConverter>.  
  
> [!CAUTION]
> Mit dem WCF-Web-HTTP-Programmiermodell geschriebene Dienste verwenden keine SOAP-Nachrichten. Da SOAP nicht verwendet wird, können die von WCF bereitgestellten Sicherheitsfunktionen nicht verwendet werden. Sie können jedoch transportbasierte Sicherheit verwenden, indem Sie den Dienst mit HTTPS hosten. Weitere Informationen zur WCF-Sicherheit finden Sie unter [Sicherheitsübersicht](../../../../docs/framework/wcf/feature-details/security-overview.md) .  
  
> [!WARNING]
> Die Installation der WebDAV-Erweiterung für IIS kann dazu führen, dass Web-HTTP-Dienste den HTTP-Fehler 405 zurückgeben, da die WebDAV-Erweiterung versucht, alle PUT-Anforderungen zu verarbeiten. Um dieses Problem zu umgehen, können Sie die WebDAV-Erweiterung deinstallieren oder für Ihre Website deaktivieren. Weitere Informationen finden Sie unter [IIS und WebDAV](https://learn.iis.net/page.aspx/357/webdav-for-iis-70/) .  
  
## <a name="uri-processing-with-uritemplate-and-uritemplatetable"></a>URI-Verarbeitung mit UriTemplate und UriTemplateTable  
 URI-Vorlagen stellen eine rationelle Syntax zur Angabe großer Sätze strukturell ähnlicher URIs bereit. Beispielsweise wird mit der folgenden Vorlage der Satz aller aus drei Segmenten bestehenden URIs angegeben, die mit "a" beginnen, mit "c" enden und im mittleren Segment einen beliebigen Wert enthalten können: a/{segment}/c  
  
 Diese Vorlage beschreibt URIs wie die Folgenden:  
  
- a/x/c  
  
- a/y/c  
  
- a/z/c  
  
- usw.  
  
 In dieser Vorlage gibt die Notation mit geschweiften Klammern ("{segment}") ein variables Segment statt eines Literalwerts an.  
  
 .NET Framework stellt eine API mit dem Namen <xref:System.UriTemplate> zum Arbeiten mit URI-Vorlagen bereit. Mit `UriTemplates` können Sie Folgendes ausführen:  
  
- Sie können eine der `Bind` Methoden mit einer Reihe von Parametern aufzurufen, um einen *vollständig geschlossenen URI* zu erstellen, der mit der Vorlage übereinstimmt. Dies bedeutet, dass alle Variablen innerhalb der URI-Vorlage durch Istwerte ersetzt werden.  
  
- Sie können `Match`() mit einem potenziellen URI aufrufen. Diese Methode schlüsselt den potenziellen URI mithilfe einer Vorlage in seine Bestandteile auf und gibt ein Wörterbuch zurück, in dem die verschiedenen URI-Teile mit den zugehörigen Variablen aus der Vorlage verzeichnet sind.  
  
- `Bind`() und `Match`() sind Gegenstücke, sodass Sie `Match`( `Bind`( x ) ) aufrufen können und wieder zur Ausgangsumgebung zurückkehren.  
  
 Es ist häufig wünschenswert (insbesondere auf dem Server, wo es erforderlich ist, eine Anforderung basierend auf dem URI an einen Dienstvorgang weiterzuleiten), einen Satz von <xref:System.UriTemplate>-Objekten in einer Datenstruktur zu verfolgen, die unabhängig voneinander die einzelnen darin enthaltenen Vorlagen darstellen können. <xref:System.UriTemplateTable> stellt einen Satz von URI-Vorlagen dar und wählt aus einem gegebenen Vorlagensatz die beste Übereinstimmung für den zu prüfenden URI aus. Dies ist nicht mit einem bestimmten Netzwerk Stapel verbunden (WCF eingeschlossen), sodass Sie ihn bei Bedarf verwenden können.  
  
 Das WCF-Dienstmodell verwendet <xref:System.UriTemplate> und <xref:System.UriTemplateTable>, um Dienstvorgänge mit einem Satz URIs zu verknüpfen, die durch eine <xref:System.UriTemplate> beschrieben werden. Ein Dienstvorgang wird mithilfe von <xref:System.UriTemplate> oder <xref:System.ServiceModel.Web.WebGetAttribute> mit einer <xref:System.ServiceModel.Web.WebInvokeAttribute> verknüpft. Weitere Informationen zu <xref:System.UriTemplate> und <xref:System.UriTemplateTable>finden Sie unter [UriTemplate und UriTemplateTable](../../../../docs/framework/wcf/feature-details/uritemplate-and-uritemplatetable.md) .  
  
## <a name="webget-and-webinvoke-attributes"></a>WebGet- und WebInvoke-Attribute  
 WCF-Web-HTTP-Dienste nutzen zusätzlich zu verschiedenen Aufruf Verben (z. b. HTTP Post, Put und DELETE) Abruf Verben (z. b. HTTP Get). Mit dem WCF-Web-HTTP-Programmiermodell können Dienst Entwickler sowohl die URI-Vorlage als auch das Verb steuern, die den Dienst Vorgängen mit dem <xref:System.ServiceModel.Web.WebGetAttribute> und <xref:System.ServiceModel.Web.WebInvokeAttribute>zugeordnet sind. Mit <xref:System.ServiceModel.Web.WebGetAttribute> und <xref:System.ServiceModel.Web.WebInvokeAttribute> können Sie steuern, wie einzelne Vorgänge an die URIs und die mit diesen URIs verknüpften HTTP–Methoden gebunden werden. Beispielsweise durch Hinzufügen von <xref:System.ServiceModel.Web.WebGetAttribute> und <xref:System.ServiceModel.Web.WebInvokeAttribute> im folgenden Code.  
  
```csharp
[ServiceContract]  
interface ICustomer  
{  
  //"View It"  
  
  [WebGet]  
  Customer GetCustomer():  
  
  //"Do It"  
    [WebInvoke]  
  Customer UpdateCustomerName( string id,   
                               string newName );  
}  
```  
  
 Der vorangehende Code ermöglicht es Ihnen, die folgenden HTTP-Anforderungen zu formulieren.  
  
 `GET /GetCustomer`  
  
 `POST /UpdateCustomerName`  
  
 Für <xref:System.ServiceModel.Web.WebInvokeAttribute> wird standardmäßig POST eingesetzt, aber Sie können das Attribut auch für andere Verben verwenden.  
  
```csharp
[ServiceContract]  
interface ICustomer  
{  
  //"View It" -> HTTP GET  
    [WebGet( UriTemplate="customers/{id}" )]  
  Customer GetCustomer( string id ):  
  
  //"Do It" -> HTTP PUT  
  [WebInvoke( UriTemplate="customers/{id}", Method="PUT" )]  
  Customer UpdateCustomer( string id, Customer newCustomer );  
}  
```  
  
 Ein umfassendes Beispiel eines WCF-Diensts, der das WCF-Web-HTTP-Programmiermodell verwendet, finden Sie unter Gewusst [wie: Erstellen eines einfachen WCF-Web-HTTP-Diensts](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md) .  
  
## <a name="uritemplate-query-string-parameters-and-urls"></a>UriTemplate-Abfragezeichenfolgenparameter und URLs  
 Webdienste können aus einem Webbrowser heraus aufgerufen werden, indem eine URL eingegeben wird, die mit einem Dienstvorgang verknüpft ist. Diese Dienstvorgänge verarbeiten möglicherweise Abfragezeichenfolgenparameter, die in Form einer Zeichenfolge innerhalb der URL angegeben werden müssen. In der folgenden Tabelle sind die Typen, die innerhalb einer URL übergeben werden können, und das hierfür verwendete Format aufgeführt.  
  
|type|Format|  
|----------|------------|  
|<xref:System.Byte>|0 - 255|  
|<xref:System.SByte>|-128 - 127|  
|<xref:System.Int16>|-32768 - 32767|  
|<xref:System.Int32>|-2,147,483,648 - 2,147,483,647|  
|<xref:System.Int64>|-9,223,372,036,854,775,808 - 9,223,372,036,854,775,807|  
|<xref:System.UInt16>|0 - 65535|  
|<xref:System.UInt32>|0 - 4,294,967,295|  
|<xref:System.UInt64>|0 - 18,446,744,073,709,551,615|  
|<xref:System.Single>|-3.402823e38 - 3.402823e38 (Exponentennotation nicht erforderlich)|  
|<xref:System.Double>|-1.79769313486232e308 - 1.79769313486232e308 (Exponentennotation nicht erforderlich)|  
|<xref:System.Char>|Ein einzelnes Zeichen|  
|<xref:System.Decimal>|Eine beliebige Dezimalzahl in Standardnotation (kein Exponent)|  
|<xref:System.Boolean>|True oder False (Groß-/Kleinschreibung wird nicht berücksichtigt)|  
|<xref:System.String>|Beliebige Zeichenfolge (leere Zeichenfolgen werden nicht unterstützt, und es werden keine Escapezeichen hinzugefügt)|  
|<xref:System.DateTime>|TT.MM.JJJJ<br /><br /> mm/dd/yyyy HH: mm: SS [am&#124;pm]<br /><br /> Monat Tag Jahr<br /><br /> Monat Tag Jahr hh: mm: SS [am&#124;pm]|  
|<xref:System.TimeSpan>|TT.HH:MM:SS<br /><br /> Wobei TT = Tage, HH = Stunden, MM = Minuten, SS = Sekunden|  
|<xref:System.Guid>|Ein GUID, beispielsweise:<br /><br /> 936DA01F-9ABD-4d9d-80C7-02AF85C822A8|  
|<xref:System.DateTimeOffset>|MM/TT/JJJJ HH:MM:SS MM:SS<br /><br /> Wobei TT = Tage, HH = Stunden, MM = Minuten, SS = Sekunden|  
|Enumerationen|Beispielsweise der Enumerationswert, der die Enumeration definiert, wie im folgenden Code gezeigt.<br /><br /> `public enum Days{ Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday };`<br /><br /> Jeder der einzelnen Enumerationswerte (bzw. der entsprechenden ganzzahligen Werte) kann in der Abfragezeichenfolge angegeben werden.|  
|Typen, die über ein `TypeConverterAttribute` verfügen, mit dem der Typ in eine Zeichenfolgendarstellung bzw. aus einer Zeichenfolgendarstellung konvertiert werden kann.|Hängt vom Typkonverter ab.|  
  
## <a name="formats-and-the-wcf-web-http-programming-model"></a>Formate und das WCF-WEB-HTTP-Programmiermodell  
 Das WCF-Web-HTTP-Programmiermodell verfügt über neue Funktionen, die mit vielen verschiedenen Datenformaten arbeiten. Auf der Bindungsebene kann <xref:System.ServiceModel.WebHttpBinding> die folgenden anderen Arten von Daten lesen und schreiben:  
  
- XML  
  
- JSON  
  
- Nicht transparente binäre Streams  
  
 Dies bedeutet, dass das WCF-Web-HTTP-Programmiermodell beliebige Datentypen verarbeiten kann. Sie können jedoch auch für <xref:System.IO.Stream>programmieren.  
  
 .NET Framework 3,5 bietet Unterstützung für JSON-Daten (Ajax) sowie Syndizierungs Feeds (einschließlich Atom und RSS). Weitere Informationen zu diesen Features finden Sie unter WCF- [Web-http-Formatierung](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)[WCF-Syndizierung (Übersicht](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md) ) und [AJAX-Integration und JSON-Unterstützung](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md).  
  
## <a name="wcf-web-http-programming-model-and-security"></a>WCF-WEB-HTTP-Programmiermodell und Sicherheit  

Da das WCF-Web-HTTP-Programmiermodell die WS-*-Protokolle nicht unterstützt, ist die einzige Möglichkeit zum Sichern eines WCF-Web-HTTP-Diensts das verfügbar machen des Diensts über HTTPS mithilfe von SSL. Weitere Informationen zum Einrichten von SSL mit IIS 7,0 finden Sie unter Gewusst [wie: Implementieren von SSL in IIS](https://support.microsoft.com/help/299875/how-to-implement-ssl-in-iis).
  
## <a name="troubleshooting-the-wcf-web-http-programming-model"></a>Fehlerbehebung im WCF-WEB-HTTP-Programmiermodell  
 Beim Aufrufen der WCF-WEB-HTTP-Dienste mit einer <xref:System.ServiceModel.Channels.ChannelFactoryBase%601> zur Erstellung eines Kanals verwendet das <xref:System.ServiceModel.Description.WebHttpBehavior> den <xref:System.ServiceModel.EndpointAddress>-Satz in der Konfigurationsdatei, selbst wenn eine andere <xref:System.ServiceModel.EndpointAddress> an die <xref:System.ServiceModel.Channels.ChannelFactoryBase%601> weitergegeben wird.  
  
## <a name="see-also"></a>Weitere Informationen

- [WCF Syndication](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)
- [Objektmodell für WCF-Web-HTTP-Programmierung](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md)
- [WCF-Web-HTTP-Programmiermodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
