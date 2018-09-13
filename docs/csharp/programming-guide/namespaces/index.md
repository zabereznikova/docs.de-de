---
title: Namespaces (C#-Programmierhandbuch)
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: c4011092a6c605137053b544d4b9f14cce2fdb4c
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "44755709"
---
# <a name="namespaces-c-programming-guide"></a>Namespaces (C#-Programmierhandbuch)

Namespaces werden beim Programmieren mit C# häufig und auf zwei verschiedene Arten verwendet. Erstens: Das .NET Framework verwendet Namespaces, um seine vielen Klassen folgendermaßen zu organisieren:  
  
[!code-csharp[csProgGuide#22](../inside-a-program/codesnippet/CSharp/index_1.cs)]  
  
`System` ist ein Namespace, und `Console` ist eine Klasse in diesem Namespace. Das `using`-Schlüsselwort kann verwendet werden, sodass der vollständige Name nicht erforderlich ist, wie im folgenden Beispiel:  
  
[!code-csharp[csProgGuide#1](../inside-a-program/codesnippet/CSharp/index_2.cs)]  
  
[!code-csharp[csProgGuide#25](../inside-a-program/codesnippet/CSharp/index_3.cs)]  
  
Weitere Information finden Sie unter der [using-Anweisung](../../language-reference/keywords/using-directive.md).  
  
Zweitens: Eigene Namespaces zu deklarieren kann Ihnen dabei helfen, den Umfang der Klassen- und Methodennamen in größeren Programmierprojekten zu steuern. Verwenden Sie das [Namespace](../../language-reference/keywords/namespace.md)-Schlüsselwort, um einen Namespace wie im folgenden Beispiel zu deklarieren:  
  
[!code-csharp[csProgGuideNamespaces#6](codesnippet/CSharp/index_4.cs)]

Der Name des Namespace muss ein gültiger C#- [Bezeichnername](../inside-a-program/identifier-names.md) sein.

## <a name="namespaces-overview"></a>Übersicht über Namespaces  

Namespaces verfügen über die folgenden Eigenschaften:  
  
- Sie organisieren umfangreiche Codeprojekte.  
- Sie werden durch den `.`-Operator getrennt.  
- Durch `using directive` besteht keine Notwendigkeit, den Namen des Namespace für jede Klasse anzugeben.  
- Der `global`-Namespace ist der Stammnamespace: `global::System` verweist immer auf den `System`-Namespace des .NET Framework.  

## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Using-Namespaces](using-namespaces.md)
- [Gewusst wie: Verwenden des globalen Namespacealias](how-to-use-the-global-namespace-alias.md)
- [Gewusst wie: Verwenden des My-Namespaces](how-to-use-the-my-namespace.md)
- [C#-Programmierhandbuch](../index.md)  
- [Bezeichnernamen](../inside-a-program/identifier-names.md)
- [Namespaceschlüsselwörter](../../language-reference/keywords/namespace-keywords.md)  
- [using-Direktive](../../language-reference/keywords/using-directive.md)  
- [::-Operator](../../language-reference/operators/namespace-alias-qualifer.md)  
- [ Operator](../../language-reference/operators/member-access-operator.md)
>>>>>>> Benennungsregeln für Bezeichner hinzufügen
