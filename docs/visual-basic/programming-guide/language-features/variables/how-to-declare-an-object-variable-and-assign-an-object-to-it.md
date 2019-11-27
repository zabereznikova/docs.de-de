---
title: 'Gewusst wie: Deklarieren einer Objektvariablen und Zuweisen eines Objekts'
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: 4cfad1d820b584d4610d24c392b14ac3958471b7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352907"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a><span data-ttu-id="35b66-102">Gewusst wie: Deklarieren einer Objektvariablen und Zuweisen eines entsprechenden Objekts in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="35b66-102">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>

<span data-ttu-id="35b66-103">Sie deklarieren eine Variable des [Object-Datentyps](../../../../visual-basic/language-reference/data-types/object-data-type.md) , indem Sie `As Object` in einer [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md)angeben.</span><span class="sxs-lookup"><span data-stu-id="35b66-103">You declare a variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="35b66-104">Sie weisen einer solchen Variablen ein Objekt zu, indem Sie das-Objekt nach dem Gleichheitszeichen (`=`) in einer Zuweisungsanweisung oder Initialisierungs Klausel platzieren.</span><span class="sxs-lookup"><span data-stu-id="35b66-104">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span></span>

## <a name="example"></a><span data-ttu-id="35b66-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="35b66-105">Example</span></span>

<span data-ttu-id="35b66-106">Im folgenden Beispiel wird eine `Object` Variable deklariert und der aktuellen Instanz zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="35b66-106">The following example declares an `Object` variable and assigns the current instance to it.</span></span>

```vb
Dim thisObject As Object
thisObject = "This is an Object"
```

<span data-ttu-id="35b66-107">Sie können die Deklaration und Zuweisung kombinieren, indem Sie die Variable als Teil der Deklaration initialisieren.</span><span class="sxs-lookup"><span data-stu-id="35b66-107">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span></span> <span data-ttu-id="35b66-108">Das folgende Beispiel entspricht dem vorherigen Beispiel.</span><span class="sxs-lookup"><span data-stu-id="35b66-108">The following example is equivalent to the preceding example.</span></span>

```vb
Dim thisObject As Object= "This is an Object"
```

## <a name="compiling-the-code"></a><span data-ttu-id="35b66-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="35b66-109">Compiling the Code</span></span>

<span data-ttu-id="35b66-110">Dieses Beispiel erfordert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="35b66-110">This example requires:</span></span>

- <span data-ttu-id="35b66-111">Einen Verweis auf den <xref:System>-Namespace</span><span class="sxs-lookup"><span data-stu-id="35b66-111">A reference to the <xref:System> namespace.</span></span>

- <span data-ttu-id="35b66-112">Eine Klasse, Struktur oder ein Modul, in das die `Dim`-Anweisung eingefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="35b66-112">A class, structure, or module in which to put the `Dim` statement.</span></span>

- <span data-ttu-id="35b66-113">Eine Prozedur, in der die Zuweisungsanweisung eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="35b66-113">A procedure in which to put the assignment statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="35b66-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35b66-114">See also</span></span>

- [<span data-ttu-id="35b66-115">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="35b66-115">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="35b66-116">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="35b66-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="35b66-117">Deklaration von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="35b66-117">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="35b66-118">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="35b66-118">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="35b66-119">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="35b66-119">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="35b66-120">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="35b66-120">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="35b66-121">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="35b66-121">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
