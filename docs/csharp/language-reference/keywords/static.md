---
title: static-Modifizierer – C#-Referenz
ms.date: 01/22/2020
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: e7671e9db488a7b50f4ed736864d6fa8d95eef1a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744665"
---
# <a name="static-c-reference"></a>static (C#-Referenz)

Verwenden Sie den Modifizierer `static`, um einen statischen Member zu deklarieren, der zum Typ selbst gehört, anstatt zu einem bestimmten Objekt. Der `static`-Modifizierer kann zum Deklarieren von `static`-Klassen verwendet werden. In Klassen, Schnittstellen und Strukturen können Sie den Modifizierer `static` zu Feldern, Methoden, Eigenschaften, Operatoren, Ereignissen und Konstruktoren hinzufügen. Der `static`-Modifizierer kann nicht mit Indexern oder Finalizern verwendet werden. Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).

## <a name="example"></a>Beispiel

Die folgende Klasse wird als `static` deklariert und enthält nur `static`-Methoden:

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

Eine Konstante oder Typdeklaration ist implizit ein `static`-Member. Ein `static`-Member kann nicht über eine Instanz verwiesen werden. Stattdessen wird er über den Typnamen verwiesen. Betrachten Sie beispielsweise die folgende Klasse:

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

Verwenden Sie zum Verweisen auf einen `static`-Member `x` den vollqualifizierten Namen `MyBaseC.MyStruct.x`, außer es kann auf den Member vom selben Geltungsbereich zugegriffen werden:

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

Während die Instanz einer Klasse eine separate Kopie aller Instanzfelder der Klasse enthält, gibt es nur eine Kopie von jedem `static`-Feld.

Es ist nicht möglich, [`this`](this.md) zum Verweis auf `static`-Methoden oder Eigenschaftenaccessoren zu verwenden.

Wenn das Schlüsselwort `static` auf eine Klasse angewandt wird, müssen alle Member der Klasse `static` sein.

Klassen, Schnittstellen und `static`-Klassen können `static`-Konstruktoren haben. Ein `static`-Konstruktor wird irgendwann zwischen Programmstart und Klasseninstanziierung aufgerufen.

> [!NOTE]
> Die Verwendung des Schlüsselworts `static` ist in C# eingeschränkter als in C++. Vergleiche mit dem C++-Schlüsselwort finden Sie unter [Speicherklassen (C++)](/cpp/cpp/storage-classes-cpp#static).

Stellen Sie sich zur Veranschaulichung von `static`-Membern eine Klasse vor, die einen Angestellten eines Unternehmens darstellt. Es wird angenommen, dass die Klasse eine Methode zum Zählen von Angestellten sowie ein Feld enthält, in dem die Anzahl von Angestellten gespeichert wird. Sowohl die Methode als auch das Feld gehören nicht zu einer Instanz eines Angestellten. Stattdessen gehören diese zur Klasse der Angestellten als Ganzes. Diese sollten als `static`-Member der Klasse deklariert werden.

## <a name="example"></a>Beispiel

In diesem Beispiel wird der Name und die ID eines neuen Angestellten gelesen, der Angestelltenzähler wird um 1 erhöht, und die Informationen zum neuen Angestellten sowie die neue Anzahl von Angestellten wird angezeigt. Das Programm liest die aktuelle Anzahl von Angestellten von der Tastatur.

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt, dass Sie ein `static`-Feld durch Verwendung eines anderen `static`-Felds initialisieren können, das noch nicht deklariert ist. Die Ergebnisse sind undefiniert, bis Sie dem Feld `static` explizit einen Wert zuweisen.

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Modifizierer](index.md)
- [Statische Klassen und statische Klassenmember](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
