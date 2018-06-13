---
title: Schlüsselwörter als Elementnamen in Code (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: 53c3172e8518115d001c23be2430fbc87ae1b60f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652577"
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a><span data-ttu-id="b3320-102">Schlüsselwörter als Elementnamen in Code (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3320-102">Keywords as Element Names in Code (Visual Basic)</span></span>
<span data-ttu-id="b3320-103">Jedem Programmelement, z. B. eine Variable, eine Klasse oder ein Member – kann den gleichen Namen wie ein eingeschränktes Schlüsselwort haben.</span><span class="sxs-lookup"><span data-stu-id="b3320-103">Any program element — such as a variable, class, or member — can have the same name as a restricted keyword.</span></span> <span data-ttu-id="b3320-104">Sie können z. B. erstellen eine Variablen namens `Loop`.</span><span class="sxs-lookup"><span data-stu-id="b3320-104">For example, you can create a variable named `Loop`.</span></span> <span data-ttu-id="b3320-105">Allerdings zum Verweisen auf die Version zu – die hat des gleichen Namens wie die eingeschränkte `Loop` Schlüsselwort – müssen Sie ein vollständiger Qualifizierungspfad voran oder schließen Sie ihn in eckige Klammern (`[ ]`), wie das folgende Beispiel zeigt.</span><span class="sxs-lookup"><span data-stu-id="b3320-105">However, to refer to your version of it — which has the same name as the restricted `Loop` keyword — you must either precede it with a full qualification string or enclose it in square brackets (`[ ]`), as the following example shows.</span></span>  
  
 [!code-vb[VbVbcnConventions#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/keywords-as-element-names-in-code_1.vb)]  
  
 <span data-ttu-id="b3320-106">Wenn Sie nicht eine dieser Optionen, und klicken Sie dann Visual Basic davon aus, die systeminterne Funktion dass `Loop` Schlüsselwort und erzeugt einen Fehler, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="b3320-106">If you do not do either of these, then Visual Basic assumes use of the intrinsic `Loop` keyword and produces an error, as in the following example:</span></span>  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 <span data-ttu-id="b3320-107">Eckige Klammern können beim Verweisen auf Formularen und Steuerelementen und beim Deklarieren einer Variablen oder eine Prozedur mit dem gleichen Namen wie ein eingeschränktes Schlüsselwort definieren.</span><span class="sxs-lookup"><span data-stu-id="b3320-107">You can use square brackets when referring to forms and controls, and when declaring a variable or defining a procedure with the same name as a restricted keyword.</span></span> <span data-ttu-id="b3320-108">Es kann leicht vergessen, qualifizieren Namen oder eckige Klammern einschließen und somit einführen von Fehlern in Ihren Code und schwieriger zu lesen sein.</span><span class="sxs-lookup"><span data-stu-id="b3320-108">It can be easy to forget to qualify names or include square brackets, and thus introduce errors into your code and make it harder to read.</span></span> <span data-ttu-id="b3320-109">Aus diesem Grund wird empfohlen, dass Sie eingeschränkte Schlüsselwörter nicht als den Namen der Anwendung Elemente verwenden.</span><span class="sxs-lookup"><span data-stu-id="b3320-109">For this reason, we recommend that you not use restricted keywords as the names of program elements.</span></span> <span data-ttu-id="b3320-110">Jedoch wenn eine zukünftige Version von Visual Basic einem neuen Schlüsselwort, steht in Konflikt mit vorhandenen Steuerelementnamen eines Formulars oder definiert, können klicken Sie dann diese Technik Sie beim Aktualisieren von Code mit der neuen Version funktioniert.</span><span class="sxs-lookup"><span data-stu-id="b3320-110">However, if a future version of Visual Basic defines a new keyword that conflicts with an existing form or control name, then you can use this technique when updating your code to work with the new version.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3320-111">Das Programm kann auch Elementnamen, die von anderen Assemblys verwiesen wird bereitgestellt enthalten.</span><span class="sxs-lookup"><span data-stu-id="b3320-111">Your program also might include element names provided by other referenced assemblies.</span></span> <span data-ttu-id="b3320-112">Wenn diese Namen mit eingeschränkte Schlüsselwörter in Konflikt stehen, führt dazu, dass Platzieren von eckigen Klammern darum Visual Basic, um sie als Ihre definierten Elemente interpretiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="b3320-112">If these names conflict with restricted keywords, then placing square brackets around them causes Visual Basic to interpret them as your defined elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3320-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3320-113">See Also</span></span>  
 [<span data-ttu-id="b3320-114">Visual Basic-Benennungskonventionen</span><span class="sxs-lookup"><span data-stu-id="b3320-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [<span data-ttu-id="b3320-115">Programmstruktur und Codekonventionen</span><span class="sxs-lookup"><span data-stu-id="b3320-115">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="b3320-116">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b3320-116">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
