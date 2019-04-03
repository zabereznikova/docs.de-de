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
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58820856"
---
# <a name="membername-is-ambiguous-across-the-inherited-interfaces-interfacename1-and-interfacename2"></a>'\<Membername >' ist mehrdeutig, in der geerbten Schnittstelle\<schnittstellenname1 >' und '\<schnittstellenname2 >'
Die Schnittstelle erbt mindestens zwei Elemente mit dem gleichen Namen von mehreren Schnittstellen.  
  
 **Fehler-ID:** BC30685  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wandeln Sie den Wert für die Basisschnittstelle, die Sie verwenden möchten; Zum Beispiel:  
  
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
  
## <a name="see-also"></a>Siehe auch

- [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
