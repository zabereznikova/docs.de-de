---
title: Erstellen von WCF AJAX-Diensten ohne ASP.NET
ms.date: 03/30/2017
ms.assetid: ba4a7d1b-e277-4978-9f62-37684e6dc934
ms.openlocfilehash: b5f0f730f90227dcccc7e5ebf533d80a28f6e6eb
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599294"
---
# <a name="creating-wcf-ajax-services-without-aspnet"></a>Erstellen von WCF AJAX-Diensten ohne ASP.NET
Auf Windows Communication Foundation (WCF) AJAX-Dienste kann von jeder JavaScript-aktivierten Webseite zugegriffen werden, ohne dass ASP.NET AJAX erforderlich ist. In diesem Thema wird beschrieben, wie ein solcher WCF-Dienst erstellt wird.  
  
 Anweisungen zur Verwendung von WCF mit ASP.NET AJAX finden Sie unter [Erstellen von WCF-Diensten für ASP.NET AJAX](creating-wcf-services-for-aspnet-ajax.md).  
  
 Die Erstellung eines WCF AJAX-Dienstanbieter besteht aus drei Teilen:  
  
- Erstellen eines AJAX-Endpunkts, auf den vom Browser aus zugegriffen werden kann.  
  
- Erstellen eines AJAX-kompatiblen Dienstvertrags.  
  
- Zugreifen auf den WCF AJAX-Dienst.  
  
## <a name="creating-an-ajax-endpoint"></a>Erstellen eines AJAX-Endpunkts  
 Die einfachste Möglichkeit, die AJAX-Unterstützung in einem WCF-Dienst zu aktivieren, ist die Verwendung der <xref:System.ServiceModel.Activation.WebServiceHostFactory> in der SVC-Datei, die dem Dienst zugeordnet ist, wie im folgenden Beispiel gezeigt.  
  
```text
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
  
 Ein funktionierendes Beispiel finden Sie unter [AJAX-Dienst mit JSON und XML](../samples/ajax-service-with-json-and-xml-sample.md).  
  
## <a name="creating-an-ajax-compatible-service-contract"></a>Erstellen eines AJAX-kompatiblen Dienstvertrags  
 Standardmäßig geben die über einem AJAX-Endpunkt verfügbar gemachten Dienstverträge Daten im XML-Format zurück. Ebenso standardmäßig kann auf die Dienstvorgänge über HTTP POST-Anforderungen mit URLs zugegriffen werden, die die Endpunktadresse gefolgt vom Vorgangsnamen enthalten, wie im folgenden Beispiel gezeigt.  
  
```csharp
[OperationContract]  
string[] GetCities(string firstLetters);  
```  
  
 Auf diesen Vorgang kann über HTTP Post an `http://serviceaddress/endpointaddress/GetCities` und eine XML-Nachricht zurückgegeben werden.  
  
 Sie können das vollständige Webprogrammiermodell verwenden, um diese grundlegenden Aspekte anzupassen. Sie können beispielsweise die Attribute <xref:System.ServiceModel.Web.WebGetAttribute> oder <xref:System.ServiceModel.Web.WebInvokeAttribute> verwenden, um zu steuern, auf welche HTTP-Verben der Vorgang reagiert, oder die Eigenschaft `UriTemplate` dieser jeweiligen Attribute verwenden, um benutzerdefinierte URIs anzugeben usw. Weitere Informationen finden Sie im Thema [WCF-Web-HTTP-Programmiermodell](wcf-web-http-programming-model.md) .  
  
 Das JSON-Datenformat wird oft in AJAX-Diensten verwendet. Um einen Vorgang zu erstellen, der JSON statt XML zurückgibt, legen Sie die <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A>-Eigenschaft (oder die <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>-Eigenschaft) auf <xref:System.ServiceModel.Web.WebMessageFormat.Json> fest. Das Thema zur [eigenständigen JSON-Serialisierung](stand-alone-json-serialization.md) zeigt, wie integrierte .NET-Typen und Daten Vertragstypen JSON zugeordnet werden.  
  
 Normalerweise bestehen JSON-Anforderungen und -Antworten aus nur einem Element. Für den vorangehenden `GetCities`-Vorgang ähnelt die Anforderung der folgenden Anweisung.  
  
```json
"na"  
```  
  
 Die Antwort auf diese Anforderung ähnelt der folgenden Anweisung.  
  
```json
["Nairobi", "Naples", "Nashville"]  
```  
  
 Wenn der Vorgang einen zusätzlichen Parameter annimmt, muss der Anforderungsstil auf "wrapped" festgelegt werden, damit beide Parameter einem einzigen JSON-Objekt zugeordnet werden. Ein Beispiel für eine JSON-Nachricht in diesem Stil finden Sie im folgenden Beispiel.  
  
```json  
{"firstLetters": "na", "maxNumber": 2}  
```  
  
 Der folgende Vertrag akzeptiert diese Nachricht.  
  
```csharp
[WebInvoke(BodyStyle=WebMessageBodyStyle.WrappedRequest, ResponseFormat=WebMessageFormat.Json)]  
[OperationContract]  
string[] GetCities(string firstLetters, int maxNumber);  
```  
  
## <a name="accessing-ajax-services"></a>Zugreifen auf AJAX-Dienste  
 WCF AJAX-Endpunkte akzeptieren immer sowohl JSON-als auch XML-Anforderungen.  
  
 HTTP POST-Anforderungen mit dem Inhaltstyp "application/json" werden als JSON behandelt, und diejenigen mit Inhaltstyp, die XML angeben (z. b. "Text/XML") werden als XML behandelt.  
  
 HTTP GET-Anforderungen enthalten alle Anforderungsparameter in der URL selbst.  
  
 Es obliegt dem Benutzer zu entscheiden, wie die HTTP-Anforderung für den Endpunkt erstellt wird. Der Benutzer kann umfassend steuern, wie das den Text der Anforderung bildende JSON erstellt wird. Ein Beispiel für das Erstellen einer Anforderung aus JavaScript finden Sie unter [AJAX-Dienst mit JSON und XML](../samples/ajax-service-with-json-and-xml-sample.md).
