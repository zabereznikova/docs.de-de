---
title: Einfacher AJAX-Dienst
ms.date: 03/30/2017
ms.assetid: d66d0c91-0109-45a0-a901-f3e4667c2465
ms.openlocfilehash: d8da6469101511b6b5a9ce19a11f1e5e3fe9d83e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524882"
---
# <a name="basic-ajax-service"></a>Einfacher AJAX-Dienst
In diesem Beispiel wird veranschaulicht, wie Windows Communication Foundation (WCF) zu verwenden, um das Erstellen eines einfachen (ASP.NET Asynchronous JavaScript and XML (AJAX)-Diensts (ein Dienst, die Sie mithilfe von JavaScript-Codes über einen Webbrowserclient zugreifen können). Der Dienst nutzt das <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut, um sicherzustellen, dass der Dienst auf HTTP GET-Anforderungen antwortet und für die Verwendung von JSON-Daten (JavaScript Object Notation) für Antworten konfiguriert ist.  
  
 AJAX-Unterstützung in WCF ist optimiert für die Verwendung mit ASP.NET AJAX über das `ScriptManager` Steuerelement. Ein Beispiel der Verwendung von WCF mit ASP.NET AJAX finden Sie unter den [AJAX-Beispielen](https://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Im folgenden Code wird das <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut auf den `Add`-Vorgang angewandt, um sicherzustellen, dass der Dienst auf HTTP GET-Anforderungen antwortet. Der Einfachheit halber nutzt der Code GET (Sie können eine HTTP GET-Anforderung von jedem Webbrowser aus erstellen). Sie können GET auch verwenden, um Caching zu aktivieren. Bei Fehlen des `WebGetAttribute`-Attributs ist die Standardeinstellung HTTP POST.  

```csharp
[ServiceContract(Namespace = "SimpleAjaxService")]
public interface ICalculator
{
    [WebGet]
    double Add(double n1, double n2);
    //Other operations omitted…
}
```

 Die SVC-Beispieldatei verwendet <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, wodurch dem Dienst ein <xref:System.ServiceModel.Description.WebScriptEndpoint>-Standardendpunkt hinzugefügt wird. Der Endpunkt wird an einer leeren Adresse relativ zur SVC-Datei konfiguriert. Dies bedeutet, dass die Adresse des Diensts http://localhost/ServiceModelSamples/service.svc, mit Ausnahme des Vorgangsnamens keine zusätzlichen Suffixe.  

```svc
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
  
 Der <xref:System.ServiceModel.Description.WebScriptEndpoint> legt das Standarddatenformat für den Dienst auf JSON anstelle von XML fest. Um den Dienst aufzurufen, navigieren Sie zu http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 nach dem Ausführen der Reihe nach oben und Buildanweisungen weiter unten in diesem Thema. Diese Testfunktion wird durch die Verwendung einer HTTP GET-Anforderung aktiviert.  
  
 Die Clientwebseite SimpleAjaxClientPage.aspx enthält ASP.NET-Code zum Aufrufen des Diensts, wenn der Benutzer auf eine der Vorgangsschaltflächen auf der Seite klickt. Das `ScriptManager`-Steuerelement wird verwendet, um dem Dienst durch JavaScript einen Proxy verfügbar zu machen.  

```aspx-csharp
<asp:ScriptManager ID="ScriptManager" runat="server">  
    <Services>  
        <asp:ServiceReference Path="service.svc" />  
    </Services>  
</asp:ScriptManager>  
```

 Der lokale Proxy wird instanziiert, und Vorgänge werden mit dem folgenden JavaScript-Code aufgerufen.  

```javascript
// Code for extracting arguments n1 and n2 omitted…  
// Instantiate a service proxy  
var proxy = new SimpleAjaxService.ICalculator();  
// Code for selecting operation omitted…  
proxy.Add(parseFloat(n1), parseFloat(n2), onSuccess, onFail, null);  
```

 Ist der Dienstaufruf erfolgreich, ruft der Code einen `onSuccess`-Handler auf, und das Ergebnis des Vorgangs wird in einem Textfeld angezeigt.  

```javascript
function onSuccess(mathResult){  
     document.getElementById("result").value = mathResult;  
}
```

> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\SimpleAjaxService`  
  
## <a name="see-also"></a>Siehe auch
