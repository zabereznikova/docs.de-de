---
title: 'Vorgehensweise: Verwenden des globalen Namespacealias – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
ms.openlocfilehash: f44bb1f010f154973fc6982882c9b5a09528da76
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629445"
---
# <a name="how-to-use-the-global-namespace-alias-c-programming-guide"></a>Vorgehensweise: Verwenden des globalen Namespacealias (C#-Programmierhandbuch)
Die Möglichkeit, auf einen Member im globalen [Namespace](../../../csharp/language-reference/keywords/namespace.md) zuzugreifen, ist nützlich, wenn der Member möglicherweise von einer anderen Entität mit dem gleichen Namen verdeckt wird.  
  
 Im folgenden Code wird `Console` z.B. zu `TestApp.Console` statt zum `Console`-Typ im <xref:System>-Namespace aufgelöst.  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 [!code-csharp[csProgGuideNamespaces#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#1)]  
  
 Wenn Sie `System.Console` verwenden, führt dies immer noch zu einem Fehler, da der `System`-Namespace von der `TestApp.System`-Klasse verborgen wird:  
  
 [!code-csharp[csProgGuideNamespaces#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#2)]  
  
 Diesen Fehler können Sie jedoch umgehen, indem Sie `global::System.Console` folgendermaßen verwenden:  
  
 [!code-csharp[csProgGuideNamespaces#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#3)]  
  
 Wenn der linke Bezeichner `global` ist, beginnt die Suche nach dem richtigen Bezeichner im globalen Namespace. Die folgende Deklaration verweist z.B. auf `TestApp` als Member des globalen Spaces.  
  
 [!code-csharp[csProgGuideNamespaces#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#4)]  
  
 Es wird natürlich nicht empfohlen, dass Sie Ihren eigenen Namespace mit dem Namen `System` erstellen, und es ist unwahrscheinlich, dass Sie Code finden, in dem dies der Fall ist. In größeren Projekte ist es jedoch mehr als möglich, dass Namespaceduplikate auf irgendeine Weise vorkommen. In derartigen Situationen ist der globale Namespacequalifizierer die Garantie für Sie, den Stammnamespace angeben zu können.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird der `System`-Namespace verwendet, um die `TestClass`-Klasse einzubeziehen, weshalb `global::System.Console` verwendet werden muss, um auf die `System.Console`-Klasse zu verweisen, die vom `System`-Namespace verborgen wird. Darüber hinaus wird der `colAlias`-Alias verwendet, um auf den `System.Collections`-Namespace zu verweisen. Deshalb wurde die Instanz einer <xref:System.Collections.Hashtable?displayProperty=nameWithType> mit diesem Alias statt mit dem Namespace erstellt.  
  
 [!code-csharp[csProgGuideNamespaces#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#5)]  
  
**A 1**
**B 2**
**C 3**

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Namespaces](../../../csharp/programming-guide/namespaces/index.md)
- [:: Operator](../../../csharp/language-reference/operators/namespace-alias-qualifier.md)
- [extern](../../../csharp/language-reference/keywords/extern.md)
