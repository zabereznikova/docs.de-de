---
title: Konstanten – C#-Programmierhandbuch
description: Bei Konstanten in C# handelt es sich um Literalwerte zur Kompilierzeit, die sich nicht ändern, wenn das Programm kompiliert wird. Nur in C# integrierte Typen können Konstanten sein.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 1fb39621-1738-49b1-a1b3-8587f109123f
ms.openlocfilehash: 1252e214be03f8a180fadb7667ee59f36a862040
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558425"
---
# <a name="constants-c-programming-guide"></a>Konstanten (C#-Programmierhandbuch)
Konstanten sind unveränderliche Werte, die zur Kompilierzeit bekannt sind und sich während der Lebensdauer des Programms nicht ändern. Konstanten werden mit dem [const](../../language-reference/keywords/const.md)-Modifizierer deklariert. Nur die in C# [integrierten Typen](../../language-reference/builtin-types/built-in-types.md) (außer <xref:System.Object?displayProperty=nameWithType>) können als `const` deklariert werden. Benutzerdefinierte Typen einschließlich Klassen, Strukturen und Arrays können nicht `const` sein. Verwenden Sie den [readonly](../../language-reference/keywords/readonly.md)-Modifizierer zum Erstellen einer Klasse, einer Struktur oder eines Arrays, die/das zur Laufzeit einmal initialisiert wird (z.B. in einem Konstruktor) und danach nicht geändert werden kann.  
  
 C# unterstützt keine `const`-Methoden, -Eigenschaften oder -Ereignisse.  
  
 Der Enumerationstyp ermöglicht Ihnen das Definieren benannter Konstanten für ganzzahlige integrierte Typen (z.B. `int`, `uint`, `long` usw.). Weitere Informationen finden Sie unter [enum](../../language-reference/builtin-types/enum.md).  
  
 Konstanten müssen initialisiert werden, wenn sie deklariert werden. Zum Beispiel:  
  
 [!code-csharp[csProgGuideObjects#64](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#64)]  
  
 In diesem Beispiel ist die Konstante `Months` immer 12 und kann nicht einmal durch die Klasse selbst geändert werden. Wenn der Compiler einen konstanten Bezeichner im C#-Quellcode erkennt (z.B. `Months`), ersetzt er den Literalwert direkt durch Code der Zwischensprache (Intermediate Language, IL), den er produziert. Da zur Laufzeit keine Variablenadresse einer Konstanten zugeordnet ist, können `const`-Felder nicht durch Verweis übergeben werden und können nicht als l-Wert in einem Ausdruck stehen.  
  
> [!NOTE]
> Seien Sie vorsichtig beim Verweisen auf konstante Werte, die in anderem Code wie z.B. DLLs definiert sind. Wenn eine neue Version der DLL einen neuen Wert für die Konstante definiert, enthält das Programm weiterhin den alten Literalwert, bis es mit der neuen Version erneut kompiliert wird.  
  
 Mehrere Konstanten desselben Typs können zur gleichen Zeit deklariert werden wie zum Beispiel:  
  
 [!code-csharp[csProgGuideObjects#65](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#65)]  
  
 Der Ausdruck, mit dem eine Konstante initialisiert wird, kann auf eine andere Konstante verweisen, wenn dadurch kein Zirkelverweis entsteht. Zum Beispiel:  
  
 [!code-csharp[csProgGuideObjects#66](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#66)]  
  
 Konstanten können als [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) oder [private protected](../../language-reference/keywords/private-protected.md) markiert werden. Diese Zugriffsmodifizierer definieren, wie Benutzer der Klasse auf die Konstante zugreifen können. Weitere Informationen finden Sie unter [Zugriffsmodifizierer](./access-modifiers.md).  
  
 Auf Konstanten wird zugegriffen, als wären sie [statische](../../language-reference/keywords/static.md) Felder, da der Wert der Konstante für alle Instanzen des Typs identisch ist. Sie verwenden nicht das `static`-Schlüsselwort, um sie zu deklarieren. Ausdrücke, die nicht in der Klasse enthalten sind, die die Konstante definiert, müssen den Klassennamen, einen Punkt und den Namen der Konstante verwenden, um auf die Konstante zuzugreifen. Zum Beispiel:  
  
 [!code-csharp[csProgGuideObjects#67](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#67)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Klassen und Strukturen](./index.md)
- [Eigenschaften](./properties.md)
- [Typen](../types/index.md)
- [readonly](../../language-reference/keywords/readonly.md)
- [Unveränderlichkeit in C#, Teil 1: Arten von Unveränderlichkeit](https://docs.microsoft.com/archive/blogs/ericlippert/immutability-in-c-part-one-kinds-of-immutability)
