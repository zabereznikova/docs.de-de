---
title: "Überblick über WCF-Web-HTTP-Programmiermodelle"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 381fdc3a-6e6c-4890-87fe-91cca6f4b476
caps.latest.revision: "45"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4ebc3c349e0eedcbe20f126f5252dadf8a6b8096
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="wcf-web-http-programming-model-overview"></a>Überblick über WCF-Web-HTTP-Programmiermodelle
Das WEB-HTTP-Programmiermodell in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] stellt die grundlegenden Elemente zur Erstellung von WEB-HTTP-Diensten mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bereit. WEB-HTTP-Dienste in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] wurden für den Zugriff von vielen möglichen Clients aus entwickelt, einschließlich Webbrowsern, und weisen folgende eindeutige Anforderungen auf:  
  
-   **URIs und URI-Verarbeitung** URIs spielen eine zentrale Rolle in den Entwurf WEB-HTTP-Dienste. Das WCF-Webprogrammiermodell in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet die <xref:System.UriTemplate>-Klasse und die <xref:System.UriTemplateTable>-Klasse, um URI-Verarbeitungsfunktionen bereitzustellen.  
  
-   **Unterstützung für GET und Post-ANFORDERUNGEN** WEB-HTTP-Dienste machen die Verwendung von GET-Verb für den Datenabruf von, zusätzlich zu den verschiedenen aufrufverben für datenbearbeitung und Remoteaufrufe. Das Webprogrammiermodell in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet die <xref:System.ServiceModel.Web.WebGetAttribute>- und <xref:System.ServiceModel.Web.WebInvokeAttribute>-Attribute, um Dienstoperationen sowohl das GET-Verb als auch andere HTTP-Verben wie PUT, POST oder DELETE zuzuordnen.  
  
-   **Mehrere Datenformate** Webdienste viele Arten von Daten, zusätzlich zu SOAP-Nachrichten zu verarbeiten. Im WEB-HTTP-Programmiermodell von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] werden durch den Einsatz von <xref:System.ServiceModel.WebHttpBinding> und <xref:System.ServiceModel.Description.WebHttpBehavior> viele verschiedene Datenformate unterstützt. Hierzu gehören XML-Dokumente, JSON-Datenobjekte und Streams mit Binärdaten, wie z. B. Bilder, Videodateien oder Klartext.  
  
 Das WEB-HTTP-Programmiermodell von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] erweitert den Einsatzbereich von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] um Webszenarien, wie beispielsweise WEB-HTTP-Dienste, AJAX- und JSON-Dienste sowie Syndication-Feeds (ATOM/RSS). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]AJAX- und JSON-Dienste finden Sie unter [AJAX-Integration und JSON-Unterstützung](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Syndication finden Sie unter [Übersicht über WCF Syndication](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md).  
  
 Es gibt keine zusätzlichen Einschränkungen bei den Datentypen, die von einem WEB-HTTP-Dienst zurückgegeben werden können. Jeder serialisierbare Typ kann von einem WEB-HTTP-Dienstvorgang zurückgegeben werden. Da WEB-HTTP-Dienstvorgänge durch einen Webbrowser aufgerufen werden können, gibt es eine Einschränkung in Bezug auf Datentypen, die in einer URL angegeben werden können. Welche Typen standardmäßig unterstützt werden weitere Informationen finden Sie unter der **UriTemplate-Abfragezeichenfolgenparameter und URLs** Abschnitt weiter unten. Das Standardverhalten kann geändert werden, indem eine eigene T:System.ServiceModel.Dispatcher.QueryStringConverter-Implementierung bereitgestellt wird, die angibt, wie die in einer URL angegebenen Parameter in den tatsächlichen Parametertyp konvertiert werden. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] <xref:System.ServiceModel.Dispatcher.QueryStringConverter>  
  
