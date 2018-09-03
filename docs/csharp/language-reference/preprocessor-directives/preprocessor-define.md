---
title: '#define (C#-Referenz)'
ms.date: 06/30/2018
f1_keywords:
- '#define'
helpviewer_keywords:
- '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
ms.openlocfilehash: 305d52c26fb2592874d06f2c9a75ec63b472a812
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42933063"
---
# <a name="define-c-reference"></a>#define (C#-Referenz)
Mit `#define` wird ein Symbol definiert. Wenn Sie das Symbol als Ausdruck verwenden, der an die [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)-Anweisung übergeben wird, wird der Ausdruck als `true` ausgewertet, wie in folgendem Beispiel dargestellt:  
 
 ```csharp
 #define DEBUG
 ```
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Die `#define`-Direktive kann nicht zur Deklaration konstanter Werte wie in C und C++ verwendet werden. Definieren Sie Konstanten in C# als statische Member einer Klasse oder einer Struktur. Wenn Sie über mehrere solcher Konstanten verfügen, erwägen Sie, eine separate "Constants"-Klasse zu erstellen.  
  
 Symbole können verwendet werden, um Bedingungen für die Kompilierung anzugeben. Ein Symbol kann entweder mit [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) oder mit [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md) überprüft werden. Für die bedingte Kompilierung kann auch <xref:System.Diagnostics.ConditionalAttribute> verwendet werden.  
  
 Ein Symbol kann zwar definiert werden, aber es kann ihm kein Wert zugewiesen werden. Die `#define`-Direktive muss in einer Datei vor allen Anweisungen, bei denen es sich nicht um Präprozessordirektiven handelt, verwendet werden.  
  
 Ein Symbol kann auch mit der Compileroption [-define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) definiert werden. Die Definition eines Symbols kann mit [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) aufgehoben werden.  
  
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
  
 Ein Beispiel dafür, wie eine Symboldefinition aufgehoben wird, finden Sie unter [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Präprozessoranweisungen](../../../csharp/language-reference/preprocessor-directives/index.md)  
- [const](../../../csharp/language-reference/keywords/const.md)  
- [Vorgehensweise: Bedingtes Kompilieren mit Ablaufverfolgung und Debuggen](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)  
- [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)  
- [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)
