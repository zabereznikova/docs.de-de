---
title: Arrays, die als Strukturmember deklariert sind, können nicht mit einer vorgegebenen Größe definiert werden.
ms.date: 07/20/2015
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
ms.openlocfilehash: 06e5e36f3e0522e0449c0ef9698f3a1b01b9cb5f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549066"
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a>Arrays, die als Strukturmember deklariert sind, können nicht mit einer vorgegebenen Größe definiert werden.
Ein Array in einer Struktur wird mit einer vorgegebenen Größe deklariert. Jedes Strukturelement kann nicht initialisiert, und deklarieren eine Arraygröße ist eine Form der Initialisierung.  
  
 **Fehler-ID:** BC31043  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Definieren Sie das Array als dynamisches (keine anfängliche Größe) in Ihrer Struktur.  
  
2.  Wenn Sie eine bestimmte Größe des Arrays benötigen, können Sie ein dynamisches Array mit dimensionieren eine [ReDim-Anweisung](../../../visual-basic/language-reference/statements/redim-statement.md) Wenn Ihr Code ausgeführt wird. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
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
- [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Vorgehensweise: Deklarieren einer Struktur](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
