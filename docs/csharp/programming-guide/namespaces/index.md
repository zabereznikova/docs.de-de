---
title: Namespaces (C#-Programmierhandbuch)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
caps.latest.revision: "27"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3eb645f5beb61d3cec97a70a54e660c65be52091
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="namespaces-c-programming-guide"></a>Namespaces (C#-Programmierhandbuch)
Namespaces werden beim Programmieren mit C# häufig und auf zwei verschiedene Arten verwendet. Erstens: Das .NET Framework verwendet Namespaces, um seine vielen Klassen folgendermaßen zu organisieren:  
  
 [!code-csharp[csProgGuide#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_1.cs)]  
  
 `System` ist ein Namespace, und `Console` ist eine Klasse in diesem Namespace. Das `using`-Schlüsselwort kann verwendet werden, sodass der vollständige Name nicht erforderlich ist, wie im folgenden Beispiel:  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_2.cs)]  
  
 [!code-csharp[csProgGuide#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_3.cs)]  
  
 Weitere Information finden Sie unter [using-Direktive](../../../csharp/language-reference/keywords/using-directive.md).  
  
 Zweitens: Eigene Namespaces zu deklarieren kann Ihnen dabei helfen, den Umfang der Klassen- und Methodennamen in größeren Programmierprojekten zu steuern. Verwenden Sie das [Namespace](../../../csharp/language-reference/keywords/namespace.md)-Schlüsselwort, um einen Namespace wie im folgenden Beispiel zu deklarieren:  
  
 [!code-csharp[csProgGuideNamespaces#6](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/index_4.cs)]  
  
## <a name="namespaces-overview"></a>Übersicht über Namespaces  
 Namespaces verfügen über die folgenden Eigenschaften:  
  
-   Sie organisieren umfangreiche Codeprojekte.  
  
-   Sie werden durch den `.`-Operator getrennt.  
  
-   Durch `using directive` besteht keine Notwendigkeit, den Namen des Namespace für jede Klasse anzugeben.  
  
-   Der `global`-Namespace ist der Stammnamespace: `global::System` verweist immer auf den `System`-Namespace des .NET Framework.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 Weitere Informationen zu Namespaces finden Sie unter folgenden Themen:  
  
-   [Using-Namespaces](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [Gewusst wie: Verwenden des globalen Namespacealias](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
-   [Gewusst wie: Verwenden des My-Namespaces](../../../csharp/programming-guide/namespaces/how-to-use-the-my-namespace.md)  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Namespaceschlüsselwörter](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [using-Direktive](../../../csharp/language-reference/keywords/using-directive.md)  
 [::-Operator](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
 [. Operator](../../../csharp/language-reference/operators/member-access-operator.md)
