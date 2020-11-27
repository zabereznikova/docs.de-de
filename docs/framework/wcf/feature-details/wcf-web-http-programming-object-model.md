---
title: Objektmodell für WCF-Web-HTTP-Programmierung
ms.date: 03/30/2017
ms.assetid: ed96b5fc-ca2c-4b0d-bdba-d06b77c3cb2a
ms.openlocfilehash: 4cd23ccb1956a73e36d5c7d3e444c347247e338d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266882"
---
# <a name="wcf-web-http-programming-object-model"></a>Objektmodell für WCF-Web-HTTP-Programmierung

Das WCF-Web-HTTP-Programmiermodell ermöglicht es Entwicklern, Windows Communication Foundation (WCF)-Webdienste über einfache HTTP-Anforderungen ohne SOAP verfügbar zu machen. Das WCF-Web-HTTP-Programmiermodell basiert auf dem vorhandenen WCF-Erweiterbarkeits Modell. Mit diesem Modell werden folgende Klassen definiert:  
  
 **Programmiermodell:**  
  
- <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>  
  
- <xref:System.ServiceModel.Web.WebGetAttribute>  
  
- <xref:System.ServiceModel.Web.WebInvokeAttribute>  
  
- <xref:System.ServiceModel.Web.WebServiceHost>  
  
 **Kanäle und Verteilerinfrastruktur:**  
  
- <xref:System.ServiceModel.WebHttpBinding>  
  
- <xref:System.ServiceModel.Description.WebHttpBehavior>  
  
 **Hilfsprogrammklassen und Erweiterungspunkte:**  
  
- <xref:System.UriTemplate>  
  
- <xref:System.UriTemplateTable>  
  
- <xref:System.ServiceModel.Dispatcher.QueryStringConverter>  
  
- <xref:System.ServiceModel.Dispatcher.WebHttpDispatchOperationSelector>  
  
## <a name="aspnetcacheprofileattribute"></a>AspNetCacheProfileAttribute  

 <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> gibt bei Anwendung auf einen Dienstvorgang das ASP.NET-Ausgabecacheprofil in der Konfigurationsdatei an, das zum Zwischenspeichern von Antworten aus dem Vorgang im ASP.NET-Ausgabecache verwendet werden soll. Diese Eigenschaft verwendet nur einen Parameter, den Cacheprofilnamen, der die Cacheeinstellungen in der Konfigurationsdatei angibt.  
  
## <a name="webgetattribute"></a>WebGetAttribute  

 Das <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut wird dazu verwendet, einen Dienstvorgang als Vorgang zu kennzeichnen, der auf HTTP GET-Anforderungen reagiert. Es handelt sich um ein passives Vorgangsverhalten (von den <xref:System.ServiceModel.Description.IOperationBehavior>-Methoden werden keine Aktionen ausgeführt), durch das der Vorgangsbeschreibung Metadaten hinzugefügt werden. Die Anwendung von <xref:System.ServiceModel.Web.WebGetAttribute> hat nur dann Auswirkungen, wenn ein Verhalten, das in der Vorgangsbeschreibung nach diesen Metadaten sucht (insbesondere <xref:System.ServiceModel.Description.WebHttpBehavior>), der Verhaltensauflistung des Diensts hinzugefügt wird. Das <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut verwendet die in der folgenden Tabelle beschriebenen optionalen Parameter.  
  
|Parameter|BESCHREIBUNG|  
|---------------|-----------------|  
|`BodyStyle`|Steuert, ob Anforderungen und Antworten, die an den Dienstvorgang, auf den das Attribut angewendet wird, gesendet oder von diesem empfangen werden, umschlossen werden.|  
|`RequestFormat`|Steuert die Formatierung von Anforderungsnachrichten.|  
|`ResponseFormat`|Steuert die Formatierung von Antwortnachrichten.|  
|`UriTemplate`|Gibt die URI-Vorlage an, mit der gesteuert wird, welche HTTP-Anforderungen dem Dienstvorgang zugeordnet werden, auf den das Attribut angewendet wird.|  
  
