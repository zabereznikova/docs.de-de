---
title: "Beispiel f&#252;r AJAX-Dienst mit komplexen Typen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# Beispiel f&#252;r AJAX-Dienst mit komplexen Typen
In diesem Beispiel wird veranschaulicht, wie mit [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ein AJAX\-Dienst \(ASP.NET Asynchronous JavaScript and XML\) erstellt werden kann, der Instanzen komplexer Typen erstellt und diese zwischen Dienst und Client als Daten im Datenformat Javascript Object Notation \(JSON\) sendet.Sie können auf einen AJAX\-Dienst zugreifen, indem Sie JavaScript\-Code in einem Webbrowserclient verwenden.Dieses Beispiel basiert auf dem [Einfacher AJAX\-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md)\-Beispiel.  
  
 Die AJAX\-Unterstützung in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ist für die Verwendung mit ASP.NET AJAX über das <xref:System.Web.UI.ScriptManager>\-Steuerelement optimiert.Ein Beispiel für das Verwenden von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mit ASP.NET AJAX finden Sie unter [AJAX Samples](http://msdn.microsoft.com/de-de/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Der Dienst im folgenden Beispiel ist ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst ohne AJAX\-spezifischen Code.Da kein <xref:System.ServiceModel.Web.WebGetAttribute>\-Attribut angewendet wird, wird das standardmäßige HTTP\-Verb \("POST"\) verwendet.Der Dienst hat einen Vorgang, `DoMath`, der einen komplexen Typ namens `MathResult` zurückgibt.Der komplexe Typ ist ein Standarddatenvertragstyp, der ebenfalls keinen AJAX\-spezifischen Code enthält.  
  
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
  
 Erstellen Sie im Dienst mithilfe von <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> einen AJAX\-Endpunkt wie im Beispiel "Einfacher AJAX\-Dienst".  
  
 Die Clientwebseite ComplexTypeClientPage.aspx enthält ASP.NET\-Code und JavaScript\-Code zum Aufrufen des Diensts, wenn der Benutzer auf der Seite auf die Schaltfläche **Berechnung durchführen** klickt.Im zum Aufrufen des Diensts verwendeten Code wird ein JSON\-Text erstellt und mit HTTP\-POST gesendet, ähnlich wie im Beispiel [AJAX\-Dienst mit HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
 Wenn der Dienstaufruf erfolgreich war, können Sie im resultierenden JaveScript\-Objekt auf die einzelnen Datenmember \(`sum`, `difference`, `product` und `quotient`\) zugreifen.  
  
```  
function onSuccess(mathResult){  
     document.getElementById("sum").value = mathResult.sum;  
     document.getElementById("difference").value = mathResult.difference;  
     document.getElementById("product").value = mathResult.product;  
     document.getElementById("quotient").value = mathResult.quotient;  
}  
  
```  
  
### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Erstellen Sie die Projektmappe ComplexTypeAjaxService.sln, wie in [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md) beschrieben.  
  
3.  Navigieren Sie zu http:\/\/localhost\/ServiceModelSamples\/ComplexTypeClientPage.aspx \(öffnen Sie ComplexTypeClientPage.aspx nicht aus dem Projektverzeichnis im Browser\).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`  
  
## Siehe auch  
 [Einfacher AJAX\-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md)