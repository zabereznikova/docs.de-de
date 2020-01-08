---
title: 'Gewusst wie: Erstellen einer Zeichenfolge aus einem Array mit Char-Werten'
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: bf37ceba901e712df10ad4b39f9ad74194843136
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346773"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a><span data-ttu-id="86ae2-102">Gewusst wie: Erstellen einer Zeichenfolge aus einem Array mit Char-Werten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86ae2-102">How to: Create a String from An Array of Char Values (Visual Basic)</span></span>
<span data-ttu-id="86ae2-103">In diesem Beispiel wird die Zeichenfolge "abcd" aus einzelnen Zeichen erstellt.</span><span class="sxs-lookup"><span data-stu-id="86ae2-103">This example creates the string "abcd" from individual characters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86ae2-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="86ae2-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="86ae2-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="86ae2-105">Compile the code</span></span>  
 <span data-ttu-id="86ae2-106">Diese Methode hat keine besonderen Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="86ae2-106">This method has no special requirements.</span></span>  
  
 <span data-ttu-id="86ae2-107">Die Syntax `"a"c`, bei der ein einzelner `c` einem einzelnen Zeichen in Anführungszeichen folgt, wird zum Erstellen eines Zeichenliterals verwendet.</span><span class="sxs-lookup"><span data-stu-id="86ae2-107">The syntax `"a"c`, where a single `c` follows a single character in quotation marks, is used to create a character literal.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="86ae2-108">Robuste Programmierung</span><span class="sxs-lookup"><span data-stu-id="86ae2-108">Robust Programming</span></span>  
 <span data-ttu-id="86ae2-109">NULL-Zeichen (äquivalent zu `Chr(0)`) in der Zeichenfolge führen zu unerwarteten Ergebnissen, wenn die Zeichenfolge verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="86ae2-109">Null characters (equivalent to `Chr(0)`) in the string lead to unexpected results when using the string.</span></span> <span data-ttu-id="86ae2-110">Das NULL-Zeichen wird in die Zeichenfolge eingeschlossen, jedoch werden Zeichen, die auf das NULL-Zeichen folgen, in einigen Situationen nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="86ae2-110">The null character will be included with the string, but characters following the null character will not be displayed in some situations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86ae2-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86ae2-111">See also</span></span>

- <xref:System.String>
- [<span data-ttu-id="86ae2-112">Char-Datentyp</span><span class="sxs-lookup"><span data-stu-id="86ae2-112">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="86ae2-113">Datentypen</span><span class="sxs-lookup"><span data-stu-id="86ae2-113">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