## <a name="webhttpbinding"></a>WebHttpBinding  

 Die <xref:System.ServiceModel.WebHttpBinding>-Klasse bietet mit dem <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement> Unterstützung für XML-, JSON- und unformatierte Binärdaten. Das Element besteht aus <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpTransportBindingElement> und einem <xref:System.ServiceModel.WebHttpSecurity>-Objekt. Die <xref:System.ServiceModel.WebHttpBinding> wurde so konzipiert, dass sie in Verbindung mit <xref:System.ServiceModel.Description.WebHttpBehavior> verwendet werden kann.  
  
## <a name="webinvokeattribute"></a>WebInvokeAttribute  

 Das <xref:System.ServiceModel.Web.WebInvokeAttribute>-Attribut ist vergleichbar mit <xref:System.ServiceModel.Web.WebGetAttribute>, wird jedoch dazu verwendet, einen Dienstvorgang als einen Vorgang zu kennzeichnen, der auf andere HTTP-Anforderungen als GET antwortet. Es handelt sich um ein passives Vorgangsverhalten (von den <xref:System.ServiceModel.Description.IOperationBehavior>-Methoden werden keine Aktionen ausgeführt), durch das der Vorgangsbeschreibung Metadaten hinzugefügt werden. Die Anwendung von <xref:System.ServiceModel.Web.WebInvokeAttribute> hat nur dann Auswirkungen, wenn ein Verhalten, das in der Vorgangsbeschreibung nach diesen Metadaten sucht (insbesondere <xref:System.ServiceModel.Description.WebHttpBehavior>), der Verhaltensauflistung des Diensts hinzugefügt wird.  
  
 Das <xref:System.ServiceModel.Web.WebInvokeAttribute>-Attribut verwendet die in der folgenden Tabelle beschriebenen optionalen Parameter.  
  
|Parameter|BESCHREIBUNG|  
|---------------|-----------------|  
|`BodyStyle`|Steuert, ob Anforderungen und Antworten, die an den Dienstvorgang, auf den das Attribut angewendet wird, gesendet oder von diesem empfangen werden, umschlossen werden.|  
|`Method`|Gibt die HTTP-Methode an, der der Dienstvorgang zugeordnet wird.|  
|`RequestFormat`|Steuert die Formatierung von Anforderungsnachrichten.|  
|`ResponseFormat`|Steuert die Formatierung von Antwortnachrichten.|  
|`UriTemplate`|Gibt die URI-Vorlage an, mit der gesteuert wird, welche GET-Anforderungen dem Dienstvorgang zugeordnet werden, auf den das Attribut angewendet wird.|  
  
## <a name="uritemplate"></a>UriTemplate  

 Mit der <xref:System.UriTemplate>-Klasse können Sie einen Satz strukturell ähnlicher URIs definieren. Vorlagen bestehen aus zwei Teilen, einem Pfad und einer Abfrage. Ein Pfad besteht aus einer Reihe von Segmenten, die durch einen Schrägstrich (/) voneinander getrennt werden. Jedes Segment kann einen Literalwert, einen variablen Wert (geschrieben in geschweiften Klammern [{}], so eingeschränkt, dass er mit dem Inhalt von genau einem Segment übereinstimmt) oder einen Platzhalter (geschrieben als Sternchen [ \* ], der "der Rest des Pfades" entspricht) enthalten, der am Ende des Pfads angezeigt werden muss. Der Abfrageausdruck kann vollständig weggelassen werden. Sofern der Abfrageausdruck vorhanden ist, wird eine ungeordnete Reihe von Name-Wert-Paaren angegeben. Bei den Elementen des Abfrage Ausdrucks kann es sich entweder um Literale Paare (? x = 2) oder Variablen Paare (? x = {*value*}) handeln. Alleinstehende Werte sind nicht zulässig. <xref:System.UriTemplate> wird intern vom WCF-Web-HTTP-Programmiermodell verwendet, um Dienst Vorgängen bestimmte URIs oder Gruppen von URIs zuzuordnen.  
  
