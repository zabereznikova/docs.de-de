---
title: Es wurde keine zugreifbare Main-Methode mit entsprechender Signatur in "<name>" gefunden.
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: f5053bddf4b9ba791ad6d0733e1dd89c4ded91bd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918267"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a><span data-ttu-id="72575-102">Es wurde keine zugreifbare Main-Methode mit entsprechender Signatur in gefunden "\<Name >'</span><span class="sxs-lookup"><span data-stu-id="72575-102">No accessible 'Main' method with an appropriate signature was found in '\<name>'</span></span>
<span data-ttu-id="72575-103">Befehlszeile-Anwendungen benötigen eine `Sub Main` definiert.</span><span class="sxs-lookup"><span data-stu-id="72575-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="72575-104">`Main` muss deklariert werden, als `Public Shared` ggf. in einer Klasse oder als definierten `Public` Wenn in einem Modul definiert.</span><span class="sxs-lookup"><span data-stu-id="72575-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="72575-105">**Fehler-ID:** BC30737</span><span class="sxs-lookup"><span data-stu-id="72575-105">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="72575-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="72575-106">To correct this error</span></span>  
  
- <span data-ttu-id="72575-107">Definieren einer `Public Sub Main` Verfahren für Ihr Projekt.</span><span class="sxs-lookup"><span data-stu-id="72575-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="72575-108">Deklarieren Sie sie als `Shared` nur, wenn Sie sie innerhalb einer Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="72575-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72575-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72575-109">See also</span></span>

- [<span data-ttu-id="72575-110">Struktur der Visual Basic-Programmen</span><span class="sxs-lookup"><span data-stu-id="72575-110">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="72575-111">Verfahren</span><span class="sxs-lookup"><span data-stu-id="72575-111">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
