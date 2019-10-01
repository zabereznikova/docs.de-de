---
title: Ein Array, das als For-Schleifensteuerungsvariable deklariert ist, kann nicht mit einer vorgegebenen Größe deklariert werden.
ms.date: 07/20/2015
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords:
- BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
ms.openlocfilehash: 9e8bb7b79b5a770c3c92e47d8e7c01c5b83d6061
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701210"
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="20cce-102">Ein Array, das als For-Schleifensteuerungsvariable deklariert ist, kann nicht mit einer vorgegebenen Größe deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="20cce-102">Array declared as for loop control variable cannot be declared with an initial size</span></span>
<span data-ttu-id="20cce-103">Eine `For Each`-Schleife verwendet ein Array als *Element* Iterations Variable, aber initialisiert dieses Array.</span><span class="sxs-lookup"><span data-stu-id="20cce-103">A `For Each` loop uses an array as its *element* iteration variable but initializes that array.</span></span>  
  
 <span data-ttu-id="20cce-104">Die folgenden Anweisungen zeigen, wie dieser Fehler generiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="20cce-104">The following statements show how this error can be generated.</span></span>  
  
```vb  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 <span data-ttu-id="20cce-105">Die erste `For Each`-Anweisung ist die richtige Methode für den Zugriff auf Elemente von `arrayList`.</span><span class="sxs-lookup"><span data-stu-id="20cce-105">The first `For Each` statement is the correct way to access elements of `arrayList`.</span></span> <span data-ttu-id="20cce-106">Der zweite `For Each`-Anweisung generiert diesen Fehler.</span><span class="sxs-lookup"><span data-stu-id="20cce-106">The second `For Each` statement generates this error.</span></span>  
  
 <span data-ttu-id="20cce-107">**Fehler-ID:** BC32039</span><span class="sxs-lookup"><span data-stu-id="20cce-107">**Error ID:** BC32039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="20cce-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="20cce-108">To correct this error</span></span>  
  
- <span data-ttu-id="20cce-109">Entfernen Sie die Initialisierung aus der Deklaration der *elementiterations* -Variablen.</span><span class="sxs-lookup"><span data-stu-id="20cce-109">Remove the initialization from the declaration of the *element* iteration variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20cce-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20cce-110">See also</span></span>

- [<span data-ttu-id="20cce-111">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="20cce-111">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="20cce-112">Arrays</span><span class="sxs-lookup"><span data-stu-id="20cce-112">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="20cce-113">Sammlungen</span><span class="sxs-lookup"><span data-stu-id="20cce-113">Collections</span></span>](../../../standard/collections/index.md)
