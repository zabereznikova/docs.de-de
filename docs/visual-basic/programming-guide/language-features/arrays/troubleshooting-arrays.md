---
title: Problembehandlung bei Arrays
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
ms.openlocfilehash: 3c50c68c2a39aa04cff2dd43b5dfde709aec290f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349067"
---
# <a name="troubleshooting-arrays-visual-basic"></a><span data-ttu-id="c3be4-102">Problembehandlung bei Arrays (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c3be4-102">Troubleshooting Arrays (Visual Basic)</span></span>
<span data-ttu-id="c3be4-103">Auf dieser Seite werden einige allgemeine Probleme aufgelistet, die beim Arbeiten mit Arrays auftreten können.</span><span class="sxs-lookup"><span data-stu-id="c3be4-103">This page lists some common problems that can occur when working with arrays.</span></span>  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a><span data-ttu-id="c3be4-104">Kompilierungsfehler beim Deklarieren und Initialisieren eines Arrays</span><span class="sxs-lookup"><span data-stu-id="c3be4-104">Compilation Errors Declaring and Initializing an Array</span></span>  
 <span data-ttu-id="c3be4-105">Kompilierungsfehler können aus einem Missverständnis der Regeln zum deklarieren, erstellen und Initialisieren von Arrays entstehen.</span><span class="sxs-lookup"><span data-stu-id="c3be4-105">Compilation errors can arise from misunderstanding of the rules for declaring, creating, and initializing arrays.</span></span> <span data-ttu-id="c3be4-106">Die häufigsten Fehlerursache sind folgende:</span><span class="sxs-lookup"><span data-stu-id="c3be4-106">The most common causes of errors are the following:</span></span>  
  
- <span data-ttu-id="c3be4-107">Bereitstellen einer [neuen Operator](../../../../visual-basic/language-reference/operators/new-operator.md) Klausel nach Angabe von Dimensions Längen in der Deklaration der Array Variablen.</span><span class="sxs-lookup"><span data-stu-id="c3be4-107">Supplying a [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) clause after specifying dimension lengths in the array variable declaration.</span></span> <span data-ttu-id="c3be4-108">Die folgenden Codezeilen zeigen ungültige Deklarationen dieses Typs an.</span><span class="sxs-lookup"><span data-stu-id="c3be4-108">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
- <span data-ttu-id="c3be4-109">Angeben von Dimensions Längen für mehr als das Array einer Jagged Array auf oberster Ebene.</span><span class="sxs-lookup"><span data-stu-id="c3be4-109">Specifying dimension lengths for more than the top-level array of a jagged array.</span></span> <span data-ttu-id="c3be4-110">In der folgenden Codezeile wird eine ungültige Deklaration dieses Typs angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c3be4-110">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
- <span data-ttu-id="c3be4-111">Beim Angeben der Element Werte wird das `New` Schlüsselwort weggelassen.</span><span class="sxs-lookup"><span data-stu-id="c3be4-111">Omitting the `New` keyword when specifying the element values.</span></span> <span data-ttu-id="c3be4-112">In der folgenden Codezeile wird eine ungültige Deklaration dieses Typs angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c3be4-112">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
- <span data-ttu-id="c3be4-113">Bereitstellen einer `New`-Klausel ohne geschweifte Klammern (`{}`).</span><span class="sxs-lookup"><span data-stu-id="c3be4-113">Supplying a `New` clause without braces (`{}`).</span></span> <span data-ttu-id="c3be4-114">Die folgenden Codezeilen zeigen ungültige Deklarationen dieses Typs an.</span><span class="sxs-lookup"><span data-stu-id="c3be4-114">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a><span data-ttu-id="c3be4-115">Zugreifen auf ein Array außerhalb der Grenzen</span><span class="sxs-lookup"><span data-stu-id="c3be4-115">Accessing an Array Out of Bounds</span></span>  
 <span data-ttu-id="c3be4-116">Der Prozess der Initialisierung eines Arrays weist jeder Dimension eine obere Grenze und eine untere Grenze zu.</span><span class="sxs-lookup"><span data-stu-id="c3be4-116">The process of initializing an array assigns an upper bound and a lower bound to each dimension.</span></span> <span data-ttu-id="c3be4-117">Bei jedem Zugriff auf ein Element des Arrays muss ein gültiger Index oder ein Index für jede Dimension angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c3be4-117">Every access to an element of the array must specify a valid index, or subscript, for every dimension.</span></span> <span data-ttu-id="c3be4-118">Wenn ein Index unterhalb seiner unteren Grenze oder über der oberen Grenze liegt, ergibt sich eine <xref:System.IndexOutOfRangeException> Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="c3be4-118">If any index is below its lower bound or above its upper bound, an <xref:System.IndexOutOfRangeException> exception results.</span></span> <span data-ttu-id="c3be4-119">Der Compiler kann einen solchen Fehler nicht erkennen, weshalb zur Laufzeit ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="c3be4-119">The compiler cannot detect such an error, so an error occurs at run time.</span></span>  
  
