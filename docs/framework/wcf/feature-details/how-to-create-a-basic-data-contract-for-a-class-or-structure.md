---
title: 'Vorgehensweise: Erstellen eines grundlegenden Datenvertrags für eine Klasse oder Struktur'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataMemberAttribute
- DataContractAttribute class
- data contracts [WCF], creating for a class or structure
ms.assetid: bc464889-3070-4a2f-91d2-e788a0f686a7
ms.openlocfilehash: 0fd7bbea4d6e8d315566aa798ed89a0fd2657f58
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599034"
---
# <a name="how-to-create-a-basic-data-contract-for-a-class-or-structure"></a>Vorgehensweise: Erstellen eines grundlegenden Datenvertrags für eine Klasse oder Struktur
In diesem Thema werden die grundlegenden Schritte zum Erstellen eines Datenvertrags mithilfe einer Klasse oder Struktur beschrieben. Weitere Informationen zu Daten Verträgen und ihrer Verwendung finden Sie unter Verwenden von [Daten Verträgen](using-data-contracts.md).  
  
 Ein Tutorial, in dem die Schritte zum Erstellen eines Basic Windows Communication Foundation (WCF)-Dienstanbieter und-Clients erläutert werden, finden Sie im [Tutorial zu](../getting-started-tutorial.md)den ersten Schritten. Eine funktionierende Beispielanwendung, die aus einem grundlegenden Dienst und Client besteht, finden Sie unter [grundlegender Datenvertrag](../samples/basic-data-contract.md).  
  
### <a name="to-create-a-basic-data-contract-for-a-class-or-structure"></a>So erstellen Sie einen grundlegenden Datenvertrag für eine Klasse oder Struktur  
  
1. Deklarieren Sie, dass der Typ einen Datenvertrag aufweist, indem Sie das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut auf die Klasse anwenden. Beachten Sie, dass alle öffentlichen Typen, einschließlich der Typen ohne Attribute, serialisierbar sind. Der <xref:System.Runtime.Serialization.DataContractSerializer> leitet einen Datenvertrag ab, wenn das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut nicht vorhanden ist. Weitere Informationen finden Sie unter [serialisierbare Typen](serializable-types.md).  
  
2. Definieren Sie die zu serialisierenden Member (Eigenschaften, Felder oder Ereignisse), indem Sie das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut auf die einzelnen Member anwenden. Diese Member werden als Datenmember bezeichnet. Standardmäßig sind alle öffentlichen Typen serialisierbar. Weitere Informationen finden Sie unter [serialisierbare Typen](serializable-types.md).  
  
    > [!NOTE]
    > Sie können das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut auf private Felder anwenden und so bewirken, dass die Daten für andere verfügbar gemacht werden. Stellen Sie sicher, dass der Member keine vertraulichen Daten enthält.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie einen Datenvertrag für den `Person`-Typ erstellen, indem Sie die Attribute <xref:System.Runtime.Serialization.DataContractAttribute> und <xref:System.Runtime.Serialization.DataMemberAttribute> auf die Klassen und ihre Member anwenden.  
  
 [!code-csharp[DataContractAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#2)]
 [!code-vb[DataContractAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [Verwenden von Datenverträgen](using-data-contracts.md)
- [Tutorial zu den ersten Schritten](../getting-started-tutorial.md)
- [Erste Schritte](../samples/getting-started-sample.md)
