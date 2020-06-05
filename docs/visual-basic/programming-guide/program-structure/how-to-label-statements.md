---
title: 'Vorgehensweise: Label-Anweisungen'
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: 8f04d592c51b6a0630bfe623fd3574555aef9ff8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403212"
---
# <a name="how-to-label-statements-visual-basic"></a><span data-ttu-id="ecf4c-102">Gewusst wie: Label-Anweisungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ecf4c-102">How to: Label Statements (Visual Basic)</span></span>

<span data-ttu-id="ecf4c-103">Anweisungsblöcke bestehen aus Codezeilen, die durch Doppelpunkte getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="ecf4c-103">Statement blocks are made up of lines of code delimited by colons.</span></span> <span data-ttu-id="ecf4c-104">Codezeilen, denen eine identifizierende Zeichenfolge oder eine ganze Zahl vorangestellt ist, werden *als bezeichnet*.</span><span class="sxs-lookup"><span data-stu-id="ecf4c-104">Lines of code preceded by an identifying string or integer are said to be *labeled*.</span></span> <span data-ttu-id="ecf4c-105">Mithilfe von Anweisungs Bezeichnungen wird eine Codezeile gekennzeichnet, um Sie für die Verwendung mit Anweisungen wie zu kennzeichnen `On Error Goto` .</span><span class="sxs-lookup"><span data-stu-id="ecf4c-105">Statement labels are used to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>

<span data-ttu-id="ecf4c-106">Bezeichnungen können entweder gültige Visual Basic Bezeichner sein – z. b. diejenigen, die Programmier Elemente identifizieren – oder ganzzahlige Literale.</span><span class="sxs-lookup"><span data-stu-id="ecf4c-106">Labels may be either valid Visual Basic identifiers—such as those that identify programming elements—or integer literals.</span></span> <span data-ttu-id="ecf4c-107">Eine Bezeichnung muss am Anfang einer Zeile des Quellcodes vorhanden sein, und es muss ein Doppelpunkt folgen, unabhängig davon, ob auf Sie eine-Anweisung in derselben Zeile folgt.</span><span class="sxs-lookup"><span data-stu-id="ecf4c-107">A label must appear at the beginning of a line of source code and must be followed by a colon, regardless of whether it is followed by a statement on the same line.</span></span>

<span data-ttu-id="ecf4c-108">Der Compiler identifiziert Bezeichnungen, indem er überprüft, ob der Anfang der Zeile mit einem bereits definierten Bezeichner übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="ecf4c-108">The compiler identifies labels by checking whether the beginning of the line matches any already-defined identifier.</span></span> <span data-ttu-id="ecf4c-109">Andernfalls geht der Compiler davon aus, dass es sich um eine Bezeichnung handelt.</span><span class="sxs-lookup"><span data-stu-id="ecf4c-109">If it does not, the compiler assumes it is a label.</span></span>

<span data-ttu-id="ecf4c-110">Bezeichnungen verfügen über einen eigenen Deklarations Bereich und stören andere Bezeichner nicht.</span><span class="sxs-lookup"><span data-stu-id="ecf4c-110">Labels have their own declaration space and do not interfere with other identifiers.</span></span> <span data-ttu-id="ecf4c-111">Der Gültigkeitsbereich einer Bezeichnung ist der Text der Methode.</span><span class="sxs-lookup"><span data-stu-id="ecf4c-111">A label's scope is the body of the method.</span></span> <span data-ttu-id="ecf4c-112">Die Bezeichnungs Deklaration hat in jeder mehrdeutigen Situation Vorrang.</span><span class="sxs-lookup"><span data-stu-id="ecf4c-112">Label declaration takes precedence in any ambiguous situation.</span></span>

> [!NOTE]
> <span data-ttu-id="ecf4c-113">Bezeichnungen können nur für ausführbare Anweisungen innerhalb von Methoden verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ecf4c-113">Labels can be used only on executable statements inside methods.</span></span>

## <a name="to-label-a-line-of-code"></a><span data-ttu-id="ecf4c-114">So bezeichnen Sie eine Codezeile</span><span class="sxs-lookup"><span data-stu-id="ecf4c-114">To label a line of code</span></span>

<span data-ttu-id="ecf4c-115">Platzieren Sie einen Bezeichner, gefolgt von einem Doppelpunkt, am Anfang der Zeile des Quellcodes.</span><span class="sxs-lookup"><span data-stu-id="ecf4c-115">Place an identifier, followed by a colon, at the beginning of the line of source code.</span></span>

<span data-ttu-id="ecf4c-116">Die folgenden Codezeilen werden z. b. mit bzw. gekennzeichnet `Jump` `120` :</span><span class="sxs-lookup"><span data-stu-id="ecf4c-116">For example, the following lines of code are labeled with `Jump` and `120`, respectively:</span></span>

[!code-vb[VbVbalrStatements#708](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#708)]

## <a name="see-also"></a><span data-ttu-id="ecf4c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ecf4c-117">See also</span></span>

- [<span data-ttu-id="ecf4c-118">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="ecf4c-118">Statements</span></span>](../language-features/statements.md)
- [<span data-ttu-id="ecf4c-119">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="ecf4c-119">Declared Element Names</span></span>](../language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="ecf4c-120">Programmstruktur und Codekonventionen</span><span class="sxs-lookup"><span data-stu-id="ecf4c-120">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)