> [!CAUTION]
>  Im WEB-HTTP-Programmiermodell von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] geschriebene Dienste verwenden keine SOAP-Nachrichten. Da SOAP nicht verwendet wird, können die von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bereitgestellten Sicherheitsfunktionen nicht genutzt werden. Sie können jedoch transportbasierte Sicherheit verwenden, indem Sie den Dienst mit HTTPS hosten. [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Sicherheit, finden Sie unter [Sicherheit (Übersicht)](../../../../docs/framework/wcf/feature-details/security-overview.md)  
  
> [!WARNING]
>  Die Installation der WebDAV-Erweiterung für IIS kann dazu führen, dass Web-HTTP-Dienste den HTTP-Fehler 405 zurückgeben, da die WebDAV-Erweiterung versucht, alle PUT-Anforderungen zu verarbeiten. Um dieses Problem zu umgehen, können Sie die WebDAV-Erweiterung deinstallieren oder für Ihre Website deaktivieren. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][IIS und WebDav](http://learn.iis.net/page.aspx/357/webdav-for-iis-70/)  
  
## <a name="uri-processing-with-uritemplate-and-uritemplatetable"></a>URI-Verarbeitung mit UriTemplate und UriTemplateTable  
 URI-Vorlagen stellen eine rationelle Syntax zur Angabe großer Sätze strukturell ähnlicher URIs bereit. Beispielsweise wird mit der folgenden Vorlage der Satz aller aus drei Segmenten bestehenden URIs angegeben, die mit "a" beginnen, mit "c" enden und im mittleren Segment einen beliebigen Wert enthalten können: a/{segment}/c  
  
 Diese Vorlage beschreibt URIs wie die Folgenden:  
  
-   a/x/c  
  
-   a/y/c  
  
-   a/z/c  
  
-   und so weiter.  
  
 In dieser Vorlage gibt die Notation mit geschweiften Klammern ("{segment}") ein variables Segment statt eines Literalwerts an.  
  
 .NET Framework stellt eine API mit dem Namen <xref:System.UriTemplate> zum Arbeiten mit URI-Vorlagen bereit. Mit `UriTemplates` können Sie Folgendes ausführen:  
  
-   Rufen Sie eine der der `Bind` Methoden mit einer Reihe von Parametern zum Erstellen einer *vollständig geschlossenen URI* , die mit die Vorlage übereinstimmt. Dies bedeutet, dass alle Variablen innerhalb der URI-Vorlage durch Istwerte ersetzt werden.  
  
-   Sie können `Match`() mit einem potenziellen URI aufrufen. Diese Methode schlüsselt den potenziellen URI mithilfe einer Vorlage in seine Bestandteile auf und gibt ein Wörterbuch zurück, in dem die verschiedenen URI-Teile mit den zugehörigen Variablen aus der Vorlage verzeichnet sind.  
  
-   `Bind`() und `Match`() sind Gegenstücke, sodass Sie `Match`( `Bind`( x ) ) aufrufen können und wieder zur Ausgangsumgebung zurückkehren.  
  
 Es ist häufig wünschenswert (insbesondere auf dem Server, wo es erforderlich ist, eine Anforderung basierend auf dem URI an einen Dienstvorgang weiterzuleiten), einen Satz von <xref:System.UriTemplate>-Objekten in einer Datenstruktur zu verfolgen, die unabhängig voneinander die einzelnen darin enthaltenen Vorlagen darstellen können. <xref:System.UriTemplateTable> stellt einen Satz von URI-Vorlagen dar und wählt aus einem gegebenen Vorlagensatz die beste Übereinstimmung für den zu prüfenden URI aus. Da diese Methode an keinen bestimmten Netzwerkstapel (einschließlich [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]) gebunden ist, können Sie sie an allen erforderlichen Positionen einsetzen.  
  
 Das Dienstmodell in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet <xref:System.UriTemplate> und <xref:System.UriTemplateTable>, um Dienstvorgänge mit einer Reihe von URIs zu verknüpfen, die durch ein <xref:System.UriTemplate>-Objekt beschrieben werden. Ein Dienstvorgang wird mithilfe von <xref:System.UriTemplate> oder <xref:System.ServiceModel.Web.WebGetAttribute> mit einer <xref:System.ServiceModel.Web.WebInvokeAttribute> verknüpft. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<xref:System.UriTemplate> und <xref:System.UriTemplateTable>, finden Sie unter [UriTemplate und UriTemplateTable](../../../../docs/framework/wcf/feature-details/uritemplate-and-uritemplatetable.md)  
  
## <a name="webget-and-webinvoke-attributes"></a>WebGet- und WebInvoke-Attribute  
 WEB-HTTP-Dienste in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nutzen neben den verschiedenen Aufrufverben (beispielsweise HTTP POST, PUT oder DELETE) Verben zum Abruf von Daten (z. B. WEB-HTTP). Das [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-WEB-HTTP-Programmiermodell ermöglicht den Entwicklern von Diensten, sowohl die URI-Vorlage als auch das mit den Dienstvorgängen verknüpfte Verb mithilfe von <xref:System.ServiceModel.Web.WebGetAttribute> und <xref:System.ServiceModel.Web.WebInvokeAttribute> festzulegen. Mit <xref:System.ServiceModel.Web.WebGetAttribute> und <xref:System.ServiceModel.Web.WebInvokeAttribute> können Sie steuern, wie einzelne Vorgänge an die URIs und die mit diesen URIs verknüpften HTTP–Methoden gebunden werden. Beispielsweise durch Hinzufügen von <xref:System.ServiceModel.Web.WebGetAttribute> und <xref:System.ServiceModel.Web.WebInvokeAttribute> im folgenden Code.  
  
```  
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
  
```  
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
  
 Um ein vollständiges Beispiel finden Sie unter eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Dienst, verwendet der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WEB-HTTP-Programmiermodell, finden Sie unter [wie: Erstellen einer grundlegenden WCF-Web-HTTP-Diensts](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md)  
  
## <a name="uritemplate-query-string-parameters-and-urls"></a>UriTemplate-Abfragezeichenfolgenparameter und URLs  
 Webdienste können aus einem Webbrowser heraus aufgerufen werden, indem eine URL eingegeben wird, die mit einem Dienstvorgang verknüpft ist. Diese Dienstvorgänge verarbeiten möglicherweise Abfragezeichenfolgenparameter, die in Form einer Zeichenfolge innerhalb der URL angegeben werden müssen. In der folgenden Tabelle sind die Typen, die innerhalb einer URL übergeben werden können, und das hierfür verwendete Format aufgeführt.  
  
|Typ|Format|  
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
|<xref:System.Char>|Ein beliebiges einzelnes Zeichen|  
|<xref:System.Decimal>|Eine beliebige Dezimalzahl in Standardnotation (kein Exponent)|  
|<xref:System.Boolean>|True oder False (Groß-/Kleinschreibung wird nicht berücksichtigt)|  
|<xref:System.String>|Beliebige Zeichenfolge (leere Zeichenfolgen werden nicht unterstützt, und es werden keine Escapezeichen hinzugefügt)|  
|<xref:System.DateTime>|MM/TT/JJJJ<br /><br /> MM/TT/JJJJ HH: MM: [UHR &#124; PM]<br /><br /> Monat Tag Jahr<br /><br /> Monatstag Jahr hh: mm: [Uhr &#124; PM]|  
|<xref:System.TimeSpan>|TT.HH:MM:SS<br /><br /> Wobei TT = Tage, HH = Stunden, MM = Minuten, SS = Sekunden|  
|<xref:System.Guid>|Ein GUID, beispielsweise:<br /><br /> 936DA01F-9ABD-4d9d-80C7-02AF85C822A8|  
|<xref:System.DateTimeOffset>|MM/TT/JJJJ HH:MM:SS MM:SS<br /><br /> Wobei TT = Tage, HH = Stunden, MM = Minuten, SS = Sekunden|  
|Enumerationen|Beispielsweise der Enumerationswert, der die Enumeration definiert, wie im folgenden Code gezeigt.<br /><br /> `public enum Days{ Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday };`<br /><br /> Jeder der einzelnen Enumerationswerte (bzw. der entsprechenden ganzzahligen Werte) kann in der Abfragezeichenfolge angegeben werden.|  
|Typen, die über ein `TypeConverterAttribute` verfügen, mit dem der Typ in eine Zeichenfolgendarstellung bzw. aus einer Zeichenfolgendarstellung konvertiert werden kann.|Hängt vom Typkonverter ab.|  
  
## <a name="formats-and-the-wcf-web-http-programming-model"></a>Formate und das WCF-WEB-HTTP-Programmiermodell  
 Das WEB-HTTP-Programmiermodell in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] umfasst neue Funktionen, die die Verwendung von vielen verschiedenen Datenformaten ermöglichen. Auf der Bindungsebene kann <xref:System.ServiceModel.WebHttpBinding> die folgenden anderen Arten von Daten lesen und schreiben:  
  
-   XML  
  
-   JSON  
  
-   Nicht transparente binäre Streams  
  
 Das heißt, dass das WEB-HTTP-Programmiermodell in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] jeden Datentyp verarbeiten kann, aber unter Umständen die Programmierung mit <xref:System.IO.Stream> erfordert.  
  
 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] stellt Unterstützung für JSON-Daten (AJAX) sowie Syndication-Feeds (einschließlich ATOM und RSS) bereit. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Diese Funktionen finden Sie unter [WCF Web-HTTP-Formatierung](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)[Übersicht über WCF Syndication](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md) und [AJAX-Integration und JSON-Unterstützung](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md).  
  
