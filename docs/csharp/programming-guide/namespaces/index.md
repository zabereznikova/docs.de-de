---
title: Namespaces (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: 60e4c6e98ca9e71d1a095a0c7ee1df6be6d13f4b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33334349"
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
 [ Operator](../../../csharp/language-reference/operators/member-access-operator.md)
