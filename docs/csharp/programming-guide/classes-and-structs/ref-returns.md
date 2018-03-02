---
title: "Ref-Rückgabewerte und lokale ref-Variablen (Leitfaden für C#)"
description: "Erfahren Sie, wie Sie ref-Rückgaben und lokale ref-Werte definieren und verwenden können."
author: rpetrusha
ms.author: ronpet
ms.date: 01/23/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.openlocfilehash: a74563c0d24b6cd2a2fa8534787f078f3cc92674
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2018
---
# <a name="ref-returns-and-ref-locals"></a>Ref-Rückgaben und lokale ref-Variablen

Ab C# 7 unterstützt C# Verweisrückgabewerte (ref-Rückgaben). Mit einem Verweisrückgabewert kann eine Methode einen Verweis auf eine Variable statt eines Werts an eine aufrufende Funktion zurückgeben. Die aufrufende Funktion kann dann wählen, ob sie die zurückgegebene Variable behandelt, als wäre sie als Wert oder als Verweis zurückgegeben worden. Die aufrufende Funktion kann eine neue Variable erstellen, die selbst einen Verweis auf den zurückgegebenen Wert (als lokaler Verweis bezeichnet) darstellt.

## <a name="what-is-a-reference-return-value"></a>Was ist ein Verweisrückgabewert?

Die meisten Entwickler sind mit dem Übergeben eines Arguments *als Verweis* an eine aufgerufene Methode vertraut. Die Argumentliste einer aufgerufenen Methode umfasst eine als Verweis übergebene Variable, und alle durch die aufgerufene Methode am Wert vorgenommenen Änderungen werden von der aufrufenden Funktion überwacht. Ein *Verweisrückgabewert* bedeutet, dass eine Methode einen *Verweis* (oder Alias) an einige Variablen zurückgibt, deren Geltungsbereich die Methode umfasst und deren Lebensdauer über die Rückgabe der Methode hinausgehen muss. Änderungen am Methodenrückgabewert durch die aufrufende Funktion werden auf die Variable angewendet, die von der Methode zurückgegeben wird.

Die Deklaration der Rückgabe eines *Verweisrückgabewerts* durch eine Methode weist darauf hin, dass die Methode einen Alias an eine Variable zurückgibt. Das Entwurfsziel dahinter besteht häufig darin, dem aufrufenden Code über den Alias Zugriff auf diese Variable sowie die Möglichkeit zu deren Änderung zu gewähren. Daraus folgt, dass vom Verweis zurückgegebene Methoden nicht den Rückgabetyp `void` aufweisen dürfen.

Es gibt einige Einschränkungen für den Ausdruck, den eine Methode als Verweisrückgabewert zurückgeben kann. Dazu gehören:

- Der Rückgabewert muss eine Lebensdauer aufweisen, die über die Ausführung der Methode hinausgeht. Mit anderen Worten: Er darf in der Methode, die diesen zurückgibt, keine lokale Variable sein. Es kann sich dabei um eine Instanz oder ein statisches Feld einer Klasse oder um ein Argument handeln, das an die Methode übergeben wurde. Beim Versuch, eine lokale Variable zurückzugeben, tritt der Compilerfehler CS8168 „Cannot return local 'obj' by reference because it is not a ref local.“ (Der lokale Wert „obj“ kann nicht als Verweis zurückgegeben werden, da er kein lokaler ref-Wert ist.) auf.

- Der Rückgabewert darf nicht das `null`-Literal sein. Beim Versuch, `null` zurückzugeben, tritt der Compilerfehler CS8156 „Ein Ausdruck kann in diesem Kontext nicht verwendet werden, weil er ggf. nicht als Verweis zurückgegeben wird.“ auf.

   Eine Methode mit einer Verweisrückgabe kann einen Alias an eine Variable zurückgeben, deren Wert derzeit null ist (nicht instanziiert) oder ein [Nullable-Typ](../nullable-types/index.md) für einen Werttyp darstellt.
 
- Der Rückgabewert darf keine Konstante, kein Enumerationsmember, nicht der by-value-Rückgabewert einer Eigenschaft und keine Methode einer `class` oder `struct` sein. Beim Versuch, diese zurückzugeben, tritt der Compilerfehler CS8156 „Ein Ausdruck kann in diesem Kontext nicht verwendet werden, weil er ggf. nicht als Verweis zurückgegeben wird.“ auf.

Darüber hinaus sind Verweisrückgabewerte bei asynchronen Methoden nicht erlaubt, da eine asynchrone Methode etwas zurückgeben könnte, bevor die Ausführung abgeschlossen und ihr Rückgabewert bekannt ist.
 
## <a name="defining-a-ref-return-value"></a>Definieren eines ref-Rückgabewerts

Sie definieren einen ref-Rückgabewert, indem Sie dem Rückgabetyp der Methodensignatur das Schlüsselwort [ref](../../language-reference/keywords/ref.md) hinzufügen. Beispielsweise gibt die folgende Signatur an, dass die `GetContactInformation`-Eigenschaft einen Verweis auf ein `Person`-Objekt an die aufrufende Funktion zurückgibt:

