---
title: Beispiel für AJAX-Dienst mit JSON und XML
ms.date: 03/30/2017
ms.assetid: 8ea5860d-0c42-4ae9-941a-e07efdd8e29c
ms.openlocfilehash: f8e112a75d537927d7a099d2988c1219515e2c1a
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/16/2019
ms.locfileid: "56332342"
---
# <a name="ajax-service-with-json-and-xml-sample"></a>Beispiel für AJAX-Dienst mit JSON und XML
In diesem Beispiel wird veranschaulicht, wie Windows Communication Foundation (WCF) zu verwenden, um einen Dienst Asynchronous JavaScript and XML (AJAX) zu erstellen, der entweder JavaScript Object Notation (JSON) oder XML-Daten zurückgibt. Sie können auf einen AJAX-Dienst zugreifen, indem Sie JavaScript-Code in einem Webbrowserclient verwenden. Dieses Beispiel baut auf den [einfacher AJAX-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md) Beispiel.  
  
 Im Gegensatz zu den anderen AJAX-Beispielen werden in diesem Beispiel ASP.NET AJAX und das <xref:System.Web.UI.ScriptManager>-Steuerelement nicht verwendet. Klicken Sie mit einigen zusätzlichen Konfigurationseinstellungen kann WCF AJAX-Dienst können von jeder HTML-Seite über JavaScript zugegriffen werden, und dieses Szenario ist hier dargestellt. Ein Beispiel der Verwendung von WCF mit ASP.NET AJAX finden Sie unter [AJAX-Beispielen](ajax.md).
  
 In diesem Beispiel wird gezeigt, wie der Antworttyp eines Vorgangs zwischen JSON und XML umgeschaltet wird. Diese Funktion ist unabhängig davon verfügbar, ob der Dienst für den Zugriff durch ASP.NET AJAX oder eine HTML/JavaScript-Clientseite konfiguriert wurde.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.
  
Um die Verwendung von Nicht-ASP.NET AJAX-Clients zu aktivieren, verwenden Sie <xref:System.ServiceModel.Activation.WebServiceHostFactory> (nicht <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>) in der SVC-Datei. <xref:System.ServiceModel.Activation.WebServiceHostFactory> fügt dem Dienst einen <xref:System.ServiceModel.Description.WebHttpEndpoint>-Standardendpunkt hinzu. Der Endpunkt wird an einer leeren Adresse relativ zur SVC-Datei konfiguriert; Dies bedeutet, dass die Adresse des Diensts `http://localhost/ServiceModelSamples/service.svc`, mit Ausnahme des Vorgangsnamens keine zusätzlichen Suffixe.  
  
```svc
<%@ServiceHost language="c#" Debug="true" Service="Microsoft.Samples.XmlAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebServiceHostFactory" %>  
```  
  
 Im folgenden Abschnitt in der Datei Web.config können zusätzliche Konfigurationsänderungen am Endpunkt vorgenommen werden. Wenn keine zusätzlichen Änderungen erforderlich sind, kann der Abschnitt entfernt werden.  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>  
    <webHttpEndpoint>  
      <!-- Use this element to configure the endpoint -->  
      <standardEndpoint name="" />  
    </webHttpEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 Das Standarddatenformat für <xref:System.ServiceModel.Description.WebHttpEndpoint> ist XML und das Standarddatenformat für <xref:System.ServiceModel.Description.WebScriptEndpoint> ist JSON. Weitere Informationen finden Sie unter [Erstellen von WCF AJAX-Diensten ohne ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md).  
  
 Der Dienst im folgenden Beispiel wird eine standard-WCF-Dienst mit zwei Vorgängen. Beide Vorgänge erfordern den <xref:System.ServiceModel.Web.WebMessageBodyStyle.Wrapped>-Textstil beim <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut oder <xref:System.ServiceModel.Web.WebInvokeAttribute>-Attribut. Dieser Textstil ist typisch für das `webHttp`-Verhalten und hat keinen Einfluss auf den JSON/XML-Datenformatwechsel.  

```csharp
[OperationContract]  
[WebInvoke(ResponseFormat = WebMessageFormat.Xml, BodyStyle = WebMessageBodyStyle.Wrapped)]  
MathResult DoMathXml(double n1, double n2);  
```

 Das Format der Antwort für den Vorgang angegeben ist, als XML, wobei der Standardwert ist für die [ \<WebHttp >](../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) Verhalten. Es wird jedoch empfohlen, das Antwortformat explizit festzulegen.  
  
 Der andere Vorgang verwendet das `WebInvokeAttribute`-Attribut und gibt explizit JSON statt XML als Antwortformat an.  

```csharp
[OperationContract]  
[WebInvoke(ResponseFormat = WebMessageFormat.Json, BodyStyle = WebMessageBodyStyle.Wrapped)]  
MathResult DoMathJson(double n1, double n2);  
```

 Beachten Sie, dass die Vorgänge in beiden Fällen geben einen komplexen Typ zurück `MathResult`, dies ist ein standard-WCF-Datenvertragstyp.  
  
 Die Webseite XmlAjaxClientPage.htm enthält JavaScript-Code, der eines der oben beschriebenen beiden Vorgänge aufruft, klickt der Benutzer die **führen Berechnung (JSON zurückgeben)** oder **Berechnung (XML zurückgeben) ausführen**  Schaltflächen auf der Seite. Im zum Aufrufen des Diensts verwendeten Code wird ein JSON-Text erstellt und mit HTTP-POST gesendet. Die Anforderung wird manuell in JavaScript erstellt, im Gegensatz zu den [einfacher AJAX-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md) Beispiel und den anderen Beispielen, die mithilfe von ASP.NET AJAX.  

```csharp
// Create HTTP request  
var xmlHttp;  
// Request instantiation code omitted…  
// Result handler code omitted…  
  
// Build the operation URL  
var url = "service.svc/ajaxEndpoint/";  
url = url + operation;  
  
// Build the body of the JSON message  
var body = '{"n1":';  
body = body + document.getElementById("num1").value + ',"n2":';  
body = body + document.getElementById("num2").value + '}';  
  
// Send the HTTP request  
xmlHttp.open("POST", url, true);  
xmlHttp.setRequestHeader("Content-type", "application/json");  
xmlHttp.send(body);  
```

 Wenn der Dienst antwortet, wird die Antwort, ohne vorher weiterverarbeitet zu werden, in einem Textfeld auf der Seite angezeigt. Dies dient der Veranschaulichung, sodass Sie direkt die verwendeten XML- und JSON-Datenformate prüfen können.  

```javascript
// Create result handler   
xmlHttp.onreadystatechange=function(){  
     if(xmlHttp.readyState == 4){  
          document.getElementById("result").value = xmlHttp.responseText;  
     }  
}  
```

> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\XmlAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Erstellen Sie die Projektmappe XmlAjaxService.sln, wie in beschrieben [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Navigieren Sie zu `http://localhost/ServiceModelSamples/XmlAjaxClientPage.htm` (Öffnen Sie XmlAjaxClientPage.htm nicht im Browser aus dem Projektverzeichnis).  
  
## <a name="see-also"></a>Siehe auch
- [AJAX-Dienst mit HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)
