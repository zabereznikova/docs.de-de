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
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="5bff0-102">Arrays, die als Strukturmember deklariert sind, können nicht mit einer vorgegebenen Größe definiert werden.</span><span class="sxs-lookup"><span data-stu-id="5bff0-102">Arrays declared as structure members cannot be declared with an initial size</span></span>

<span data-ttu-id="5bff0-103">Ein Array in einer Struktur wird mit einer Anfangs Größe deklariert.</span><span class="sxs-lookup"><span data-stu-id="5bff0-103">An array in a structure is declared with an initial size.</span></span> <span data-ttu-id="5bff0-104">Sie können kein Strukturelement initialisieren, und das Deklarieren einer Array Größe ist eine Form der Initialisierung.</span><span class="sxs-lookup"><span data-stu-id="5bff0-104">You cannot initialize any structure element, and declaring an array size is one form of initialization.</span></span>

<span data-ttu-id="5bff0-105">**Fehler-ID:** BC31043</span><span class="sxs-lookup"><span data-stu-id="5bff0-105">**Error ID:** BC31043</span></span>

## <a name="example"></a><span data-ttu-id="5bff0-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5bff0-106">Example</span></span>

<span data-ttu-id="5bff0-107">Im folgenden Beispiel wird BC31043 generiert:</span><span class="sxs-lookup"><span data-stu-id="5bff0-107">The following example generates BC31043:</span></span>

```vb
Structure DemoStruct
    Public demoArray(9) As Integer
End Structure
```

## <a name="to-correct-this-error"></a><span data-ttu-id="5bff0-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="5bff0-108">To correct this error</span></span>

1. <span data-ttu-id="5bff0-109">Definieren Sie das Array in der Struktur als dynamisch (keine anfängliche Größe).</span><span class="sxs-lookup"><span data-stu-id="5bff0-109">Define the array in your structure as dynamic (no initial size).</span></span>

2. <span data-ttu-id="5bff0-110">Wenn Sie eine bestimmte Array Größe benötigen, können Sie ein dynamisches Array mit einer [ReDim-Anweisung](../statements/redim-statement.md) redimensionen, wenn der Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5bff0-110">If you require a certain size of array, you can redimension a dynamic array with a [ReDim Statement](../statements/redim-statement.md) when your code is running.</span></span> <span data-ttu-id="5bff0-111">Dies wird anhand des folgenden Beispiels veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="5bff0-111">The following example illustrates this:</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="5bff0-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5bff0-112">See also</span></span>

- [<span data-ttu-id="5bff0-113">Arrays</span><span class="sxs-lookup"><span data-stu-id="5bff0-113">Arrays</span></span>](../../programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="5bff0-114">Vorgehensweise: Deklarieren einer Struktur</span><span class="sxs-lookup"><span data-stu-id="5bff0-114">How to: Declare a Structure</span></span>](../../programming-guide/language-features/data-types/how-to-declare-a-structure.md)
