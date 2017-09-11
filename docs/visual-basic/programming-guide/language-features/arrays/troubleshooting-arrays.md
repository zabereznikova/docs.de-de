---
title: Problembehandlung bei Arrays (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 571731ae7066ba7ec52d4a2413b4d948f3f35bfe
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="troubleshooting-arrays-visual-basic"></a><span data-ttu-id="7c327-102">Problembehandlung bei Arrays (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c327-102">Troubleshooting Arrays (Visual Basic)</span></span>
<span data-ttu-id="7c327-103">Diese Seite listet einige der häufigsten Probleme, die beim Arbeiten mit Arrays auftreten können.</span><span class="sxs-lookup"><span data-stu-id="7c327-103">This page lists some common problems that can occur when working with arrays.</span></span>  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a><span data-ttu-id="7c327-104">Kompilierungsfehler beim Deklarieren und Initialisieren eines Arrays</span><span class="sxs-lookup"><span data-stu-id="7c327-104">Compilation Errors Declaring and Initializing an Array</span></span>  
 <span data-ttu-id="7c327-105">Kompilierungsfehler können aufgrund eines unzureichenden Verständnisses der Regeln zum Deklarieren, erstellen und Initialisieren von Arrays auftreten.</span><span class="sxs-lookup"><span data-stu-id="7c327-105">Compilation errors can arise from misunderstanding of the rules for declaring, creating, and initializing arrays.</span></span> <span data-ttu-id="7c327-106">Die häufigsten Ursachen von Fehlern sind folgende:</span><span class="sxs-lookup"><span data-stu-id="7c327-106">The most common causes of errors are the following:</span></span>  
  
-   <span data-ttu-id="7c327-107">Bereitstellen einer [Operator New](../../../../visual-basic/language-reference/operators/new-operator.md) -Klausel nach der Angabe der Längen der Dimension in der Deklaration der Arrayvariablen.</span><span class="sxs-lookup"><span data-stu-id="7c327-107">Supplying a [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) clause after specifying dimension lengths in the array variable declaration.</span></span> <span data-ttu-id="7c327-108">Die folgenden Codezeilen werden ungültige Deklarationen dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="7c327-108">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
-   <span data-ttu-id="7c327-109">Längen der Dimension für mehr als Arrays der obersten Ebene eines verzweigten Arrays angeben.</span><span class="sxs-lookup"><span data-stu-id="7c327-109">Specifying dimension lengths for more than the top-level array of a jagged array.</span></span> <span data-ttu-id="7c327-110">Die folgende Codezeile zeigt eine ungültige Deklaration dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="7c327-110">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
-   <span data-ttu-id="7c327-111">Das Weglassen der `New` Schlüsselwort beim Angeben der Elementwerte.</span><span class="sxs-lookup"><span data-stu-id="7c327-111">Omitting the `New` keyword when specifying the element values.</span></span> <span data-ttu-id="7c327-112">Die folgende Codezeile zeigt eine ungültige Deklaration dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="7c327-112">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
-   <span data-ttu-id="7c327-113">Bereitstellen einer `New` -Klausel ohne geschweifte Klammern (`{}`).</span><span class="sxs-lookup"><span data-stu-id="7c327-113">Supplying a `New` clause without braces (`{}`).</span></span> <span data-ttu-id="7c327-114">Die folgenden Codezeilen werden ungültige Deklarationen dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="7c327-114">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a><span data-ttu-id="7c327-115">Zugreifen auf ein Array außerhalb des gültigen Bereichs</span><span class="sxs-lookup"><span data-stu-id="7c327-115">Accessing an Array Out of Bounds</span></span>  
 <span data-ttu-id="7c327-116">Der Prozess der Initialisierung ein Array weist eine Obergrenze und eine Untergrenze für jede Dimension.</span><span class="sxs-lookup"><span data-stu-id="7c327-116">The process of initializing an array assigns an upper bound and a lower bound to each dimension.</span></span> <span data-ttu-id="7c327-117">Bei jedem Zugriff auf ein Element des Arrays muss ein gültiger Index oder Feldindex, für eine Dimension angeben.</span><span class="sxs-lookup"><span data-stu-id="7c327-117">Every access to an element of the array must specify a valid index, or subscript, for every dimension.</span></span> <span data-ttu-id="7c327-118">Wenn ein Index niedriger als die Untergrenze oder höher als die Obergrenze ist ein <xref:System.IndexOutOfRangeException>Ausnahmeergebnisse.</xref:System.IndexOutOfRangeException></span><span class="sxs-lookup"><span data-stu-id="7c327-118">If any index is below its lower bound or above its upper bound, an <xref:System.IndexOutOfRangeException> exception results.</span></span> <span data-ttu-id="7c327-119">Der Compiler kann einen derartigen Fehler nicht erkennen, sodass zur Laufzeit ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="7c327-119">The compiler cannot detect such an error, so an error occurs at run time.</span></span>  
  
### <a name="determining-bounds"></a><span data-ttu-id="7c327-120">Bestimmen von Grenzen</span><span class="sxs-lookup"><span data-stu-id="7c327-120">Determining Bounds</span></span>  
 <span data-ttu-id="7c327-121">Wenn eine andere Komponente ein Array an den Code übergeben, wissen z. B. als Prozedurarguments, Sie nicht die Größe des Arrays oder die Länge der Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="7c327-121">If another component passes an array to your code, for example as a procedure argument, you do not know the size of that array or the lengths of its dimensions.</span></span> <span data-ttu-id="7c327-122">Sie sollten immer die Obergrenze für jede Dimension eines Arrays bestimmen, bevor Sie versuchen, Zugriff auf alle Elemente.</span><span class="sxs-lookup"><span data-stu-id="7c327-122">You should always determine the upper bound for every dimension of an array before you attempt to access any elements.</span></span> <span data-ttu-id="7c327-123">Wenn das Array als Weise erstellt wurde eine [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `New` -Klausel, die Untergrenze möglicherweise etwas anderes als 0, und es ist am sichersten, die Untergrenze ebenfalls zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="7c327-123">If the array has been created by some means other than a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `New` clause, the lower bound might be something other than 0, and it is safest to determine that lower bound as well.</span></span>  
  
### <a name="specifying-the-dimension"></a><span data-ttu-id="7c327-124">Angeben der Dimension</span><span class="sxs-lookup"><span data-stu-id="7c327-124">Specifying the Dimension</span></span>  
 <span data-ttu-id="7c327-125">Wenn Sie die Grenzen eines mehrdimensionalen Arrays bestimmen, achten Sie wie Sie die Dimension angeben.</span><span class="sxs-lookup"><span data-stu-id="7c327-125">When determining the bounds of a multidimensional array, take care how you specify the dimension.</span></span> <span data-ttu-id="7c327-126">Die `dimension` Parameter der <xref:System.Array.GetLowerBound%2A>und <xref:System.Array.GetUpperBound%2A>Methoden sind 0-basiert, während die `Rank` Parameter von der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Information.LBound%2A>und <xref:Microsoft.VisualBasic.Information.UBound%2A>Funktionen sind 1-basiert.</xref:Microsoft.VisualBasic.Information.UBound%2A> </xref:Microsoft.VisualBasic.Information.LBound%2A> </xref:System.Array.GetUpperBound%2A> </xref:System.Array.GetLowerBound%2A></span><span class="sxs-lookup"><span data-stu-id="7c327-126">The `dimension` parameters of the <xref:System.Array.GetLowerBound%2A> and <xref:System.Array.GetUpperBound%2A> methods are 0-based, while the `Rank` parameters of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Information.LBound%2A> and <xref:Microsoft.VisualBasic.Information.UBound%2A> functions are 1-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c327-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c327-127">See Also</span></span>  
 <span data-ttu-id="7c327-128">[Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="7c327-128">[Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md) </span></span>  
<span data-ttu-id="7c327-129"> [Gewusst wie: Initialisieren einer Arrayvariablen in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)</span><span class="sxs-lookup"><span data-stu-id="7c327-129"> [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)</span></span>
