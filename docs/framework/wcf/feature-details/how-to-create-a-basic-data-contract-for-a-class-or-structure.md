---
title: 'Vorgehensweise: Erstellen eines grundlegenden Datenvertrags für eine Klasse oder Struktur'
description: In diesem Beispiel erfahren Sie, wie Sie mithilfe des DataContractAttribute-Attributs einen Datenvertrag mithilfe einer Klasse oder Struktur in WCF erstellen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataMemberAttribute
- DataContractAttribute class
- data contracts [WCF], creating for a class or structure
ms.assetid: bc464889-3070-4a2f-91d2-e788a0f686a7
ms.openlocfilehash: a45fde58795947c3e46fa45750ae1a3faddd8849
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247168"
---
# <a name="how-to-create-a-basic-data-contract-for-a-class-or-structure"></a><span data-ttu-id="7f69f-103">Vorgehensweise: Erstellen eines grundlegenden Datenvertrags für eine Klasse oder Struktur</span><span class="sxs-lookup"><span data-stu-id="7f69f-103">How to: Create a Basic Data Contract for a Class or Structure</span></span>
<span data-ttu-id="7f69f-104">In diesem Thema werden die grundlegenden Schritte zum Erstellen eines Datenvertrags mithilfe einer Klasse oder Struktur beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7f69f-104">This topic shows the basic steps to create a data contract using a class or structure.</span></span> <span data-ttu-id="7f69f-105">Weitere Informationen zu Daten Verträgen und ihrer Verwendung finden Sie unter Verwenden von [Daten Verträgen](using-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="7f69f-105">For more information about data contracts and how they are used, see [Using Data Contracts](using-data-contracts.md).</span></span>  
  
 <span data-ttu-id="7f69f-106">Ein Tutorial, in dem die Schritte zum Erstellen eines Basic Windows Communication Foundation (WCF)-Dienstanbieter und-Clients erläutert werden, finden Sie im [Tutorial zu](../getting-started-tutorial.md)den ersten Schritten.</span><span class="sxs-lookup"><span data-stu-id="7f69f-106">For a tutorial that walks through the steps of creating a basic Windows Communication Foundation (WCF) service and client, see the [Getting Started Tutorial](../getting-started-tutorial.md).</span></span> <span data-ttu-id="7f69f-107">Eine funktionierende Beispielanwendung, die aus einem grundlegenden Dienst und Client besteht, finden Sie unter [grundlegender Datenvertrag](../samples/basic-data-contract.md).</span><span class="sxs-lookup"><span data-stu-id="7f69f-107">For a working sample application that consists of a basic service and client, see [Basic Data Contract](../samples/basic-data-contract.md).</span></span>  
  
### <a name="to-create-a-basic-data-contract-for-a-class-or-structure"></a><span data-ttu-id="7f69f-108">So erstellen Sie einen grundlegenden Datenvertrag für eine Klasse oder Struktur</span><span class="sxs-lookup"><span data-stu-id="7f69f-108">To create a basic data contract for a class or structure</span></span>  
  
1. <span data-ttu-id="7f69f-109">Deklarieren Sie, dass der Typ einen Datenvertrag aufweist, indem Sie das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut auf die Klasse anwenden.</span><span class="sxs-lookup"><span data-stu-id="7f69f-109">Declare that the type has a data contract by applying the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the class.</span></span> <span data-ttu-id="7f69f-110">Beachten Sie, dass alle öffentlichen Typen, einschließlich der Typen ohne Attribute, serialisierbar sind.</span><span class="sxs-lookup"><span data-stu-id="7f69f-110">Note that all public types, including those without attributes, are serializable.</span></span> <span data-ttu-id="7f69f-111">Der <xref:System.Runtime.Serialization.DataContractSerializer> leitet einen Datenvertrag ab, wenn das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7f69f-111">The <xref:System.Runtime.Serialization.DataContractSerializer> infers a data contract if the <xref:System.Runtime.Serialization.DataContractAttribute> attribute is absent.</span></span> <span data-ttu-id="7f69f-112">Weitere Informationen finden Sie unter [serialisierbare Typen](serializable-types.md).</span><span class="sxs-lookup"><span data-stu-id="7f69f-112">For more information, see [Serializable Types](serializable-types.md).</span></span>  
  
2. <span data-ttu-id="7f69f-113">Definieren Sie die zu serialisierenden Member (Eigenschaften, Felder oder Ereignisse), indem Sie das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut auf die einzelnen Member anwenden.</span><span class="sxs-lookup"><span data-stu-id="7f69f-113">Define the members (properties, fields, or events) that are serialized by applying the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to each member.</span></span> <span data-ttu-id="7f69f-114">Diese Member werden als Datenmember bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="7f69f-114">These members are called data members.</span></span> <span data-ttu-id="7f69f-115">Standardmäßig sind alle öffentlichen Typen serialisierbar.</span><span class="sxs-lookup"><span data-stu-id="7f69f-115">By default, all public types are serializable.</span></span> <span data-ttu-id="7f69f-116">Weitere Informationen finden Sie unter [serialisierbare Typen](serializable-types.md).</span><span class="sxs-lookup"><span data-stu-id="7f69f-116">For more information, see [Serializable Types](serializable-types.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="7f69f-117">Sie können das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut auf private Felder anwenden und so bewirken, dass die Daten für andere verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="7f69f-117">You can apply the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to private fields, causing the data to be exposed to others.</span></span> <span data-ttu-id="7f69f-118">Stellen Sie sicher, dass der Member keine vertraulichen Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="7f69f-118">Be sure that the member does not contain sensitive data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f69f-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7f69f-119">Example</span></span>  
 <span data-ttu-id="7f69f-120">Das folgende Beispiel zeigt, wie Sie einen Datenvertrag für den `Person`-Typ erstellen, indem Sie die Attribute <xref:System.Runtime.Serialization.DataContractAttribute> und <xref:System.Runtime.Serialization.DataMemberAttribute> auf die Klassen und ihre Member anwenden.</span><span class="sxs-lookup"><span data-stu-id="7f69f-120">The following example shows how to create a data contract for the `Person` type by applying the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes to the class and its members.</span></span>  
  
 [!code-csharp[DataContractAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#2)]
 [!code-vb[DataContractAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="7f69f-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f69f-121">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [<span data-ttu-id="7f69f-122">Verwenden von Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="7f69f-122">Using Data Contracts</span></span>](using-data-contracts.md)
- [<span data-ttu-id="7f69f-123">Tutorial zu den ersten Schritten</span><span class="sxs-lookup"><span data-stu-id="7f69f-123">Getting Started Tutorial</span></span>](../getting-started-tutorial.md)
- [<span data-ttu-id="7f69f-124">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="7f69f-124">Getting Started</span></span>](../samples/getting-started-sample.md)
