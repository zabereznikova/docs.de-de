---
title: Der Vorgang konnte nicht abgeschlossen werden, da sich das Zielverzeichnis unterhalb des Quellverzeichnisses befindet.
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: 39373cd368282f3b109b450189561366b9e74484
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200571"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="03d92-102">Der Vorgang konnte nicht abgeschlossen werden, da sich das Zielverzeichnis unterhalb des Quellverzeichnisses befindet.</span><span class="sxs-lookup"><span data-stu-id="03d92-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="03d92-103">Ein zyklischer Vorgang ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="03d92-103">A cyclic operation has failed.</span></span> <span data-ttu-id="03d92-104">Ein zyklischer Vorgang wird zyklisch ausgeführt und kann daher nicht abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="03d92-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="03d92-105">Beispielsweise könnte Objekt A versuchen, von Objekt B zu erben, das wiederum versucht, von Objekt A zu erben.</span><span class="sxs-lookup"><span data-stu-id="03d92-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="03d92-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="03d92-106">To correct this error</span></span>  
  
-   <span data-ttu-id="03d92-107">Wenn geerbt wird, müssen Sie sicherstellen, dass keine zyklischen Verweise vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="03d92-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03d92-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03d92-108">See also</span></span>
- [<span data-ttu-id="03d92-109">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="03d92-109">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="03d92-110">Verwenden von Haltepunkten in Visual Studio-debugger</span><span class="sxs-lookup"><span data-stu-id="03d92-110">Use breakpoints in the Visual Studio debugger</span></span>](/visualstudio/debugger/using-breakpoints)
