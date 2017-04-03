---
title: "Puffer fester Größe (C#-Programmierhandbuch) | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- fixed size buffers [C#]
- unsafe buffers [C#]
- unsafe code [C#], fixed size buffers
ms.assetid: 6220d454-947c-4977-ac9d-9308c6ed5051
caps.latest.revision: 31
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6c5cacb588dc263e5b72e4b3cd93ad10b4b681f2
ms.lasthandoff: 03/13/2017

---
# <a name="fixed-size-buffers-c-programming-guide"></a>Puffer fester Größe (C#-Programmierhandbuch)
In C# können Sie die [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)-Anweisung verwenden, um einen Puffer mit einem Array fester Größe in einer Datenstruktur zu erstellen. Dies ist hilfreich, wenn Sie mit vorhandenem Code, z.B. Code in anderen Sprachen, bereits vorhandenen DLLs oder COM-Projekten arbeiten. Das Array fester Größe kann sämtliche Attribute und Modifizierer, die für reguläre Strukturmember zulässig sind, in Anspruch nehmen. Die einzige Einschränkung besteht darin, dass der Arraytyp `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` oder `double` sein muss.  
  
```  
private fixed char name[30];  
```  
  
## <a name="remarks"></a>Hinweise  
 In frühen Versionen von C# war das Deklarieren einer C++-Struktur mit fester Größe schwierig, da eine C#-Struktur, die ein Array enthält, keine Elemente des Arrays enthält. Stattdessen enthält die Struktur einen Verweis auf die Elemente.  
  
 C# 2.0 hat die Möglichkeit hinzugefügt, ein Array fester Größe in ein [struct](../../../csharp/language-reference/keywords/struct.md) einzubetten, wenn es in einem [unsafe](../../../csharp/language-reference/keywords/unsafe.md)-Codeblock verwendet wird.  
  
 Vor C# 2.0 wäre das folgende `struct` z.B. 8 Bytes groß. Das `pathName`-Array ist ein Verweis auf das Heap zugeordnete Array:  
  
 [!code-cs[csProgGuidePointers#19](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_1.cs)]  
  
 Beginnend mit C# 2.0 kann ein `struct` ein eingebettetes Array enthalten. Im folgenden Beispiel verfügt das `fixedBuffer`-Array über eine feste Größe. Um auf die Elemente des Arrays zuzugreifen, verwenden Sie eine `fixed`-Anweisung, um einen Zeiger auf das erste Element festzulegen. Die `fixed`-Anweisung fixiert eine Instanz von `fixedBuffer` an einem bestimmten Speicherort im Arbeitsspeicher.  
  
 [!code-cs[csProgGuidePointers#20](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_2.cs)]  
  
 Die Größe des 128-Element-`char`-Arrays beträgt 256 Bytes. [Char](../../../csharp/language-reference/keywords/char.md)-Puffer mit fester Größe verwenden immer zwei Bytes pro Zeichen, unabhängig von der Codierung. Dies gilt auch, wenn Char-Puffer zu API-Methoden oder Strukturen mit `CharSet = CharSet.Auto` oder `CharSet = CharSet.Ansi` gemarshallt werden. Weitere Informationen finden Sie unter <xref:System.Runtime.InteropServices.CharSet>.  
  
 Ein anderes häufiges Array mit fester Größe ist das [bool](../../../csharp/language-reference/keywords/bool.md)-Array. Die Elemente in einem `bool`-Array sind immer ein Byte groß. `bool`-Arrays eignen sich nicht zum Erstellen von Bitarrays oder Puffern.  
  
> [!NOTE]
>  Mit Ausnahme von Arbeitsspeicher, der mithilfe von [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md) erstellt wurde, führen der C#-Compiler und die Common Language Runtime (CLR) keine Sicherheitsüberprüfungen für Pufferüberlauf aus. Lassen Sie, wie bei jedem unsicheren Code, Vorsicht walten.  
  
 Unsichere Puffer unterscheiden sich folgendermaßen von normalen Arrays:  
  
-   Sie können nur in einem unsicheren Kontext unsichere Puffer verwenden.  
  
-   Unsichere Puffer sind immer Vektoren oder eindimensionale Arrays.  
  
-   Die Deklaration des Arrays muss eine Anzahl enthalten, z.B. `char id[8]`. Sie können stattdessen nicht `char id[]` verwenden.  
  
-   Unsichere Puffer können nur Instanzfelder von Strukturen in einem unsicheren Kontext sein.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [fixed-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [Interoperabilität](../../../csharp/programming-guide/interop/index.md)