### <a name="determining-bounds"></a><span data-ttu-id="c3be4-120">Bestimmen von Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="c3be4-120">Determining Bounds</span></span>  
 <span data-ttu-id="c3be4-121">Wenn eine andere Komponente ein Array an Ihren Code übergibt, z. b. als Prozedur Argument, kennen Sie die Größe des Arrays oder die Längen seiner Dimensionen nicht.</span><span class="sxs-lookup"><span data-stu-id="c3be4-121">If another component passes an array to your code, for example as a procedure argument, you do not know the size of that array or the lengths of its dimensions.</span></span> <span data-ttu-id="c3be4-122">Sie sollten immer die obere Grenze für jede Dimension eines Arrays ermitteln, bevor Sie versuchen, auf Elemente zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="c3be4-122">You should always determine the upper bound for every dimension of an array before you attempt to access any elements.</span></span> <span data-ttu-id="c3be4-123">Wenn das Array mit einer anderen Methode als einer Visual Basic `New`-Klausel erstellt wurde, ist die untere Grenze möglicherweise etwas anderes als 0 (null), und es ist am sichersten, dass auch die untere Grenze bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="c3be4-123">If the array has been created by some means other than a Visual Basic `New` clause, the lower bound might be something other than 0, and it is safest to determine that lower bound as well.</span></span>  
  
### <a name="specifying-the-dimension"></a><span data-ttu-id="c3be4-124">Angeben der Dimension</span><span class="sxs-lookup"><span data-stu-id="c3be4-124">Specifying the Dimension</span></span>  
 <span data-ttu-id="c3be4-125">Wenn Sie die Begrenzungen eines mehrdimensionalen Arrays ermitteln, achten Sie darauf, wie Sie die Dimension angeben.</span><span class="sxs-lookup"><span data-stu-id="c3be4-125">When determining the bounds of a multidimensional array, take care how you specify the dimension.</span></span> <span data-ttu-id="c3be4-126">Die `dimension` Parameter der Methoden <xref:System.Array.GetLowerBound%2A> und <xref:System.Array.GetUpperBound%2A> sind 0-basiert, während die `Rank` Parameter der Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A>-und <xref:Microsoft.VisualBasic.Information.UBound%2A>-Funktionen 1-basiert sind.</span><span class="sxs-lookup"><span data-stu-id="c3be4-126">The `dimension` parameters of the <xref:System.Array.GetLowerBound%2A> and <xref:System.Array.GetUpperBound%2A> methods are 0-based, while the `Rank` parameters of the Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> and <xref:Microsoft.VisualBasic.Information.UBound%2A> functions are 1-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3be4-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3be4-127">See also</span></span>

- [<span data-ttu-id="c3be4-128">Arrays</span><span class="sxs-lookup"><span data-stu-id="c3be4-128">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- <span data-ttu-id="c3be4-129">[How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md) (Gewusst wie: Initialisieren einer Arrayvariable in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c3be4-129">[How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)</span></span>
