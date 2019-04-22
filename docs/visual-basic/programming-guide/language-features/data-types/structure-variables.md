---
title: Strukturvariablen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 9a6e542e297a17f44d929235530ae6058cf13a36
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816329"
---
# <a name="structure-variables-visual-basic"></a><span data-ttu-id="dd55c-102">Strukturvariablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd55c-102">Structure Variables (Visual Basic)</span></span>
<span data-ttu-id="dd55c-103">Nachdem Sie eine Struktur erstellt haben, können Sie Variablen auf Prozedurebene und auf Modulebene wie dieser Typ deklarieren.</span><span class="sxs-lookup"><span data-stu-id="dd55c-103">Once you have created a structure, you can declare procedure-level and module-level variables as that type.</span></span> <span data-ttu-id="dd55c-104">Beispielsweise können Sie eine Struktur, zeichnet Informationen zu einem Computersystem erstellen.</span><span class="sxs-lookup"><span data-stu-id="dd55c-104">For example, you can create a structure that records information about a computer system.</span></span> <span data-ttu-id="dd55c-105">Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="dd55c-105">The following example demonstrates this.</span></span>  
  
```  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public purchaseDate As Date  
End Structure  
```  
  
 <span data-ttu-id="dd55c-106">Nun können Sie die Variablen dieses Typs deklarieren.</span><span class="sxs-lookup"><span data-stu-id="dd55c-106">You can now declare variables of that type.</span></span> <span data-ttu-id="dd55c-107">Dies wird in die folgende Deklaration veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="dd55c-107">The following declaration illustrates this.</span></span>  
  
```  
Dim mySystem, yourSystem As systemInfo  
```  
  
> [!NOTE]
>  <span data-ttu-id="dd55c-108">In Klassen und Modulen, Strukturen deklariert mit dem [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) standardmäßig öffentlichen Zugriff auf.</span><span class="sxs-lookup"><span data-stu-id="dd55c-108">In classes and modules, structures declared using the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) default to public access.</span></span> <span data-ttu-id="dd55c-109">Wenn Sie eine Struktur privat festlegen möchten deklarieren Sie sie mithilfe, der [Private](../../../../visual-basic/language-reference/modifiers/private.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="dd55c-109">If you intend a structure to be private, make sure you declare it using the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword.</span></span>  
  
## <a name="access-to-structure-values"></a><span data-ttu-id="dd55c-110">Zugriff auf die Strukturwerte</span><span class="sxs-lookup"><span data-stu-id="dd55c-110">Access to Structure Values</span></span>  
 <span data-ttu-id="dd55c-111">Zum Zuweisen und Abrufen von Werten aus den Elementen einer Strukturvariablen, verwenden Sie die gleiche Syntax wie zum Festlegen und Abrufen von Eigenschaften für ein Objekt.</span><span class="sxs-lookup"><span data-stu-id="dd55c-111">To assign and retrieve values from the elements of a structure variable, you use the same syntax as you use to set and get properties on an object.</span></span> <span data-ttu-id="dd55c-112">Platzieren Sie den Memberzugriffsoperator (`.`) zwischen der Name der Struktur und der Elementname.</span><span class="sxs-lookup"><span data-stu-id="dd55c-112">You place the member access operator (`.`) between the structure variable name and the element name.</span></span> <span data-ttu-id="dd55c-113">Das folgende Beispiel greift auf die Elemente der zuvor als Typ deklarierten Variablen `systemInfo`.</span><span class="sxs-lookup"><span data-stu-id="dd55c-113">The following example accesses elements of the variables previously declared as type `systemInfo`.</span></span>  
  
```  
mySystem.cPU = "486"  
Dim tooOld As Boolean  
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True  
```  
  
## <a name="assigning-structure-variables"></a><span data-ttu-id="dd55c-114">Zuweisen von Strukturvariablen</span><span class="sxs-lookup"><span data-stu-id="dd55c-114">Assigning Structure Variables</span></span>  
 <span data-ttu-id="dd55c-115">Sie können auch eine Variable in einen anderen zuweisen, wenn vom selben Strukturtyp angehören.</span><span class="sxs-lookup"><span data-stu-id="dd55c-115">You can also assign one variable to another if both are of the same structure type.</span></span> <span data-ttu-id="dd55c-116">Dies kopiert alle Elemente einer Struktur in die entsprechenden Elemente im anderen.</span><span class="sxs-lookup"><span data-stu-id="dd55c-116">This copies all the elements of one structure to the corresponding elements in the other.</span></span> <span data-ttu-id="dd55c-117">Dies wird in die folgende Deklaration veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="dd55c-117">The following declaration illustrates this.</span></span>  
  
```  
yourSystem = mySystem  
```  
  
 <span data-ttu-id="dd55c-118">Wenn ein Strukturelement einen Referenztyp darstellt, z. B. eine `String`, `Object`, oder ein Array, das Zeiger auf die Daten werden kopiert.</span><span class="sxs-lookup"><span data-stu-id="dd55c-118">If a structure element is a reference type, such as a `String`, `Object`, or array, the pointer to the data is copied.</span></span> <span data-ttu-id="dd55c-119">Im vorherigen Beispiel wenn `systemInfo` hatte eine Objektvariable enthalten, und klicken Sie dann im vorherigen Beispiel wird den Zeiger von kopiert haben, würden `mySystem` zu `yourSystem`, und eine Änderung an den Daten des Objekts durch eine Struktur wäre in Kraft, beim Zugriff auf über die andere Struktur.</span><span class="sxs-lookup"><span data-stu-id="dd55c-119">In the previous example, if `systemInfo` had included an object variable, then the preceding example would have copied the pointer from `mySystem` to `yourSystem`, and a change to the object's data through one structure would be in effect when accessed through the other structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd55c-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd55c-120">See also</span></span>

- [<span data-ttu-id="dd55c-121">Datentypen</span><span class="sxs-lookup"><span data-stu-id="dd55c-121">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="dd55c-122">Elementare Datentypen</span><span class="sxs-lookup"><span data-stu-id="dd55c-122">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="dd55c-123">Zusammengesetzte Datentypen</span><span class="sxs-lookup"><span data-stu-id="dd55c-123">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="dd55c-124">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="dd55c-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="dd55c-125">Strukturen</span><span class="sxs-lookup"><span data-stu-id="dd55c-125">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="dd55c-126">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="dd55c-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="dd55c-127">Vorgehensweise: Deklarieren einer Struktur</span><span class="sxs-lookup"><span data-stu-id="dd55c-127">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="dd55c-128">Strukturen und andere Programmierelemente</span><span class="sxs-lookup"><span data-stu-id="dd55c-128">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [<span data-ttu-id="dd55c-129">Strukturen und Klassen</span><span class="sxs-lookup"><span data-stu-id="dd55c-129">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="dd55c-130">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="dd55c-130">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
