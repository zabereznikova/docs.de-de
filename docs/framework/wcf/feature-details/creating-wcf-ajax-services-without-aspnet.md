---
title: Erstellen von WCF AJAX-Diensten ohne ASP.NET
ms.date: 03/30/2017
ms.assetid: ba4a7d1b-e277-4978-9f62-37684e6dc934
ms.openlocfilehash: 77a850408c3d952dbd4f682ea704d3248ae17c3e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="creating-wcf-ajax-services-without-aspnet"></a>Erstellen von WCF AJAX-Diensten ohne ASP.NET
Windows Communication Foundation (WCF)-AJAX-Diensten können von jeder JavaScript-aktivierten Webseite zugegriffen werden, ohne ASP.NET AJAX. In diesem Thema wird beschrieben, wie z. B. einen WCF-Dienst erstellt wird.  
  
 Anleitungen zur Verwendung von WCF mit ASP.NET AJAX finden Sie unter [Erstellen von WCF-Diensten für ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md).  
  
 Es gibt drei Teile für das Erstellen eines WCF AJAX-Diensts:  
  
-   Erstellen eines AJAX-Endpunkts, auf den vom Browser aus zugegriffen werden kann.  
  
-   Erstellen eines AJAX-kompatiblen Dienstvertrags.  
  
-   Zugreifen auf den WCF AJAX-Dienst.  
  
## <a name="creating-an-ajax-endpoint"></a>Erstellen eines AJAX-Endpunkts  
 Die grundlegendste Möglichkeit zum Aktivieren der AJAX-Unterstützung in einem WCF-Dienst ist die Verwendung der <xref:System.ServiceModel.Activation.WebServiceHostFactory> in der SVC-Datei, die dem Dienst, wie im folgenden Beispiel zugeordnet.  
  
```  
<%ServiceHost   
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CityService"  
    Factory=System.ServiceModel.Activation.WebServiceHostFactory  
%>  
```  
  
 Alternativ können Sie auch die Konfiguration verwenden, um einen AJAX-Endpunkt hinzuzufügen. Verwenden Sie die <xref:System.ServiceModel.WebHttpBinding> des Dienstendpunkts, und konfigurieren Sie diesen Endpunkt mit dem <xref:System.ServiceModel.Description.WebHttpBehavior>, wie im folgenden Codeausschnitt dargestellt.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="AjaxBehavior">  
          <webHttp/>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <services>  
      <service name="Microsoft.Ajax.Samples.CityService">  
        <endpoint   
          address="ajaxEndpoint"  
          behaviorConfiguration="AjaxBehavior"  
          binding="webHttpBinding"  
          contract="Microsoft.Ajax.Samples.ICityService" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 Ein Arbeitsbeispiel finden Sie unter der [AJAX-Dienst mit JSON und XML-](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).  
  
## <a name="creating-an-ajax-compatible-service-contract"></a>Erstellen eines AJAX-kompatiblen Dienstvertrags  
 Standardmäßig geben die über einem AJAX-Endpunkt verfügbar gemachten Dienstverträge Daten im XML-Format zurück. Ebenso standardmäßig kann auf die Dienstvorgänge über HTTP POST-Anforderungen mit URLs zugegriffen werden, die die Endpunktadresse gefolgt vom Vorgangsnamen enthalten, wie im folgenden Beispiel gezeigt.  
  
```  
[OperationContract]  
string[] GetCities(string firstLetters);  
```  
  
 Dieser Vorgang ist mit HTTP POST für `http://serviceaddress/endpointaddress/GetCities` und zurückgeben eine XML-Nachricht.  
  
 Sie können das vollständige Webprogrammiermodell verwenden, um diese grundlegenden Aspekte anzupassen. Sie können beispielsweise die Attribute <xref:System.ServiceModel.Web.WebGetAttribute> oder <xref:System.ServiceModel.Web.WebInvokeAttribute> verwenden, um zu steuern, auf welche HTTP-Verben der Vorgang reagiert, oder die Eigenschaft `UriTemplate` dieser jeweiligen Attribute verwenden, um benutzerdefinierte URIs anzugeben usw. Weitere Informationen finden Sie unter der [WCF Web-HTTP-Programmiermodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md) Thema.  
  
 Das JSON-Datenformat wird oft in AJAX-Diensten verwendet. Um einen Vorgang zu erstellen, der JSON statt XML zurückgibt, legen Sie die <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A>-Eigenschaft (oder die <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>-Eigenschaft) auf <xref:System.ServiceModel.Web.WebMessageFormat.Json> fest. Die [eigenständige JSON-Serialisierung](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md) Thema zeigt wie integrierte .NET Typen und Daten Vertrag Typen Zuordnung zu JSON.  
  
 Normalerweise bestehen JSON-Anforderungen und -Antworten aus nur einem Element. Für den vorangehenden `GetCities`-Vorgang ähnelt die Anforderung der folgenden Anweisung.  
  
```  
"na"  
```  
  
 Die Antwort auf diese Anforderung ähnelt der folgenden Anweisung.  
  
```  
["Nairobi", "Naples", "Nashville"]  
```  
  
 Wenn der Vorgang einen zusätzlichen Parameter annimmt, muss der Anforderungsstil auf "wrapped" festgelegt werden, damit beide Parameter einem einzigen JSON-Objekt zugeordnet werden. Ein Beispiel für eine JSON-Nachricht in diesem Stil finden Sie im folgenden Beispiel.  
  
```json  
{"firstLetters": "na", "maxNumber": 2}  
```  
  
 Der folgende Vertrag akzeptiert diese Nachricht.  
  
```  
[WebInvoke(BodyStyle=WebMessageBodyStyle.WrappedRequest, ResponseFormat=WebMessageFormat.Json)]  
[OperationContract]  
string[] GetCities(string firstLetters, int maxNumber);  
```  
  
## <a name="accessing-ajax-services"></a>Zugreifen auf AJAX-Dienste  
 WCF AJAX-Endpunkte akzeptieren immer sowohl JSON- und XML-Anforderungen.  
  
 HTTP POST-Anforderungen mit einem Inhaltstyp "Application/Json" werden als JSON behandelt, und mit dem Inhaltstyp, die XML (z. B. "Text/Xml") angeben, werden als XML behandelt.  
  
 HTTP GET-Anforderungen enthalten alle Anforderungsparameter in der URL selbst.  
  
 Es obliegt dem Benutzer zu entscheiden, wie die HTTP-Anforderung für den Endpunkt erstellt wird. Der Benutzer kann umfassend steuern, wie das den Text der Anforderung bildende JSON erstellt wird. Ein Beispiel für eine Anforderung aus JavaScript zu erstellen, finden Sie unter der [AJAX-Dienst mit JSON und XML-](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).
