---
title: Problembehandlung bei Arrays (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
ms.openlocfilehash: 2b051d22fe3d331626f2e181c008043e576b7526
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61908127"
---
# <a name="troubleshooting-arrays-visual-basic"></a><span data-ttu-id="6717b-102">Problembehandlung bei Arrays (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6717b-102">Troubleshooting Arrays (Visual Basic)</span></span>
<span data-ttu-id="6717b-103">Diese Seite listet einige der häufigsten Probleme, die bei der Arbeit mit Arrays auftreten können.</span><span class="sxs-lookup"><span data-stu-id="6717b-103">This page lists some common problems that can occur when working with arrays.</span></span>  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a><span data-ttu-id="6717b-104">Kompilierungsfehler deklarieren und Initialisieren eines Arrays</span><span class="sxs-lookup"><span data-stu-id="6717b-104">Compilation Errors Declaring and Initializing an Array</span></span>  
 <span data-ttu-id="6717b-105">Kompilierungsfehler können von Missverständnissen Regeln zum Deklarieren, erstellen und Initialisieren von Arrays auftreten.</span><span class="sxs-lookup"><span data-stu-id="6717b-105">Compilation errors can arise from misunderstanding of the rules for declaring, creating, and initializing arrays.</span></span> <span data-ttu-id="6717b-106">Die häufigsten Ursachen von Fehlern sind die folgenden:</span><span class="sxs-lookup"><span data-stu-id="6717b-106">The most common causes of errors are the following:</span></span>  
  
- <span data-ttu-id="6717b-107">Angeben einer [neuer Operator](../../../../visual-basic/language-reference/operators/new-operator.md) -Klausel nach der Angabe der Längen der Dimension in der Deklaration der Arrayvariablen.</span><span class="sxs-lookup"><span data-stu-id="6717b-107">Supplying a [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) clause after specifying dimension lengths in the array variable declaration.</span></span> <span data-ttu-id="6717b-108">Die folgenden Codezeilen zeigen ungültige Deklarationen dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="6717b-108">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
- <span data-ttu-id="6717b-109">Angeben von Längen der Dimension für mehr als Arrays der obersten Ebene eines verzweigten Arrays.</span><span class="sxs-lookup"><span data-stu-id="6717b-109">Specifying dimension lengths for more than the top-level array of a jagged array.</span></span> <span data-ttu-id="6717b-110">Die folgende Codezeile zeigt eine ungültige Deklaration dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="6717b-110">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
- <span data-ttu-id="6717b-111">Das Auslassen der `New` Schlüsselwort, wenn Sie die Elementwerte angeben.</span><span class="sxs-lookup"><span data-stu-id="6717b-111">Omitting the `New` keyword when specifying the element values.</span></span> <span data-ttu-id="6717b-112">Die folgende Codezeile zeigt eine ungültige Deklaration dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="6717b-112">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
- <span data-ttu-id="6717b-113">Angeben einer `New` -Klausel ohne geschweifte Klammern (`{}`).</span><span class="sxs-lookup"><span data-stu-id="6717b-113">Supplying a `New` clause without braces (`{}`).</span></span> <span data-ttu-id="6717b-114">Die folgenden Codezeilen zeigen ungültige Deklarationen dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="6717b-114">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a><span data-ttu-id="6717b-115">Zugreifen auf ein Array außerhalb des gültigen Bereichs</span><span class="sxs-lookup"><span data-stu-id="6717b-115">Accessing an Array Out of Bounds</span></span>  
 <span data-ttu-id="6717b-116">Bei der Initialisieren eines Arrays wird eine Obergrenze und einer unteren Grenze für jede Dimension zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="6717b-116">The process of initializing an array assigns an upper bound and a lower bound to each dimension.</span></span> <span data-ttu-id="6717b-117">Jeder Zugriff auf ein Element des Arrays muss einen gültigen Index oder Feldindex, für eine Dimension angeben.</span><span class="sxs-lookup"><span data-stu-id="6717b-117">Every access to an element of the array must specify a valid index, or subscript, for every dimension.</span></span> <span data-ttu-id="6717b-118">Wenn ein Index unter der unteren Grenze oder über die Obergrenze ist ein <xref:System.IndexOutOfRangeException> Ausnahme führt.</span><span class="sxs-lookup"><span data-stu-id="6717b-118">If any index is below its lower bound or above its upper bound, an <xref:System.IndexOutOfRangeException> exception results.</span></span> <span data-ttu-id="6717b-119">Der Compiler kann solche Fehler, nicht erkennen, damit zur Laufzeit ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="6717b-119">The compiler cannot detect such an error, so an error occurs at run time.</span></span>  
  
### <a name="determining-bounds"></a><span data-ttu-id="6717b-120">Bestimmen von Grenzen</span><span class="sxs-lookup"><span data-stu-id="6717b-120">Determining Bounds</span></span>  
 <span data-ttu-id="6717b-121">Wenn ein Array mit Ihrem Code eine andere Komponente übergeben wird, wissen z. B. als Prozedurargument, Sie nicht die Größe des Arrays oder der Länge seiner Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="6717b-121">If another component passes an array to your code, for example as a procedure argument, you do not know the size of that array or the lengths of its dimensions.</span></span> <span data-ttu-id="6717b-122">Sie sollten immer die obere Grenze jeder Dimension eines Arrays bestimmen, bevor Sie versuchen, den Zugriff auf alle Elemente.</span><span class="sxs-lookup"><span data-stu-id="6717b-122">You should always determine the upper bound for every dimension of an array before you attempt to access any elements.</span></span> <span data-ttu-id="6717b-123">Wenn das Array mit der eine Visual Basic erstellt wurde `New` -Klausel, die untere Grenze kann einen anderen Wert als 0 sein, und es ist am sichersten, sowie die Untergrenze bestimmen.</span><span class="sxs-lookup"><span data-stu-id="6717b-123">If the array has been created by some means other than a Visual Basic `New` clause, the lower bound might be something other than 0, and it is safest to determine that lower bound as well.</span></span>  
  
### <a name="specifying-the-dimension"></a><span data-ttu-id="6717b-124">Die Dimension angeben</span><span class="sxs-lookup"><span data-stu-id="6717b-124">Specifying the Dimension</span></span>  
 <span data-ttu-id="6717b-125">Wenn Sie die Grenzen eines mehrdimensionalen Arrays zu bestimmen, achten Sie wie Sie die Dimension angeben.</span><span class="sxs-lookup"><span data-stu-id="6717b-125">When determining the bounds of a multidimensional array, take care how you specify the dimension.</span></span> <span data-ttu-id="6717b-126">Die `dimension` Parameter von der <xref:System.Array.GetLowerBound%2A> und <xref:System.Array.GetUpperBound%2A> Methoden sind 0-basiert, während die `Rank` Parameter der Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> und <xref:Microsoft.VisualBasic.Information.UBound%2A> Funktionen sind 1-basiert.</span><span class="sxs-lookup"><span data-stu-id="6717b-126">The `dimension` parameters of the <xref:System.Array.GetLowerBound%2A> and <xref:System.Array.GetUpperBound%2A> methods are 0-based, while the `Rank` parameters of the Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> and <xref:Microsoft.VisualBasic.Information.UBound%2A> functions are 1-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6717b-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6717b-127">See also</span></span>

- [<span data-ttu-id="6717b-128">Arrays</span><span class="sxs-lookup"><span data-stu-id="6717b-128">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="6717b-129">Vorgehensweise: Initialisieren einer Arrayvariablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6717b-129">How to: Initialize an Array Variable in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
