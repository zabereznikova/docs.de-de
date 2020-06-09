---
title: Datenmember-Reihenfolge
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], ordering members
ms.assetid: 0658a47d-b6e5-4ae0-ba72-ababc3c6ff33
ms.openlocfilehash: 717d7014f4c4a56249ead0c839cf05f4f83a6f5f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593463"
---
# <a name="data-member-order"></a>Datenmember-Reihenfolge
Bei einigen Anwendungen ist es hilfreich, die Reihenfolge zu kennen, in der die Daten aus verschiedenen Datenmembern gesendet oder erwartet werden (wie z.&#160;B. die Reihenfolge, in der die Daten im serialisierten XML angezeigt werden). Manchmal kann es auch notwendig sein, diese Reihenfolge zu ändern. In diesem Thema werden die Sortierungsregeln beschrieben.  
  
## <a name="basic-rules"></a>Grundregeln  
 Zu den grundlegenden Regeln für die Sortierung von Daten gehören u.&#160;a.:  
  
- Wenn ein Datenvertragstyp Teil einer Vererbungshierarchie ist, stehen die Datenmember der Basistypen immer am Anfang der Reihenfolge.  
  
- Danach folgen die Datenmember des aktuellen Typs, für die die <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A>-Eigenschaft des Attributs <xref:System.Runtime.Serialization.DataMemberAttribute> nicht festgelegt ist, in alphabetischer Reihenfolge.  
  
- Dann folgen die Datenmember mit der <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A>-Eigenschaft der <xref:System.Runtime.Serialization.DataMemberAttribute>Attributgruppe. Diese sind zunächst nach dem Wert der `Order`-Eigenschaft geordnet und dann alphabetisch, falls mehr als ein Member eines bestimmten `Order`-Werts vorhanden ist. Die Reihenfolgenwerte können übersprungen werden.  
  
 Die alphabetische Reihenfolge wird erstellt, indem die <xref:System.String.CompareOrdinal%2A>-Methode aufgerufen wird.  
  
## <a name="examples"></a>Beispiele  
 Betrachten Sie folgenden Code.  
  
 [!code-csharp[C_DataContractNames#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#4)]
 [!code-vb[C_DataContractNames#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#4)]  
  
 Das generierte XML sieht ähnlich aus wie das folgende.  
  
```xml  
<DerivedType>  
    <!-- Zebra is a base data member, and appears first. -->  
    <zebra/>
  
    <!-- Cat has no Order, appears alphabetically first. -->  
    <cat/>  
  
   <!-- Dog has no Order, appears alphabetically last. -->  
    <dog/>
  
    <!-- Bird is the member with the smallest Order value -->  
    <bird/>  
  
    <!-- Albatross has the next Order value, alphabetically first. -->  
    <albatross/>  
  
    <!-- Parrot, with the next Order value, alphabetically last. -->  
     <parrot/>  
  
    <!-- Antelope is the member with the highest Order value. Note that   
    Order=2 is skipped -->  
     <antelope/>
</DerivedType>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.Serialization.DataContractAttribute>
- [Datenvertragsäquivalenz](data-contract-equivalence.md)
- [Verwenden von Datenverträgen](using-data-contracts.md)
