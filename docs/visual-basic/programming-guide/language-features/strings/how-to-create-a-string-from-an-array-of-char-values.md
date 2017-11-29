---
title: 'Gewusst wie: Erstellen einer Zeichenfolge aus einem Array mit Char-Werten (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 06e5c6923c26f3cb84b38475d6680523853d727d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a><span data-ttu-id="68a2f-102">Gewusst wie: Erstellen einer Zeichenfolge aus einem Array mit Char-Werten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68a2f-102">How to: Create a String from An Array of Char Values (Visual Basic)</span></span>
<span data-ttu-id="68a2f-103">In diesem Beispiel erstellt die Zeichenfolge "Abcd" aus einzelnen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="68a2f-103">This example creates the string "abcd" from individual characters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68a2f-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="68a2f-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#61](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-a-string-from-an-array-of-char-values_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="68a2f-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="68a2f-105">Compiling the Code</span></span>  
 <span data-ttu-id="68a2f-106">Diese Methode hat keine besonderen Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="68a2f-106">This method has no special requirements.</span></span>  
  
 <span data-ttu-id="68a2f-107">Die Syntax `"a"c`, wobei eine einzelne `c` ein einzelnes Zeichen in Anführungszeichen folgt, wird verwendet, um ein Zeichenliteral erstellt.</span><span class="sxs-lookup"><span data-stu-id="68a2f-107">The syntax `"a"c`, where a single `c` follows a single character in quotation marks, is used to create a character literal.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="68a2f-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="68a2f-108">Robust Programming</span></span>  
 <span data-ttu-id="68a2f-109">NULL-Zeichen (entspricht `Chr(0)`) in der Zeichenfolge nach zu unerwarteten Ergebnissen führen, wenn die Zeichenfolge verwenden.</span><span class="sxs-lookup"><span data-stu-id="68a2f-109">Null characters (equivalent to `Chr(0)`) in the string lead to unexpected results when using the string.</span></span> <span data-ttu-id="68a2f-110">Das Null-Zeichen werden mit der Zeichenfolge enthalten, aber das Nullzeichen folgen Zeichen in einigen Situationen nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="68a2f-110">The null character will be included with the string, but characters following the null character will not be displayed in some situations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68a2f-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68a2f-111">See Also</span></span>  
 <xref:System.String>  
 [<span data-ttu-id="68a2f-112">Char-Datentyp</span><span class="sxs-lookup"><span data-stu-id="68a2f-112">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)  
 [<span data-ttu-id="68a2f-113">Datentypen</span><span class="sxs-lookup"><span data-stu-id="68a2f-113">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
