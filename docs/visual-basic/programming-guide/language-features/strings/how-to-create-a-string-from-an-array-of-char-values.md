---
title: 'Vorgehensweise: Erstellen einer Zeichenfolge aus einem Array mit Char-Werten'
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: d9ec897467f0caac0afc089a028516c0316a2bda
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410592"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a><span data-ttu-id="c3bb5-102">Gewusst wie: Erstellen einer Zeichenfolge aus einem Array mit Char-Werten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c3bb5-102">How to: Create a String from An Array of Char Values (Visual Basic)</span></span>
<span data-ttu-id="c3bb5-103">In diesem Beispiel wird die Zeichenfolge "abcd" aus einzelnen Zeichen erstellt.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-103">This example creates the string "abcd" from individual characters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3bb5-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3bb5-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="c3bb5-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="c3bb5-105">Compile the code</span></span>  
 <span data-ttu-id="c3bb5-106">Diese Methode hat keine besonderen Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-106">This method has no special requirements.</span></span>  
  
 <span data-ttu-id="c3bb5-107">Die Syntax `"a"c` , bei der ein einzelnes `c` einem einzelnen Zeichen in Anführungszeichen folgt, wird zum Erstellen eines Zeichenliterals verwendet.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-107">The syntax `"a"c`, where a single `c` follows a single character in quotation marks, is used to create a character literal.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c3bb5-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="c3bb5-108">Robust Programming</span></span>  
 <span data-ttu-id="c3bb5-109">NULL-Zeichen (äquivalent zu `Chr(0)` ) in der Zeichenfolge führen zu unerwarteten Ergebnissen, wenn die Zeichenfolge verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-109">Null characters (equivalent to `Chr(0)`) in the string lead to unexpected results when using the string.</span></span> <span data-ttu-id="c3bb5-110">Das NULL-Zeichen wird in die Zeichenfolge eingeschlossen, jedoch werden Zeichen, die auf das NULL-Zeichen folgen, in einigen Situationen nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c3bb5-110">The null character will be included with the string, but characters following the null character will not be displayed in some situations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3bb5-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c3bb5-111">See also</span></span>

- <xref:System.String>
- [<span data-ttu-id="c3bb5-112">Char-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c3bb5-112">Char Data Type</span></span>](../../../language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="c3bb5-113">Datentypen</span><span class="sxs-lookup"><span data-stu-id="c3bb5-113">Data Types</span></span>](../data-types/index.md)
