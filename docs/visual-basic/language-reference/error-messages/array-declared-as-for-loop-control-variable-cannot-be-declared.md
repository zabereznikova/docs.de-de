---
title: "Ein Array, das als For-Schleifensteuerungsvariable deklariert ist, kann nicht mit einer vorgegebenen Größe deklariert werden."
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords: BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0635e1b18b24a241fabad6d67da34f8dde9530db
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="489d5-102">Ein Array, das als For-Schleifensteuerungsvariable deklariert ist, kann nicht mit einer vorgegebenen Größe deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="489d5-102">Array declared as for loop control variable cannot be declared with an initial size</span></span>
<span data-ttu-id="489d5-103">Ein `For Each` Schleife verwendet ein Array als seine *Element* Iterationsvariable aber das Array initialisiert.</span><span class="sxs-lookup"><span data-stu-id="489d5-103">A `For Each` loop uses an array as its *element* iteration variable but initializes that array.</span></span>  
  
 <span data-ttu-id="489d5-104">Die folgenden Anweisungen zeigen, wie dieser Fehler generiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="489d5-104">The following statements show how this error can be generated.</span></span>  
  
```  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 <span data-ttu-id="489d5-105">Die erste `For Each` -Anweisung ist die richtige Methode zum Zugriff auf Elemente des `arrayList`.</span><span class="sxs-lookup"><span data-stu-id="489d5-105">The first `For Each` statement is the correct way to access elements of `arrayList`.</span></span> <span data-ttu-id="489d5-106">Die zweite `For Each` -Anweisung generiert diesen Fehler.</span><span class="sxs-lookup"><span data-stu-id="489d5-106">The second `For Each` statement generates this error.</span></span>  
  
 <span data-ttu-id="489d5-107">**Fehler-ID:** BC32039</span><span class="sxs-lookup"><span data-stu-id="489d5-107">**Error ID:** BC32039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="489d5-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="489d5-108">To correct this error</span></span>  
  
-   <span data-ttu-id="489d5-109">Entfernen Sie die Initialisierung aus der Deklaration der *Element* Iterationsvariable.</span><span class="sxs-lookup"><span data-stu-id="489d5-109">Remove the initialization from the declaration of the *element* iteration variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="489d5-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="489d5-110">See Also</span></span>  
 [<span data-ttu-id="489d5-111">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="489d5-111">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="489d5-112">Arrays</span><span class="sxs-lookup"><span data-stu-id="489d5-112">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="489d5-113">Sammlungen</span><span class="sxs-lookup"><span data-stu-id="489d5-113">Collections</span></span>](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)
