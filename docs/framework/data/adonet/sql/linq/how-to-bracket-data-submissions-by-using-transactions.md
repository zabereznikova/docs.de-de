---
title: "Gewusst wie: Einklammern von Datenübergaben durch das Verwenden von Transaktionen"
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
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a5d7f1e0b0419874f694a0b3953f6b037a777016
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a><span data-ttu-id="4f623-102">Gewusst wie: Einklammern von Datenübergaben durch das Verwenden von Transaktionen</span><span class="sxs-lookup"><span data-stu-id="4f623-102">How to: Bracket Data Submissions by Using Transactions</span></span>
<span data-ttu-id="4f623-103">Sie können <xref:System.Transactions.TransactionScope> verwenden, um die Übergaben zur Datenbank einzuklammern.</span><span class="sxs-lookup"><span data-stu-id="4f623-103">You can use <xref:System.Transactions.TransactionScope> to bracket your submissions to the database.</span></span> <span data-ttu-id="4f623-104">Weitere Informationen finden Sie unter [Transaktionsunterstützung](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md).</span><span class="sxs-lookup"><span data-stu-id="4f623-104">For more information, see [Transaction Support](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f623-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4f623-105">Example</span></span>  
 <span data-ttu-id="4f623-106">Im folgenden Code wird die Datenbankübergabe in einem <xref:System.Transactions.TransactionScope> eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4f623-106">The following code encloses the database submission in a <xref:System.Transactions.TransactionScope>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="4f623-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f623-107">See Also</span></span>  
 [<span data-ttu-id="4f623-108">Downloading Sample Databases (Herunterladen von Beispieldatenbanken)</span><span class="sxs-lookup"><span data-stu-id="4f623-108">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [<span data-ttu-id="4f623-109">Vornehmen und Übergeben von Datenänderungen</span><span class="sxs-lookup"><span data-stu-id="4f623-109">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 [<span data-ttu-id="4f623-110">Transaktionsunterstützung</span><span class="sxs-lookup"><span data-stu-id="4f623-110">Transaction Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)
