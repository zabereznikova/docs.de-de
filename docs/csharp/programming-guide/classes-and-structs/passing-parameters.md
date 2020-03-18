---
title: Übergeben von Parametern – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
ms.openlocfilehash: 60ac7a8d982e7788f07debce114896859385c8e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705469"
---
# <a name="passing-parameters-c-programming-guide"></a>Übergeben von Parametern (C#-Programmierhandbuch)
In C# können Argumente an Parameter entweder als Wert oder als Verweis übergeben werden. Durch die Übergabe als Verweis können Funktionsmember, Methoden, Eigenschaften, Indexer, Operatoren und Konstruktoren den Wert der Parameter ändern und behalten diese Änderung in der aufrufenden Umgebung bei. Wenn Sie den Wert ändern und darum den Parameter pro Verweis übergeben möchten, verwenden Sie die Schlüsselwörter `ref` oder `out`. Wenn Sie den Wert zwar ändern, aber keine Kopie erstellen möchten, und darum den Parameter pro Verweis übergeben möchten, verwenden Sie den Modifizierer `in`. Der Einfachheit halber wird in den Beispielen in diesem Thema nur das Schlüsselwort `ref` verwendet. Weitere Informationen zum Unterschied zwischen `in`, `ref` und `out` finden Sie unter [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md) und [out](../../language-reference/keywords/out-parameter-modifier.md).  
  
 Das folgende Beispiel veranschaulicht die Unterschiede zwischen Wert- und Verweisparametern.  
  
 [!code-csharp[csProgGuideParameters#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#10)]  
  
 Weitere Informationen finden Sie unter den folgenden Themen:  
  
- [Übergeben von Werttypparametern](./passing-value-type-parameters.md)  
  
- [Übergeben von Verweistypparametern](./passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  

Weitere Informationen erhalten Sie in den [Argumentlisten](~/_csharplang/spec/expressions.md#argument-lists) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Programmierhandbuch](../index.md)
- [Methoden](./methods.md)
