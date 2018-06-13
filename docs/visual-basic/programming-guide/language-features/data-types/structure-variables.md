---
title: Strukturvariablen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 0dad7bdcac5428753e252f3b26ca0a127c293a7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648498"
---
# <a name="structure-variables-visual-basic"></a><span data-ttu-id="3d175-102">Strukturvariablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d175-102">Structure Variables (Visual Basic)</span></span>
<span data-ttu-id="3d175-103">Nachdem Sie eine Struktur erstellt haben, können Sie Variablen auf Prozedurebene und auf Modulebene als diesen Typ deklarieren.</span><span class="sxs-lookup"><span data-stu-id="3d175-103">Once you have created a structure, you can declare procedure-level and module-level variables as that type.</span></span> <span data-ttu-id="3d175-104">Beispielsweise können Sie eine Struktur, zeichnet Informationen zu einem Computersystem erstellen.</span><span class="sxs-lookup"><span data-stu-id="3d175-104">For example, you can create a structure that records information about a computer system.</span></span> <span data-ttu-id="3d175-105">Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="3d175-105">The following example demonstrates this.</span></span>  
  
```  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public purchaseDate As Date  
End Structure  
```  
  
 <span data-ttu-id="3d175-106">Nun können Sie Variablen dieses Typs deklarieren.</span><span class="sxs-lookup"><span data-stu-id="3d175-106">You can now declare variables of that type.</span></span> <span data-ttu-id="3d175-107">Dies wird anhand die folgende Deklaration veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3d175-107">The following declaration illustrates this.</span></span>  
  
```  
Dim mySystem, yourSystem As systemInfo  
```  
  
> [!NOTE]
>  <span data-ttu-id="3d175-108">In Klassen und Module mit Strukturen deklariert die [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) standardmäßig öffentlichen Zugriff auf.</span><span class="sxs-lookup"><span data-stu-id="3d175-108">In classes and modules, structures declared using the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) default to public access.</span></span> <span data-ttu-id="3d175-109">Wenn Sie beabsichtigen die eine Struktur, die privat sein, sicher deklarieren Sie sie mit der [Private](../../../../visual-basic/language-reference/modifiers/private.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="3d175-109">If you intend a structure to be private, make sure you declare it using the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword.</span></span>  
  
## <a name="access-to-structure-values"></a><span data-ttu-id="3d175-110">Zugriff auf die Strukturwerte</span><span class="sxs-lookup"><span data-stu-id="3d175-110">Access to Structure Values</span></span>  
 <span data-ttu-id="3d175-111">Um zuzuweisen, und rufen Werte aus den Elementen einer Strukturvariablen, verwenden Sie die gleiche Syntax wie zum Festlegen und Abrufen von Eigenschaften für ein Objekt.</span><span class="sxs-lookup"><span data-stu-id="3d175-111">To assign and retrieve values from the elements of a structure variable, you use the same syntax as you use to set and get properties on an object.</span></span> <span data-ttu-id="3d175-112">Platzieren Sie den Memberzugriffsoperator (`.`) zwischen den Struktur-Variablennamen und den Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="3d175-112">You place the member access operator (`.`) between the structure variable name and the element name.</span></span> <span data-ttu-id="3d175-113">Das folgende Beispiel greift auf die Elemente der zuvor als Typ deklarierten Variablen `systemInfo`.</span><span class="sxs-lookup"><span data-stu-id="3d175-113">The following example accesses elements of the variables previously declared as type `systemInfo`.</span></span>  
  
```  
mySystem.cPU = "486"  
Dim tooOld As Boolean  
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True  
```  
  
## <a name="assigning-structure-variables"></a><span data-ttu-id="3d175-114">Zuweisen von Strukturvariablen</span><span class="sxs-lookup"><span data-stu-id="3d175-114">Assigning Structure Variables</span></span>  
 <span data-ttu-id="3d175-115">Sie können auch eine Variable auf einen anderen zuweisen, wenn vom selben Strukturtyp angehören.</span><span class="sxs-lookup"><span data-stu-id="3d175-115">You can also assign one variable to another if both are of the same structure type.</span></span> <span data-ttu-id="3d175-116">Kopiert alle Elemente einer Struktur in die entsprechenden Elemente in der anderen.</span><span class="sxs-lookup"><span data-stu-id="3d175-116">This copies all the elements of one structure to the corresponding elements in the other.</span></span> <span data-ttu-id="3d175-117">Dies wird anhand die folgende Deklaration veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3d175-117">The following declaration illustrates this.</span></span>  
  
```  
yourSystem = mySystem  
```  
  
 <span data-ttu-id="3d175-118">Wenn ein Strukturelement einen Referenztyp darstellt, wie eine `String`, `Object`, oder Array, der Zeiger auf die Daten kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="3d175-118">If a structure element is a reference type, such as a `String`, `Object`, or array, the pointer to the data is copied.</span></span> <span data-ttu-id="3d175-119">Im vorherigen Beispiel wenn `systemInfo` hatte eine Objektvariable enthalten, und klicken Sie dann im vorherige Beispiel den Zeiger von kopiert haben, würden `mySystem` auf `yourSystem`, und eine Änderung an den Daten des Objekts durch eine Struktur wäre beim Zugriff aktiviert über die andere Struktur.</span><span class="sxs-lookup"><span data-stu-id="3d175-119">In the previous example, if `systemInfo` had included an object variable, then the preceding example would have copied the pointer from `mySystem` to `yourSystem`, and a change to the object's data through one structure would be in effect when accessed through the other structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d175-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d175-120">See Also</span></span>  
 [<span data-ttu-id="3d175-121">Datentypen</span><span class="sxs-lookup"><span data-stu-id="3d175-121">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="3d175-122">Elementare Datentypen</span><span class="sxs-lookup"><span data-stu-id="3d175-122">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="3d175-123">Zusammengesetzte Datentypen</span><span class="sxs-lookup"><span data-stu-id="3d175-123">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [<span data-ttu-id="3d175-124">Werttypen und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="3d175-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="3d175-125">Strukturen</span><span class="sxs-lookup"><span data-stu-id="3d175-125">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="3d175-126">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="3d175-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="3d175-127">Gewusst wie: Deklarieren einer Struktur</span><span class="sxs-lookup"><span data-stu-id="3d175-127">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="3d175-128">Strukturen und andere Programmierelemente</span><span class="sxs-lookup"><span data-stu-id="3d175-128">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 [<span data-ttu-id="3d175-129">Strukturen und Klassen</span><span class="sxs-lookup"><span data-stu-id="3d175-129">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [<span data-ttu-id="3d175-130">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3d175-130">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
