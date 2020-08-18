---
title: Anonyme Funktionen – C#-Programmierhandbuch
description: Erfahren Sie mehr über anonyme Funktionen. Sie können einen Lambdaausdruck oder eine anonyme Methode verwenden, um eine anonyme Funktion zu erstellen.
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymous functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: 1fde7d535054f09d55018a010468776622ebfba7
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063262"
---
# <a name="anonymous-functions-c-programming-guide"></a>Anonyme Funktionen (C#-Programmierhandbuch)

Eine anonyme Funktion ist eine „Inline“-Anweisung oder ein „Inline“-Ausdruck, der überall dort verwendet werden kann, wo ein Delegattyp erwartet wird. Sie können sie zum Initialisieren eines benannten Delegaten verwenden oder anstelle eines benannten Delegattypen als Methodenparameter übergeben.

Sie können einen [Lambdaausdruck](../../language-reference/operators/lambda-expressions.md) oder eine [anonyme Methode](../../language-reference/operators/delegate-operator.md) verwenden, um eine anonyme Funktion zu erstellen. Wir empfehlen die Verwendung von Lambdaausdrücken, da sie eine präzisere und aussagekräftigere Möglichkeit zum Schreiben von Inlinecode bieten. Im Gegensatz zu anonymen Methoden können einige Arten von Lambdaausdrücken in Ausdrucksbaumstrukturtypen konvertiert werden.

## <a name="the-evolution-of-delegates-in-c"></a>Entwicklung von Delegaten in C\#

 In C# 1.0 haben Sie eine Instanz eines Delegaten durch explizites Initialisieren mit einer Methode erstellt, die an anderer Stelle im Code definiert wurde. C# 2.0 führte das Konzept anonymer Methoden ein, als eine Möglichkeit, unbenannte Inline-Anweisungsblöcke zu schreiben, die in einem Delegataufruf ausgeführt werden können. C# 3.0 führte Lambdaausdrücke ein, die anonymen Methoden ähneln, jedoch aussagekräftiger und präziser sind. Diese beiden Funktionen werden zusammenfassend als *anonyme Funktionen* bezeichnet. In der Regel sollten Anwendungen, die für .NET Framework 3.5 oder höher gedacht sind, Lambdaausdrücke verwenden.  
  
 Das folgende Beispiel zeigt die Entwicklung der Delegaterstellung von C# 1.0 zu C# 3.0:  
  
 [!code-csharp[csProgGuideLINQ#65](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#65)]  
  
## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Anonyme Funktionsausdrücke](~/_csharplang/spec/expressions.md#anonymous-function-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).
  
## <a name="see-also"></a>Siehe auch

- [Anweisungen, Ausdrücke und Operatoren](./index.md)
- [Lambda-Ausdrücke](../../language-reference/operators/lambda-expressions.md)
- [Delegaten](../delegates/index.md)
- [Ausdrucksbaumstrukturen (C#)](../concepts/expression-trees/index.md)
