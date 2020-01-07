---
title: 'Gewusst wie: Suchen innerhalb einer Zeichenfolge'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: 655f746e4e496e1935afcd2a9f9fe36d9e3a2564
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348422"
---
# <a name="how-to-search-within-a-string-visual-basic"></a><span data-ttu-id="8f9e5-102">Gewusst wie: Suchen innerhalb einer Zeichenfolge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f9e5-102">How to: search within a string (Visual Basic)</span></span>

<span data-ttu-id="8f9e5-103">Dieser Artikel zeigt ein Beispiel für die Suche in einer Zeichenfolge in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8f9e5-103">This article shows an example of how to search within a string in Visual Basic.</span></span>

## <a name="example"></a><span data-ttu-id="8f9e5-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f9e5-104">Example</span></span>

<span data-ttu-id="8f9e5-105">In diesem Beispiel wird die <xref:System.String.IndexOf%2A>-Methode für ein <xref:System.String> Objekt aufgerufen, um den Index des ersten Vorkommens einer Teil Zeichenfolge zu melden:</span><span class="sxs-lookup"><span data-stu-id="8f9e5-105">This example calls the <xref:System.String.IndexOf%2A> method on a <xref:System.String> object to report the index of the first occurrence of a substring:</span></span>

 [!code-vb[VbVbalrStrings#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#71)]

## <a name="robust-programming"></a><span data-ttu-id="8f9e5-106">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="8f9e5-106">Robust programming</span></span>

<span data-ttu-id="8f9e5-107">Die <xref:System.String.IndexOf%2A>-Methode gibt den Speicherort des ersten Zeichens des ersten Vorkommens der Teil Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="8f9e5-107">The <xref:System.String.IndexOf%2A> method returns the location of the first character of the first occurrence of the substring.</span></span> <span data-ttu-id="8f9e5-108">Der Index ist 0-basiert, was bedeutet, dass das erste Zeichen einer Zeichenfolge einen Index von 0 aufweist.</span><span class="sxs-lookup"><span data-stu-id="8f9e5-108">The index is 0-based, which means the first character of a string has an index of 0.</span></span>

<span data-ttu-id="8f9e5-109">Wenn die Teil Zeichenfolge von <xref:System.String.IndexOf%2A> nicht gefunden wird, wird-1 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8f9e5-109">If <xref:System.String.IndexOf%2A> does not find the substring, it returns -1.</span></span>

<span data-ttu-id="8f9e5-110">Bei der <xref:System.String.IndexOf%2A>-Methode wird die Groß-/Kleinschreibung beachtet und die aktuelle Kultur verwendet.</span><span class="sxs-lookup"><span data-stu-id="8f9e5-110">The <xref:System.String.IndexOf%2A> method is case-sensitive and uses the current culture.</span></span>

<span data-ttu-id="8f9e5-111">Um die optimale Fehler Steuerung zu erzielen, sollten Sie die Zeichen folgen Suche in den `Try`-Block eines [try... Catch... Schließlich ist die Anweisungs](../../../language-reference/statements/try-catch-finally-statement.md) Erstellung.</span><span class="sxs-lookup"><span data-stu-id="8f9e5-111">For optimal error control, you might want to enclose the string search in the `Try` block of a [Try...Catch...Finally Statement](../../../language-reference/statements/try-catch-finally-statement.md) construction.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f9e5-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f9e5-112">See also</span></span>

- <xref:System.String.IndexOf%2A>
- [<span data-ttu-id="8f9e5-113">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8f9e5-113">Try...Catch...Finally Statement</span></span>](../../../language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="8f9e5-114">Einführung in Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8f9e5-114">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
- [<span data-ttu-id="8f9e5-115">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="8f9e5-115">Strings</span></span>](index.md)