## <a name="wcf-web-http-programming-model-and-security"></a>WCF-WEB-HTTP-Programmiermodell und Sicherheit  
 Da das WEB-HTTP-Programmiermodell in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die WS-*-Protokolle nicht unterstützt, ist die einzige Möglichkeit zur Absicherung eines WEB-HTTP-Diensts in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] das Verfügbarmachen des Diensts über HTTPS mithilfe von SSL. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Einrichten von SSL mit [!INCLUDE[iisver](../../../../includes/iisver-md.md)], finden Sie unter [Gewusst wie: Implementieren von SSL auf IIS](http://go.microsoft.com/fwlink/?LinkId=131613)  
  
## <a name="troubleshooting-the-wcf-web-http-programming-model"></a>Fehlerbehebung im WCF-WEB-HTTP-Programmiermodell  
 Beim Aufrufen der WCF-WEB-HTTP-Dienste mit einer <xref:System.ServiceModel.Channels.ChannelFactoryBase%601> zur Erstellung eines Kanals verwendet das <xref:System.ServiceModel.Description.WebHttpBehavior> den <xref:System.ServiceModel.EndpointAddress>-Satz in der Konfigurationsdatei, selbst wenn eine andere <xref:System.ServiceModel.EndpointAddress> an die <xref:System.ServiceModel.Channels.ChannelFactoryBase%601> weitergegeben wird.  
  
## <a name="see-also"></a>Siehe auch  
 [WCF Syndication](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)  
 [WCF Web-HTTP-Programmiermodell Objekt](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md)  
 [WCF-Web-HTTP-Programmiermodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
