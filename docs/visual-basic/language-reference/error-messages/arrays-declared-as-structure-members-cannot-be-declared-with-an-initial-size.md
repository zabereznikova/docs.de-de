---
title: Arrays, die als Strukturmember deklariert sind, können nicht mit einer vorgegebenen Größe definiert werden.
ms.date: 07/20/2015
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
ms.openlocfilehash: 0a7424e5dbfadd78c4071ba5b76086b7f6c9b94a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585852"
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a>Arrays, die als Strukturmember deklariert sind, können nicht mit einer vorgegebenen Größe definiert werden.
Ein Array in einer Struktur wird mit einer vorgegebenen Größe deklariert. Sie können nicht initialisiert werden, ein Strukturelement, und deklarieren eine Arraygröße ist eine Form der Initialisierung.  
  
 **Fehler-ID:** BC31043  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Definieren Sie das Array in der Struktur als Dynamic (keine Anfangsgröße).  
  
2.  Wenn Sie eine bestimmte Größe des Arrays benötigen, können Sie dimensionieren ein dynamisches Arrays mit einer [ReDim-Anweisung](../../../visual-basic/language-reference/statements/redim-statement.md) Wenn Ihr Code ausgeführt wird. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Gewusst wie: Deklarieren einer Struktur](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
