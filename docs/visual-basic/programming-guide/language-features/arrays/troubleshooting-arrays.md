---
title: Problembehandlung bei Arrays (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0417ae8d37642a65b14cc81ae9dcf3a3c32d63ce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="troubleshooting-arrays-visual-basic"></a><span data-ttu-id="2e35b-102">Problembehandlung bei Arrays (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2e35b-102">Troubleshooting Arrays (Visual Basic)</span></span>
<span data-ttu-id="2e35b-103">Auf dieser Seite sind einige allgemeine Probleme, die beim Arbeiten mit Arrays auftreten können.</span><span class="sxs-lookup"><span data-stu-id="2e35b-103">This page lists some common problems that can occur when working with arrays.</span></span>  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a><span data-ttu-id="2e35b-104">Kompilierungsfehler deklarieren und Initialisieren eines Arrays</span><span class="sxs-lookup"><span data-stu-id="2e35b-104">Compilation Errors Declaring and Initializing an Array</span></span>  
 <span data-ttu-id="2e35b-105">In puncto der Regeln zum Deklarieren, erstellen und Initialisieren von Arrays können Kompilierungsfehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="2e35b-105">Compilation errors can arise from misunderstanding of the rules for declaring, creating, and initializing arrays.</span></span> <span data-ttu-id="2e35b-106">Die häufigsten Ursachen von Fehlern sind die folgenden:</span><span class="sxs-lookup"><span data-stu-id="2e35b-106">The most common causes of errors are the following:</span></span>  
  
-   <span data-ttu-id="2e35b-107">Angeben einer [New-Operator](../../../../visual-basic/language-reference/operators/new-operator.md) -Klausel nach Längen der Dimension in der Arrayvariablendeklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="2e35b-107">Supplying a [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) clause after specifying dimension lengths in the array variable declaration.</span></span> <span data-ttu-id="2e35b-108">Die folgenden Codezeilen zeigen ungültige Deklarationen dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="2e35b-108">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
-   <span data-ttu-id="2e35b-109">Angeben von Längen der Dimension mehr als Arrays der obersten Ebene eines verzweigten Arrays.</span><span class="sxs-lookup"><span data-stu-id="2e35b-109">Specifying dimension lengths for more than the top-level array of a jagged array.</span></span> <span data-ttu-id="2e35b-110">Die folgende Codezeile wird eine ungültige Deklaration dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="2e35b-110">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
-   <span data-ttu-id="2e35b-111">Das Weglassen der `New` -Schlüsselwort, wenn die Elementwerte festlegen.</span><span class="sxs-lookup"><span data-stu-id="2e35b-111">Omitting the `New` keyword when specifying the element values.</span></span> <span data-ttu-id="2e35b-112">Die folgende Codezeile wird eine ungültige Deklaration dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="2e35b-112">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
-   <span data-ttu-id="2e35b-113">Angeben einer `New` -Klausel ohne geschweifte Klammern (`{}`).</span><span class="sxs-lookup"><span data-stu-id="2e35b-113">Supplying a `New` clause without braces (`{}`).</span></span> <span data-ttu-id="2e35b-114">Die folgenden Codezeilen zeigen ungültige Deklarationen dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="2e35b-114">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a><span data-ttu-id="2e35b-115">Zugreifen auf ein Array außerhalb des gültigen Bereichs</span><span class="sxs-lookup"><span data-stu-id="2e35b-115">Accessing an Array Out of Bounds</span></span>  
 <span data-ttu-id="2e35b-116">Der Prozess Initialisieren eines Arrays weist eine Obergrenze und eine Untergrenze für jede Dimension.</span><span class="sxs-lookup"><span data-stu-id="2e35b-116">The process of initializing an array assigns an upper bound and a lower bound to each dimension.</span></span> <span data-ttu-id="2e35b-117">Jeder Zugriff auf ein Element des Arrays muss einen gültigen Index oder Feldindex, für jede Dimension angeben.</span><span class="sxs-lookup"><span data-stu-id="2e35b-117">Every access to an element of the array must specify a valid index, or subscript, for every dimension.</span></span> <span data-ttu-id="2e35b-118">Wenn ein Index niedriger als die Untergrenze oder über seine Obergrenze ist ein <xref:System.IndexOutOfRangeException> Ausnahmeergebnisse.</span><span class="sxs-lookup"><span data-stu-id="2e35b-118">If any index is below its lower bound or above its upper bound, an <xref:System.IndexOutOfRangeException> exception results.</span></span> <span data-ttu-id="2e35b-119">Der Compiler kann solche Fehler nicht erkennen, damit zur Laufzeit ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="2e35b-119">The compiler cannot detect such an error, so an error occurs at run time.</span></span>  
  
### <a name="determining-bounds"></a><span data-ttu-id="2e35b-120">Bestimmen von Grenzen</span><span class="sxs-lookup"><span data-stu-id="2e35b-120">Determining Bounds</span></span>  
 <span data-ttu-id="2e35b-121">Wenn ein Array für Ihren Code eine andere Komponente übergeben wird, wissen z. B. wie eines Prozedurarguments Sie nicht die Größe des Arrays oder Größen seiner Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="2e35b-121">If another component passes an array to your code, for example as a procedure argument, you do not know the size of that array or the lengths of its dimensions.</span></span> <span data-ttu-id="2e35b-122">Sie sollten immer die obere Grenze für eine Dimension eines Arrays bestimmen, bevor Sie versuchen, Zugriff auf alle Elemente.</span><span class="sxs-lookup"><span data-stu-id="2e35b-122">You should always determine the upper bound for every dimension of an array before you attempt to access any elements.</span></span> <span data-ttu-id="2e35b-123">Wenn das Array außer Weise erstellt wurde eine [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] `New` -Klausel, die untere Grenze kann einen anderen Wert als 0 sein, und es ist am sichersten, sowie die Untergrenze bestimmen.</span><span class="sxs-lookup"><span data-stu-id="2e35b-123">If the array has been created by some means other than a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] `New` clause, the lower bound might be something other than 0, and it is safest to determine that lower bound as well.</span></span>  
  
### <a name="specifying-the-dimension"></a><span data-ttu-id="2e35b-124">Angeben der Dimension</span><span class="sxs-lookup"><span data-stu-id="2e35b-124">Specifying the Dimension</span></span>  
 <span data-ttu-id="2e35b-125">Wenn die Grenzen eines mehrdimensionalen Arrays bestimmt wird, achten Sie darauf wie Sie die Dimension angeben.</span><span class="sxs-lookup"><span data-stu-id="2e35b-125">When determining the bounds of a multidimensional array, take care how you specify the dimension.</span></span> <span data-ttu-id="2e35b-126">Die `dimension` Parameter der <xref:System.Array.GetLowerBound%2A> und <xref:System.Array.GetUpperBound%2A> Methoden sind 0-basiert, während die `Rank` Parameter der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Information.LBound%2A> und <xref:Microsoft.VisualBasic.Information.UBound%2A> Funktionen basieren auf 1.</span><span class="sxs-lookup"><span data-stu-id="2e35b-126">The `dimension` parameters of the <xref:System.Array.GetLowerBound%2A> and <xref:System.Array.GetUpperBound%2A> methods are 0-based, while the `Rank` parameters of the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Information.LBound%2A> and <xref:Microsoft.VisualBasic.Information.UBound%2A> functions are 1-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e35b-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e35b-127">See Also</span></span>  
 [<span data-ttu-id="2e35b-128">Arrays</span><span class="sxs-lookup"><span data-stu-id="2e35b-128">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 <span data-ttu-id="2e35b-129">[How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md) (Gewusst wie: Initialisieren einer Arrayvariable in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2e35b-129">[How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)</span></span>
