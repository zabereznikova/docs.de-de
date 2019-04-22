---
title: <membername> ist nicht eindeutig. Er wird sowohl in der geerbten Schnittstelle "<interfacename1>" als auch in "<interfacename2>" verwendet.
ms.date: 07/20/2015
f1_keywords:
- vbc30685
- bc30685
helpviewer_keywords:
- BC30685
ms.assetid: 756add7a-23d5-4b4f-a48d-8297d6459c73
ms.openlocfilehash: 4415608bcfca63b43b3d9ebf17ce622ccd418775
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58820856"
---
# <a name="membername-is-ambiguous-across-the-inherited-interfaces-interfacename1-and-interfacename2"></a><span data-ttu-id="f29a8-102">'\<Membername >' ist mehrdeutig, in der geerbten Schnittstelle\<schnittstellenname1 >' und '\<schnittstellenname2 >'</span><span class="sxs-lookup"><span data-stu-id="f29a8-102">'\<membername>' is ambiguous across the inherited interfaces '\<interfacename1>' and '\<interfacename2>'</span></span>
<span data-ttu-id="f29a8-103">Die Schnittstelle erbt mindestens zwei Elemente mit dem gleichen Namen von mehreren Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="f29a8-103">The interface inherits two or more members with the same name from multiple interfaces.</span></span>  
  
 <span data-ttu-id="f29a8-104">**Fehler-ID:** BC30685</span><span class="sxs-lookup"><span data-stu-id="f29a8-104">**Error ID:** BC30685</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f29a8-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="f29a8-105">To correct this error</span></span>  
  
-   <span data-ttu-id="f29a8-106">Wandeln Sie den Wert für die Basisschnittstelle, die Sie verwenden möchten; Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f29a8-106">Cast the value to the base interface that you want to use; for example:</span></span>  
  
    ```  
    Interface Left  
        Sub MySub()  
    End Interface  
  
    Interface Right  
        Sub MySub()  
    End Interface  
  
    Interface LeftRight  
        Inherits Left, Right  
    End Interface  
  
    Module test  
        Sub Main()  
            Dim x As LeftRight  
            ' x.MySub()  'x is ambiguous.  
            CType(x, Left).MySub() ' Cast to base type.  
            CType(x, Right).MySub() ' Call the other base type.  
        End Sub  
    End Module  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f29a8-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f29a8-107">See also</span></span>

- [<span data-ttu-id="f29a8-108">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f29a8-108">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
