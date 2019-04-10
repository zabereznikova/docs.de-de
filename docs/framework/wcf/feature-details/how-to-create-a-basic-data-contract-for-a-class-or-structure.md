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
ms.openlocfilehash: 4e5e6b77cdb13c17557f176a37fbb9e7d42ab667
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59346001"
---
# <a name="how-to-create-a-basic-data-contract-for-a-class-or-structure"></a>Vorgehensweise: Erstellen eines grundlegenden Datenvertrags für eine Klasse oder Struktur
In diesem Thema werden die grundlegenden Schritte zum Erstellen eines Datenvertrags mithilfe einer Klasse oder Struktur beschrieben. Weitere Informationen über Datenverträge und deren Verwendung finden Sie unter [Using Data Contracts](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).  
  
 Ein Lernprogramm, das durch die Schritte zum Erstellen einer grundlegenden Windows Communication Foundation (WCF)-Dienst und Client führt, finden Sie unter den [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md). Eine funktionierende beispielanwendung, die aus einem grundlegenden Dienst und Client besteht, finden Sie unter [Basic Data Contract](../../../../docs/framework/wcf/samples/basic-data-contract.md).  
  
### <a name="to-create-a-basic-data-contract-for-a-class-or-structure"></a>So erstellen Sie einen grundlegenden Datenvertrag für eine Klasse oder Struktur  
  
1. Deklarieren Sie, dass der Typ einen Datenvertrag aufweist, indem Sie das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut auf die Klasse anwenden. Beachten Sie, dass alle öffentlichen Typen, einschließlich der Typen ohne Attribute, serialisierbar sind. Der <xref:System.Runtime.Serialization.DataContractSerializer> leitet einen Datenvertrag ab, wenn das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut nicht vorhanden ist. Weitere Informationen finden Sie unter [serialisierbare Typen](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
2. Definieren Sie die zu serialisierenden Member (Eigenschaften, Felder oder Ereignisse), indem Sie das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut auf die einzelnen Member anwenden. Diese Member werden als Datenmember bezeichnet. Standardmäßig sind alle öffentlichen Typen serialisierbar. Weitere Informationen finden Sie unter [serialisierbare Typen](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
    > [!NOTE]
    >  Sie können das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut auf private Felder anwenden und so bewirken, dass die Daten für andere verfügbar gemacht werden. Stellen Sie sicher, dass der Member keine vertraulichen Daten enthält.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie einen Datenvertrag für den `Person`-Typ erstellen, indem Sie die Attribute <xref:System.Runtime.Serialization.DataContractAttribute> und <xref:System.Runtime.Serialization.DataMemberAttribute> auf die Klassen und ihre Member anwenden.  
  
 [!code-csharp[DataContractAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#2)]
 [!code-vb[DataContractAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [Verwenden von Datenverträgen](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
- [Lernprogramm 'Erste Schritte'](../../../../docs/framework/wcf/getting-started-tutorial.md)
- [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md)
