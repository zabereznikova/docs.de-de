---
title: Ref-Rückgabewerte und lokale ref-Variablen (Leitfaden für C#)
description: Erfahren Sie, wie Sie ref-Rückgaben und lokale ref-Werte definieren und verwenden können.
ms.date: 04/04/2018
ms.openlocfilehash: 7ade422b5b3805ef2e1f487252a98fb85cdfe70c
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736822"
---
# <a name="ref-returns-and-ref-locals"></a>Ref-Rückgaben und lokale ref-Variablen

Ab C# 7.0 unterstützt C# Verweisrückgabewerte (ref-Rückgaben). Mit einem Verweisrückgabewert kann eine Methode einen Verweis auf eine Variable statt eines Werts an eine aufrufende Funktion zurückgeben. Die aufrufende Funktion kann dann wählen, ob sie die zurückgegebene Variable behandelt, als wäre sie als Wert oder als Verweis zurückgegeben worden. Die aufrufende Funktion kann eine neue Variable erstellen, die selbst einen Verweis auf den zurückgegebenen Wert (als lokaler Verweis bezeichnet) darstellt.

## <a name="what-is-a-reference-return-value"></a>Was ist ein Verweisrückgabewert?

Die meisten Entwickler sind mit dem Übergeben eines Arguments *als Verweis* an eine aufgerufene Methode vertraut. Die Argumentliste einer aufgerufenen Methode enthält eine Variable, die als Verweis übergeben wird. Änderungen, die an diesem Wert von der aufgerufenen Methode vorgenommen werden, werden vom Aufrufer überwacht. Ein *Verweisrückgabewert* bedeutet, dass eine Methode einen *Verweis* (oder Alias) an einige Variablen zurückgibt. Der Geltungsbereich der Variable muss die Methode enthalten. Die Lebensdauer dieser Variable muss über die Rückgabe der Methode hinausgehen. Änderungen am Methodenrückgabewert durch die aufrufende Funktion werden auf die Variable angewendet, die von der Methode zurückgegeben wird.

Die Deklaration der Rückgabe eines *Verweisrückgabewerts* durch eine Methode weist darauf hin, dass die Methode einen Alias an eine Variable zurückgibt. Das Entwurfsziel dahinter besteht häufig darin, dem aufrufenden Code über den Alias Zugriff auf diese Variable sowie die Möglichkeit zu deren Änderung zu gewähren. Daraus folgt, dass vom Verweis zurückgegebene Methoden nicht den Rückgabetyp `void` aufweisen dürfen.

Es gibt einige Einschränkungen für den Ausdruck, den eine Methode als Verweisrückgabewert zurückgeben kann. Es gelten folgende Beschränkungen:

- Der Rückgabewert muss eine Lebensdauer aufweisen, die über die Ausführung der Methode hinausgeht. Mit anderen Worten: Er darf in der Methode, die diesen zurückgibt, keine lokale Variable sein. Es kann sich dabei um eine Instanz oder ein statisches Feld einer Klasse oder um ein Argument handeln, das an die Methode übergeben wurde. Beim Versuch, eine lokale Variable zurückzugeben, tritt der Compilerfehler CS8168 „Cannot return local 'obj' by reference because it is not a ref local.“ (Der lokale Wert „obj“ kann nicht als Verweis zurückgegeben werden, da er kein lokaler ref-Wert ist.) auf.

- Der Rückgabewert darf nicht das `null`-Literal sein. Bei der Rückgabe von `null` tritt der Compilerfehler CS8156 „Ein Ausdruck kann in diesem Kontext nicht verwendet werden, weil er ggf. nicht als Verweis zurückgegeben wird.“ auf.

   Eine Methode mit einer Verweisrückgabe kann einen Alias an eine Variable zurückgeben, deren Wert derzeit NULL ist (nicht instanziiert) oder ein [Nullable-Werttyp](../../language-reference/builtin-types/nullable-value-types.md) für einen Werttyp darstellt.

- Der Rückgabewert darf keine Konstante, kein Enumerationsmember, nicht der by-value-Rückgabewert einer Eigenschaft und keine Methode einer `class` oder `struct` sein. Wenn gegen diese Regel verstoßen wird, tritt der Compilerfehler CS8156 „Ein Ausdruck kann in diesem Kontext nicht verwendet werden, weil er ggf. nicht als Verweis zurückgegeben wird.“ auf.

Zusätzlich sind Verweisrückgabewerte nicht für asynchrone Methoden zulässig. Eine asynchrone Methode wird möglicherweise zurückgegeben, bevor die Ausführung abgeschlossen ist, wobei der Rückgabewert noch unbekannt ist.

## <a name="defining-a-ref-return-value"></a>Definieren eines ref-Rückgabewerts

Eine Methode, die einen *Verweisrückgabewert* zurückgibt, muss die beiden folgenden Bedingungen erfüllen:

- Die Methodensignatur enthält das [ref](../../language-reference/keywords/ref.md)-Schlüsselwort vor den Rückgabetyp.
- Jede [return](../../language-reference/keywords/return.md)-Anweisung im Hauptteil der Methode enthält das [ref](../../language-reference/keywords/ref.md)-Schlüsselwort vor den Namen der zurückgegebenen Instanz.

Das folgende Beispiel zeigt eine Methode, die die Bedingungen erfüllt und einen Verweis auf ein `Person`-Objekt mit dem Namen `p` zurückgibt:

```csharp
public ref Person GetContactInformation(string fname, string lname)
{
    // ...method implementation...
    return ref p;
}
```

## <a name="consuming-a-ref-return-value"></a>Verarbeiten eines ref-Rückgabewerts

Der Verweisrückgabewert ist ein Alias für eine andere Variable im Bereich der aufgerufenen Methode. Sie können jede Verwendung der Verweisrückgabe als Verwendung der Variable interpretieren, für die diese als Alias fungiert:

- Wenn Sie den jeweiligen Wert zuweisen, weisen Sie der Variable, für die diese als Alias fungiert, einen Wert zu.
- Wenn Sie dessen Wert lesen, lesen Sie den Wert der Variable, für die diese als Alias fungiert.
- Wenn Sie diesen *nach Verweis* zurückgeben, geben Sie einen Alias für diese Variable zurück.
- Wenn Sie ihn *nach Verweis* an eine andere Methode übergeben, übergeben Sie einen Verweis auf die Variable, für die diese als Alias fungiert.
- Wenn Sie einen Alias für einen [lokalen Verweis](#ref-locals) erstellen, erstellen Sie einen neuen Alias für diese Variable.

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

Das Schlüsselwort `ref` wird sowohl vor der Deklaration lokaler Variablen *als auch* vor dem Methodenaufruf verwendet. 

Auch auf Werte können Sie per Verweis zugreifen. In einigen Fällen erhöht dies die Leistung, da ein möglicherweise aufwendiger Kopiervorgang vermieden wird. In der folgenden Anweisung wird z.B. gezeigt, wie ein lokaler Verweiswert definiert wird, mit dem auf einen Wert verwiesen wird.

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

Das Schlüsselwort `ref` wird sowohl vor der Deklaration lokaler Variablen *als auch* vor dem Wert im zweiten Beispiel verwendet. Wenn nicht in beiden Beispielen beide `ref`-Schlüsselwörter in den Ergebnissen der Variablendeklaration und der Zuweisung enthalten sind, tritt der Compilerfehler CS8172 "Cannot initialize a by-reference variable with a value." (Eine by-reference-Variable kann nicht mit einem Wert initialisiert werden) auf. 

Vor C# 7.3 konnten lokalen ref-Variablen nach der Initialisierung nicht neu zugewiesen werden, um auf einen anderen Speicher zu verweisen. Diese Einschränkung wurde entfernt. Im folgenden Beispiel wird eine Neuzuweisung veranschaulicht:

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct; // initialization
refLocal = ref anotherVeryLargeStruct; // reassigned, refLocal refers to different storage.
```

 Lokale ref-Variablen müssen noch immer initialisiert werden, wenn sie deklariert werden.

## <a name="ref-returns-and-ref-locals-an-example"></a>Ref-Rückgaben und lokale ref-Variablen: ein Beispiel

Das folgende Beispiel definiert eine `NumberStore`-Klasse, die ein Array von Integer-Werten speichert. Die `FindNumber`-Methode gibt die erste Anzahl, die größer als oder gleich der Anzahl ist, die als Argument übergeben wurde, als Verweis zurück. Wenn keine Anzahl größer als oder gleich dem Argument ist, gibt die Methode die Anzahl im Index 0 zurück. 

[!code-csharp[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/NumberStore.cs#1)]

Im folgenden Beispiel wird die `NumberStore.FindNumber`-Methode aufgerufen, um den ersten Wert abzurufen, der größer als oder gleich 16 ist. Die aufrufende Funktion verdoppelt dann den von der Methode zurückgegebenen Wert. Die Ausgabe aus dem Beispiel zeigt die Änderung, die im Wert der Arrayelemente der `NumberStore`-Instanz wiedergegeben wird.

[!code-csharp[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/NumberStore.cs#2)]

Ohne Unterstützung für Verweisrückgabewerte wird ein solcher Vorgang durchgeführt, indem der Index des Arrayelements zusammen mit seinem Wert zurückgegeben wird. Die aufrufende Funktion kann diesen Index dann dazu verwenden, den Wert in einem separaten Methodenaufruf zu ändern. Die aufrufende Funktion kann den Index jedoch auch ändern, um auf andere Arraywerte zuzugreifen und diese zu bearbeiten.  

Im folgenden Beispiel wird gezeigt, wie die `FindNumber`-Methode nach C# 7.3 neu geschrieben werden kann, damit sie die lokale ref-Neuzuweisung verwendet:

[!code-csharp[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/NumberStoreUpdated.cs#1)]

Diese zweite Version ist durch längere Sequenzen in Szenarios, in denen die gesuchte Zahl am Ende des Arrays liegt, effizienter.

## <a name="see-also"></a>Siehe auch

- [ref (C#-Referenz)](../../language-reference/keywords/ref.md)
- [Schreiben von sicherem und effizientem Code](../../write-safe-efficient-code.md)
