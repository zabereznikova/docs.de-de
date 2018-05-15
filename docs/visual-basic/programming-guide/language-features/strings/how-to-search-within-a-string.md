---
title: 'Gewusst wie: Suchen innerhalb einer Zeichenfolge (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: 08a005f2927a76c9b29c1ff0092ea8282188b2b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-search-within-a-string-visual-basic"></a><span data-ttu-id="4a7a9-102">Gewusst wie: Suchen innerhalb einer Zeichenfolge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a7a9-102">How to: Search Within a String (Visual Basic)</span></span>
<span data-ttu-id="4a7a9-103">Dieses Beispiel ruft die <xref:System.String.IndexOf%2A> Methode auf eine <xref:System.String> Objekt, das den Index des ersten Vorkommens einer Teilzeichenfolge gemeldet.</span><span class="sxs-lookup"><span data-stu-id="4a7a9-103">This example calls the <xref:System.String.IndexOf%2A> method on a <xref:System.String> object to report the index of the first occurrence of a substring.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a7a9-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4a7a9-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#71](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-search-within-a-string_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4a7a9-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="4a7a9-105">Compiling the Code</span></span>  
 <span data-ttu-id="4a7a9-106">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4a7a9-106">This example requires:</span></span>  
  
-   <span data-ttu-id="4a7a9-107">Ein `Imports` Anweisung Angabe der <xref:System> Namespace.</span><span class="sxs-lookup"><span data-stu-id="4a7a9-107">An `Imports` statement specifying the <xref:System> namespace.</span></span> <span data-ttu-id="4a7a9-108">Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="4a7a9-108">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4a7a9-109">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="4a7a9-109">Robust Programming</span></span>  
 <span data-ttu-id="4a7a9-110">Die <xref:System.String.IndexOf%2A> -Methode gibt den Speicherort des ersten Zeichens des ersten Vorkommens der Teilzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4a7a9-110">The <xref:System.String.IndexOf%2A> method reports the location of the first character of the first occurrence of the substring.</span></span> <span data-ttu-id="4a7a9-111">Der Index ist 0-basierte, was bedeutet, dass das erste Zeichen einer Zeichenfolge mit den Index 0 hat.</span><span class="sxs-lookup"><span data-stu-id="4a7a9-111">The index is 0-based, which means the first character of a string has an index of 0.</span></span>  
  
 <span data-ttu-id="4a7a9-112">Wenn <xref:System.String.IndexOf%2A> findet nicht die Teilzeichenfolge, wird-1 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4a7a9-112">If <xref:System.String.IndexOf%2A> does not find the substring, it returns -1.</span></span>  
  
 <span data-ttu-id="4a7a9-113">Die <xref:System.String.IndexOf%2A> Methode Groß-/Kleinschreibung beachtet, und die aktuelle Kultur verwendet.</span><span class="sxs-lookup"><span data-stu-id="4a7a9-113">The <xref:System.String.IndexOf%2A> method is case-sensitive and uses the current culture.</span></span>  
  
 <span data-ttu-id="4a7a9-114">Für eine optimale Fehlersteuerung, möchten Sie möglicherweise die Zeichenfolgensuche in der `Try` -Block ein [versuchen... Catch... Finally-Anweisung](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) Konstruktion.</span><span class="sxs-lookup"><span data-stu-id="4a7a9-114">For optimal error control, you might want to enclose the string search in the `Try` block of a [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) construction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a7a9-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a7a9-115">See Also</span></span>  
 <xref:System.String.IndexOf%2A>  
 [<span data-ttu-id="4a7a9-116">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4a7a9-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="4a7a9-117">Einführung in Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4a7a9-117">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)  
 [<span data-ttu-id="4a7a9-118">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="4a7a9-118">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
