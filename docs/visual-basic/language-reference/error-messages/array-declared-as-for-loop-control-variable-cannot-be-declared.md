---
title: Ein Array, das als For-Schleifensteuerungsvariable deklariert ist, kann nicht mit einer vorgegebenen Größe deklariert werden.
ms.date: 07/20/2015
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords:
- BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
ms.openlocfilehash: d8fe794adcc1c2d28437bac7e732f99a6b6c07c0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518617"
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="4fcfc-102">Ein Array, das als For-Schleifensteuerungsvariable deklariert ist, kann nicht mit einer vorgegebenen Größe deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="4fcfc-102">Array declared as for loop control variable cannot be declared with an initial size</span></span>
<span data-ttu-id="4fcfc-103">Ein `For Each` -Schleife verwendet ein Array als seine *Element* Iterationsvariable initialisiert jedoch dieses Array.</span><span class="sxs-lookup"><span data-stu-id="4fcfc-103">A `For Each` loop uses an array as its *element* iteration variable but initializes that array.</span></span>  
  
 <span data-ttu-id="4fcfc-104">Die folgenden Anweisungen zeigen, wie dieser Fehler generiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="4fcfc-104">The following statements show how this error can be generated.</span></span>  
  
```  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 <span data-ttu-id="4fcfc-105">Die erste `For Each` -Anweisung ist die korrekte Methode zum Zugriff auf Elemente von `arrayList`.</span><span class="sxs-lookup"><span data-stu-id="4fcfc-105">The first `For Each` statement is the correct way to access elements of `arrayList`.</span></span> <span data-ttu-id="4fcfc-106">Die zweite `For Each` -Anweisung generiert diesen Fehler.</span><span class="sxs-lookup"><span data-stu-id="4fcfc-106">The second `For Each` statement generates this error.</span></span>  
  
 <span data-ttu-id="4fcfc-107">**Fehler-ID:** BC32039</span><span class="sxs-lookup"><span data-stu-id="4fcfc-107">**Error ID:** BC32039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4fcfc-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="4fcfc-108">To correct this error</span></span>  
  
-   <span data-ttu-id="4fcfc-109">Entfernen Sie die Initialisierung aus der Deklaration der *Element* Iterationsvariable.</span><span class="sxs-lookup"><span data-stu-id="4fcfc-109">Remove the initialization from the declaration of the *element* iteration variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fcfc-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4fcfc-110">See also</span></span>
- [<span data-ttu-id="4fcfc-111">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4fcfc-111">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="4fcfc-112">Arrays</span><span class="sxs-lookup"><span data-stu-id="4fcfc-112">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="4fcfc-113">Sammlungen</span><span class="sxs-lookup"><span data-stu-id="4fcfc-113">Collections</span></span>](../../../standard/collections/index.md)
