---
title: "Anforderung-Antwort-Dienste | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Verträge [WCF], Anforderung-Antwort-Dienste"
  - "Anforderung-Antwort-Verträge [WCF]"
  - "WCF [WCF], Anforderung-Antwort-Dienste"
  - "Windows Communication Foundation [WCF], Anforderung-Antwort-Dienste"
ms.assetid: 2fa710f1-47f4-4598-b063-3ab3bd22ebba
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Anforderung-Antwort-Dienste
Anforderung\-Antwort\-Dienste sind der Standardtyp des Vorgangsvertrags in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Clients machen Aufrufe zu Dienstvorgängen und warten auf eine Antwort vom Dienst.Sie können Aufrufe zu einem Dienstvorgang entweder synchron vornehmen, wobei der Client sperrt, bis er eine Antwort vom Dienst oder die Aufrufzeiten erhält, oder asynchron, wobei der Client einen Aufruf zum Dienstvorgang startet, seine Arbeit weiter fortsetzt und die Antwort vom Dienst auf einem anderen Thread erhält.  
  
 Um einen Anforderung\-Antwort\-Dienstvertrag zu erstellen, definieren Sie Ihren Dienstvertrag, und wenden Sie die <xref:System.ServiceModel.OperationContractAttribute>\-Klasse, wie im folgenden Beispielcode gezeigt, auf alle Vorgänge an.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IRequestReplyCalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
}  
  
```  
  
 Sie müssen die <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>\-Eigenschaft nicht auf `false` festlegen, da dies das Standardverhalten ist.  
  
## Siehe auch  
 [Unidirektionale Dienste](../../../../docs/framework/wcf/feature-details/one-way-services.md)   
 [Duplexdienste](../../../../docs/framework/wcf/feature-details/duplex-services.md)