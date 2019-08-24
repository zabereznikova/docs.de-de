---
title: 'Vorgehensweise: Erstellen eines Windows Communication Foundation-Vertrags mit einer Klasse'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
ms.openlocfilehash: 2cd757107d9f62ce749d98db1d4968c02a09c5d2
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/23/2019
ms.locfileid: "69988750"
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a>Vorgehensweise: Erstellen eines Windows Communication Foundation-Vertrags mit einer Klasse
Die bevorzugte Methode zum Erstellen eines Windows Communication Foundation (WCF)-Vertrags ist die Verwendung einer-Schnittstelle. Weitere Informationen finden Sie unter [Vorgehensweise: Definieren Sie einen Dienst](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)Vertrag. Eine Alternative besteht darin, eine Klasse zu erstellen und anschließend das <xref:System.ServiceModel.ServiceContractAttribute>-Attribut direkt auf die Klasse anzuwenden und das <xref:System.ServiceModel.OperationContractAttribute>-Attribut auf die einzelnen Methoden in der Klasse, die Teil des Vertrags sind, anzuwenden.  
  
> [!WARNING]
> `[ServiceContract]` und `[ServiceContractAttribute]` dienen dem gleichen Zweck. Dasselbe gilt für `[OperationContract]` und `[OperationContractAttribute]`. In jedem Fall ist der erste Kurzwert für Letzteres.  
  
 Weitere Informationen zu Dienstverträgen finden Sie unter [Entwerfen von Dienstverträgen](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a>Erstellen eines Windows Communication Foundation-Vertrags mit einer Klasse  
  
1. Erstellen Sie eine neue Klasse mit Visual Basic C#, oder einer beliebigen anderen Common Language Runtime Sprache.  
  
2. Wenden Sie die <xref:System.ServiceModel.ServiceContractAttribute>-Klasse auf die Klasse an.  
  
3. Erstellen Sie Methoden in der Klasse.  
  
4. Wenden Sie <xref:System.ServiceModel.OperationContractAttribute> die-Klasse auf jede Methode an, die als Teil des öffentlichen WCF-Vertrags verfügbar gemacht werden muss.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird eine Klasse dargestellt, die einen Dienstvertrag definiert.  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 Die Methoden, auf die die <xref:System.ServiceModel.OperationContractAttribute>-Klasse angewendet wird, verwenden standardmäßig ein Anforderung-Antwort-Nachrichtenmuster. Weitere Informationen zu diesem Nachrichten Muster finden [Sie unter Gewusst wie: Erstellen Sie einen Anforderung-Antwort](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md)-Vertrag. Sie können auch andere Nachrichtenmuster erstellen und verwenden, indem Sie die Eigenschaften des Attributs festlegen. Weitere Beispiele finden Sie unter [Vorgehensweise: Erstellen eines unidirektionalen](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) Vertrags [und Gewusst wie: Erstellen Sie einen Duplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)Vertrag.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
