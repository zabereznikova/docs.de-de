---
title: 'Vorgehensweise: Erkennen und Auflösen von Übergabekonflikten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
ms.openlocfilehash: 606231449263f1c26596ca8606a88053c6aded8e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138124"
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a><span data-ttu-id="1977c-102">Vorgehensweise: Erkennen und Auflösen von Übergabekonflikten</span><span class="sxs-lookup"><span data-stu-id="1977c-102">How to: Detect and Resolve Conflicting Submissions</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="1977c-103">bietet viele Ressourcen zum Erkennen und Lösen von Konflikten, die in der Datenbank von mehreren Benutzern Änderungen ergeben.</span><span class="sxs-lookup"><span data-stu-id="1977c-103">provides many resources for detecting and resolving conflicts that stem from multi-user changes to the database.</span></span> <span data-ttu-id="1977c-104">Weitere Informationen finden Sie unter [Vorgehensweise: Verwalten von Änderungskonflikten](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).</span><span class="sxs-lookup"><span data-stu-id="1977c-104">For more information, see [How to: Manage Change Conflicts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1977c-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1977c-105">Example</span></span>  
 <span data-ttu-id="1977c-106">Das folgende Beispiel zeigt eine `try` / `catch` Block, der fängt eine <xref:System.Data.Linq.ChangeConflictException> Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="1977c-106">The following example shows a `try`/`catch` block that catches a <xref:System.Data.Linq.ChangeConflictException> exception.</span></span> <span data-ttu-id="1977c-107">Entitäts- und Memberinformationen für jeden Konflikt werden im Konsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1977c-107">Entity and member information for each conflict is displayed in the console window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1977c-108">Sie müssen die `using System.Reflection`-Direktive (`Imports System.Reflection` in Visual Basic) einschließen, um das Abrufen von Informationen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1977c-108">You must include the `using System.Reflection` directive (`Imports System.Reflection` in Visual Basic) to support the information retrieval.</span></span> <span data-ttu-id="1977c-109">Weitere Informationen finden Sie unter <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="1977c-109">For more information, see <xref:System.Reflection>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="1977c-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1977c-110">See also</span></span>

- [<span data-ttu-id="1977c-111">Vornehmen und Übergeben von Datenänderungen</span><span class="sxs-lookup"><span data-stu-id="1977c-111">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
- [<span data-ttu-id="1977c-112">Vorgehensweise: Verwalten von Änderungskonflikten</span><span class="sxs-lookup"><span data-stu-id="1977c-112">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
