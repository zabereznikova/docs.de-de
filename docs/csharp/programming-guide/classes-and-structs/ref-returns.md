---
title: "Ref-Rückgabewerte und lokale ref-Variablen (Leitfaden für C#)"
description: "Erfahren Sie, wie Sie ref-Rückgaben und lokale ref-Werte definieren und verwenden können."
author: rpetrusha
ms.author: ronpet
ms.date: 05/30/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 18cf7a4b-29f0-4b14-85b8-80af754aabd8
ms.translationtype: HT
ms.sourcegitcommit: 4582cb0ee091526423cce3fc1d8243029f34f59c
ms.openlocfilehash: 3f2ee35db5b77efcce629b6315060a723429b19c
ms.contentlocale: de-de
ms.lasthandoff: 08/16/2017

---
# <a name="ref-returns-and-ref-locals"></a>Ref-Rückgaben und lokale ref-Variablen

Ab C# 7 unterstützt C# Verweisrückgabewerte (ref-Rückgaben). Mit einem Verweisrückgabewert kann eine Methode einen Verweis auf ein Objekt statt einen Wert an eine aufrufende Funktion zurückgeben. Die aufrufende Funktion kann dann wählen, ob sie das zurückgegebene Objekt behandelt, als wäre es als Wert oder als Verweis zurückgegeben worden. Ein als Verweis zurückgegebener Wert, den die aufrufende Funktion als Verweis statt als Wert behandelt, ist ein lokaler ref-Wert.

## <a name="what-is-a-reference-return-value"></a>Was ist ein Verweisrückgabewert?

Die meisten Entwickler sind mit dem Übergeben eines Arguments *als Verweis* an eine aufgerufene Methode vertraut. Die Argumentliste einer aufgerufenen Methode umfasst einen als Verweis übergebenen Wert, und alle durch die aufgerufene Methode am Wert vorgenommenen Änderungen werden an die aufrufende Funktion zurückgegeben. Ein *Verweisrückgabewert* ist das Gegenteil:

- Bei dem Rückgabewert der aufgerufenen Methode handelt es sich um einen Verweis statt um ein Argument, das an sie übergeben wurde.

- Statt der aufgerufenen Methode kann die aufrufende Funktion den von der Methode zurückgegebenen Wert ändern.

- Anstelle von Änderungen am Argument, die im Zustand des Objekts auf der aufrufenden Funktion wiedergegeben werden, werden Änderungen durch die aufrufende Funktion am Rückgabewert der Methode im Zustand des Objekts wiedergegeben, dessen Methode aufgerufen wurde.

Verweisrückgabewerte können kompakteren Code erzeugen sowie einem Objekt die Möglichkeit geben, nur die einzelnen Datenelemente wie ein Arrayelement verfügbar zu machen, die für die aufrufende Funktion von Interesse sind. Dadurch wird die Wahrscheinlichkeit geringer, dass die aufrufende Funktion den Zustand des Objekts versehentlich ändert.

Es gibt einige Einschränkungen für den Wert, den eine Methode als Rückgabewert zurückgeben kann. Dazu gehören:

- Der Rückgabewert kann nicht `void` sein. Bei dem Versuch, eine Methode mit einem `void`-Verweisrückgabewert zu definieren, tritt der Compilerfehler CS1547 „Das void-Schlüsselwort kann in diesem Kontext nicht verwendet werden.“ auf.
 
- Der zurückgegebene Wert darf keine lokale Variable in der Methode sein, die ihn zurückgibt; er muss über einen Bereich verfügen, der außerhalb der Methode liegt, die ihn zurückgibt. Es kann sich dabei um eine Instanz oder ein statisches Feld einer Klasse oder um ein Argument handeln, das an die Methode übergeben wurde. Beim Versuch, eine lokale Variable zurückzugeben, tritt der Compilerfehler CS8168 „Cannot return local 'obj' by reference because it is not a ref local.“ (Der lokale Wert „obj“ kann nicht als Verweis zurückgegeben werden, da er kein lokaler ref-Wert ist.) auf.

- Der Rückgabewert kann nicht `null` sein. Beim Versuch, `null` zurückzugeben, tritt der Compilerfehler CS8156 „Ein Ausdruck kann in diesem Kontext nicht verwendet werden, weil er ggf. nicht als Verweis zurückgegeben wird.“ auf.

   Wenn eine Methode mit einer ref-Rückgabe einen NULL-Wert zurückgeben muss, können Sie entweder einen NULL-Wert (nicht instanziiert) für einen Verweistyp oder einen [Nullable-Typ](../nullable-types/index.md) für einen Werttyp zurückgeben.
 
- Der zurückgegebene Wert darf keine Konstante, kein Enumerationsmember und keine Eigenschaft einer `class` oder `struct` sein. Beim Versuch, diese zurückzugeben, tritt der Compilerfehler CS8156 „Ein Ausdruck kann in diesem Kontext nicht verwendet werden, weil er ggf. nicht als Verweis zurückgegeben wird.“ auf.

Darüber hinaus sind Verweisrückgabewerte bei asynchronen Methoden nicht erlaubt, da eine asynchrone Methode etwas zurückgeben könnte, bevor die Ausführung abgeschlossen und ihr Rückgabewert bekannt ist.
 
## <a name="defining-a-ref-return-value"></a>Definieren eines ref-Rückgabewerts

