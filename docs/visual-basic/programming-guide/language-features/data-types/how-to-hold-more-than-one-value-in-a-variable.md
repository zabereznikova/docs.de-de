---
title: 'Vorgehensweise: Ablegen mehrerer Werte in einer Variablen'
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
ms.openlocfilehash: 399c5909ee6988f96bcc85260b0401f3bd18a0f2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393895"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a><span data-ttu-id="64816-102">Gewusst wie: Ablegen mehrerer Werte in einer Variablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64816-102">How to: Hold More Than One Value in a Variable (Visual Basic)</span></span>

<span data-ttu-id="64816-103">Eine Variable enthält mehr als einen Wert, wenn Sie Sie als einen zusammen *gesetzten Datentyp*deklarieren.</span><span class="sxs-lookup"><span data-stu-id="64816-103">A variable holds more than one value if you declare it to be of a *composite data type*.</span></span>

<span data-ttu-id="64816-104">Zusammen [gesetzte Datentypen](composite-data-types.md) umfassen Strukturen, Arrays und Klassen.</span><span class="sxs-lookup"><span data-stu-id="64816-104">[Composite Data Types](composite-data-types.md) include structures, arrays, and classes.</span></span> <span data-ttu-id="64816-105">Eine Variable eines zusammengesetzten Datentyps kann eine Kombination aus elementaren Datentypen und anderen zusammengesetzten Typen enthalten.</span><span class="sxs-lookup"><span data-stu-id="64816-105">A variable of a composite data type can hold a combination of elementary data types and other composite types.</span></span> <span data-ttu-id="64816-106">Strukturen und Klassen können sowohl Code als auch Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="64816-106">Structures and classes can hold code as well as data.</span></span>

## <a name="to-hold-more-than-one-value-in-a-variable"></a><span data-ttu-id="64816-107">So speichern Sie mehr als einen Wert in einer Variablen</span><span class="sxs-lookup"><span data-stu-id="64816-107">To hold more than one value in a variable</span></span>

1. <span data-ttu-id="64816-108">Bestimmen Sie den zusammengesetzten Datentyp, den Sie für die Variable verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="64816-108">Determine what composite data type you want to use for your variable.</span></span>

2. <span data-ttu-id="64816-109">Wenn der zusammengesetzte Datentyp nicht bereits definiert ist, definieren Sie ihn so, dass er von der Variablen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="64816-109">If the composite data type is not already defined, define it so that your variable can use it.</span></span>

    - <span data-ttu-id="64816-110">Definieren Sie eine Struktur mit einer [Structure-Anweisung](../../../language-reference/statements/structure-statement.md).</span><span class="sxs-lookup"><span data-stu-id="64816-110">Define a structure with a [Structure Statement](../../../language-reference/statements/structure-statement.md).</span></span>

    - <span data-ttu-id="64816-111">Definieren Sie ein Array mit einer [Dim-Anweisung](../../../language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="64816-111">Define an array with a [Dim Statement](../../../language-reference/statements/dim-statement.md).</span></span>

    - <span data-ttu-id="64816-112">Definieren Sie eine Klasse mit einer [Class-Anweisung](../../../language-reference/statements/class-statement.md).</span><span class="sxs-lookup"><span data-stu-id="64816-112">Define a class with a [Class Statement](../../../language-reference/statements/class-statement.md).</span></span>

3. <span data-ttu-id="64816-113">Deklarieren Sie die Variable mit einer- `Dim` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="64816-113">Declare your variable with a `Dim` statement.</span></span>

4. <span data-ttu-id="64816-114">Befolgen Sie den Variablennamen mit einer- `As` Klausel.</span><span class="sxs-lookup"><span data-stu-id="64816-114">Follow the variable name with an `As` clause.</span></span>

5. <span data-ttu-id="64816-115">Befolgen Sie das- `As` Schlüsselwort mit dem Namen des entsprechenden zusammengesetzten Datentyps.</span><span class="sxs-lookup"><span data-stu-id="64816-115">Follow the `As` keyword with the name of the appropriate composite data type.</span></span>

## <a name="see-also"></a><span data-ttu-id="64816-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="64816-116">See also</span></span>

- [<span data-ttu-id="64816-117">Datentypen</span><span class="sxs-lookup"><span data-stu-id="64816-117">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="64816-118">Typzeichen</span><span class="sxs-lookup"><span data-stu-id="64816-118">Type Characters</span></span>](type-characters.md)
- [<span data-ttu-id="64816-119">Zusammengesetzte Datentypen</span><span class="sxs-lookup"><span data-stu-id="64816-119">Composite Data Types</span></span>](composite-data-types.md)
- [<span data-ttu-id="64816-120">Strukturen</span><span class="sxs-lookup"><span data-stu-id="64816-120">Structures</span></span>](structures.md)
- [<span data-ttu-id="64816-121">Arrays</span><span class="sxs-lookup"><span data-stu-id="64816-121">Arrays</span></span>](../arrays/index.md)
- [<span data-ttu-id="64816-122">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="64816-122">Objects and Classes</span></span>](../objects-and-classes/index.md)
- [<span data-ttu-id="64816-123">Wert- und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="64816-123">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
