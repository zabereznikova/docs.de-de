---
title: "Beispiel für AJAX-Dienst mit komplexen Typen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5af5840dde2cb72ee6b39b75ece3606e3c58b32b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ajax-service-using-complex-types-sample"></a>Beispiel für AJAX-Dienst mit komplexen Typen
In diesem Beispiel wird veranschaulicht, wie mit [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ein AJAX-Dienst (ASP.NET Asynchronous JavaScript and XML) erstellt werden kann, der Instanzen komplexer Typen erstellt und diese zwischen Dienst und Client als Daten im Datenformat Javascript Object Notation (JSON) sendet. Sie können auf einen AJAX-Dienst zugreifen, indem Sie JavaScript-Code in einem Webbrowserclient verwenden. Dieses Beispiel baut auf den [einfacher AJAX-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md) Beispiel.  
  
 Die AJAX-Unterstützung in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ist für die Verwendung mit ASP.NET AJAX über das <xref:System.Web.UI.ScriptManager>-Steuerelement optimiert. Ein Beispiel der Verwendung von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mit ASP.NET AJAX finden Sie unter der [AJAX-Beispielen](http://msdn.microsoft.com/en-us/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Der Dienst im folgenden Beispiel ist ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst ohne AJAX-spezifischen Code. Da kein <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut angewendet wird, wird das standardmäßige HTTP-Verb ("POST") verwendet. Der Dienst hat einen Vorgang, `DoMath`, der einen komplexen Typ namens `MathResult` zurückgibt. Der komplexe Typ ist ein Standarddatenvertragstyp, der ebenfalls keinen AJAX-spezifischen Code enthält.  
  
```  
[DataContract]  
    public class MathResult  
    {  
        [DataMember]  
        public double sum;  
        [DataMember]  
        public double difference;  
        [DataMember]  
        public double product;  
        [DataMember]  
        public double quotient;  
    }  
```  
  
 Erstellen Sie im Dienst mithilfe von <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> einen AJAX-Endpunkt wie im Beispiel "Einfacher AJAX-Dienst".  
  
 Der Client clientwebseite ComplexTypeClientPage.aspx enthält ASP.NET-Code und JavaScript-Code zum Aufrufen des Diensts, klickt der Benutzer die **Berechnung durchführen** Schaltfläche auf der Seite. Der Code zum Aufrufen des Diensts erstellt einen JSON-Text und sendet diese mithilfe von HTTP POST, ähnlich wie die [AJAX-Dienst mithilfe von HTTP-POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) Beispiel.  
  
 Wenn der Dienstaufruf erfolgreich war, können Sie im resultierenden JaveScript-Objekt auf die einzelnen Datenmember (`sum`, `difference`, `product` und `quotient`) zugreifen.  
  
```  
function onSuccess(mathResult){  
     document.getElementById("sum").value = mathResult.sum;  
     document.getElementById("difference").value = mathResult.difference;  
     document.getElementById("product").value = mathResult.product;  
     document.getElementById("quotient").value = mathResult.quotient;  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Erstellen Sie die Projektmappe ComplexTypeAjaxService.sln, wie in beschrieben [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Navigieren Sie zu http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx (öffnen Sie ComplexTypeClientPage.aspx nicht aus dem Projektverzeichnis im Browser).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`  
  
## <a name="see-also"></a>Siehe auch  
 [Einfacher AJAX-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
