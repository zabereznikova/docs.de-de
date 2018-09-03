---
title: volatile (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
ms.openlocfilehash: be7e081b18702710c00b5b86a9bc152800f0cf3d
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2018
ms.locfileid: "43253166"
---
# <a name="volatile-c-reference"></a>volatile (C#-Referenz)
Das Schlüsselwort `volatile` gibt an, dass ein Feld von mehreren Threads geändert werden kann, die zur gleichen Zeit ausgeführt werden. Felder, die als `volatile` deklariert sind, unterliegen keinen Compileroptimierungen, die von Zugriff durch einen einzelnen Thread ausgehen. Diese Einschränkungen stellen sicher, dass alle Threads volatile-Schreibvorgänge, die von einem anderen Thread ausgeführt werden, in der Reihenfolge ihrer Ausführung berücksichtigen. Es gibt keine Garantie für eine einzelne Gesamtsortierung von volatile-Schreibvorgängen aus der Sicht aller ausgeführten Threads.  
  
 Der `volatile`-Modifizierer wird normalerweise für Felder verwendet, auf die von mehreren Threads ohne die [lock](../../../csharp/language-reference/keywords/lock-statement.md)-Anweisung zugegriffen wird, um den Zugriff zu serialisieren.  
  
 Das Schlüsselwort `volatile` kann auf Felder der folgenden Typen angewendet werden:  
  
-   Verweistypen.  
  
-   Zeigertypen (in unsicherem Kontext). Beachten Sie, dass der Zeiger selbst als „volatile“ deklariert sein kann, das Objekt, auf das er zeigt aber nicht. Anders ausgedrückt können Sie keinen „Zeiger auf ‚volatile‘“ deklarieren.  
  
-   Typen wie sbyte, byte, short, ushort, int, uint, char, float und bool.  
  
-   Ein Enumerationstyp mit einem der folgenden Basistypen: byte, sbyte, short, ushort, int oder uint.  
  
-   Generische Typparameter, die als Verweistypen bekannt sind.  
  
-   <xref:System.IntPtr> und <xref:System.UIntPtr>.  
  
 Das Schlüsselwort „volatile“ kann nur auf Felder einer Klasse oder Struktur angewendet werden. Lokale Variablen können nicht als `volatile` deklariert werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Deklaration einer öffentlichen Feldvariable als `volatile` dargestellt.  
  
 [!code-csharp[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Hilfs- oder Arbeitsthread erstellt wird und für das Ausführen der Verarbeitung parallel mit dem primären Thread verwendet werden kann. Hintergrundinformationen zum Multithreading finden Sie unter [Verwaltetes Threading](../../../standard/threading/index.md) und [Threading (C#)](../../programming-guide/concepts/threading/index.md).  
  
 [!code-csharp[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
- [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)
