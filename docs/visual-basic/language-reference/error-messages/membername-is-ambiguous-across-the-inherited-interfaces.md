---
title: <membername> ist nicht eindeutig. Er wird sowohl in der geerbten Schnittstelle "<interfacename1>" als auch in "<interfacename2>" verwendet.
ms.date: 07/20/2015
f1_keywords:
- vbc30685
- bc30685
helpviewer_keywords:
- BC30685
ms.assetid: 756add7a-23d5-4b4f-a48d-8297d6459c73
ms.openlocfilehash: f242db9e02a1983e731dce280be0e8f8a8b12712
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397271"
---
# <a name="membername-is-ambiguous-across-the-inherited-interfaces-interfacename1-and-interfacename2"></a><span data-ttu-id="75e7f-102">\<membername> ist nicht eindeutig. Er wird sowohl in der geerbten Schnittstelle "\<interfacename1>" als auch in "\<interfacename2>" verwendet.</span><span class="sxs-lookup"><span data-stu-id="75e7f-102">'\<membername>' is ambiguous across the inherited interfaces '\<interfacename1>' and '\<interfacename2>'</span></span>
<span data-ttu-id="75e7f-103">Die-Schnittstelle erbt mindestens zwei Member mit demselben Namen von mehreren Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="75e7f-103">The interface inherits two or more members with the same name from multiple interfaces.</span></span>  
  
 <span data-ttu-id="75e7f-104">**Fehler-ID:** BC30685</span><span class="sxs-lookup"><span data-stu-id="75e7f-104">**Error ID:** BC30685</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="75e7f-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="75e7f-105">To correct this error</span></span>  
  
- <span data-ttu-id="75e7f-106">Wandeln Sie den Wert in die Basisschnittstelle um, die Sie verwenden möchten. Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="75e7f-106">Cast the value to the base interface that you want to use; for example:</span></span>  
  
    ```vb  
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
  
## <a name="see-also"></a><span data-ttu-id="75e7f-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="75e7f-107">See also</span></span>

- [<span data-ttu-id="75e7f-108">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="75e7f-108">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
