---
title: 'Vorgehensweise: Erstellen eines grundlegenden Datenvertrags für eine Klasse oder Struktur'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataMemberAttribute
- DataContractAttribute class
- data contracts [WCF], creating for a class or structure
ms.assetid: bc464889-3070-4a2f-91d2-e788a0f686a7
caps.latest.revision: 25
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 43fa318d2910fcd8b1d9ce75fc02d75bb39d4079
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-create-a-basic-data-contract-for-a-class-or-structure"></a><span data-ttu-id="a253b-102">Vorgehensweise: Erstellen eines grundlegenden Datenvertrags für eine Klasse oder Struktur</span><span class="sxs-lookup"><span data-stu-id="a253b-102">How to: Create a Basic Data Contract for a Class or Structure</span></span>
<span data-ttu-id="a253b-103">In diesem Thema werden die grundlegenden Schritte zum Erstellen eines Datenvertrags mithilfe einer Klasse oder Struktur beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a253b-103">This topic shows the basic steps to create a data contract using a class or structure.</span></span> <span data-ttu-id="a253b-104">Weitere Informationen über Datenverträge und deren Verwendung finden Sie unter [mithilfe von Datenverträgen](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="a253b-104">For more information about data contracts and how they are used, see [Using Data Contracts](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).</span></span>  
  
 <span data-ttu-id="a253b-105">Ein Lernprogramm, das durch die Schritte zum Erstellen einer grundlegenden führt [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] -Dienst und Client finden Sie unter der [Lernprogramm für erste Schritte](../../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="a253b-105">For a tutorial that walks through the steps of creating a basic [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service and client, see the [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span> <span data-ttu-id="a253b-106">Eine funktionierende beispielanwendung, aus denen ein grundlegender Dienst und Client besteht, finden Sie unter [grundlegenden Datenvertrag](../../../../docs/framework/wcf/samples/basic-data-contract.md).</span><span class="sxs-lookup"><span data-stu-id="a253b-106">For a working sample application that consists of a basic service and client, see [Basic Data Contract](../../../../docs/framework/wcf/samples/basic-data-contract.md).</span></span>  
  
### <a name="to-create-a-basic-data-contract-for-a-class-or-structure"></a><span data-ttu-id="a253b-107">So erstellen Sie einen grundlegenden Datenvertrag für eine Klasse oder Struktur</span><span class="sxs-lookup"><span data-stu-id="a253b-107">To create a basic data contract for a class or structure</span></span>  
  
1.  <span data-ttu-id="a253b-108">Deklarieren Sie, dass der Typ einen Datenvertrag aufweist, indem Sie das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut auf die Klasse anwenden.</span><span class="sxs-lookup"><span data-stu-id="a253b-108">Declare that the type has a data contract by applying the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the class.</span></span> <span data-ttu-id="a253b-109">Beachten Sie, dass alle öffentlichen Typen, einschließlich der Typen ohne Attribute, serialisierbar sind.</span><span class="sxs-lookup"><span data-stu-id="a253b-109">Note that all public types, including those without attributes, are serializable.</span></span> <span data-ttu-id="a253b-110">Der <xref:System.Runtime.Serialization.DataContractSerializer> leitet einen Datenvertrag ab, wenn das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a253b-110">The <xref:System.Runtime.Serialization.DataContractSerializer> infers a data contract if the <xref:System.Runtime.Serialization.DataContractAttribute> attribute is absent.</span></span> <span data-ttu-id="a253b-111">Weitere Informationen finden Sie unter [serialisierbaren Typen](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span><span class="sxs-lookup"><span data-stu-id="a253b-111">For more information, see [Serializable Types](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span></span>  
  
2.  <span data-ttu-id="a253b-112">Definieren Sie die zu serialisierenden Member (Eigenschaften, Felder oder Ereignisse), indem Sie das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut auf die einzelnen Member anwenden.</span><span class="sxs-lookup"><span data-stu-id="a253b-112">Define the members (properties, fields, or events) that are serialized by applying the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to each member.</span></span> <span data-ttu-id="a253b-113">Diese Member werden als Datenmember bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a253b-113">These members are called data members.</span></span> <span data-ttu-id="a253b-114">Standardmäßig sind alle öffentlichen Typen serialisierbar.</span><span class="sxs-lookup"><span data-stu-id="a253b-114">By default, all public types are serializable.</span></span> <span data-ttu-id="a253b-115">Weitere Informationen finden Sie unter [serialisierbaren Typen](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span><span class="sxs-lookup"><span data-stu-id="a253b-115">For more information, see [Serializable Types](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a253b-116">Sie können das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut auf private Felder anwenden und so bewirken, dass die Daten für andere verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="a253b-116">You can apply the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to private fields, causing the data to be exposed to others.</span></span> <span data-ttu-id="a253b-117">Stellen Sie sicher, dass der Member keine vertraulichen Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="a253b-117">Be sure that the member does not contain sensitive data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a253b-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a253b-118">Example</span></span>  
 <span data-ttu-id="a253b-119">Das folgende Beispiel zeigt, wie Sie einen Datenvertrag für den `Person`-Typ erstellen, indem Sie die Attribute <xref:System.Runtime.Serialization.DataContractAttribute> und <xref:System.Runtime.Serialization.DataMemberAttribute> auf die Klassen und ihre Member anwenden.</span><span class="sxs-lookup"><span data-stu-id="a253b-119">The following example shows how to create a data contract for the `Person` type by applying the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes to the class and its members.</span></span>  
  
 [!code-csharp[DataContractAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#2)]
 [!code-vb[DataContractAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="a253b-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a253b-120">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 [<span data-ttu-id="a253b-121">Verwenden von Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="a253b-121">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [<span data-ttu-id="a253b-122">Tutorial mit ersten Schritten</span><span class="sxs-lookup"><span data-stu-id="a253b-122">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)  
 [<span data-ttu-id="a253b-123">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="a253b-123">Getting Started</span></span>](../../../../docs/framework/wcf/samples/getting-started-sample.md)
