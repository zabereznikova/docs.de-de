---
title: Arrays, die als Strukturmember deklariert sind, können nicht mit einer vorgegebenen Größe definiert werden.
ms.date: 07/20/2015
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
ms.openlocfilehash: 83342b780c0fa7c3a2e0a6797b80ef788117ae92
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250154"
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a>Arrays, die als Strukturmember deklariert sind, können nicht mit einer vorgegebenen Größe definiert werden.

Ein Array in einer Struktur wird mit einer Anfangs Größe deklariert. Sie können kein Strukturelement initialisieren, und das Deklarieren einer Array Größe ist eine Form der Initialisierung.

**Fehler-ID:** BC31043

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird BC31043 generiert:

```vb
Structure DemoStruct
    Public demoArray(9) As Integer
End Structure
```

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Definieren Sie das Array in der Struktur als dynamisch (keine anfängliche Größe).

2. Wenn Sie eine bestimmte Array Größe benötigen, können Sie ein dynamisches Array mit einer [ReDim-Anweisung](../statements/redim-statement.md) redimensionen, wenn der Code ausgeführt wird. Dies wird anhand des folgenden Beispiels veranschaulicht:
  
    ```vb
    Structure DemoStruct
        Public demoArray() As Integer
    End Structure
    Sub UseStruct()
        Dim struct As DemoStruct  
        ReDim struct.demoArray(9)
        Struct.demoArray(2) = 777
    End Sub  
    ```
  
## <a name="see-also"></a>Siehe auch

- [Arrays](../../programming-guide/language-features/arrays/index.md)
- [Vorgehensweise: Deklarieren einer Struktur](../../programming-guide/language-features/data-types/how-to-declare-a-structure.md)
