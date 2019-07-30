---
title: 'Vorgehensweise: Deklarieren Sie eine Objekt Variable, und weisen Sie Ihr ein Objekt in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: 71949d50b01d7f252a988e86ca259261086d3b3b
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630868"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a><span data-ttu-id="49a73-102">Vorgehensweise: Deklarieren Sie eine Objekt Variable, und weisen Sie Ihr ein Objekt in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="49a73-102">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>

<span data-ttu-id="49a73-103">Sie deklarieren eine Variable des [Object-Datentyps](../../../../visual-basic/language-reference/data-types/object-data-type.md) , indem Sie in einer `As Object` Dim- [Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md)angeben.</span><span class="sxs-lookup"><span data-stu-id="49a73-103">You declare a variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="49a73-104">Sie weisen einer solchen Variablen ein Objekt zu, indem Sie das-Objekt nach dem Gleichheitszeichen (`=`) in einer Zuweisungsanweisung oder Initialisierungs Klausel platzieren.</span><span class="sxs-lookup"><span data-stu-id="49a73-104">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span></span>

## <a name="example"></a><span data-ttu-id="49a73-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="49a73-105">Example</span></span>

<span data-ttu-id="49a73-106">Im folgenden Beispiel wird eine `Object` -Variable deklariert und der aktuellen Instanz zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="49a73-106">The following example declares an `Object` variable and assigns the current instance to it.</span></span>

```vb
Dim thisObject As Object
thisObject = "This is an Object"
```

<span data-ttu-id="49a73-107">Sie können die Deklaration und Zuweisung kombinieren, indem Sie die Variable als Teil der Deklaration initialisieren.</span><span class="sxs-lookup"><span data-stu-id="49a73-107">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span></span> <span data-ttu-id="49a73-108">Das folgende Beispiel entspricht dem vorherigen Beispiel.</span><span class="sxs-lookup"><span data-stu-id="49a73-108">The following example is equivalent to the preceding example.</span></span>

```vb
Dim thisObject As Object= "This is an Object"
```

## <a name="compiling-the-code"></a><span data-ttu-id="49a73-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="49a73-109">Compiling the Code</span></span>

<span data-ttu-id="49a73-110">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="49a73-110">This example requires:</span></span>

- <span data-ttu-id="49a73-111">Einen Verweis auf den <xref:System>-Namespace</span><span class="sxs-lookup"><span data-stu-id="49a73-111">A reference to the <xref:System> namespace.</span></span>

- <span data-ttu-id="49a73-112">Eine Klasse, Struktur oder ein Modul, in das die `Dim` Anweisung eingefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="49a73-112">A class, structure, or module in which to put the `Dim` statement.</span></span>

- <span data-ttu-id="49a73-113">Eine Prozedur, in der die Zuweisungsanweisung eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="49a73-113">A procedure in which to put the assignment statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="49a73-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49a73-114">See also</span></span>

- [<span data-ttu-id="49a73-115">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="49a73-115">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="49a73-116">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="49a73-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="49a73-117">Deklaration von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="49a73-117">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="49a73-118">Object-Datentyp</span><span class="sxs-lookup"><span data-stu-id="49a73-118">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="49a73-119">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="49a73-119">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="49a73-120">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="49a73-120">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="49a73-121">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="49a73-121">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
