---
title: 'Vorgehensweise: Einklammern von Datenübergaben mithilfe von Transaktionen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: 6a4c5ba7c4938b48fe489e43ff4a3ff806bd8916
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793804"
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a><span data-ttu-id="f9042-102">Vorgehensweise: Einklammern von Datenübergaben mithilfe von Transaktionen</span><span class="sxs-lookup"><span data-stu-id="f9042-102">How to: Bracket Data Submissions by Using Transactions</span></span>
<span data-ttu-id="f9042-103">Sie können <xref:System.Transactions.TransactionScope> verwenden, um die Übergaben zur Datenbank einzuklammern.</span><span class="sxs-lookup"><span data-stu-id="f9042-103">You can use <xref:System.Transactions.TransactionScope> to bracket your submissions to the database.</span></span> <span data-ttu-id="f9042-104">Weitere Informationen finden Sie [unter Transaktionsunterstützung](transaction-support.md).</span><span class="sxs-lookup"><span data-stu-id="f9042-104">For more information, see [Transaction Support](transaction-support.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9042-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f9042-105">Example</span></span>  
 <span data-ttu-id="f9042-106">Im folgenden Code wird die Datenbankübergabe in einem <xref:System.Transactions.TransactionScope> eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f9042-106">The following code encloses the database submission in a <xref:System.Transactions.TransactionScope>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="f9042-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9042-107">See also</span></span>

- [<span data-ttu-id="f9042-108">Downloading Sample Databases (Herunterladen von Beispieldatenbanken)</span><span class="sxs-lookup"><span data-stu-id="f9042-108">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="f9042-109">Vornehmen und Übergeben von Datenänderungen</span><span class="sxs-lookup"><span data-stu-id="f9042-109">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
- [<span data-ttu-id="f9042-110">Transaktionsunterstützung</span><span class="sxs-lookup"><span data-stu-id="f9042-110">Transaction Support</span></span>](transaction-support.md)
