---
title: Schlüsselwörter als Elementnamen in Code
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: e895db180dbb44cd4cfe4053d4be429f13324fe8
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91065748"
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a><span data-ttu-id="06b68-102">Schlüsselwörter als Elementnamen in Code (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06b68-102">Keywords as Element Names in Code (Visual Basic)</span></span>

<span data-ttu-id="06b68-103">Jedes Programmelement – z. b. eine Variable, eine Klasse oder ein Member – kann denselben Namen wie ein eingeschränktes Schlüsselwort haben.</span><span class="sxs-lookup"><span data-stu-id="06b68-103">Any program element — such as a variable, class, or member — can have the same name as a restricted keyword.</span></span> <span data-ttu-id="06b68-104">Beispielsweise können Sie eine Variable mit dem Namen erstellen `Loop` .</span><span class="sxs-lookup"><span data-stu-id="06b68-104">For example, you can create a variable named `Loop`.</span></span> <span data-ttu-id="06b68-105">Um jedoch auf Ihre Version des IT-– mit dem gleichen Namen wie das Schlüsselwort "Restricted" zu verweisen `Loop` – müssen Sie entweder eine vollständige Qualifikations Zeichenfolge voranstellen oder Sie in eckige Klammern ( `[ ]` ) einschließen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="06b68-105">However, to refer to your version of it — which has the same name as the restricted `Loop` keyword — you must either precede it with a full qualification string or enclose it in square brackets (`[ ]`), as the following example shows.</span></span>  
  
 [!code-vb[VbVbcnConventions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#8)]  
  
 <span data-ttu-id="06b68-106">Wenn Sie keine dieser Aktionen ausführen, wird Visual Basic die Verwendung des systeminternen `Loop` Schlüssel Worts annimmt und einen Fehler erzeugt, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="06b68-106">If you do not do either of these, then Visual Basic assumes use of the intrinsic `Loop` keyword and produces an error, as in the following example:</span></span>  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 <span data-ttu-id="06b68-107">Sie können eckige Klammern verwenden, wenn Sie auf Formulare und Steuerelemente verweisen, und wenn Sie eine Variable deklarieren oder eine Prozedur mit demselben Namen wie ein eingeschränktes Schlüsselwort definieren.</span><span class="sxs-lookup"><span data-stu-id="06b68-107">You can use square brackets when referring to forms and controls, and when declaring a variable or defining a procedure with the same name as a restricted keyword.</span></span> <span data-ttu-id="06b68-108">Es kann leicht vergessen werden, Namen zu qualifizieren oder eckige Klammern einzuschließen. auf diese Weise können Sie Fehler in Ihren Code einbringen und das Lesen erschweren.</span><span class="sxs-lookup"><span data-stu-id="06b68-108">It can be easy to forget to qualify names or include square brackets, and thus introduce errors into your code and make it harder to read.</span></span> <span data-ttu-id="06b68-109">Aus diesem Grund wird empfohlen, dass Sie keine eingeschränkten Schlüsselwörter als Namen von Programmelementen verwenden.</span><span class="sxs-lookup"><span data-stu-id="06b68-109">For this reason, we recommend that you not use restricted keywords as the names of program elements.</span></span> <span data-ttu-id="06b68-110">Wenn eine zukünftige Version von Visual Basic jedoch ein neues Schlüsselwort definiert, das mit einem vorhandenen Formular-oder Steuerelement Namen in Konflikt steht, können Sie dieses Verfahren verwenden, wenn Sie Ihren Code aktualisieren, um mit der neuen Version zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="06b68-110">However, if a future version of Visual Basic defines a new keyword that conflicts with an existing form or control name, then you can use this technique when updating your code to work with the new version.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="06b68-111">Ihr Programm kann auch Elementnamen enthalten, die von anderen referenzierten Assemblys bereitgestellt werden</span><span class="sxs-lookup"><span data-stu-id="06b68-111">Your program also might include element names provided by other referenced assemblies.</span></span> <span data-ttu-id="06b68-112">Wenn diese Namen mit eingeschränkten Schlüsselwörtern in Konflikt stehen, bewirkt das Platzieren von eckigen Klammern, Visual Basic Sie als die definierten Elemente interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="06b68-112">If these names conflict with restricted keywords, then placing square brackets around them causes Visual Basic to interpret them as your defined elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06b68-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06b68-113">See also</span></span>

- [<span data-ttu-id="06b68-114">Benennungskonventionen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="06b68-114">Visual Basic Naming Conventions</span></span>](naming-conventions.md)
- [<span data-ttu-id="06b68-115">Programmstruktur und Codekonventionen</span><span class="sxs-lookup"><span data-stu-id="06b68-115">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)
- [<span data-ttu-id="06b68-116">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="06b68-116">Keywords</span></span>](../../language-reference/keywords/index.md)
