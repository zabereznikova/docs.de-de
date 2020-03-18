---
title: '#define – C#-Referenz'
ms.date: 06/30/2018
f1_keywords:
- '#define'
helpviewer_keywords:
- '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
ms.openlocfilehash: c08d6f42c11184a4d14aa6712f9f0f8706a72cab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173431"
---
# <a name="define-c-reference"></a>#define (C#-Referenz)
Mit `#define` wird ein Symbol definiert. Wenn Sie das Symbol als Ausdruck verwenden, der an die [#if](./preprocessor-if.md)-Anweisung übergeben wird, wird der Ausdruck als `true` ausgewertet, wie in folgendem Beispiel dargestellt:  

 ```csharp
 #define DEBUG
 ```
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Die `#define`-Direktive kann nicht zur Deklaration konstanter Werte wie in C und C++ verwendet werden. Definieren Sie Konstanten in C# als statische Member einer Klasse oder einer Struktur. Wenn Sie über mehrere solcher Konstanten verfügen, erwägen Sie, eine separate "Constants"-Klasse zu erstellen.  
  
 Symbole können verwendet werden, um Bedingungen für die Kompilierung anzugeben. Ein Symbol kann entweder mit [#if](./preprocessor-if.md) oder mit [#elif](./preprocessor-elif.md) überprüft werden. Für die bedingte Kompilierung kann auch <xref:System.Diagnostics.ConditionalAttribute> verwendet werden.  
  
 Ein Symbol kann zwar definiert werden, aber es kann ihm kein Wert zugewiesen werden. Die `#define`-Direktive muss in einer Datei vor allen Anweisungen, bei denen es sich nicht um Präprozessordirektiven handelt, verwendet werden.  
  
 Ein Symbol kann auch mit der Compileroption [-define](../compiler-options/define-compiler-option.md) definiert werden. Die Definition eines Symbols kann mit [#undef](./preprocessor-undef.md) aufgehoben werden.  
  
 Zwischen einem Symbol, das mit `-define` oder mit `#define` definiert wird, und einer Variablen mit dem gleichen Namen kommt es zu keinem Konflikt. Das bedeutet, dass ein Variablenname nicht an eine Präprozessordirektive übergeben werden sollte und ein Symbol nur von einer Präprozessordirektive ausgewertet werden kann.  
  
 Bei dem Gültigkeitsbereich eines mit `#define` erstellten Symbols handelt es sich um die Datei, in der es definiert wurde.  
  
 Wie im folgenden Beispiel dargestellt, müssen Sie die `#define`-Direktive am Anfang der Datei eingeben.  
  
```csharp  
#define DEBUG  
//#define TRACE  
#undef TRACE  
  
using System;  
  
public class TestDefine  
{  
    static void Main()  
    {  
#if (DEBUG)  
        Console.WriteLine("Debugging is enabled.");  
#endif  
  
#if (TRACE)  
     Console.WriteLine("Tracing is enabled.");  
#endif  
    }  
}  
// Output:  
// Debugging is enabled.  
```  
  
 Ein Beispiel dafür, wie eine Symboldefinition aufgehoben wird, finden Sie unter [#undef](./preprocessor-undef.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Präprozessoranweisungen](./index.md)
- [const](../keywords/const.md)
- [Vorgehensweise: Bedingtes Kompilieren mit Ablaufverfolgung und Debuggen](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)
- [#undef](./preprocessor-undef.md)
- [#if](./preprocessor-if.md)
