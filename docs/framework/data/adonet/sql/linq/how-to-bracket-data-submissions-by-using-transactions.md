---
title: 'Vorgehensweise: Einklammern von Datenübergaben mithilfe von Transaktionen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: 4d3efedbf15be55fa7a9ab235f881f1c97758953
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161359"
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a><span data-ttu-id="33b52-102">Vorgehensweise: Einklammern von Datenübergaben mithilfe von Transaktionen</span><span class="sxs-lookup"><span data-stu-id="33b52-102">How to: Bracket Data Submissions by Using Transactions</span></span>

<span data-ttu-id="33b52-103">Sie können <xref:System.Transactions.TransactionScope> verwenden, um die Übergaben zur Datenbank einzuklammern.</span><span class="sxs-lookup"><span data-stu-id="33b52-103">You can use <xref:System.Transactions.TransactionScope> to bracket your submissions to the database.</span></span> <span data-ttu-id="33b52-104">Weitere Informationen finden Sie [unter Transaktionsunterstützung](transaction-support.md).</span><span class="sxs-lookup"><span data-stu-id="33b52-104">For more information, see [Transaction Support](transaction-support.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="33b52-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="33b52-105">Example</span></span>  

 <span data-ttu-id="33b52-106">Im folgenden Code wird die Datenbankübergabe in einem <xref:System.Transactions.TransactionScope> eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="33b52-106">The following code encloses the database submission in a <xref:System.Transactions.TransactionScope>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="33b52-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="33b52-107">See also</span></span>

- [<span data-ttu-id="33b52-108">Herunterladen von Beispieldatenbanken</span><span class="sxs-lookup"><span data-stu-id="33b52-108">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="33b52-109">Vornehmen und Übergeben von Datenänderungen</span><span class="sxs-lookup"><span data-stu-id="33b52-109">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
- [<span data-ttu-id="33b52-110">Transaktionsunterstützung</span><span class="sxs-lookup"><span data-stu-id="33b52-110">Transaction Support</span></span>](transaction-support.md)
