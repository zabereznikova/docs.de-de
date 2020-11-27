---
title: Datenmember-Reihenfolge
description: Weitere Informationen zur Reihenfolge der Datenelemente in WCF. Anwendungen müssen möglicherweise die Reihenfolge kennen, in der die Datenmember gesendet oder erwartet werden.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], ordering members
ms.assetid: 0658a47d-b6e5-4ae0-ba72-ababc3c6ff33
ms.openlocfilehash: 1cb63569c1789b1577588caf63fb0a0259e530ff
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262163"
---
# <a name="data-member-order"></a><span data-ttu-id="9c605-104">Datenmember-Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="9c605-104">Data Member Order</span></span>

<span data-ttu-id="9c605-105">Bei einigen Anwendungen ist es hilfreich, die Reihenfolge zu kennen, in der die Daten aus verschiedenen Datenmembern gesendet oder erwartet werden (wie z.&#160;B. die Reihenfolge, in der die Daten im serialisierten XML angezeigt werden).</span><span class="sxs-lookup"><span data-stu-id="9c605-105">In some applications, it is useful to know the order in which data from the various data members is sent or is expected to be received (such as the order in which data appears in the serialized XML).</span></span> <span data-ttu-id="9c605-106">Manchmal kann es auch notwendig sein, diese Reihenfolge zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9c605-106">Sometimes it may be necessary to change this order.</span></span> <span data-ttu-id="9c605-107">In diesem Thema werden die Sortierungsregeln beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9c605-107">This topic explains the ordering rules.</span></span>  
  
## <a name="basic-rules"></a><span data-ttu-id="9c605-108">Grundregeln</span><span class="sxs-lookup"><span data-stu-id="9c605-108">Basic Rules</span></span>  

 <span data-ttu-id="9c605-109">Zu den grundlegenden Regeln für die Sortierung von Daten gehören u.&#160;a.:</span><span class="sxs-lookup"><span data-stu-id="9c605-109">The basic rules for data ordering include:</span></span>  
  
- <span data-ttu-id="9c605-110">Wenn ein Datenvertragstyp Teil einer Vererbungshierarchie ist, stehen die Datenmember der Basistypen immer am Anfang der Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="9c605-110">If a data contract type is a part of an inheritance hierarchy, data members of its base types are always first in the order.</span></span>  
  
- <span data-ttu-id="9c605-111">Danach folgen die Datenmember des aktuellen Typs, für die die <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A>-Eigenschaft des Attributs <xref:System.Runtime.Serialization.DataMemberAttribute> nicht festgelegt ist, in alphabetischer Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="9c605-111">Next in order are the current type’s data members that do not have the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute set, in alphabetical order.</span></span>  
  
- <span data-ttu-id="9c605-112">Dann folgen die Datenmember mit der <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A>-Eigenschaft der <xref:System.Runtime.Serialization.DataMemberAttribute>Attributgruppe.</span><span class="sxs-lookup"><span data-stu-id="9c605-112">Next are any data members that have the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute set.</span></span> <span data-ttu-id="9c605-113">Diese sind zunächst nach dem Wert der `Order`-Eigenschaft geordnet und dann alphabetisch, falls mehr als ein Member eines bestimmten `Order`-Werts vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="9c605-113">These are ordered by the value of the `Order` property first and then alphabetically if there is more than one member of a certain `Order` value.</span></span> <span data-ttu-id="9c605-114">Die Reihenfolgenwerte können übersprungen werden.</span><span class="sxs-lookup"><span data-stu-id="9c605-114">Order values may be skipped.</span></span>  
  
 <span data-ttu-id="9c605-115">Die alphabetische Reihenfolge wird erstellt, indem die <xref:System.String.CompareOrdinal%2A>-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="9c605-115">Alphabetical order is established by calling the <xref:System.String.CompareOrdinal%2A> method.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="9c605-116">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9c605-116">Examples</span></span>  

 <span data-ttu-id="9c605-117">Betrachten Sie folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="9c605-117">Consider the following code.</span></span>  
  
 [!code-csharp[C_DataContractNames#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#4)]
 [!code-vb[C_DataContractNames#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#4)]  
  
 <span data-ttu-id="9c605-118">Das generierte XML sieht ähnlich aus wie das folgende.</span><span class="sxs-lookup"><span data-stu-id="9c605-118">The XML produced is similar to the following.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9c605-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9c605-119">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- [<span data-ttu-id="9c605-120">Datenvertragsäquivalenz</span><span class="sxs-lookup"><span data-stu-id="9c605-120">Data Contract Equivalence</span></span>](data-contract-equivalence.md)
- [<span data-ttu-id="9c605-121">Verwenden von Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="9c605-121">Using Data Contracts</span></span>](using-data-contracts.md)
