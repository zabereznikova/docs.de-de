---
title: 'Vorgehensweise: Erstellen eines Windows Communication Foundation-Vertrags mit einer Klasse'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cafdda20332bb6f690214a9a9d9c9b6eaa34e911
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a>Vorgehensweise: Erstellen eines Windows Communication Foundation-Vertrags mit einer Klasse
Die bevorzugte Möglichkeit, einen [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Vertrag zu erstellen, besteht in der Verwendung einer Schnittstelle. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Wie: Definieren eines Dienstvertrags](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md). Eine Alternative besteht darin, eine Klasse zu erstellen und anschließend das <xref:System.ServiceModel.ServiceContractAttribute>-Attribut direkt auf die Klasse anzuwenden und das <xref:System.ServiceModel.OperationContractAttribute>-Attribut auf die einzelnen Methoden in der Klasse, die Teil des Vertrags sind, anzuwenden.  
  
> [!WARNING]
>  `[ServiceContract]` und `[ServiceContractAttribute]` dienen dem gleichen Zweck. Dasselbe gilt für `[OperationContract]` und `[OperationContractAttribute]`. Dabei ist jeweils das Erstere die Kurznotation für das Letztere.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]-Dienstverträge, finden Sie unter [Entwerfen von Dienstverträgen](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a>Erstellen eines Windows Communication Foundation-Vertrags mit einer Klasse  
  
1.  Erstellen Sie mit [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], C# oder einer beliebigen anderen Common Language Runtime-Sprache eine neue Klasse.  
  
2.  Wenden Sie die <xref:System.ServiceModel.ServiceContractAttribute>-Klasse auf die Klasse an.  
  
3.  Erstellen Sie Methoden in der Klasse.  
  
4.  Wenden Sie die <xref:System.ServiceModel.OperationContractAttribute>-Klasse auf jede Methode an, die als Teil des öffentlichen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Vertrags verfügbar gemacht werden muss.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird eine Klasse dargestellt, die einen Dienstvertrag definiert.  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 Die Methoden, auf die die <xref:System.ServiceModel.OperationContractAttribute>-Klasse angewendet wird, verwenden standardmäßig ein Anforderung-Antwort-Nachrichtenmuster. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Dieses Nachrichtenmuster finden Sie unter [Vorgehensweise: Erstellen Sie einen Anforderung-Antwort-Vertrag](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md). Sie können auch andere Nachrichtenmuster erstellen und verwenden, indem Sie die Eigenschaften des Attributs festlegen. Weitere Beispiele finden Sie unter [Vorgehensweise: Erstellen eines unidirektionalen Vertrags](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) und [Vorgehensweise: Erstellen eines Duplexvertrags](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>