```csharp
public ref Person GetContactInformation(string fname, string lname);
```

Darüber hinaus muss vor dem Namen des Objekts, das durch jede [return](../../language-reference/keywords/return.md)-Anweisung im Methodentext zurückgegeben wird, das Schlüsselwort [ref](../../language-reference/keywords/ref.md) stehen. Beispielsweise gibt die folgende `return`-Anweisung einen Verweis auf ein `Person`-Objekt mit dem Namen `p` zurück:

```csharp
return ref p;
```

## <a name="consuming-a-ref-return-value"></a>Verarbeiten eines ref-Rückgabewerts

Der Verweisrückgabewert ist ein Alias für eine andere Variable im Bereich der aufgerufenen Methode. Sie können jede Verwendung der Verweisrückgabe als Verwendung der Variable interpretieren, für die diese als Alias fungiert:

- Wenn Sie den jeweiligen Wert zuweisen, weisen Sie der Variable, für die diese als Alias fungiert, einen Wert zu.
- Wenn Sie dessen Wert lesen, lesen Sie den Wert der Variable, für die diese als Alias fungiert.
- Wenn Sie diesen *nach Verweis* zurückgeben, geben Sie einen Alias für diese Variable zurück.
- Wenn Sie ihn *nach Verweis* an eine andere Methode übergeben, übergeben Sie einen Verweis auf die Variable, für die diese als Alias fungiert.
- Wenn Sie einen Alias für einen [lokalen Verweis](#ref-local) erstellen, erstellen Sie einen neuen Alias für diese Variable.


## <a name="ref-locals"></a>Lokale ref-Variablen

Nehmen Sie an, dass die `GetContactInformation`-Methode als Verweisrückgabe deklariert ist:

```csharp
public ref Person GetContactInformation(string fname, string lname)
```

Eine by-value-Zuweisung liest den Wert einer Variable und weist diesen einer neuen Variable zu:

```csharp
Person p = contacts.GetContactInformation("Brandie", "Best");
```

Die vorangehende Zuweisung deklariert `p` als lokale Variable. Der ursprüngliche Wert wird durch Lesen des Rückgabewerts kopiert, der von `GetContactInformation` zurückgegeben wurde. Keine der zukünftigen Zuweisungen zu `p` ändern den Wert der von `GetContactInformation` zurückgegebenen Variable. Die Variable `p` fungiert nicht mehr als Alias für die zurückgegebene Variable.

Sie deklarieren eine *lokale Verweisvariable*, um den Alias in den ursprünglichen Wert zu kopieren. In der folgenden Zuweisung ist `p` ein Alias für die von `GetContactInformation` zurückgegebene Variable.

```csharp
ref Person p = ref contacts.GetContactInformation("Brandie", "Best");
```

Die nachfolgende Verwendung von `p` ist mit der Verwendung der von `GetContactInformation` zurückgegebenen Variable identisch, da `p` ein Alias für diese Variable darstellt. Durch Änderungen an `p` wird auch die von `GetContactInformation` zurückgegebene Variable geändert.

Beachten Sie, dass das Schlüsselwort `ref` sowohl vor der Deklaration lokaler Variablen *als auch* vor dem Methodenaufruf verwendet wird. Wenn nicht beide `ref`-Schlüsselwörter in den Ergebnissen der Variablendeklaration und der Zuweisung enthalten sind, tritt der Compilerfehler CS8172 „Eine by-reference-Variable kann nicht mit einem Wert initialisiert werden.“ auf. 
 
## <a name="ref-returns-and-ref-locals-an-example"></a>Ref-Rückgaben und lokale ref-Variablen: ein Beispiel

Das folgende Beispiel definiert eine `NumberStore`-Klasse, die ein Array von Integer-Werten speichert. Die `FindNumber`-Methode gibt die erste Anzahl, die größer als oder gleich der Anzahl ist, die als Argument übergeben wurde, als Verweis zurück. Wenn keine Anzahl größer als oder gleich dem Argument ist, gibt die Methode die Anzahl im Index 0 zurück. 

[!code-csharp[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/ref-returns1.cs#1)]

Im folgenden Beispiel wird die `NumberStore.FindNumber`-Methode aufgerufen, um den ersten Wert abzurufen, der größer als oder gleich 16 ist. Die aufrufende Funktion verdoppelt dann den von der Methode zurückgegebenen Wert. Wie die Ausgabe aus dem Beispiel zeigt, wird diese Änderung im Wert der Arrayelemente der `NumberStore`-Instanz wiedergegeben.

[!code-csharp[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/ref-returns1.cs#2)]

Ohne Unterstützung für Verweisrückgabewerte wird ein solcher Vorgang in der Regel durchgeführt, indem der Index des Arrayelements zusammen mit seinem Wert zurückgegeben wird. Die aufrufende Funktion kann diesen Index dann dazu verwenden, den Wert in einem separaten Methodenaufruf zu ändern. Die aufrufende Funktion kann den Index jedoch auch ändern, um auf andere Arraywerte zuzugreifen und diese zu bearbeiten.  
 
## <a name="see-also"></a>Siehe auch

[ref (C#-Referenz)](../../language-reference/keywords/ref.md)
