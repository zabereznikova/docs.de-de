---
title: Keine zugreifbare &#39;Main&#39; Methode mit einer entsprechenden Signatur gefunden &#39; &lt;Name&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 6a60e26a2bd0e31c0f92dbbfb2518c75f304d9f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a><span data-ttu-id="1caa2-102">Keine zugreifbare &#39;Main&#39; Methode mit einer entsprechenden Signatur gefunden &#39; &lt;Name&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="1caa2-102">No accessible &#39;Main&#39; method with an appropriate signature was found in &#39;&lt;name&gt;&#39;</span></span>
<span data-ttu-id="1caa2-103">Befehlszeilenanwendungen benötigen eine `Sub Main` definiert.</span><span class="sxs-lookup"><span data-stu-id="1caa2-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="1caa2-104">`Main` muss deklariert werden, als `Public Shared` ggf. in einer Klasse oder als definierten `Public` Wenn in einem Modul definiert.</span><span class="sxs-lookup"><span data-stu-id="1caa2-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="1caa2-105">**Fehler-ID:** BC30737</span><span class="sxs-lookup"><span data-stu-id="1caa2-105">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1caa2-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="1caa2-106">To correct this error</span></span>  
  
-   <span data-ttu-id="1caa2-107">Definieren einer `Public Sub Main` Verfahren für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="1caa2-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="1caa2-108">Deklarieren Sie es als `Shared` nur, wenn Sie innerhalb einer Klasse zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1caa2-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1caa2-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1caa2-109">See Also</span></span>  
 [<span data-ttu-id="1caa2-110">Struktur eines Visual Basic-Programms</span><span class="sxs-lookup"><span data-stu-id="1caa2-110">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [<span data-ttu-id="1caa2-111">Verfahren</span><span class="sxs-lookup"><span data-stu-id="1caa2-111">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
