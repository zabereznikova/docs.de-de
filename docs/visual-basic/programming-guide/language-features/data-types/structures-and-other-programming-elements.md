---
title: Strukturen und andere Programmierelemente
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], arrays
- procedures [Visual Basic], structures as arguments to
- objects [Visual Basic], structure elements
- arrays [Visual Basic], structure elements
- nested structures [Visual Basic]
ms.assetid: 0f849313-ccd2-4c9a-acb9-69de6751c088
ms.openlocfilehash: 309d0e5214897675e1758bd98b964392b379ca1b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346119"
---
# <a name="structures-and-other-programming-elements-visual-basic"></a><span data-ttu-id="604a2-102">Strukturen und andere Programmierelemente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="604a2-102">Structures and Other Programming Elements (Visual Basic)</span></span>
<span data-ttu-id="604a2-103">Sie können Strukturen in Verbindung mit Arrays, Objekten und Prozeduren sowie untereinander verwenden.</span><span class="sxs-lookup"><span data-stu-id="604a2-103">You can use structures in conjunction with arrays, objects, and procedures, as well as with each other.</span></span> <span data-ttu-id="604a2-104">Die Interaktionen verwenden die gleiche Syntax wie diese Elemente einzeln verwenden.</span><span class="sxs-lookup"><span data-stu-id="604a2-104">The interactions use the same syntax as these elements use individually.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="604a2-105">Sie können keines der Structure-Elemente in der Struktur Deklaration initialisieren.</span><span class="sxs-lookup"><span data-stu-id="604a2-105">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="604a2-106">Sie können Werte nur Elementen einer Variablen zuweisen, die als Strukturtyp deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="604a2-106">You can assign values only to elements of a variable that has been declared to be of a structure type.</span></span>  
  
## <a name="structures-and-arrays"></a><span data-ttu-id="604a2-107">Strukturen und Arrays</span><span class="sxs-lookup"><span data-stu-id="604a2-107">Structures and Arrays</span></span>  
 <span data-ttu-id="604a2-108">Eine Struktur kann ein Array als ein oder mehrere Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="604a2-108">A structure can contain an array as one or more of its elements.</span></span> <span data-ttu-id="604a2-109">Das folgende Beispiel veranschaulicht dies.</span><span class="sxs-lookup"><span data-stu-id="604a2-109">The following example illustrates this.</span></span>  
  
```vb  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure   
```  
  
 <span data-ttu-id="604a2-110">Sie greifen auf die Werte eines Arrays innerhalb einer Struktur auf die gleiche Weise zu, wie Sie auf eine Eigenschaft in einem Objekt zugreifen.</span><span class="sxs-lookup"><span data-stu-id="604a2-110">You access the values of an array within a structure the same way you access a property on an object.</span></span> <span data-ttu-id="604a2-111">Das folgende Beispiel veranschaulicht dies.</span><span class="sxs-lookup"><span data-stu-id="604a2-111">The following example illustrates this.</span></span>  
  
```vb  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 <span data-ttu-id="604a2-112">Sie können auch ein Array von-Strukturen deklarieren.</span><span class="sxs-lookup"><span data-stu-id="604a2-112">You can also declare an array of structures.</span></span> <span data-ttu-id="604a2-113">Das folgende Beispiel veranschaulicht dies.</span><span class="sxs-lookup"><span data-stu-id="604a2-113">The following example illustrates this.</span></span>  
  
```vb  
Dim allSystems(100) As systemInfo  
```  
  
 <span data-ttu-id="604a2-114">Sie befolgen die gleichen Regeln für den Zugriff auf die Komponenten dieser Datenarchitektur.</span><span class="sxs-lookup"><span data-stu-id="604a2-114">You follow the same rules to access the components of this data architecture.</span></span> <span data-ttu-id="604a2-115">Das folgende Beispiel veranschaulicht dies.</span><span class="sxs-lookup"><span data-stu-id="604a2-115">The following example illustrates this.</span></span>  
  
```vb  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## <a name="structures-and-objects"></a><span data-ttu-id="604a2-116">Strukturen und Objekte</span><span class="sxs-lookup"><span data-stu-id="604a2-116">Structures and Objects</span></span>  
 <span data-ttu-id="604a2-117">Eine Struktur kann ein Objekt als ein oder mehrere Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="604a2-117">A structure can contain an object as one or more of its elements.</span></span> <span data-ttu-id="604a2-118">Das folgende Beispiel veranschaulicht dies.</span><span class="sxs-lookup"><span data-stu-id="604a2-118">The following example illustrates this.</span></span>  
  
