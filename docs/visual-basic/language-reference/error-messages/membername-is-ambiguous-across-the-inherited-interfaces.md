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
# <a name="membername-is-ambiguous-across-the-inherited-interfaces-interfacename1-and-interfacename2"></a>\<membername> ist nicht eindeutig. Er wird sowohl in der geerbten Schnittstelle "\<interfacename1>" als auch in "\<interfacename2>" verwendet.
Die-Schnittstelle erbt mindestens zwei Member mit demselben Namen von mehreren Schnittstellen.  
  
 **Fehler-ID:** BC30685  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Wandeln Sie den Wert in die Basisschnittstelle um, die Sie verwenden möchten. Zum Beispiel:  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Schnittstellen](../../programming-guide/language-features/interfaces/index.md)
