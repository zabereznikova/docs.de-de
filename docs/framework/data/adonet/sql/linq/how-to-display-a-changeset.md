---
title: 'Gewusst wie: Anzeigen eines "ChangeSets"'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 126e7245-c5a0-4ebf-800d-cc1fcf9cd0ab
ms.openlocfilehash: c9664c6d32f78f455aa29311f111acaecb5c7905
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33359984"
---
# <a name="how-to-display-a-changeset"></a><span data-ttu-id="b4431-102">Gewusst wie: Anzeigen eines "ChangeSets"</span><span class="sxs-lookup"><span data-stu-id="b4431-102">How to: Display a ChangeSet</span></span>
<span data-ttu-id="b4431-103">Sie können die von einem <xref:System.Data.Linq.DataContext> verfolgten Änderungen mithilfe von <xref:System.Data.Linq.DataContext.GetChangeSet%2A> anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b4431-103">You can view changes tracked by a <xref:System.Data.Linq.DataContext> by using <xref:System.Data.Linq.DataContext.GetChangeSet%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4431-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4431-104">Example</span></span>  
 <span data-ttu-id="b4431-105">Im folgenden Beispiel werden Kunden aus London abgerufen, der Ort wird in Paris geändert, und die Änderungen werden wieder an die Datenbank übergeben.</span><span class="sxs-lookup"><span data-stu-id="b4431-105">The following example retrieves customers whose city is London, changes the city to Paris, and submits the changes back to the database.</span></span>  
  
 [!code-csharp[DLinqDebuggingSupport#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#2)]
 [!code-vb[DLinqDebuggingSupport#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#2)]  
  
 <span data-ttu-id="b4431-106">Die Ausgabe dieses Codes ähnelt der folgenden.</span><span class="sxs-lookup"><span data-stu-id="b4431-106">Output from this code appears similar to the following.</span></span> <span data-ttu-id="b4431-107">Beachten Sie, dass die Zusammenfassung am Ende zeigt, dass acht Änderungen vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="b4431-107">Note that the summary at the end shows that eight changes were made.</span></span>  
  
 `CustomerID: AROUT`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: BSBEV`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: CONSH`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: EASTC`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: NORTS`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: PARIS`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: SEVES`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: SPECD`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 ``  
  
 `Total changes: {Added: 0, Removed: 0, Modified: 8}`  
  
## <a name="see-also"></a><span data-ttu-id="b4431-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4431-108">See Also</span></span>  
 [<span data-ttu-id="b4431-109">Debugunterstützung</span><span class="sxs-lookup"><span data-stu-id="b4431-109">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)