## <a name="uritemplatetable"></a>UriTemplateTable  

 Die <xref:System.UriTemplateTable>-Klasse stellt einen assoziativen Satz von <xref:System.UriTemplate>-Objekten dar, die an ein Objekt nach Wahl des Entwicklers gebunden sind. Sie ermöglicht es Ihnen, mögliche URIs (Uniform Resource Identifiers) mit den Vorlagen im Satz abzugleichen und die den übereinstimmenden Vorlagen zugeordneten Daten abzurufen. <xref:System.UriTemplateTable> wird intern vom WCF-Web-HTTP-Programmiermodell verwendet, um Dienst Vorgängen bestimmte URIs oder Gruppen von URIs zuzuordnen.  
  
## <a name="webservicehost"></a>WebServiceHost  

 <xref:System.ServiceModel.Web.WebServiceHost> erweitert <xref:System.ServiceModel.ServiceHost>, um das Hosten eines Nicht-SOAP-Webdiensts zu vereinfachen. Werden von <xref:System.ServiceModel.Web.WebServiceHost> in der Dienstbeschreibung keine Endpunkte gefunden, wird automatisch ein Standardendpunkt an der Basisadresse des Diensts erstellt. Beim Erstellen eines standardmäßigen HTTP-Endpunkts deaktiviert <xref:System.ServiceModel.Web.WebServiceHost> auch die HTTP-Hilfeseite und die GET-Funktion der Web Services Description Language (WSDL), damit der Metadatenendpunkt nicht in Konflikt mit dem standardmäßigen HTTP-Endpunkt gerät. Von <xref:System.ServiceModel.Web.WebServiceHost> wird zudem gewährleistet, dass an alle Endpunkte, die <xref:System.ServiceModel.WebHttpBinding> verwenden, das erforderliche <xref:System.ServiceModel.Description.WebHttpBehavior> angehängt ist. Zuletzt konfiguriert <xref:System.ServiceModel.Web.WebServiceHost> automatisch die Bindung des Endpunkts für die Kooperation mit den entsprechenden Sicherheitseinstellungen für Internetinformationsdienste (IIS), wenn sie in einem sicheren virtuellen Verzeichnis verwendet wird.  
  
## <a name="webservicehostfactory"></a>WebServiceHostFactory  

 Die <xref:System.ServiceModel.Activation.WebServiceHostFactory>-Klasse wird dazu verwendet, dynamisch einen <xref:System.ServiceModel.Web.WebServiceHost> zu erstellen, wenn ein Dienst unter Internetinformationsdienste (IIS) oder Windows Process Activation Service (WAS) gehostet wird. Im Gegensatz zu einem selbst gehosteten Dienst, bei dem <xref:System.ServiceModel.Web.WebServiceHost> von der Hostanwendung instanziiert wird, erstellen unter IIS oder WAS gehostete Dienste mithilfe dieser Klasse den <xref:System.ServiceModel.Web.WebServiceHost> für den Dienst. Die <xref:System.ServiceModel.Activation.WebServiceHostFactory.CreateServiceHost%28System.Type%2CSystem.Uri%5B%5D%29>-Methode wird aufgerufen, wenn eine eingehende Anforderung für den Dienst empfangen wird.  
  
## <a name="webhttpbehavior"></a>WebHttpBehavior  

 Die <xref:System.ServiceModel.Description.WebHttpBehavior>-Klasse stellt die erforderlichen Formatierungsprogramme, Vorgangsselektoren usw. bereit, die für die Unterstützung von Webdiensten auf der Dienstmodellebene erforderlich sind. Dieses Verhalten wird als Endpunktverhalten implementiert (das in Verbindung mit der <xref:System.ServiceModel.WebHttpBinding> verwendet wird) und ermöglicht die Angabe von Formatierungsprogrammen und Vorgangsselektoren für jeden Endpunkt, sodass von derselben Dienstimplementierung sowohl SOAP- als auch POX-Endpunkte verfügbar gemacht werden können.  
  
