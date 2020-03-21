---
title: Überblick über WCF-Web-HTTP-Programmiermodelle
ms.date: 03/30/2017
ms.assetid: 381fdc3a-6e6c-4890-87fe-91cca6f4b476
ms.openlocfilehash: fb6ef0fdcefbc6ceec75ce30db3abf5896d85c61
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184189"
---
# <a name="wcf-web-http-programming-model-overview"></a>Überblick über WCF-Web-HTTP-Programmiermodelle
Das Web-HTTP-Programmiermodell (Windows Communication Foundation) bietet die grundlegenden Elemente, die zum Erstellen von WEB-HTTP-Diensten mit WCF erforderlich sind. WCF WEB HTTP-Dienste sind für den Zugriff auf eine breite Palette von Clients, einschließlich Webbrowsern, konzipiert und haben die folgenden eindeutigen Anforderungen:  
  
- **URIs und URI-Verarbeitung** URIs spielen eine zentrale Rolle beim Entwurf von WEB HTTP-Diensten. Das WCF WEB HTTP-Programmiermodell verwendet die <xref:System.UriTemplate> und <xref:System.UriTemplateTable> Klassen, um URI-Verarbeitungsfunktionen bereitzustellen.  
  
- **Unterstützung für GET- und POST-Vorgänge** WEB-HTTP-Dienste verwenden das GET-Verb für den Datenabruf, zusätzlich zu verschiedenen Aufrufverben für Datenänderung und Remoteaufruf. Das WCF WEB-HTTP-Programmiermodell verwendet die <xref:System.ServiceModel.Web.WebGetAttribute> und <xref:System.ServiceModel.Web.WebInvokeAttribute> zum Zuordnen von Dienstvorgängen sowohl GET als auch anderen HTTP-Verben wie PUT, POST und DELETE.  
  
- **Mehrere Datenformate** Web-Dienste verarbeiten neben SOAP-Nachrichten viele Arten von Daten. Das WCF WEB-HTTP-Programmiermodell verwendet die <xref:System.ServiceModel.WebHttpBinding> und <xref:System.ServiceModel.Description.WebHttpBehavior> unterstützt viele verschiedene Datenformate, einschließlich XML-Dokumente, JSON-Datenobjekt und Streams von binären Inhalten wie Bildern, Videodateien oder Nur-Text.  
  
 Das WCF WEB-HTTP-Programmiermodell erweitert die Reichweite von WCF auf Web-Szenarien, die WEB-HTTP-Dienste, AJAX- und JSON-Dienste sowie Syndication-Feeds (ATOM/RSS) umfassen. Weitere Informationen zu AJAX- und JSON-Diensten finden Sie unter [AJAX-Integration und JSON-Support](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md). Weitere Informationen zur Syndizierung finden Sie unter [WCF Syndication Overview](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md).  
  
 Es gibt keine zusätzlichen Einschränkungen bei den Datentypen, die von einem WEB-HTTP-Dienst zurückgegeben werden können. Jeder serialisierbare Typ kann von einem WEB-HTTP-Dienstvorgang zurückgegeben werden. Da WEB-HTTP-Dienstvorgänge durch einen Webbrowser aufgerufen werden können, gibt es eine Einschränkung in Bezug auf Datentypen, die in einer URL angegeben werden können. Weitere Informationen dazu, welche Typen standardmäßig unterstützt werden, finden Sie im Abschnitt **UriTemplate Query String Parameters and URLs** unten. Das Standardverhalten kann geändert werden, indem eine eigene T:System.ServiceModel.Dispatcher.QueryStringConverter-Implementierung bereitgestellt wird, die angibt, wie die in einer URL angegebenen Parameter in den tatsächlichen Parametertyp konvertiert werden. Weitere Informationen finden Sie unter <xref:System.ServiceModel.Dispatcher.QueryStringConverter>.  
  
> [!CAUTION]
> Dienste, die mit dem WCF WEB HTTP-Programmiermodell geschrieben wurden, verwenden keine SOAP-Nachrichten. Da SOAP nicht verwendet wird, können die von WCF bereitgestellten Sicherheitsfeatures nicht verwendet werden. Sie können jedoch transportbasierte Sicherheit verwenden, indem Sie den Dienst mit HTTPS hosten. Weitere Informationen zur WCF-Sicherheit finden Sie unter [Sicherheitsübersicht](../../../../docs/framework/wcf/feature-details/security-overview.md)  
  
