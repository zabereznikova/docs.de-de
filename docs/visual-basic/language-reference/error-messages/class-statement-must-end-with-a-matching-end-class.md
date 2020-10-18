---
title: "\"Class\" muss mit einem entsprechenden \"End Class\" abgeschlossen werden."
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: 6889e97aad913f6911ce438892752542de0d10f0
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163193"
---
# <a name="bc30481-class-statement-must-end-with-a-matching-end-class"></a><span data-ttu-id="97c99-102">BC30481: die "Class"-Anweisung muss mit einem entsprechenden "End Class" abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="97c99-102">BC30481: 'Class' statement must end with a matching 'End Class'</span></span>

<span data-ttu-id="97c99-103">`Class` wird zum Initiieren eines- `Class` Blocks verwendet und kann daher nur am Anfang des Blocks angezeigt werden, wobei eine entsprechende- `End Class` Anweisung den Block beendet.</span><span class="sxs-lookup"><span data-stu-id="97c99-103">`Class` is used to initiate a `Class` block; hence it can only appear at the beginning of the block, with a matching `End Class` statement ending the block.</span></span> <span data-ttu-id="97c99-104">Sie haben entweder eine redundante- `Class` Anweisung, oder Sie haben den- `Class` Block nicht mit beendet `End Class` .</span><span class="sxs-lookup"><span data-stu-id="97c99-104">Either you have a redundant `Class` statement, or you have not ended your `Class` block with `End Class`.</span></span>

 <span data-ttu-id="97c99-105">**Fehler-ID:** BC30481</span><span class="sxs-lookup"><span data-stu-id="97c99-105">**Error ID:** BC30481</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="97c99-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="97c99-106">To correct this error</span></span>

- <span data-ttu-id="97c99-107">Suchen und entfernen Sie die unnötige `Class` -Anweisung.</span><span class="sxs-lookup"><span data-stu-id="97c99-107">Locate and remove the unnecessary `Class` statement.</span></span>

- <span data-ttu-id="97c99-108">Schließen Sie den `Class` Block mit einem übereinstimmenden ab `End Class` .</span><span class="sxs-lookup"><span data-stu-id="97c99-108">Conclude the `Class` block with a matching `End Class`.</span></span>

## <a name="see-also"></a><span data-ttu-id="97c99-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97c99-109">See also</span></span>

- [<span data-ttu-id="97c99-110">End- \<keyword> Anweisung</span><span class="sxs-lookup"><span data-stu-id="97c99-110">End \<keyword> Statement</span></span>](../statements/end-keyword-statement.md)
- [<span data-ttu-id="97c99-111">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="97c99-111">Class Statement</span></span>](../statements/class-statement.md)
