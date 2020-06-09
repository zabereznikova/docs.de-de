---
title: 'Vorgehensweise: Erstellen eines Windows Communication Foundation-Vertrags mit einer Klasse'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
ms.openlocfilehash: 0be2400ef3da5f0bbc218032ecd69af23f82cabd
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597136"
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a>Vorgehensweise: Erstellen eines Windows Communication Foundation-Vertrags mit einer Klasse
Die bevorzugte Methode zum Erstellen eines Windows Communication Foundation (WCF)-Vertrags ist die Verwendung einer-Schnittstelle. Weitere Informationen finden Sie unter Vorgehens [Weise: Definieren eines Dienstvertrags](../how-to-define-a-wcf-service-contract.md). Eine Alternative besteht darin, eine Klasse zu erstellen und anschließend das <xref:System.ServiceModel.ServiceContractAttribute>-Attribut direkt auf die Klasse anzuwenden und das <xref:System.ServiceModel.OperationContractAttribute>-Attribut auf die einzelnen Methoden in der Klasse, die Teil des Vertrags sind, anzuwenden.  
  
> [!WARNING]
> `[ServiceContract]` und `[ServiceContractAttribute]` dienen dem gleichen Zweck. Dasselbe gilt für `[OperationContract]` und `[OperationContractAttribute]` . In jedem Fall ist der erste Kurzwert für Letzteres.  
  
 Weitere Informationen zu Dienstverträgen finden Sie unter [Entwerfen von Dienstverträgen](../designing-service-contracts.md).  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a>Erstellen eines Windows Communication Foundation-Vertrags mit einer Klasse  
  
1. Erstellen Sie eine neue Klasse mit Visual Basic, c# oder einer beliebigen anderen Common Language Runtime Sprache.  
  
2. Wenden Sie die <xref:System.ServiceModel.ServiceContractAttribute>-Klasse auf die Klasse an.  
  
3. Erstellen Sie Methoden in der Klasse.  
  
4. Wenden Sie die- <xref:System.ServiceModel.OperationContractAttribute> Klasse auf jede Methode an, die als Teil des öffentlichen WCF-Vertrags verfügbar gemacht werden muss.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird eine Klasse dargestellt, die einen Dienstvertrag definiert.  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 Die Methoden, auf die die <xref:System.ServiceModel.OperationContractAttribute>-Klasse angewendet wird, verwenden standardmäßig ein Anforderung-Antwort-Nachrichtenmuster. Weitere Informationen zu diesem Nachrichten Muster finden Sie unter Gewusst [wie: Erstellen eines Anforderung-Antwort-Vertrags](how-to-create-a-request-reply-contract.md). Sie können auch andere Nachrichtenmuster erstellen und verwenden, indem Sie die Eigenschaften des Attributs festlegen. Weitere Beispiele finden Sie unter Gewusst [wie: Erstellen](how-to-create-a-one-way-contract.md) eines unidirektionalen Vertrags und Gewusst [wie: Erstellen eines Duplex Vertrags](how-to-create-a-duplex-contract.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
