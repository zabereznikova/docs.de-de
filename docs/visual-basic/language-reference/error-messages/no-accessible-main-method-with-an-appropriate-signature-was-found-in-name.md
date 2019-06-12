---
title: Es wurde keine zugreifbare Main-Methode mit entsprechender Signatur in '<name>' gefunden.
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 559c905d1e2e2de4500771a93d6116f9630011ba
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64591976"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a><span data-ttu-id="b6689-102">Es wurde keine zugreifbare Main-Methode mit entsprechender Signatur in gefunden '\<Name >'</span><span class="sxs-lookup"><span data-stu-id="b6689-102">No accessible 'Main' method with an appropriate signature was found in '\<name>'</span></span>
<span data-ttu-id="b6689-103">Befehlszeile-Anwendungen benötigen eine `Sub Main` definiert.</span><span class="sxs-lookup"><span data-stu-id="b6689-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="b6689-104">`Main` muss deklariert werden, als `Public Shared` ggf. in einer Klasse oder als definierten `Public` Wenn in einem Modul definiert.</span><span class="sxs-lookup"><span data-stu-id="b6689-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="b6689-105">**Fehler-ID:** BC30737</span><span class="sxs-lookup"><span data-stu-id="b6689-105">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b6689-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="b6689-106">To correct this error</span></span>  
  
- <span data-ttu-id="b6689-107">Definieren einer `Public Sub Main` Verfahren für Ihr Projekt.</span><span class="sxs-lookup"><span data-stu-id="b6689-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="b6689-108">Deklarieren Sie sie als `Shared` nur, wenn Sie sie innerhalb einer Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="b6689-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6689-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6689-109">See also</span></span>

- [<span data-ttu-id="b6689-110">Struktur der Visual Basic-Programmen</span><span class="sxs-lookup"><span data-stu-id="b6689-110">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="b6689-111">Verfahren</span><span class="sxs-lookup"><span data-stu-id="b6689-111">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
