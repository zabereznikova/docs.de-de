---
title: "Standardwertausdrücke (C#-Programmierhandbuch)"
description: "Standardwertausdrücke erzeugen den Standardwert für jeden Verweistyp oder Werttyp."
ms.date: 2017-08-23
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.assetid: b9daf449-4e64-496e-8592-6ed2c8875a98
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 0dc2fcee3903b80816c98bab47e2b9a2e5ef78b0
ms.openlocfilehash: 7b5b53d7ed92c6f6377a3e494daf1d02a4cf0934
ms.contentlocale: de-de
ms.lasthandoff: 08/28/2017

---
# <a name="default-value-expressions-c-programming-guide"></a>Standardwertausdrücke (C#-Programmierhandbuch)

Ein Standardwertausdruck erzeugt den Standardwert für einen Typ. Standardwertausdrücke sind besonders nützlich in generischen Klassen und Methoden. Das Zuweisen eines Standardwerts zu einem parametrisierten Typ `T` wird beim Verwenden von Generika erschwert, wenn folgende Punkte im Voraus noch unklar sind:

- Ob `T` ein Verweistyp oder ein Werttyp ist.
- Wenn `T` ein Werttyp ist, ob es dabei um einen numerischen Wert oder eine benutzerdefinierte Struktur handelt.

 Angenommen, dass eine Variable `t` vom parametrisierten Typ `T` vorliegt, ist die Anweisung `t = null` nur gültig, wenn `T` ein Verweistyp ist. Die Zuweisung `t = 0` funktioniert nur für numerische Werttypen, nicht aber für Strukturen. Die Lösung besteht im Verwenden eines Standardwertausdrucks, der `null` für Verweistypen (Klassentypen und Schnittstellentypen) und 0 für numerische Werttypen zurückgibt. Bei benutzerdefinierten Strukturen gibt er die Struktur zurück, die mit dem 0-Bitmuster initialisiert wurde. Dieses erzeugt 0 oder `null` für jeden Member, je nachdem, ob es sich beim entsprechenden Member um einen Werttyp oder um einen Verweistyp handelt. Bei auf NULL festlegbaren Werttypen gibt `default` <xref:System.Nullable%601?displayProperty=fullName> zurück, die Initialisierung erfolgt analog zu allen anderen Strukturen.

Der Ausdruck `default(T)` ist nicht auf generische Klassen und Methoden beschränkt. Standardwertausdrücke können mit jedem verwalteten Typ verwendet werden. Jeder der folgenden Ausdrücke ist gültig:

 [!code-cs[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]

 Im folgenden Beispiel aus der Klasse `GenericList<T>` wird die Verwendung des Operators `default(T)` in einer generischen Klasse veranschaulicht. Weitere Informationen finden Sie unter [Einführung in Generika](../generics/introduction-to-generics.md).

 [!code-cs[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]

## <a name="default-literal-and-type-inference"></a>Standardliterale und Typrückschluss

Ab C# 7.1 kann das `default`-Literal für Standardwertausdrücke verwendet werden, wenn der Compiler den Typ des Ausdrucks ableiten kann. Das `default`-Literal erzeugt die gleichen Werte wie das entsprechende `default(T)`, bei dem `T` der abgeleitete Typ ist. Dadurch kann der Code präziser werden, indem Redundanzen durch das mehrmalige Deklarieren eines Typs reduziert werden. Das `default`-Literal kann in jeder der folgenden Positionen verwendet werden:

- Variableninitialisierer
- Variablenzuweisung
- Deklarieren des Standardwerts für einen optionalen Parameter
- Bereitstellen des Werts für ein Methodenaufrufargument
- Zurückgeben einer Anweisung (oder eines Ausdrucks in einem Ausdruckskörpermember)

Das folgende Beispiel demonstriert die Verwendung des `default`-Literals in einem Standardwertausdruck:

[!code-cs[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]

## <a name="see-also"></a>Siehe auch

 <xref:System.Collections.Generic> [C#-Programmierhandbuch](../index.md)   
 [Generika](../generics/index.md)   
 [Generische Methoden](../generics/generic-methods.md)   
 [Generika](~/docs/standard/generics/index.md)   