### <a name="extending-webhttpbehavior"></a>Erweitern von WebHttpBehavior  

 <xref:System.ServiceModel.Description.WebHttpBehavior> ist durch eine Reihe von virtuellen Methoden erweiterbar: <xref:System.ServiceModel.Description.WebHttpBehavior.GetOperationSelector%28System.ServiceModel.Description.ServiceEndpoint%29>, <xref:System.ServiceModel.Description.WebHttpBehavior.GetReplyClientFormatter%28System.ServiceModel.Description.OperationDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%29>, <xref:System.ServiceModel.Description.WebHttpBehavior.GetRequestClientFormatter%28System.ServiceModel.Description.OperationDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%29>, <xref:System.ServiceModel.Description.WebHttpBehavior.GetReplyDispatchFormatter%28System.ServiceModel.Description.OperationDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%29> und <xref:System.ServiceModel.Description.WebHttpBehavior.GetRequestDispatchFormatter%28System.ServiceModel.Description.OperationDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%29>. Entwickler können eine Klasse von <xref:System.ServiceModel.Description.WebHttpBehavior> ableiten und diese Methoden überschreiben, um das Standardverhalten anzupassen.  
  
 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> ist ein Beispiel für die Erweiterung von <xref:System.ServiceModel.Description.WebHttpBehavior>. <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> ermöglicht Windows Communication Foundation (WCF)-Endpunkten, HTTP-Anforderungen von einem browserbasierten ASP.NET AJAX-Client zu empfangen. Der [AJAX-Dienst mit HTTP Post](../samples/ajax-service-using-http-post.md) ist ein Beispiel für die Verwendung dieses Erweiterungs Punkts.  
  
> [!WARNING]
> Wenn das <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> verwendet wird, wird <xref:System.UriTemplate> im <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut oder im <xref:System.ServiceModel.Web.WebInvokeAttribute>-Attribut nicht unterstützt.  
  
## <a name="webhttpdispatchoperationselector"></a>WebHttpDispatchOperationSelector  

 Die <xref:System.ServiceModel.Dispatcher.WebHttpDispatchOperationSelector>-Klasse verwendet die <xref:System.UriTemplate>-Klasse und die <xref:System.UriTemplateTable>-Klasse, um Aufrufe an Dienstvorgänge zu senden.  
  
## <a name="compatibility"></a>Kompatibilität  

 Das WCF-Web-HTTP-Programmiermodell verwendet keine SOAP-basierten Nachrichten und unterstützt daher nicht die WS-*-Protokolle. Sie können jedoch denselben Vertrag durch zwei verschiedene Endpunkte verfügbar machen, von denen einer im Gegensatz zum anderen SOAP verwendet. Ein Beispiel finden Sie unter Gewusst [wie: verfügbar machen eines Vertrags für SOAP-und Webclients](how-to-expose-a-contract-to-soap-and-web-clients.md) .  
  
## <a name="security"></a>Sicherheit  

Da das WCF-Web-HTTP-Programmiermodell die WS-*-Protokolle nicht unterstützt, besteht die einzige Möglichkeit zum Sichern eines Webdiensts, der auf dem WCF-Web-HTTP-Programmiermodell basiert, darin, den Dienst mithilfe von SSL Weitere Informationen zum Einrichten von SSL mit IIS 7,0 finden Sie unter Gewusst [wie: Implementieren von SSL in IIS](https://support.microsoft.com/help/299875/how-to-implement-ssl-in-iis).
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
- <xref:System.ServiceModel.Web.WebInvokeAttribute>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- <xref:System.ServiceModel.Dispatcher.WebHttpDispatchOperationSelector>
- [Überblick über WCF-Web-HTTP-Programmiermodelle](wcf-web-http-programming-model-overview.md)
