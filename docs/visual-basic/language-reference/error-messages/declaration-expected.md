---
title: Deklaration erwartet.
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: 64ee75c93615f57b15fea29f06fff500a395ba0c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803830"
---
# <a name="declaration-expected"></a><span data-ttu-id="fba24-102">Deklaration erwartet.</span><span class="sxs-lookup"><span data-stu-id="fba24-102">Declaration expected</span></span>
<span data-ttu-id="fba24-103">Eine nicht deklarierte-Anweisung, wie z. B. eine Zuweisung oder Schleifenanweisung, findet jede Prozedur ab.</span><span class="sxs-lookup"><span data-stu-id="fba24-103">A nondeclarative statement, such as an assignment or loop statement, occurs outside any procedure.</span></span> <span data-ttu-id="fba24-104">Nur Deklarationen sind externe Prozeduren zulässig.</span><span class="sxs-lookup"><span data-stu-id="fba24-104">Only declarations are allowed outside procedures.</span></span>  
  
 <span data-ttu-id="fba24-105">Sie können auch ein Programmierelement wird deklariert ohne Deklarationsschlüsselwort wie z. B. `Dim` oder `Const`.</span><span class="sxs-lookup"><span data-stu-id="fba24-105">Alternatively, a programming element is declared without a declaration keyword such as `Dim` or `Const`.</span></span>  
  
 <span data-ttu-id="fba24-106">**Fehler-ID:** BC30188</span><span class="sxs-lookup"><span data-stu-id="fba24-106">**Error ID:** BC30188</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fba24-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="fba24-107">To correct this error</span></span>  
  
- <span data-ttu-id="fba24-108">Verschieben Sie die nicht deklarierte Anweisung in den Text einer Prozedur an.</span><span class="sxs-lookup"><span data-stu-id="fba24-108">Move the nondeclarative statement to the body of a procedure.</span></span>  
  
- <span data-ttu-id="fba24-109">Beginnen Sie mit der Deklaration mit einer entsprechenden Deklarationsschlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="fba24-109">Begin the declaration with an appropriate declaration keyword.</span></span>  
  
- <span data-ttu-id="fba24-110">Stellen Sie sicher, dass ein Deklarationsschlüsselwort nicht falsch geschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="fba24-110">Ensure that a declaration keyword is not misspelled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fba24-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fba24-111">See also</span></span>

- [<span data-ttu-id="fba24-112">Verfahren</span><span class="sxs-lookup"><span data-stu-id="fba24-112">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="fba24-113">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fba24-113">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