Sie definieren einen ref-Rückgabewert, indem Sie dem Rückgabetyp der Methodensignatur das Schlüsselwort [ref](../../language-reference/keywords/ref.md) hinzufügen. Beispielsweise gibt die folgende Signatur an, dass die `GetContactInformation`-Eigenschaft einen Verweis auf ein `Person`-Objekt an die aufrufende Funktion zurückgibt:

```csharp
public ref Person GetContactInformation(string fname, string lname);
```

Darüber hinaus muss vor dem Namen des Objekts, das durch jede [return](../../language-reference/keywords/return.md)-Anweisung im Methodentext zurückgegeben wird, das Schlüsselwort [ref](../../language-reference/keywords/ref.md) stehen. Beispielsweise gibt die folgende `return`-Anweisung ein `Person`-Objekt mit dem Namen `p` als Verweis zurück:

```csharp
return ref p;
```

## <a name="consuming-a-ref-return-value"></a>Verarbeiten eines ref-Rückgabewerts

Eine aufrufende Funktion kann einen ref-Rückgabewert auf zwei Weisen behandeln:

- Als gewöhnlicher Wert, der von einer Methode als Wert zurückgegeben wurde. Die aufrufende Funktion kann sich dazu entscheiden, zu ignorieren, dass es sich bei dem Rückgabewert um einen Verweisrückgabewert handelt. In diesem Fall werden die Änderungen an dem vom Methodenaufruf zurückgegebenen Wert im Zustand des aufgerufenen Typs nicht wiedergegeben. Wenn es sich beim zurückgegebenen Wert um einen Werttyp handelt, werden die Änderungen an dem vom Methodenaufruf zurückgegebenen Wert im Zustand des aufgerufenen Typs nicht wiedergegeben.

- Als Verweisrückgabewert. Die aufrufende Funktion muss die Variable, der der Verweisrückgabewert zugewiesen ist, als eine [lokale ref-Variable](#ref-local) definieren, und alle Änderungen an dem vom Methodenaufruf zurückgegebenen Wert werden im Zustand des aufgerufenen Typs wiedergegeben. 

## <a name="ref-locals"></a>Lokale ref-Variablen

Um den Verweisrückgabewert als Verweis behandeln zu können, muss die aufrufende Funktion den Wert mithilfe des Schlüsselworts `ref` als *lokale ref-Variable* deklarieren. Wenn beispielsweise der von der `Person.GetContactInfomation`-Methode zurückgegebene Wert als Verweis anstatt als Wert bearbeitet werden soll, erscheint der Methodenaufruf folgendermaßen:

```csharp
ref Person p = ref contacts.GetContactInformation("Brandie", "Best");
```

Beachten Sie, dass das Schlüsselwort `ref` sowohl vor der Deklaration lokaler Variablen *als auch* vor dem Methodenaufruf verwendet wird. Wenn nicht beide `ref`-Schlüsselwörter in den Ergebnissen der Variablendeklaration und der Zuweisung enthalten sind, tritt der Compilerfehler CS8172 „Eine by-reference-Variable kann nicht mit einem Wert initialisiert werden.“ auf. 
 
Spätere Änderungen am von der Methode zurückgegebenen `Person`-Objekt werden im `contacts`-Objekt wiedergegeben.

Wenn `p` nicht mithilfe des `ref`-Schlüsselworts als eine lokale ref-Variable definiert wird, werden die von der aufrufenden Funktion vorgenommenen Änderungen an `p` nicht im `contacts`-Objekt wiedergegeben.
 
## <a name="ref-returns-and-ref-locals-an-example"></a>Ref-Rückgaben und lokale ref-Variablen: ein Beispiel

Das folgende Beispiel definiert eine `NumberStore`-Klasse, die ein Array von Integer-Werten speichert. Die `FindNumber`-Methode gibt die erste Anzahl, die größer als oder gleich der Anzahl ist, die als Argument übergeben wurde, als Verweis zurück. Wenn keine Anzahl größer als oder gleich dem Argument ist, gibt die Methode die Anzahl im Index 0 zurück. 

[!CODE-cs[ref-Rückgaben](../../../../samples/snippets/csharp/programming-guide/ref-returns/ref-returns1.cs#1)]

Im folgenden Beispiel wird die `NumberStore.FindNumber`-Methode aufgerufen, um den ersten Wert abzurufen, der größer als oder gleich 16 ist. Die aufrufende Funktion verdoppelt dann den von der Methode zurückgegebenen Wert. Wie die Ausgabe aus dem Beispiel zeigt, wird diese Änderung im Wert der Arrayelemente der `NumberStore`-Instanz wiedergegeben.

[!CODE-cs[ref-Rückgaben](../../../../samples/snippets/csharp/programming-guide/ref-returns/ref-returns1.cs#2)]

Ohne Unterstützung für Verweisrückgabewerte wird ein solcher Vorgang in der Regel durchgeführt, indem der Index des Arrayelements zusammen mit seinem Wert zurückgegeben wird. Die aufrufende Funktion kann diesen Index dann dazu verwenden, den Wert in einem separaten Methodenaufruf zu ändern. Die aufrufende Funktion kann den Index jedoch auch ändern, um auf andere Arraywerte zuzugreifen und diese zu bearbeiten.  
 
## <a name="see-also"></a>Siehe auch

[ref (C#-Referenz)](../../language-reference/keywords/ref.md)

