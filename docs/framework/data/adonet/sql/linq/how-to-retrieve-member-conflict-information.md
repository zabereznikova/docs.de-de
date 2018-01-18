---
title: 'Gewusst wie: Abrufen von Memberkonfliktinformationen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 7dd6829e-79a5-4480-9023-9e588cb0bf2e
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: fab9111bb14b41244fab3bcd9c2ea0b0f91d72ce
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-retrieve-member-conflict-information"></a><span data-ttu-id="b2dbb-102">Gewusst wie: Abrufen von Memberkonfliktinformationen</span><span class="sxs-lookup"><span data-stu-id="b2dbb-102">How to: Retrieve Member Conflict Information</span></span>
<span data-ttu-id="b2dbb-103">Sie können die <xref:System.Data.Linq.MemberChangeConflict>-Klasse verwenden, um Informationen über einzelne kollidierende Member abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b2dbb-103">You can use the <xref:System.Data.Linq.MemberChangeConflict> class to retrieve information about individual members in conflict.</span></span> <span data-ttu-id="b2dbb-104">In diesem gleichen Kontext können Sie für jeden Member für eine benutzerdefinierte Behandlung des Konflikts sorgen.</span><span class="sxs-lookup"><span data-stu-id="b2dbb-104">In this same context you can provide for custom handling of the conflict for any member.</span></span> <span data-ttu-id="b2dbb-105">Weitere Informationen finden Sie unter [vollständige Parallelität: Übersicht über](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b2dbb-105">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2dbb-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b2dbb-106">Example</span></span>  
 <span data-ttu-id="b2dbb-107">Der folgende Code wechselt durch die <xref:System.Data.Linq.ObjectChangeConflict>-Objekte.</span><span class="sxs-lookup"><span data-stu-id="b2dbb-107">The following code iterates through the <xref:System.Data.Linq.ObjectChangeConflict> objects.</span></span> <span data-ttu-id="b2dbb-108">Für jedes Objekt durchläuft er dann die <xref:System.Data.Linq.MemberChangeConflict>-Objekte.</span><span class="sxs-lookup"><span data-stu-id="b2dbb-108">For each object, it then iterates through the <xref:System.Data.Linq.MemberChangeConflict> objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2dbb-109">Schließen Sie <xref:System.Reflection> ein, um <xref:System.Data.Linq.MemberChangeConflict.Member%2A>-Informationen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b2dbb-109">Include <xref:System.Reflection> in order to provide <xref:System.Data.Linq.MemberChangeConflict.Member%2A> information.</span></span>  
  
 [!code-csharp[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.memberchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.memberchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b2dbb-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2dbb-110">See Also</span></span>  
 [<span data-ttu-id="b2dbb-111">Vorgehensweise: Verwalten von Änderungskonflikten</span><span class="sxs-lookup"><span data-stu-id="b2dbb-111">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
