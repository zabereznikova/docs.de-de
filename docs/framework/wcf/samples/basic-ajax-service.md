---
title: Einfacher AJAX-Dienst
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d66d0c91-0109-45a0-a901-f3e4667c2465
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e1890bd52d3d71ab7419cf1b89f582c3d0efbe9f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="basic-ajax-service"></a>Einfacher AJAX-Dienst
In diesem Beispiel wird die Verwendung von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] zum Erstellen eines einfachen AJAX-Diensts (ASP.NET Asynchronous JavaScript and XML) beschrieben. Ein AJAX-Dienst ist ein Dienst, auf den Sie durch die Verwendung eines JavaScript-Codes über einen Webbrowserclient zugreifen können. Der Dienst nutzt das <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut, um sicherzustellen, dass der Dienst auf HTTP GET-Anforderungen antwortet und für die Verwendung von JSON-Daten (JavaScript Object Notation) für Antworten konfiguriert ist.  
  
 Die AJAX-Unterstützung in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ist für die Verwendung mit ASP.NET AJAX über das `ScriptManager`-Steuerelement optimiert. Ein Beispiel der Verwendung von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mit ASP.NET AJAX finden Sie unter der [AJAX-Beispielen](http://msdn.microsoft.com/en-us/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Im folgenden Code wird das <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut auf den `Add`-Vorgang angewandt, um sicherzustellen, dass der Dienst auf HTTP GET-Anforderungen antwortet. Der Einfachheit halber nutzt der Code GET (Sie können eine HTTP GET-Anforderung von jedem Webbrowser aus erstellen). Sie können GET auch verwenden, um Caching zu aktivieren. Bei Fehlen des `WebGetAttribute`-Attributs ist die Standardeinstellung HTTP POST.  
  
```  
[ServiceContract(Namespace = "SimpleAjaxService")]  
public interface ICalculator  
{  
  
    [WebGet]  
    double Add(double n1, double n2);  
    //Other operations omitted…  
}  
```  
  
 Die SVC-Beispieldatei verwendet <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, wodurch dem Dienst ein <xref:System.ServiceModel.Description.WebScriptEndpoint>-Standardendpunkt hinzugefügt wird. Der Endpunkt wird an einer leeren Adresse relativ zur SVC-Datei konfiguriert. Dies bedeutet, dass die Adresse des Diensts http://localhost/ServiceModelSamples/service.svc lautet und keine Suffixe außer dem Vorgangsnamen aufweist.  
  
```  
<%@ServiceHost language="C#" Debug="true" Service="Microsoft.Samples.SimpleAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory" %>  
```  
  
 Der <xref:System.ServiceModel.Description.WebScriptEndpoint> ist so vorkonfiguriert, dass von einer ASP.NET AJAX-Clientseite aus auf den Dienst zugegriffen werden kann. Im folgenden Abschnitt in der Datei Web.config können zusätzliche Konfigurationsänderungen am Endpunkt vorgenommen werden. Wenn keine zusätzlichen Änderungen erforderlich sind, kann der Abschnitt entfernt werden.  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>  
    <webScriptEndpoint>  
      <!-- Use this element to configure the endpoint -->  
      <standardEndpoint name=""  />  
    </webScriptEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 Der <xref:System.ServiceModel.Description.WebScriptEndpoint> legt das Standarddatenformat für den Dienst auf JSON anstelle von XML fest. Um den Dienst aufzurufen, navigieren Sie zu http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200, nachdem Sie die Setup- und Buildanweisungen weiter unten in diesem Thema abgeschlossen haben. Diese Testfunktion wird durch die Verwendung einer HTTP GET-Anforderung aktiviert.  
  
 Die Clientwebseite SimpleAjaxClientPage.aspx enthält ASP.NET-Code zum Aufrufen des Diensts, wenn der Benutzer auf eine der Vorgangsschaltflächen auf der Seite klickt. Das `ScriptManager`-Steuerelement wird verwendet, um dem Dienst durch JavaScript einen Proxy verfügbar zu machen.  
  
```  
<asp:ScriptManager ID="ScriptManager" runat="server">  
    <Services>  
        <asp:ServiceReference Path="service.svc" />  
    </Services>  
</asp:ScriptManager>  
```  
  
 Der lokale Proxy wird instanziiert, und Vorgänge werden mit dem folgenden JavaScript-Code aufgerufen.  
  
```  
// Code for extracting arguments n1 and n2 omitted…  
// Instantiate a service proxy  
var proxy = new SimpleAjaxService.ICalculator();  
// Code for selecting operation omitted…  
proxy.Add(parseFloat(n1), parseFloat(n2), onSuccess, onFail, null);  
```  
  
 Ist der Dienstaufruf erfolgreich, ruft der Code einen `onSuccess`-Handler auf, und das Ergebnis des Vorgangs wird in einem Textfeld angezeigt.  
  
```  
function onSuccess(mathResult){  
     document.getElementById("result").value = mathResult;  
}  
```  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\SimpleAjaxService`  
  
## <a name="see-also"></a>Siehe auch
