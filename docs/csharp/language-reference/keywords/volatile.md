---
title: volatile (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords: volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
caps.latest.revision: "29"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1cefa39313c3c551e8d05fbc31e528b86c6888d9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="volatile-c-reference"></a>volatile (C#-Referenz)
Das Schlüsselwort `volatile` gibt an, dass ein Feld von mehreren Threads geändert werden kann, die zur gleichen Zeit ausgeführt werden. Felder, die als `volatile` deklariert sind, unterliegen keinen Compileroptimierungen, die von Zugriff durch einen einzelnen Thread ausgehen. Dadurch wird sichergestellt, dass immer der aktuelle Wert im Feld vorhanden ist.  
  
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
 Im folgenden Beispiel wird veranschaulicht, wie ein Hilfs- oder Arbeitsthread erstellt wird und für das Ausführen der Verarbeitung parallel mit dem primären Thread verwendet werden kann. Hintergrundinformationen zum Multithreading finden Sie unter [Threading](../../../standard/threading/index.md) und [Threading](../../programming-guide/concepts/threading/index.md).  
  
 [!code-csharp[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
 [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)
