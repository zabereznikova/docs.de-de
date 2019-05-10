---
title: Deklaration erwartet.
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: e6f8bf2b4ce9789a1715971b8262bdd162ba8035
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64619529"
---
# <a name="declaration-expected"></a><span data-ttu-id="75055-102">Deklaration erwartet.</span><span class="sxs-lookup"><span data-stu-id="75055-102">Declaration expected</span></span>
<span data-ttu-id="75055-103">Eine nicht deklarierte-Anweisung, wie z. B. eine Zuweisung oder Schleifenanweisung, findet jede Prozedur ab.</span><span class="sxs-lookup"><span data-stu-id="75055-103">A nondeclarative statement, such as an assignment or loop statement, occurs outside any procedure.</span></span> <span data-ttu-id="75055-104">Nur Deklarationen sind externe Prozeduren zulässig.</span><span class="sxs-lookup"><span data-stu-id="75055-104">Only declarations are allowed outside procedures.</span></span>  
  
 <span data-ttu-id="75055-105">Sie können auch ein Programmierelement wird deklariert ohne Deklarationsschlüsselwort wie z. B. `Dim` oder `Const`.</span><span class="sxs-lookup"><span data-stu-id="75055-105">Alternatively, a programming element is declared without a declaration keyword such as `Dim` or `Const`.</span></span>  
  
 <span data-ttu-id="75055-106">**Fehler-ID:** BC30188</span><span class="sxs-lookup"><span data-stu-id="75055-106">**Error ID:** BC30188</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="75055-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="75055-107">To correct this error</span></span>  
  
- <span data-ttu-id="75055-108">Verschieben Sie die nicht deklarierte Anweisung in den Text einer Prozedur an.</span><span class="sxs-lookup"><span data-stu-id="75055-108">Move the nondeclarative statement to the body of a procedure.</span></span>  
  
- <span data-ttu-id="75055-109">Beginnen Sie mit der Deklaration mit einer entsprechenden Deklarationsschlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="75055-109">Begin the declaration with an appropriate declaration keyword.</span></span>  
  
- <span data-ttu-id="75055-110">Stellen Sie sicher, dass ein Deklarationsschlüsselwort nicht falsch geschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="75055-110">Ensure that a declaration keyword is not misspelled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75055-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75055-111">See also</span></span>

- [<span data-ttu-id="75055-112">Verfahren</span><span class="sxs-lookup"><span data-stu-id="75055-112">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="75055-113">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="75055-113">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
