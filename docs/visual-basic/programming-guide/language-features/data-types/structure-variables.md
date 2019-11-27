---
title: Strukturvariablen
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 16b6cdc5a849b50f6caa8b7963dac5c12d63cf3e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346295"
---
# <a name="structure-variables-visual-basic"></a><span data-ttu-id="c8517-102">Strukturvariablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8517-102">Structure Variables (Visual Basic)</span></span>

<span data-ttu-id="c8517-103">Nachdem Sie eine Struktur erstellt haben, können Sie Variablen auf Prozedur-und Modulebene als diesen Typ deklarieren.</span><span class="sxs-lookup"><span data-stu-id="c8517-103">Once you have created a structure, you can declare procedure-level and module-level variables as that type.</span></span> <span data-ttu-id="c8517-104">Beispielsweise können Sie eine Struktur erstellen, die Informationen zu einem Computersystem aufzeichnet.</span><span class="sxs-lookup"><span data-stu-id="c8517-104">For example, you can create a structure that records information about a computer system.</span></span> <span data-ttu-id="c8517-105">Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="c8517-105">The following example demonstrates this.</span></span>

```vb
Public Structure systemInfo
    Public cPU As String
    Public memory As Long
    Public purchaseDate As Date
End Structure
```

<span data-ttu-id="c8517-106">Sie können jetzt Variablen dieses Typs deklarieren.</span><span class="sxs-lookup"><span data-stu-id="c8517-106">You can now declare variables of that type.</span></span> <span data-ttu-id="c8517-107">Dies wird in der folgenden Deklaration veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c8517-107">The following declaration illustrates this.</span></span>

```vb
Dim mySystem, yourSystem As systemInfo
```

> [!NOTE]
> <span data-ttu-id="c8517-108">In Klassen und Modulen werden Strukturen, die mithilfe der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) deklariert werden, standardmäßig auf öffentlichen Zugriff eingestellt.</span><span class="sxs-lookup"><span data-stu-id="c8517-108">In classes and modules, structures declared using the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) default to public access.</span></span> <span data-ttu-id="c8517-109">Wenn Sie beabsichtigen, eine Struktur als privat zu verwenden, stellen Sie sicher, dass Sie Sie mit dem [privaten](../../../../visual-basic/language-reference/modifiers/private.md) Schlüsselwort deklarieren.</span><span class="sxs-lookup"><span data-stu-id="c8517-109">If you intend a structure to be private, make sure you declare it using the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword.</span></span>

## <a name="access-to-structure-values"></a><span data-ttu-id="c8517-110">Zugriff auf Struktur Werte</span><span class="sxs-lookup"><span data-stu-id="c8517-110">Access to Structure Values</span></span>

<span data-ttu-id="c8517-111">Zum Zuweisen und Abrufen von Werten aus den Elementen einer Struktur Variablen verwenden Sie dieselbe Syntax wie zum Festlegen und Abrufen von Eigenschaften für ein Objekt.</span><span class="sxs-lookup"><span data-stu-id="c8517-111">To assign and retrieve values from the elements of a structure variable, you use the same syntax as you use to set and get properties on an object.</span></span> <span data-ttu-id="c8517-112">Sie platzieren den Member Access Operator (`.`) zwischen dem Struktur Variablennamen und dem Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="c8517-112">You place the member access operator (`.`) between the structure variable name and the element name.</span></span> <span data-ttu-id="c8517-113">Im folgenden Beispiel wird auf Elemente der Variablen zugegriffen, die zuvor als Typ `systemInfo`deklariert wurden.</span><span class="sxs-lookup"><span data-stu-id="c8517-113">The following example accesses elements of the variables previously declared as type `systemInfo`.</span></span>

```vb
mySystem.cPU = "486"
Dim tooOld As Boolean
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True
```

## <a name="assigning-structure-variables"></a><span data-ttu-id="c8517-114">Zuweisen von Struktur Variablen</span><span class="sxs-lookup"><span data-stu-id="c8517-114">Assigning Structure Variables</span></span>

<span data-ttu-id="c8517-115">Sie können eine Variable auch einer anderen zuweisen, wenn beide denselben Strukturtyp haben.</span><span class="sxs-lookup"><span data-stu-id="c8517-115">You can also assign one variable to another if both are of the same structure type.</span></span> <span data-ttu-id="c8517-116">Dadurch werden alle Elemente einer Struktur in die entsprechenden Elemente in der anderen kopiert.</span><span class="sxs-lookup"><span data-stu-id="c8517-116">This copies all the elements of one structure to the corresponding elements in the other.</span></span> <span data-ttu-id="c8517-117">Dies wird in der folgenden Deklaration veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c8517-117">The following declaration illustrates this.</span></span>

```vb
yourSystem = mySystem
```

<span data-ttu-id="c8517-118">Wenn ein Strukturelement ein Referenztyp ist, z. b. eine `String`, `Object`oder ein Array, wird der Zeiger auf die Daten kopiert.</span><span class="sxs-lookup"><span data-stu-id="c8517-118">If a structure element is a reference type, such as a `String`, `Object`, or array, the pointer to the data is copied.</span></span> <span data-ttu-id="c8517-119">Wenn `systemInfo` im vorherigen Beispiel eine Objekt Variable enthalten hätte, hätte das vorangehende Beispiel den Zeiger von `mySystem` auf `yourSystem`kopiert, und eine Änderung an den Daten des Objekts durch eine Struktur wäre wirksam, wenn über die andere Struktur darauf zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="c8517-119">In the previous example, if `systemInfo` had included an object variable, then the preceding example would have copied the pointer from `mySystem` to `yourSystem`, and a change to the object's data through one structure would be in effect when accessed through the other structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8517-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8517-120">See also</span></span>

- [<span data-ttu-id="c8517-121">Datentypen</span><span class="sxs-lookup"><span data-stu-id="c8517-121">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="c8517-122">Elementare Datentypen</span><span class="sxs-lookup"><span data-stu-id="c8517-122">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="c8517-123">Zusammengesetzte Datentypen</span><span class="sxs-lookup"><span data-stu-id="c8517-123">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="c8517-124">Werttypen und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="c8517-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="c8517-125">Strukturen</span><span class="sxs-lookup"><span data-stu-id="c8517-125">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="c8517-126">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="c8517-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="c8517-127">Gewusst wie: Deklarieren einer Struktur</span><span class="sxs-lookup"><span data-stu-id="c8517-127">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="c8517-128">Strukturen und andere Programmierelemente</span><span class="sxs-lookup"><span data-stu-id="c8517-128">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [<span data-ttu-id="c8517-129">Strukturen und Klassen</span><span class="sxs-lookup"><span data-stu-id="c8517-129">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="c8517-130">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c8517-130">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
