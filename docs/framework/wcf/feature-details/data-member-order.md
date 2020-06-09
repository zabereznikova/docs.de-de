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
# <a name="data-member-order"></a><span data-ttu-id="da2c9-102">Datenmember-Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="da2c9-102">Data Member Order</span></span>
<span data-ttu-id="da2c9-103">Bei einigen Anwendungen ist es hilfreich, die Reihenfolge zu kennen, in der die Daten aus verschiedenen Datenmembern gesendet oder erwartet werden (wie z.&#160;B. die Reihenfolge, in der die Daten im serialisierten XML angezeigt werden).</span><span class="sxs-lookup"><span data-stu-id="da2c9-103">In some applications, it is useful to know the order in which data from the various data members is sent or is expected to be received (such as the order in which data appears in the serialized XML).</span></span> <span data-ttu-id="da2c9-104">Manchmal kann es auch notwendig sein, diese Reihenfolge zu ändern.</span><span class="sxs-lookup"><span data-stu-id="da2c9-104">Sometimes it may be necessary to change this order.</span></span> <span data-ttu-id="da2c9-105">In diesem Thema werden die Sortierungsregeln beschrieben.</span><span class="sxs-lookup"><span data-stu-id="da2c9-105">This topic explains the ordering rules.</span></span>  
  
## <a name="basic-rules"></a><span data-ttu-id="da2c9-106">Grundregeln</span><span class="sxs-lookup"><span data-stu-id="da2c9-106">Basic Rules</span></span>  
 <span data-ttu-id="da2c9-107">Zu den grundlegenden Regeln für die Sortierung von Daten gehören u.&#160;a.:</span><span class="sxs-lookup"><span data-stu-id="da2c9-107">The basic rules for data ordering include:</span></span>  
  
- <span data-ttu-id="da2c9-108">Wenn ein Datenvertragstyp Teil einer Vererbungshierarchie ist, stehen die Datenmember der Basistypen immer am Anfang der Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="da2c9-108">If a data contract type is a part of an inheritance hierarchy, data members of its base types are always first in the order.</span></span>  
  
- <span data-ttu-id="da2c9-109">Danach folgen die Datenmember des aktuellen Typs, für die die <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A>-Eigenschaft des Attributs <xref:System.Runtime.Serialization.DataMemberAttribute> nicht festgelegt ist, in alphabetischer Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="da2c9-109">Next in order are the current type’s data members that do not have the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute set, in alphabetical order.</span></span>  
  
- <span data-ttu-id="da2c9-110">Dann folgen die Datenmember mit der <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A>-Eigenschaft der <xref:System.Runtime.Serialization.DataMemberAttribute>Attributgruppe.</span><span class="sxs-lookup"><span data-stu-id="da2c9-110">Next are any data members that have the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute set.</span></span> <span data-ttu-id="da2c9-111">Diese sind zunächst nach dem Wert der `Order`-Eigenschaft geordnet und dann alphabetisch, falls mehr als ein Member eines bestimmten `Order`-Werts vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="da2c9-111">These are ordered by the value of the `Order` property first and then alphabetically if there is more than one member of a certain `Order` value.</span></span> <span data-ttu-id="da2c9-112">Die Reihenfolgenwerte können übersprungen werden.</span><span class="sxs-lookup"><span data-stu-id="da2c9-112">Order values may be skipped.</span></span>  
  
 <span data-ttu-id="da2c9-113">Die alphabetische Reihenfolge wird erstellt, indem die <xref:System.String.CompareOrdinal%2A>-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="da2c9-113">Alphabetical order is established by calling the <xref:System.String.CompareOrdinal%2A> method.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="da2c9-114">Beispiele</span><span class="sxs-lookup"><span data-stu-id="da2c9-114">Examples</span></span>  
 <span data-ttu-id="da2c9-115">Betrachten Sie folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="da2c9-115">Consider the following code.</span></span>  
  
 [!code-csharp[C_DataContractNames#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#4)]
 [!code-vb[C_DataContractNames#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#4)]  
  
 <span data-ttu-id="da2c9-116">Das generierte XML sieht ähnlich aus wie das folgende.</span><span class="sxs-lookup"><span data-stu-id="da2c9-116">The XML produced is similar to the following.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="da2c9-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="da2c9-117">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- [<span data-ttu-id="da2c9-118">Datenvertragsäquivalenz</span><span class="sxs-lookup"><span data-stu-id="da2c9-118">Data Contract Equivalence</span></span>](data-contract-equivalence.md)
- [<span data-ttu-id="da2c9-119">Verwenden von Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="da2c9-119">Using Data Contracts</span></span>](using-data-contracts.md)
