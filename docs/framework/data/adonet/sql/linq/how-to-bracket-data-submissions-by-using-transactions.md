---
title: 'Vorgehensweise: Einklammern von Datenübergaben mithilfe von Transaktionen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: 2cbb50cc8762780849c337b597bbb36631c6ac1b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584531"
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a><span data-ttu-id="63d94-102">Vorgehensweise: Einklammern von Datenübergaben mithilfe von Transaktionen</span><span class="sxs-lookup"><span data-stu-id="63d94-102">How to: Bracket Data Submissions by Using Transactions</span></span>
<span data-ttu-id="63d94-103">Sie können <xref:System.Transactions.TransactionScope> verwenden, um die Übergaben zur Datenbank einzuklammern.</span><span class="sxs-lookup"><span data-stu-id="63d94-103">You can use <xref:System.Transactions.TransactionScope> to bracket your submissions to the database.</span></span> <span data-ttu-id="63d94-104">Weitere Informationen finden Sie unter [Transaktionsunterstützung](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md).</span><span class="sxs-lookup"><span data-stu-id="63d94-104">For more information, see [Transaction Support](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="63d94-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="63d94-105">Example</span></span>  
 <span data-ttu-id="63d94-106">Im folgenden Code wird die Datenbankübergabe in einem <xref:System.Transactions.TransactionScope> eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="63d94-106">The following code encloses the database submission in a <xref:System.Transactions.TransactionScope>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="63d94-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63d94-107">See also</span></span>
- [<span data-ttu-id="63d94-108">Downloading Sample Databases (Herunterladen von Beispieldatenbanken)</span><span class="sxs-lookup"><span data-stu-id="63d94-108">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [<span data-ttu-id="63d94-109">Vornehmen und Übergeben von Datenänderungen</span><span class="sxs-lookup"><span data-stu-id="63d94-109">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
- [<span data-ttu-id="63d94-110">Transaktionsunterstützung</span><span class="sxs-lookup"><span data-stu-id="63d94-110">Transaction Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)
