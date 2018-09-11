---
title: object (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- object_CSharpKeyword
- object
helpviewer_keywords:
- object keyword [C#]
ms.assetid: 93f60c0b-e17a-40a9-9362-cca5fb77b0e7
ms.openlocfilehash: b36703828e6027a89297ac88edaf2b55ec18f42e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44191806"
---
# <a name="object-c-reference"></a>object (C#-Referenz)

Der `object`-Typ ist ein Alias für <xref:System.Object> in .NET. Im vereinheitlichen Typsystem von C# erben alle Typen, vordefiniert und benutzerdefiniert sowie Verweis- und Werttypen, direkt oder indirekt von <xref:System.Object>. Sie können Werte eines beliebigen Typs Variablen des Typs `object` zuweisen. Wenn eine Variable eines Werttyps in ein Objekt konvertiert wird, gilt es als *geschachtelt*. Wenn eine Variable eines Typobjekts in ein Wertobjekt konvertiert wird, gilt es als *nicht geschachtelt*. Weitere Informationen finden Sie unter [Boxing und Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie Variablen des `object`-Typs Werte von jedem Datentyp akzeptieren können und Variablen des `object`-Typs Methoden auf <xref:System.Object> von .NET Framework verwenden können.

[!code-csharp[csrefKeywordsTypes#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#16)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Verweistypen](reference-types.md)
- [Werttypen](value-types.md)