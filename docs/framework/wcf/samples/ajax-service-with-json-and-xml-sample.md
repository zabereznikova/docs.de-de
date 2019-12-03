---
title: Beispiel für AJAX-Dienst mit JSON und XML
ms.date: 03/30/2017
ms.assetid: 8ea5860d-0c42-4ae9-941a-e07efdd8e29c
ms.openlocfilehash: ca9bdbfa135ac7dc0b69589d4f8fce07bc4c4afe
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716217"
---
# <a name="ajax-service-with-json-and-xml-sample"></a>Beispiel für AJAX-Dienst mit JSON und XML

In diesem Beispiel wird veranschaulicht, wie Windows Communication Foundation (WCF) verwendet wird, um einen asynchronen JavaScript-und XML (Ajax)-Dienst zu erstellen, der entweder JavaScript Object Notation (JSON)-oder XML-Daten zurückgibt. Sie können auf einen AJAX-Dienst zugreifen, indem Sie JavaScript-Code in einem Webbrowserclient verwenden. Dieses Beispiel baut auf dem [grundlegenden AJAX-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md) Beispiel auf.

Im Gegensatz zu den anderen AJAX-Beispielen werden in diesem Beispiel ASP.NET AJAX und das <xref:System.Web.UI.ScriptManager>-Steuerelement nicht verwendet. Mit einigen zusätzlichen Konfigurationen kann von jeder HTML-Seite über JavaScript auf WCF AJAX-Dienste zugegriffen werden. dieses Szenario wird hier gezeigt. Ein Beispiel für die Verwendung von WCF mit ASP.NET AJAX finden Sie unter [AJAX Samples](ajax.md).

In diesem Beispiel wird gezeigt, wie der Antworttyp eines Vorgangs zwischen JSON und XML umgeschaltet wird. Diese Funktion ist unabhängig davon verfügbar, ob der Dienst für den Zugriff durch ASP.NET AJAX oder eine HTML/JavaScript-Clientseite konfiguriert wurde.

> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.

Um die Verwendung von Nicht-ASP.NET AJAX-Clients zu aktivieren, verwenden Sie <xref:System.ServiceModel.Activation.WebServiceHostFactory> (nicht <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>) in der SVC-Datei. <xref:System.ServiceModel.Activation.WebServiceHostFactory> fügt dem Dienst einen <xref:System.ServiceModel.Description.WebHttpEndpoint>-Standardendpunkt hinzu. Der Endpunkt wird mit einer leeren Adresse relativ zur SVC-Datei konfiguriert. Dies bedeutet, dass die Adresse des Dienstanbieter `http://localhost/ServiceModelSamples/service.svc`ist, ohne dass zusätzliche Suffixe den Vorgangs Namen haben.

`<%@ServiceHost language="c#" Debug="true" Service="Microsoft.Samples.XmlAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebServiceHostFactory" %>`

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

Das Standarddatenformat für <xref:System.ServiceModel.Description.WebHttpEndpoint> ist XML, während das Standarddatenformat für <xref:System.ServiceModel.Description.WebScriptEndpoint> JSON ist. Weitere Informationen finden Sie unter [Erstellen von WCF AJAX-Diensten ohne ASP.net](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md).

Der Dienst im folgenden Beispiel ist ein WCF-Standard Dienst mit zwei Vorgängen. Beide Vorgänge erfordern den <xref:System.ServiceModel.Web.WebMessageBodyStyle.Wrapped>-Textstil beim <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut oder <xref:System.ServiceModel.Web.WebInvokeAttribute>-Attribut. Dieser Textstil ist typisch für das `webHttp`-Verhalten und hat keinen Einfluss auf den JSON/XML-Datenformatwechsel.

```csharp
[OperationContract]
[WebInvoke(ResponseFormat = WebMessageFormat.Xml, BodyStyle = WebMessageBodyStyle.Wrapped)]
MathResult DoMathXml(double n1, double n2);
```

Das Antwortformat für den Vorgang wird als XML angegeben. Dies ist die Standardeinstellung für das [\<webHttp->](../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) Verhalten. Es wird jedoch empfohlen, das Antwortformat explizit festzulegen.

Der andere Vorgang verwendet das `WebInvokeAttribute`-Attribut und gibt explizit JSON statt XML als Antwortformat an.

```csharp
[OperationContract]
[WebInvoke(ResponseFormat = WebMessageFormat.Json, BodyStyle = WebMessageBodyStyle.Wrapped)]
MathResult DoMathJson(double n1, double n2);
```

Beachten Sie, dass die Vorgänge in beiden Fällen einen komplexen Typ zurückgeben, `MathResult`, bei dem es sich um einen WCF-Standarddaten Vertragstyp handelt.

Die Client Webseite XmlAjaxClientPage. htm enthält JavaScript-Code, der einen der vorherigen beiden Vorgänge aufruft, wenn der Benutzer auf die Schaltflächen **Berechnung ausführen (JSON zurückgeben)** oder **Berechnung (Rückgabe-XML)** auf der Seite klickt. Im zum Aufrufen des Diensts verwendeten Code wird ein JSON-Text erstellt und mit HTTP-POST gesendet. Die Anforderung wird manuell in JavaScript erstellt, im Gegensatz zum [grundlegenden AJAX-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md) Beispiel und den anderen Beispielen mit ASP.NET AJAX.

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
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\XmlAjaxService`

#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

2. Erstellen Sie die Projekt Mappe XmlAjaxService. sln, wie unter [Erstellen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md)beschrieben.

3. Navigieren Sie zu `http://localhost/ServiceModelSamples/XmlAjaxClientPage.htm` (Öffnen Sie XmlAjaxClientPage. htm nicht im Browser im Projektverzeichnis).

## <a name="see-also"></a>Siehe auch

- [AJAX-Dienst mit HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)