> [!WARNING]
> Die Installation der WebDAV-Erweiterung für IIS kann dazu führen, dass Web-HTTP-Dienste den HTTP-Fehler 405 zurückgeben, da die WebDAV-Erweiterung versucht, alle PUT-Anforderungen zu verarbeiten. Um dieses Problem zu umgehen, können Sie die WebDAV-Erweiterung deinstallieren oder für Ihre Website deaktivieren. Weitere Informationen finden Sie unter [IIS und WebDav](https://learn.iis.net/page.aspx/357/webdav-for-iis-70/)  
  
## <a name="uri-processing-with-uritemplate-and-uritemplatetable"></a>URI-Verarbeitung mit UriTemplate und UriTemplateTable  
 URI-Vorlagen stellen eine rationelle Syntax zur Angabe großer Sätze strukturell ähnlicher URIs bereit. Beispielsweise wird mit der folgenden Vorlage der Satz aller aus drei Segmenten bestehenden URIs angegeben, die mit "a" beginnen, mit "c" enden und im mittleren Segment einen beliebigen Wert enthalten können: a/{segment}/c  
  
 Diese Vorlage beschreibt URIs wie die Folgenden:  
  
- a/x/c  
  
- a/y/c  
  
- a/z/c  
  
- usw.  
  
 In dieser Vorlage gibt die Notation mit geschweiften Klammern ("{segment}") ein variables Segment statt eines Literalwerts an.  
  
 .NET Framework stellt eine API mit dem Namen <xref:System.UriTemplate> zum Arbeiten mit URI-Vorlagen bereit. Mit `UriTemplates` können Sie Folgendes ausführen:  
  
- Sie können eine `Bind` der Methoden mit einer Reihe von Parametern aufrufen, um einen *vollständig geschlossenen URI* zu erzeugen, der mit der Vorlage übereinstimmt. Dies bedeutet, dass alle Variablen innerhalb der URI-Vorlage durch Istwerte ersetzt werden.  
  
- Sie können `Match`() mit einem potenziellen URI aufrufen. Diese Methode schlüsselt den potenziellen URI mithilfe einer Vorlage in seine Bestandteile auf und gibt ein Wörterbuch zurück, in dem die verschiedenen URI-Teile mit den zugehörigen Variablen aus der Vorlage verzeichnet sind.  
  
- `Bind`() und `Match`() sind Gegenstücke, sodass Sie `Match`( `Bind`( x ) ) aufrufen können und wieder zur Ausgangsumgebung zurückkehren.  
  
 Es ist häufig wünschenswert (insbesondere auf dem Server, wo es erforderlich ist, eine Anforderung basierend auf dem URI an einen Dienstvorgang weiterzuleiten), einen Satz von <xref:System.UriTemplate>-Objekten in einer Datenstruktur zu verfolgen, die unabhängig voneinander die einzelnen darin enthaltenen Vorlagen darstellen können. <xref:System.UriTemplateTable> stellt einen Satz von URI-Vorlagen dar und wählt aus einem gegebenen Vorlagensatz die beste Übereinstimmung für den zu prüfenden URI aus. Dies ist nicht mit einem bestimmten Netzwerk-Stack (WCF enthalten) verbunden, so dass Sie es verwenden können, wo immer nötig.  
  
 Das WCF-Dienstmodell verwendet <xref:System.UriTemplate> und <xref:System.UriTemplateTable>, um Dienstvorgänge mit einem Satz URIs zu verknüpfen, die durch eine <xref:System.UriTemplate> beschrieben werden. Ein Dienstvorgang wird mithilfe von <xref:System.UriTemplate> oder <xref:System.ServiceModel.Web.WebGetAttribute> mit einer <xref:System.ServiceModel.Web.WebInvokeAttribute> verknüpft. Weitere Informationen <xref:System.UriTemplate> zu <xref:System.UriTemplateTable>und finden Sie unter [UriTemplate und UriTemplateTable](../../../../docs/framework/wcf/feature-details/uritemplate-and-uritemplatetable.md)  
  
## <a name="webget-and-webinvoke-attributes"></a>WebGet- und WebInvoke-Attribute  
 WCF WEB HTTP-Dienste verwenden neben verschiedenen Aufrufverben (z. B. HTTP POST, PUT und DELETE) Abrufverben (z. B. HTTP GET). Das WCF WEB HTTP-Programmiermodell ermöglicht es Dienstentwicklern, sowohl die URI-Vorlage als auch das Verb zu steuern, das ihren Dienstvorgängen mit der <xref:System.ServiceModel.Web.WebGetAttribute> und <xref:System.ServiceModel.Web.WebInvokeAttribute>zugeordnet ist. Mit <xref:System.ServiceModel.Web.WebGetAttribute> und <xref:System.ServiceModel.Web.WebInvokeAttribute> können Sie steuern, wie einzelne Vorgänge an die URIs und die mit diesen URIs verknüpften HTTP–Methoden gebunden werden. Beispielsweise durch Hinzufügen von <xref:System.ServiceModel.Web.WebGetAttribute> und <xref:System.ServiceModel.Web.WebInvokeAttribute> im folgenden Code.  
  
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
  
 Ein vollständiges Beispiel eines WCF-Dienstes, der das WCF WEB HTTP-Programmiermodell verwendet, finden Sie unter [Gewusst wie: Erstellen eines grundlegenden WCF-Web-HTTP-Dienstes](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md)  
  
## <a name="uritemplate-query-string-parameters-and-urls"></a>UriTemplate-Abfragezeichenfolgenparameter und URLs  
 Webdienste können aus einem Webbrowser heraus aufgerufen werden, indem eine URL eingegeben wird, die mit einem Dienstvorgang verknüpft ist. Diese Dienstvorgänge verarbeiten möglicherweise Abfragezeichenfolgenparameter, die in Form einer Zeichenfolge innerhalb der URL angegeben werden müssen. In der folgenden Tabelle sind die Typen, die innerhalb einer URL übergeben werden können, und das hierfür verwendete Format aufgeführt.  
  
|type|Format|  
|----------|------------|  
|<xref:System.Byte>|0–255|  
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
|<xref:System.DateTime>|MM/TT/JJJJ<br /><br /> MM/DD/YYYY HH:MM:SS [AM&#124;PM]<br /><br /> Monat Tag Jahr<br /><br /> Monat Tag Jahr HH:MM:SS [AM&#124;PM]|  
|<xref:System.TimeSpan>|TT.HH:MM:SS<br /><br /> Wobei TT = Tage, HH = Stunden, MM = Minuten, SS = Sekunden|  
|<xref:System.Guid>|Ein GUID, beispielsweise:<br /><br /> 936DA01F-9ABD-4d9d-80C7-02AF85C822A8|  
|<xref:System.DateTimeOffset>|MM/TT/JJJJ HH:MM:SS MM:SS<br /><br /> Wobei TT = Tage, HH = Stunden, MM = Minuten, SS = Sekunden|  
|Enumerationen|Beispielsweise der Enumerationswert, der die Enumeration definiert, wie im folgenden Code gezeigt.<br /><br /> `public enum Days{ Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday };`<br /><br /> Jeder der einzelnen Enumerationswerte (bzw. der entsprechenden ganzzahligen Werte) kann in der Abfragezeichenfolge angegeben werden.|  
|Typen, die über ein `TypeConverterAttribute` verfügen, mit dem der Typ in eine Zeichenfolgendarstellung bzw. aus einer Zeichenfolgendarstellung konvertiert werden kann.|Hängt vom Typkonverter ab.|  
  
## <a name="formats-and-the-wcf-web-http-programming-model"></a>Formate und das WCF-WEB-HTTP-Programmiermodell  
 Das WCF WEB HTTP-Programmiermodell verfügt über neue Funktionen, um mit vielen verschiedenen Datenformaten zu arbeiten. Auf der Bindungsebene kann <xref:System.ServiceModel.WebHttpBinding> die folgenden anderen Arten von Daten lesen und schreiben:  
  
- XML  
  
- JSON  
  
- Nicht transparente binäre Streams  
  
 Dies bedeutet, dass das WCF WEB HTTP-Programmiermodell jede <xref:System.IO.Stream>Art von Daten verarbeiten kann, Sie jedoch möglicherweise für programmieren.  
  
 .NET Framework 3.5 bietet Unterstützung für JSON-Daten (AJAX) sowie Syndication-Feeds (einschließlich ATOM und RSS). Weitere Informationen zu diesen Features finden Sie unter [WCF Web HTTP Formatting](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)[WCF Syndication Overview](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md) und [AJAX Integration and JSON Support](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md).  
  
## <a name="wcf-web-http-programming-model-and-security"></a>WCF-WEB-HTTP-Programmiermodell und Sicherheit  

Da das WCF WEB HTTP-Programmiermodell die WS-*-Protokolle nicht unterstützt, besteht die einzige Möglichkeit, einen WCF WEB-HTTP-Dienst zu sichern, darin, den Dienst über HTTPS mithilfe von SSL verfügbar zu machen. Weitere Informationen zum Einrichten von SSL mit IIS 7.0 finden Sie unter [Implementieren von SSL in IIS](https://support.microsoft.com/help/299875/how-to-implement-ssl-in-iis).
  
## <a name="troubleshooting-the-wcf-web-http-programming-model"></a>Fehlerbehebung im WCF-WEB-HTTP-Programmiermodell  
 Beim Aufrufen der WCF-WEB-HTTP-Dienste mit einer <xref:System.ServiceModel.Channels.ChannelFactoryBase%601> zur Erstellung eines Kanals verwendet das <xref:System.ServiceModel.Description.WebHttpBehavior> den <xref:System.ServiceModel.EndpointAddress>-Satz in der Konfigurationsdatei, selbst wenn eine andere <xref:System.ServiceModel.EndpointAddress> an die <xref:System.ServiceModel.Channels.ChannelFactoryBase%601> weitergegeben wird.  
  
## <a name="see-also"></a>Weitere Informationen

- [WCF Syndication](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)
- [Objektmodell für WCF-Web-HTTP-Programmierung](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md)
- [WCF-Web-HTTP-Programmiermodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
