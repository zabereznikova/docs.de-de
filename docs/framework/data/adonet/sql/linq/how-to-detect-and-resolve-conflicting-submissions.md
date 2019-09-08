---
title: 'Vorgehensweise: Erkennen und Auflösen von Übergabekonflikten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
ms.openlocfilehash: 2de0182cc0b87768a9cff553b7ec6e77f8ccc7b8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793776"
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a><span data-ttu-id="bf392-102">Vorgehensweise: Erkennen und Auflösen von Übergabekonflikten</span><span class="sxs-lookup"><span data-stu-id="bf392-102">How to: Detect and Resolve Conflicting Submissions</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="bf392-103">stellt viele Ressourcen zur Erkennung und Auflösung von Konflikten bereit, die von Mehrbenutzeränderungen an der Datenbank stammen.</span><span class="sxs-lookup"><span data-stu-id="bf392-103">provides many resources for detecting and resolving conflicts that stem from multi-user changes to the database.</span></span> <span data-ttu-id="bf392-104">Weitere Informationen finden Sie unter [Vorgehensweise: Verwalten von Änderungs](how-to-manage-change-conflicts.md)Konflikten.</span><span class="sxs-lookup"><span data-stu-id="bf392-104">For more information, see [How to: Manage Change Conflicts](how-to-manage-change-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf392-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bf392-105">Example</span></span>  
 <span data-ttu-id="bf392-106">Das folgende Beispiel zeigt einen `try` / `catch` -Block, der <xref:System.Data.Linq.ChangeConflictException> eine-Ausnahme abfängt.</span><span class="sxs-lookup"><span data-stu-id="bf392-106">The following example shows a `try`/`catch` block that catches a <xref:System.Data.Linq.ChangeConflictException> exception.</span></span> <span data-ttu-id="bf392-107">Entitäts- und Memberinformationen für jeden Konflikt werden im Konsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bf392-107">Entity and member information for each conflict is displayed in the console window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bf392-108">Sie müssen die `using System.Reflection`-Direktive (`Imports System.Reflection` in Visual Basic) einschließen, um das Abrufen von Informationen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="bf392-108">You must include the `using System.Reflection` directive (`Imports System.Reflection` in Visual Basic) to support the information retrieval.</span></span> <span data-ttu-id="bf392-109">Weitere Informationen finden Sie unter <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="bf392-109">For more information, see <xref:System.Reflection>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="bf392-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf392-110">See also</span></span>

- [<span data-ttu-id="bf392-111">Vornehmen und Übergeben von Datenänderungen</span><span class="sxs-lookup"><span data-stu-id="bf392-111">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
- [<span data-ttu-id="bf392-112">Vorgehensweise: Verwalten von Änderungs Konflikten</span><span class="sxs-lookup"><span data-stu-id="bf392-112">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
