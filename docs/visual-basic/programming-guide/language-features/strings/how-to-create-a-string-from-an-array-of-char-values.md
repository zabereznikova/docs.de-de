---
title: 'Vorgehensweise: Erstellen Sie eine Zeichenfolge aus einem Array von Char-Werten (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: a067474d6b32589a34b031d5c3ea4e5a4be55834
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611461"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a><span data-ttu-id="f1bad-102">Vorgehensweise: Erstellen Sie eine Zeichenfolge aus einem Array von Char-Werten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1bad-102">How to: Create a String from An Array of Char Values (Visual Basic)</span></span>
<span data-ttu-id="f1bad-103">Dieses Beispiel erstellt die Zeichenfolge "Abcd" aus einzelnen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f1bad-103">This example creates the string "abcd" from individual characters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1bad-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f1bad-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#61](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-a-string-from-an-array-of-char-values_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f1bad-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="f1bad-105">Compiling the Code</span></span>  
 <span data-ttu-id="f1bad-106">Diese Methode hat keine besonderen Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="f1bad-106">This method has no special requirements.</span></span>  
  
 <span data-ttu-id="f1bad-107">Die Syntax `"a"c`, bei dem ein einzelnes `c` basiert auf ein einzelnes Zeichen in Anführungszeichen einschließen, wird verwendet, um ein Zeichenliteral erstellt.</span><span class="sxs-lookup"><span data-stu-id="f1bad-107">The syntax `"a"c`, where a single `c` follows a single character in quotation marks, is used to create a character literal.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f1bad-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="f1bad-108">Robust Programming</span></span>  
 <span data-ttu-id="f1bad-109">NULL-Zeichen (Äquivalent zu `Chr(0)`) in der Zeichenfolge nach zu unerwarteten Ergebnissen führen, wenn Sie die Zeichenfolge verwenden.</span><span class="sxs-lookup"><span data-stu-id="f1bad-109">Null characters (equivalent to `Chr(0)`) in the string lead to unexpected results when using the string.</span></span> <span data-ttu-id="f1bad-110">Das Null-Zeichen werden in der Zeichenfolge enthalten, aber das Nullzeichen folgen Zeichen in einigen Fällen nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f1bad-110">The null character will be included with the string, but characters following the null character will not be displayed in some situations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1bad-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1bad-111">See also</span></span>
- <xref:System.String>
- [<span data-ttu-id="f1bad-112">Char-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f1bad-112">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="f1bad-113">Datentypen</span><span class="sxs-lookup"><span data-stu-id="f1bad-113">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
