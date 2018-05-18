---
title: C#-Attribute – Überblick über C#
description: Informationen zur deklarativen Programmierung mithilfe von Attributen in C#
ms.date: 08/10/2016
ms.assetid: 753bcfe2-7ddd-4487-9513-ba70937fc8e9
ms.openlocfilehash: d055f5386d1dddef0b70843a0a5fa6fc04922296
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="attributes"></a>Attribute

Typen, Member und andere Entitäten in einem C#-Programm unterstützen Modifizierer, die bestimmte Aspekte ihres Verhaltens steuern. Der Zugriff auf eine Methode wird beispielsweise mithilfe der Modifizierer `public`, `protected`, `internal` und `private` kontrolliert. C# generalisiert diese Funktionalität, indem benutzerdefinierte Typen deklarativer Informationen an eine Programmentität angefügt und zur Laufzeit abgerufen werden können. Programm geben diese zusätzlichen deklarativen Informationen durch das Definieren und Verwenden von ***Attributen*** an.

Im folgenden Beispiel wird ein `HelpAttribute`-Attribut deklariert, dass in Programmentitäten platziert werden kann, um Links zur zugehörigen Dokumentation bereitzustellen.

[!code-csharp[AttributeDefined](../../../samples/snippets/csharp/tour/attributes/Program.cs#L3-L20)]

Alle Attributklassen werden von der <xref:System.Attribute> Basisklasse abgeleitet, die von der Standardbibliothek bereitgestellt wird. Attribute können durch Angabe ihres Namens angewendet werden, zusammen mit beliebigen Argumenten. Diese müssen in eckigen Klammern genau vor der zugehörigen Deklaration eingefügt werden. Wenn ein Attributname auf `Attribute` endet, kann dieser Teil des Namens beim Verweis auf das Attribut weggelassen werden. Beispielsweise kann das `HelpAttribute`-Attribut wie folgt verwendet werden.

[!code-csharp[AttributeApplied](../../../samples/snippets/csharp/tour/attributes/Program.cs#L22-L28)]

In diesem Beispiel wird `HelpAttribute` an die `Widget`-Klasse angefügt. Darüber hinaus wird der `Display`-Methode in der Klasse ein weiteres `HelpAttribute` hinzugefügt. Die öffentlichen Konstruktoren einer Attributklasse steuern die Informationen, die beim Anfügen des Attributs an eine Programmentität angegeben werden müssen. Zusätzliche Informationen können angegeben werden, indem auf öffentliche Eigenschaften mit Lese-/Schreibzugriff der Attributklasse verwiesen wird (z.B. wie der obige Verweis auf die `Topic`-Eigenschaft).

Wenn per Reflektion ein bestimmtes Attribut angefordert wird, wird der Konstruktor für die Attributklasse mit den in der Programmquelle angegebenen Informationen aufgerufen, und die resultierende Attributinstanz wird zurückgegeben. Wenn zusätzliche Informationen über Eigenschaften bereitgestellt wurden, werden diese Eigenschaften auf die vorgegebenen Werte festgelegt, bevor die Attributinstanz zurückgegeben wird.

>[!div class="step-by-step"]
[Vorherige](delegates.md)
