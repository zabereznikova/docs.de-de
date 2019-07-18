---
title: Namespaces – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: 893ac7bbfcfe159787789238c3142f34ac7ecf35
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66423287"
---
# <a name="namespaces-c-programming-guide"></a>Namespaces (C#-Programmierhandbuch)

Namespaces werden beim Programmieren mit C# häufig und auf zwei verschiedene Arten verwendet. Erstens: Das .NET Framework verwendet Namespaces, um seine vielen Klassen folgendermaßen zu organisieren:  
  
 [!code-csharp[csProgGuide#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#22)]  
  
`System` ist ein Namespace, und `Console` ist eine Klasse in diesem Namespace. Das `using`-Schlüsselwort kann verwendet werden, sodass der vollständige Name nicht erforderlich ist, wie im folgenden Beispiel:  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 [!code-csharp[csProgGuide#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#25)]  
  
Weitere Information finden Sie unter der [using-Anweisung](../../language-reference/keywords/using-directive.md).  
  
Zweitens: Eigene Namespaces zu deklarieren kann Ihnen dabei helfen, den Umfang der Klassen- und Methodennamen in größeren Programmierprojekten zu steuern. Verwenden Sie das [Namespace](../../language-reference/keywords/namespace.md)-Schlüsselwort, um einen Namespace wie im folgenden Beispiel zu deklarieren:  
  
 [!code-csharp[csProgGuideNamespaces#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#6)]

Der Name des Namespace muss ein gültiger C#- [Bezeichnername](../inside-a-program/identifier-names.md) sein.

## <a name="namespaces-overview"></a>Übersicht über Namespaces  

Namespaces verfügen über die folgenden Eigenschaften:  
  
- Sie organisieren umfangreiche Codeprojekte.  
- Sie werden durch den `.`-Operator getrennt.  
- Durch die `using`-Direktive besteht keine Notwendigkeit, den Namen des Namespace für jede Klasse anzugeben.  
- Der `global`-Namespace ist der Stammnamespace: `global::System` verweist immer auf den .NET-Namespace <xref:System>.  

## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Using-Namespaces](using-namespaces.md)
- [Vorgehensweise: Verwenden des globalen Namespacealias](how-to-use-the-global-namespace-alias.md)
- [Vorgehensweise: Verwenden des My-Namespaces](how-to-use-the-my-namespace.md)
- [Bezeichnernamen](../inside-a-program/identifier-names.md)
- [using-Direktive](../../language-reference/keywords/using-directive.md)
- [:: Operator](../../language-reference/operators/namespace-alias-qualifer.md)
