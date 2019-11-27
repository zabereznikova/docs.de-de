---
title: 'Gewusst wie: Ablegen mehrerer Werte in einer Variablen'
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- arrays [Visual Basic], compilation errors
- types [Visual Basic], composite
ms.assetid: 5fe0e558-aac2-4a40-b7f2-7cfea7336917
ms.openlocfilehash: d452fbf35f9d200348234b38c40f8636f0ec4b4e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350024"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a><span data-ttu-id="a7c5e-102">Gewusst wie: Ablegen mehrerer Werte in einer Variablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7c5e-102">How to: Hold More Than One Value in a Variable (Visual Basic)</span></span>

<span data-ttu-id="a7c5e-103">Eine Variable enthält mehr als einen Wert, wenn Sie Sie als einen zusammen *gesetzten Datentyp*deklarieren.</span><span class="sxs-lookup"><span data-stu-id="a7c5e-103">A variable holds more than one value if you declare it to be of a *composite data type*.</span></span>

<span data-ttu-id="a7c5e-104">Zusammen [gesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) umfassen Strukturen, Arrays und Klassen.</span><span class="sxs-lookup"><span data-stu-id="a7c5e-104">[Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) include structures, arrays, and classes.</span></span> <span data-ttu-id="a7c5e-105">Eine Variable eines zusammengesetzten Datentyps kann eine Kombination aus elementaren Datentypen und anderen zusammengesetzten Typen enthalten.</span><span class="sxs-lookup"><span data-stu-id="a7c5e-105">A variable of a composite data type can hold a combination of elementary data types and other composite types.</span></span> <span data-ttu-id="a7c5e-106">Strukturen und Klassen können sowohl Code als auch Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="a7c5e-106">Structures and classes can hold code as well as data.</span></span>

## <a name="to-hold-more-than-one-value-in-a-variable"></a><span data-ttu-id="a7c5e-107">So speichern Sie mehr als einen Wert in einer Variablen</span><span class="sxs-lookup"><span data-stu-id="a7c5e-107">To hold more than one value in a variable</span></span>

1. <span data-ttu-id="a7c5e-108">Bestimmen Sie den zusammengesetzten Datentyp, den Sie für die Variable verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a7c5e-108">Determine what composite data type you want to use for your variable.</span></span>

2. <span data-ttu-id="a7c5e-109">Wenn der zusammengesetzte Datentyp nicht bereits definiert ist, definieren Sie ihn so, dass er von der Variablen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a7c5e-109">If the composite data type is not already defined, define it so that your variable can use it.</span></span>

    - <span data-ttu-id="a7c5e-110">Definieren Sie eine Struktur mit einer [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a7c5e-110">Define a structure with a [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md).</span></span>

    - <span data-ttu-id="a7c5e-111">Definieren Sie ein Array mit einer [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a7c5e-111">Define an array with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>

    - <span data-ttu-id="a7c5e-112">Definieren Sie eine Klasse mit einer [Class-Anweisung](../../../../visual-basic/language-reference/statements/class-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a7c5e-112">Define a class with a [Class Statement](../../../../visual-basic/language-reference/statements/class-statement.md).</span></span>

3. <span data-ttu-id="a7c5e-113">Deklarieren Sie die Variable mit einer `Dim`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a7c5e-113">Declare your variable with a `Dim` statement.</span></span>

4. <span data-ttu-id="a7c5e-114">Befolgen Sie den Variablennamen mit einer `As`-Klausel.</span><span class="sxs-lookup"><span data-stu-id="a7c5e-114">Follow the variable name with an `As` clause.</span></span>

5. <span data-ttu-id="a7c5e-115">Befolgen Sie das `As`-Schlüsselwort mit dem Namen des entsprechenden zusammengesetzten Datentyps.</span><span class="sxs-lookup"><span data-stu-id="a7c5e-115">Follow the `As` keyword with the name of the appropriate composite data type.</span></span>

## <a name="see-also"></a><span data-ttu-id="a7c5e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7c5e-116">See also</span></span>

- [<span data-ttu-id="a7c5e-117">Datentypen</span><span class="sxs-lookup"><span data-stu-id="a7c5e-117">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="a7c5e-118">Typzeichen</span><span class="sxs-lookup"><span data-stu-id="a7c5e-118">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [<span data-ttu-id="a7c5e-119">Zusammengesetzte Datentypen</span><span class="sxs-lookup"><span data-stu-id="a7c5e-119">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="a7c5e-120">Strukturen</span><span class="sxs-lookup"><span data-stu-id="a7c5e-120">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="a7c5e-121">Arrays</span><span class="sxs-lookup"><span data-stu-id="a7c5e-121">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="a7c5e-122">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="a7c5e-122">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="a7c5e-123">Werttypen und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="a7c5e-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
