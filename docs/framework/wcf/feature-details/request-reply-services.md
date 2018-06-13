---
title: Anforderung-Antwort-Dienste
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation [WCF], request-reply services
- contracts [WCF], request-reply services
- WCF [WCF], request-reply services
- request-reply contracts [WCF]
ms.assetid: 2fa710f1-47f4-4598-b063-3ab3bd22ebba
ms.openlocfilehash: 8fe1343a4b3590622becf71f1167f4b19dbc67af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33490944"
---
# <a name="request-reply-services"></a>Anforderung-Antwort-Dienste
Anforderung-Antwort-Dienste sind der Standardtyp des vorgangsvertrags in Windows Communication Foundation (WCF). Clients machen Aufrufe zu Dienstvorgängen und warten auf eine Antwort vom Dienst. Sie können Aufrufe zu einem Dienstvorgang entweder synchron vornehmen, wobei der Client sperrt, bis er eine Antwort vom Dienst oder die Aufrufzeiten erhält, oder asynchron, wobei der Client einen Aufruf zum Dienstvorgang startet, seine Arbeit weiter fortsetzt und die Antwort vom Dienst auf einem anderen Thread erhält.  
  
 Um einen Anforderung-Antwort-Dienstvertrag zu erstellen, definieren Sie Ihren Dienstvertrag, und wenden Sie die <xref:System.ServiceModel.OperationContractAttribute>-Klasse, wie im folgenden Beispielcode gezeigt, auf alle Vorgänge an.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IRequestReplyCalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
}  
```  
  
 Sie müssen die <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>-Eigenschaft nicht auf `false` festlegen, da dies das Standardverhalten ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Unidirektionale Dienste](../../../../docs/framework/wcf/feature-details/one-way-services.md)  
 [Duplexdienste](../../../../docs/framework/wcf/feature-details/duplex-services.md)
