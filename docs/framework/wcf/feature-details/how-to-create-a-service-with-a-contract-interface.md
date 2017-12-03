---
title: 'Vorgehensweise: Erstellen eines Diensts mit einer Vertragsschnittstelle'
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
ms.assetid: 7b6803f6-d6f9-4cc2-9f1b-6f4c920475d5
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2cf3938f96674b07a7938861e217a93babd83101
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-service-with-a-contract-interface"></a>Vorgehensweise: Erstellen eines Diensts mit einer Vertragsschnittstelle
Die bevorzugte Möglichkeit, einen [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Vertrag zu erstellen, ist die Verwendung einer Schnittstelle. Dieser Vertrag gibt die Auflistung und Struktur von Nachrichten an, die erforderlich sind, um auf die Vorgänge zuzugreifen, die der Dienst anbietet. Diese Schnittstelle definiert die Eingabe- und Ausgabetypen durch Anwenden der <xref:System.ServiceModel.ServiceContractAttribute>-Klasse auf die Schnittstelle und der <xref:System.ServiceModel.OperationContractAttribute>-Klasse auf die Methoden, die verfügbar gemacht werden sollen.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]-Dienstverträge, finden Sie unter [Entwerfen von Dienstverträgen](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
### <a name="creating-a-wcf-contract-with-an-interface"></a>Erstellen eines WCF-Vertrags mit einer Schnittstelle  
  
1.  Erstellen Sie mit [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], C# oder einer beliebigen anderen Common Language Runtime-Sprache eine neue Schnittstelle.  
  
2.  Wenden Sie die <xref:System.ServiceModel.ServiceContractAttribute>-Klasse auf die Schnittstelle an.  
  
3.  Definieren Sie die Methoden in der Schnittstelle.  
  
4.  Wenden Sie die <xref:System.ServiceModel.OperationContractAttribute>-Klasse auf jede Methode an, die als Teil des öffentlichen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Vertrags verfügbar gemacht werden muss.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird eine Schnittstelle dargestellt, die einen Dienstvertrag definiert.  
  
 [!code-csharp[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithinterface/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithinterface/vb/source.vb#1)]  
  
 Die Methoden, auf die die <xref:System.ServiceModel.OperationContractAttribute>-Klasse angewendet wird, verwenden standardmäßig ein Anforderung-Antwort-Nachrichtenmuster. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Dieses Nachrichtenmuster finden Sie unter [Vorgehensweise: Erstellen Sie einen Anforderung-Antwort-Vertrag](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md). Sie können auch andere Nachrichtenmuster erstellen und verwenden, indem Sie die Eigenschaften des Attributs festlegen. Weitere Beispiele finden Sie unter [Vorgehensweise: Erstellen eines unidirektionalen Vertrags](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) und [Vorgehensweise: Erstellen eines Duplexvertrags](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>
