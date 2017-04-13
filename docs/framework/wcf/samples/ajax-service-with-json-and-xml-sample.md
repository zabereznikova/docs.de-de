---
title: "Beispiel f&#252;r AJAX-Dienst mit JSON und XML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8ea5860d-0c42-4ae9-941a-e07efdd8e29c
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Beispiel f&#252;r AJAX-Dienst mit JSON und XML
In diesem Beispiel wird veranschaulicht, wie mit [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ein AJAX\-Dienst \(Asynchronous JavaScript and XML\) erstellt werden kann, der entweder Daten im Datenformat Javascript Object Notation \(JSON\) oder XML wiedergibt.Sie können auf einen AJAX\-Dienst zugreifen, indem Sie JavaScript\-Code in einem Webbrowserclient verwenden.Dieses Beispiel basiert auf dem [Einfacher AJAX\-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md)\-Beispiel.  
  
 Im Gegensatz zu den anderen AJAX\-Beispielen werden in diesem Beispiel ASP.NET AJAX und das <xref:System.Web.UI.ScriptManager>\-Steuerelement nicht verwendet.Mit einigen zusätzlichen Konfigurationseinstellungen kann auf [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] AJAX\-Dienste von jeder HTML\-Seite über JavaScript zugegriffen werden. Dieses Szenario wird hier dargestellt.Ein Beispiel für das Verwenden von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mit ASP.NET AJAX finden Sie unter [AJAX Samples](http://msdn.microsoft.com/de-de/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
 In diesem Beispiel wird gezeigt, wie der Antworttyp eines Vorgangs zwischen JSON und XML umgeschaltet wird.Diese Funktion ist unabhängig davon verfügbar, ob der Dienst für den Zugriff durch ASP.NET AJAX oder eine HTML\/JavaScript\-Clientseite konfiguriert wurde.  
  
> [!NOTE]
>  Die Setupprozedur und die Erstellungsanweisungen für dieses Beispiel befinden sich am Ende dieses Abschnitts.  
  
 Um die Verwendung von Nicht\-ASP.NET AJAX\-Clients zu aktivieren, verwenden Sie <xref:System.ServiceModel.Activation.WebServiceHostFactory> \(nicht <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>\) in der SVC\-Datei.<xref:System.ServiceModel.Activation.WebServiceHostFactory> fügt dem Dienst einen <xref:System.ServiceModel.Description.WebHttpEndpoint>\-Standardendpunkt hinzu.Der Endpunkt ist für eine leere Adresse konfiguriert, die relativ zur SVC\-Datei festgelegt ist. Dies bedeutet, dass die Adresse des Diensts http:\/\/localhost\/ServiceModelSamples\/service.svc lautet und mit Ausnahme des Vorgangsnamens keine zusätzlichen Suffixe aufweist.  
  
```html  
<%@ServiceHost language="c#" Debug="true" Service="Microsoft.Samples.XmlAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebServiceHostFactory" %>  
  
```  
  
 Im folgenden Abschnitt in der Datei Web.config können zusätzliche Konfigurationsänderungen am Endpunkt vorgenommen werden.Wenn keine zusätzlichen Änderungen erforderlich sind, kann der Abschnitt entfernt werden.  
  
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
  
 Das Standarddatenformat für <xref:System.ServiceModel.Description.WebHttpEndpoint> ist XML und das Standarddatenformat für [for T:System.ServiceModel.Description.WebScriptEndpoint](assetId:///for T:System.ServiceModel.Description.WebScriptEndpoint?qualifyHint=False&autoUpgrade=True) ist JSON.Weitere Informationen finden Sie unter [Erstellen von WCF AJAX\-Diensten ohne ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md).  
  
 Der Dienst im folgenden Beispiel ist ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Standarddienst mit zwei Vorgängen.Beide Vorgänge erfordern den <xref:System.ServiceModel.Web.WebMessageBodyStyle>\-Textstil beim <xref:System.ServiceModel.Web.WebGetAttribute>\-Attribut oder <xref:System.ServiceModel.Web.WebInvokeAttribute>\-Attribut. Dieser Textstil ist typisch für das `webHttp`\-Verhalten und hat keinen Einfluss auf den JSON\/XML\-Datenformatwechsel.  
  
```  
[OperationContract]  
[WebInvoke(ResponseFormat = WebMessageFormat.Xml, BodyStyle = WebMessageBodyStyle.Wrapped)]  
MathResult DoMathXml(double n1, double n2);  
```  
  
 Als Antwortformat des Vorgangs wird XML angegeben. Dies entspricht der Standardeinstellung für das [\<webHttp\>](../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)\-Verhalten.Es wird jedoch empfohlen, das Antwortformat explizit festzulegen.  
  
 Der andere Vorgang verwendet das `WebInvokeAttribute`\-Attribut und gibt explizit JSON statt XML als Antwortformat an.  
  
```  
[OperationContract]  
[WebInvoke(ResponseFormat = WebMessageFormat.Json, BodyStyle = WebMessageBodyStyle.Wrapped)]  
MathResult DoMathJson(double n1, double n2);  
```  
  
 Beachten Sie, dass die Vorgänge in beiden Fällen einen komplexen Typ, `MathResult`, wiedergeben, bei dem es sich um einen standardmäßigen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Datenvertragstyp handelt.  
  
 Die Webseite des Client XmlAjaxClientPage.htm enthält JavaScript\-Code, der einen der oben beschriebenen beiden Vorgänge aufruft, wenn der Benutzer auf der Seite auf die Schaltfläche **Berechnung durchführen \(JSON zurückgeben\)** oder **Berechnung durchführen \(XML zurückgeben\)** klickt.Im zum Aufrufen des Diensts verwendeten Code wird ein JSON\-Text erstellt und mit HTTP\-POST gesendet.Die Anforderung wird manuell in JavaScript erstellt. Im [Einfacher AJAX\-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md)\-Beispiel und in den anderen Beispielen wird dagegen ASP.NET AJAX verwendet.  
  
```  
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
  
 Wenn der Dienst antwortet, wird die Antwort, ohne vorher weiterverarbeitet zu werden, in einem Textfeld auf der Seite angezeigt.Dies dient der Veranschaulichung, sodass Sie direkt die verwendeten XML\- und JSON\-Datenformate prüfen können.  
  
```  
// Create result handler   
xmlHttp.onreadystatechange=function(){  
     if(xmlHttp.readyState == 4){  
          document.getElementById("result").value = xmlHttp.responseText;  
     }  
}  
```  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\XmlAjaxService`  
  
#### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Vergewissern Sie sich, dass Sie [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Erstellen Sie die Projektmappe XmlAjaxService.sln, wie in [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md) beschrieben.  
  
3.  Navigieren Sie zu http:\/\/localhost\/ServiceModelSamples\/XmlAjaxClientPage.htm \(öffnen Sie XmlAjaxClientPage.htm nicht im Browser vom Projektverzeichnis\).  
  
## Siehe auch  
 [AJAX\-Dienst mit HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)