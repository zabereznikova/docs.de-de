---
title: Unsicherer Code und Zeiger – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- security [C#], type safety
- C# language, unsafe code
- type safety [C#]
- unsafe keyword [C#]
- unsafe code [C#]
- C# language, pointers
- pointers [C#], about pointers
ms.assetid: b0fcca10-a92d-4f2a-835b-b0ccae6739ee
ms.openlocfilehash: 7d7371fb29f12a766ef6b78544f82d021dd8dceb
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237908"
---
# <a name="unsafe-code-and-pointers-c-programming-guide"></a>Unsicherer Code und Zeiger (C#-Programmierhandbuch)
Um Typsicherheit und Sicherheit zu gewährleisten, unterstützt C# standardmäßig keine Zeigerarithmetik. Sie können jedoch das [unsafe](../../../csharp/language-reference/keywords/unsafe.md)-Schlüsselwort verwenden, um einen unsicheren Kontext zu definieren, in dem Zeiger verwendet werden können. Weitere Informationen über Zeiger finden Sie unter [Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).  
  
> [!NOTE]
>  In der Common Language Runtime (CLR) wird unsicherer Code als „nicht überprüfbarer Code“ bezeichnet. Unsicherer Code in C# ist nicht unbedingt gefährlich, es handelt sich dabei lediglich um einen Code, dessen Sicherheit nicht durch die CLR überprüft werden kann. Die CLR wird daher nur unsicheren Code ausführen, wenn sie sich in einer voll vertrauenswürdigen Assembly befindet. Wenn Sie unsicheren Code verwenden, liegt es in Ihrer Verantwortung, dafür zu sorgen, dass Ihr Code keine Sicherheitsrisiken oder Zeigerfehler enthält.  
  
## <a name="unsafe-code-overview"></a>Übersicht über unsicheren Code  
 Unsicherer Code verfügt über die folgenden Eigenschaften:  
  
-   Methoden, Typen und Codeblöcke können als unsicher definiert werden.  
  
-   In manchen Fällen kann unsicherer Code die Leistung einer Anwendung erhöhen, indem die Überprüfung von Arraygrenzen entfernt wird.  
  
-   Unsicherer Code ist erforderlich, wenn Sie native Funktionen aufrufen, die Zeiger erfordern.  
  
-   Die Verwendung von unsicherem Code führt zu Sicherheits- und Stabilitätsrisiken.  
  
-   Damit unsicherer Code in C# kompiliert werden kann, muss die Anwendung mit [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) kompiliert werden.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 Weitere Informationen finden Sie unter:  
  
-   [Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
  
-   [Puffer fester Größe](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)  
  
-   [Vorgehensweise: Verwenden von Zeigern zum Kopieren eines Bytearrays](../../../csharp/programming-guide/unsafe-code-pointers/how-to-use-pointers-to-copy-an-array-of-bytes.md)  
  
-   [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
