---
title: Anforderung-Antwort-Dienste
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation [WCF], request-reply services
- contracts [WCF], request-reply services
- WCF [WCF], request-reply services
- request-reply contracts [WCF]
ms.assetid: 2fa710f1-47f4-4598-b063-3ab3bd22ebba
ms.openlocfilehash: 10b82e859369dae4f57e0e13782e2375a304ab02
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295521"
---
# <a name="request-reply-services"></a>Anforderung-Antwort-Dienste

Anforderung-Antwort-Dienste sind der Standardtyp des Vorgangs Vertrags in Windows Communication Foundation (WCF). Clients machen Aufrufe zu Dienstvorgängen und warten auf eine Antwort vom Dienst. Sie können Aufrufe zu einem Dienstvorgang entweder synchron vornehmen, wobei der Client sperrt, bis er eine Antwort vom Dienst oder die Aufrufzeiten erhält, oder asynchron, wobei der Client einen Aufruf zum Dienstvorgang startet, seine Arbeit weiter fortsetzt und die Antwort vom Dienst auf einem anderen Thread erhält.  
  
 Um einen Anforderung-Antwort-Dienstvertrag zu erstellen, definieren Sie Ihren Dienstvertrag, und wenden Sie die <xref:System.ServiceModel.OperationContractAttribute>-Klasse, wie im folgenden Beispielcode gezeigt, auf alle Vorgänge an.  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IRequestReplyCalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
}  
```  
  
 Sie müssen die <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>-Eigenschaft nicht auf `false` festlegen, da dies das Standardverhalten ist.  
  
## <a name="see-also"></a>Weitere Informationen

- [Unidirektionale Dienste](one-way-services.md)
- [Duplexdienste](duplex-services.md)
