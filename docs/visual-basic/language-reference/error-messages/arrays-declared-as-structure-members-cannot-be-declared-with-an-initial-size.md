---
title: Arrays, die als Strukturmember deklariert sind, können nicht mit einer vorgegebenen Größe definiert werden.
ms.date: 07/20/2015
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
ms.openlocfilehash: 58889809b3d8d0823784279c421a141dc8056984
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841965"
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="c013f-102">Arrays, die als Strukturmember deklariert sind, können nicht mit einer vorgegebenen Größe definiert werden.</span><span class="sxs-lookup"><span data-stu-id="c013f-102">Arrays declared as structure members cannot be declared with an initial size</span></span>
<span data-ttu-id="c013f-103">Ein Array in einer Struktur wird mit einer vorgegebenen Größe deklariert.</span><span class="sxs-lookup"><span data-stu-id="c013f-103">An array in a structure is declared with an initial size.</span></span> <span data-ttu-id="c013f-104">Jedes Strukturelement kann nicht initialisiert, und deklarieren eine Arraygröße ist eine Form der Initialisierung.</span><span class="sxs-lookup"><span data-stu-id="c013f-104">You cannot initialize any structure element, and declaring an array size is one form of initialization.</span></span>  
  
 <span data-ttu-id="c013f-105">**Fehler-ID:** BC31043</span><span class="sxs-lookup"><span data-stu-id="c013f-105">**Error ID:** BC31043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c013f-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="c013f-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="c013f-107">Definieren Sie das Array als dynamisches (keine anfängliche Größe) in Ihrer Struktur.</span><span class="sxs-lookup"><span data-stu-id="c013f-107">Define the array in your structure as dynamic (no initial size).</span></span>  
  
2.  <span data-ttu-id="c013f-108">Wenn Sie eine bestimmte Größe des Arrays benötigen, können Sie ein dynamisches Array mit dimensionieren eine [ReDim-Anweisung](../../../visual-basic/language-reference/statements/redim-statement.md) Wenn Ihr Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c013f-108">If you require a certain size of array, you can redimension a dynamic array with a [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md) when your code is running.</span></span> <span data-ttu-id="c013f-109">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c013f-109">The following example illustrates this.</span></span>  
  
    ```  
    Structure demoStruct  
        Public demoArray() As Integer  
    End Structure  
    Sub useStruct()  
        Dim struct As demoStruct  
        ReDim struct.demoArray(9)  
        Struct.demoArray(2) = 777  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c013f-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c013f-110">See also</span></span>

- [<span data-ttu-id="c013f-111">Arrays</span><span class="sxs-lookup"><span data-stu-id="c013f-111">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="c013f-112">Vorgehensweise: Deklarieren einer Struktur</span><span class="sxs-lookup"><span data-stu-id="c013f-112">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