```vb  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 <span data-ttu-id="604a2-119">Sie sollten eine bestimmte Objektklasse in einer solchen Deklaration anstelle von `Object`verwenden.</span><span class="sxs-lookup"><span data-stu-id="604a2-119">You should use a specific object class in such a declaration, rather than `Object`.</span></span>  
  
## <a name="structures-and-procedures"></a><span data-ttu-id="604a2-120">Strukturen und Prozeduren</span><span class="sxs-lookup"><span data-stu-id="604a2-120">Structures and Procedures</span></span>  
 <span data-ttu-id="604a2-121">Sie können eine Struktur als Prozedur Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="604a2-121">You can pass a structure as a procedure argument.</span></span> <span data-ttu-id="604a2-122">Das folgende Beispiel veranschaulicht dies.</span><span class="sxs-lookup"><span data-stu-id="604a2-122">The following example illustrates this.</span></span>  
  
```vb  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 <span data-ttu-id="604a2-123">Im vorangehenden Beispiel wird die Struktur als *Verweis*weitergeleitet, sodass die Prozedur die Elemente ändern kann, sodass die Änderungen im aufrufenden Code wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="604a2-123">The preceding example passes the structure *by reference*, which allows the procedure to modify its elements so that the changes take effect in the calling code.</span></span> <span data-ttu-id="604a2-124">Wenn Sie eine Struktur vor solchen Änderungen schützen möchten, übergeben Sie Sie als Wert.</span><span class="sxs-lookup"><span data-stu-id="604a2-124">If you want to protect a structure against such modification, pass it by value.</span></span>  
  
 <span data-ttu-id="604a2-125">Sie können auch eine Struktur aus einer `Function` Prozedur zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="604a2-125">You can also return a structure from a `Function` procedure.</span></span> <span data-ttu-id="604a2-126">Das folgende Beispiel veranschaulicht dies.</span><span class="sxs-lookup"><span data-stu-id="604a2-126">The following example illustrates this.</span></span>  
  
```vb  
Dim allSystems(100) As systemInfo  
Function findByDate(ByVal searchDate As Date) As systemInfo  
    Dim i As Integer  
    For i = 1 To 100  
        If allSystems(i).purchaseDate = searchDate Then Return allSystems(i)  
    Next i  
   ' Process error: system with desired purchase date not found.  
End Function  
```  
  
## <a name="structures-within-structures"></a><span data-ttu-id="604a2-127">Strukturen innerhalb von Strukturen</span><span class="sxs-lookup"><span data-stu-id="604a2-127">Structures Within Structures</span></span>  
 <span data-ttu-id="604a2-128">Strukturen können andere Strukturen enthalten.</span><span class="sxs-lookup"><span data-stu-id="604a2-128">Structures can contain other structures.</span></span> <span data-ttu-id="604a2-129">Das folgende Beispiel veranschaulicht dies.</span><span class="sxs-lookup"><span data-stu-id="604a2-129">The following example illustrates this.</span></span>  
  
```vb  
Public Structure driveInfo  
    Public type As String  
    Public size As Long  
End Structure  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As driveInfo  
    Public purchaseDate As Date  
End Structure  
```  
  
```vb  
Dim allSystems(100) As systemInfo  
ReDim allSystems(1).diskDrives(3)  
allSystems(1).diskDrives(0).type = "Floppy"  
```  
  
 <span data-ttu-id="604a2-130">Sie können dieses Verfahren auch verwenden, um eine Struktur zu kapseln, die in einem Modul innerhalb einer Struktur definiert ist, die in einem anderen Modul definiert ist.</span><span class="sxs-lookup"><span data-stu-id="604a2-130">You can also use this technique to encapsulate a structure defined in one module within a structure defined in a different module.</span></span>  
  
 <span data-ttu-id="604a2-131">Strukturen können andere Strukturen in beliebiger Tiefe enthalten.</span><span class="sxs-lookup"><span data-stu-id="604a2-131">Structures can contain other structures to an arbitrary depth.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="604a2-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="604a2-132">See also</span></span>

- [<span data-ttu-id="604a2-133">Datentypen</span><span class="sxs-lookup"><span data-stu-id="604a2-133">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="604a2-134">Elementare Datentypen</span><span class="sxs-lookup"><span data-stu-id="604a2-134">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="604a2-135">Zusammengesetzte Datentypen</span><span class="sxs-lookup"><span data-stu-id="604a2-135">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="604a2-136">Werttypen und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="604a2-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="604a2-137">Strukturen</span><span class="sxs-lookup"><span data-stu-id="604a2-137">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="604a2-138">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="604a2-138">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="604a2-139">Gewusst wie: Deklarieren einer Struktur</span><span class="sxs-lookup"><span data-stu-id="604a2-139">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="604a2-140">Strukturvariablen</span><span class="sxs-lookup"><span data-stu-id="604a2-140">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [<span data-ttu-id="604a2-141">Strukturen und Klassen</span><span class="sxs-lookup"><span data-stu-id="604a2-141">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="604a2-142">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="604a2-142">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
