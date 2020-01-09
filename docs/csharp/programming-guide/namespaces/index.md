---
title: Namespaces – C#-Programmierhandbuch
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: e3e9dc22186e5e319c63e34bd85e5e317effde88
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712012"
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

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Namespaces](~/_csharplang/spec/namespaces.md) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Using-Namespaces](using-namespaces.md)
- [Verwenden des My-Namespaces](how-to-use-the-my-namespace.md)
- [Bezeichnernamen](../inside-a-program/identifier-names.md)
- [using-Direktive](../../language-reference/keywords/using-directive.md)
- [:: Operator](../../language-reference/operators/namespace-alias-qualifier.md)
