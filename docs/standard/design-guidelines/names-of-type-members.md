---
title: Namen von Typmembern
description: Erfahren Sie mehr über die Richtlinien für die Benennung von Typmembern in .net, z. b. Methoden, Eigenschaften, Ereignisse und Felder.
ms.date: 10/22/2008
helpviewer_keywords:
- events [.NET Framework], names
- methods [.NET Framework], names
- type members
- properties [.NET Framework], names
- fields, names
- field names
- names [.NET Framework], type members
- members [.NET Framework], type
ms.assetid: af5a0903-36af-4c2a-b848-cf959affeaa5
ms.openlocfilehash: 85f3137b4a8d75de92b12d6535415743395db890
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820912"
---
# <a name="names-of-type-members"></a>Namen von Typmembern
Typen bestehen aus Membern: Methoden, Eigenschaften, Ereignisse, Konstruktoren und Felder. In den folgenden Abschnitten werden die Richtlinien zum Benennen von Typmembern beschrieben.

## <a name="names-of-methods"></a>Namen von Methoden
 Da Methoden das Ausführen von Aktionen ermöglichen, erfordern die Entwurfsrichtlinien, dass Methodennamen Verben oder Verbalphrasen sind. Mit dieser Richtlinie ist es auch möglich, Methodennamen von Eigenschafts- und Typnamen zu unterscheiden, die Nominal- oder Adjektivphrasen sind.

 ✔️ Methodennamen, bei denen es sich um Verben oder Verb Ausdrücke handelt.

```csharp
public class String {
    public int CompareTo(...);
    public string[] Split(...);
    public string Trim();
}
```

## <a name="names-of-properties"></a>Namen von Eigenschaften
 Anders als bei anderen Membern sollten Sie Eigenschaften einen Namen geben, der eine Nominal- oder Adjektivphrase ist. Der Grund dafür ist, dass sich eine Eigenschaft auf Daten bezieht, und der Name der Eigenschaft dies widerspiegelt. Eigenschaftennamen werden immer in Pascal-Schreibweise geschrieben.

 ✔️ Sie namens Eigenschaften mit einem Substantiv, nominalen Ausdruck oder Adjektiv.

 ❌ Verwenden Sie keine Eigenschaften, die mit dem Namen der Get-Methoden identisch sind, wie im folgenden Beispiel gezeigt:

 `public string TextWriter { get {...} set {...} }` `public string GetTextWriter(int value) { ... }`

 Dieses Muster gibt normalerweise an, dass die Eigenschaft eigentlich eine Methode sein soll.

 ✔️ namens Sammlungs Eigenschaften mit einem Plural Ausdruck, der die Elemente in der Auflistung beschreibt, anstatt einen Singular Ausdruck, gefolgt von "List" oder "Collection" zu verwenden.

 ✔️ die boolesche Eigenschaften mit einem positiven Ausdruck ( `CanSeek` anstelle von `CantSeek` ) benennen. Optional können Sie auch boolesche Eigenschaften mit "is", "Can" oder "has" versehen, aber nur an der Stelle, an der der Wert hinzugefügt wird.

 ✔️ sollten Sie eine Eigenschaft mit dem gleichen Namen wie der Typ eingeben.

 Die folgende Eigenschaft ruft ordnungsgemäß einen Enumerationswert namens `Color` ab und legt ihn fest. Die Eigenschaft heißt also `Color`:

```csharp
public enum Color {...}
public class Control {
    public Color Color { get {...} set {...} }
}
```

## <a name="names-of-events"></a>Namen von Ereignissen
 Ereignisse beziehen sich immer auf Aktionen, also entweder auf eine Aktion, die gerade passiert oder eine, die in der Vergangenheit liegt. Deshalb werden Ereignisse mit Verben benannt (wie Methoden auch), und die Verbkonjugation wird genutzt, um den Zeitpunkt anzugeben, wann das Ereignis ausgelöst wird.

 ✔️ Ereignisse mit einem Verb oder einem Verb Ausdruck zu benennen.

 Beispiele dafür sind `Clicked`, `Painting`, `DroppedDown` usw.

 ✔️ die Namen von Ereignissen mit einem Konzept von before und After zu versehen, wobei die vorhandenen und vergangenen Mandanten verwendet werden.

 Beispielsweise wird ein Schließereignis, das ausgelöst wird, bevor ein Fenster geschlossen wird, als `Closing` bezeichnet. Ein Ereignis, das nach dem Schließen des Fensters ausgelöst wird, wird als `Closed` bezeichnet.

 ❌ Verwenden Sie nicht die Präfixe "Before" oder "After" oder postfixes, um Pre-und Post-Ereignisse anzugeben. Verwenden Sie wie oben beschrieben die Gegenwarts- und Vergangenheitsformen.

 ✔️ Do-Ereignishandler (Delegaten, die als Typen von Ereignissen verwendet werden) mit dem Suffix "EventHandler", wie im folgenden Beispiel gezeigt:

 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`

 in ✔️ werden zwei Parameter mit dem Namen `sender` und `e` in Ereignis Handlern verwendet.

 Der sender-Parameter stellt das Objekt dar, das das Ereignis ausgelöst hat. Der sender-Parameter ist in der Regel vom Typ `object`, auch wenn es möglich ist, einen spezifischeren Typ zu verwenden.

 ✔️ Do Event Argument-Klassen mit dem Suffix "EventArgs".

## <a name="names-of-fields"></a>Feldnamen
 Die Richtlinien für die Benennung von Feldern gelten für statische öffentliche und geschützte Felder. Interne und private Felder sind nicht Gegenstand von Richtlinien, und öffentliche oder geschützte Instanzfelder sind laut den [Entwurfsrichtlinien für Member](member.md) nicht zulässig.

 ✔️ Verwenden Sie die pascalschreibweise in Feldnamen.

 ✔️ Felder mit einem Substantiv, Substantiv Ausdruck oder Adjektiv benennen.

 ❌ Verwenden Sie kein Präfix für Feldnamen.

 Verwenden Sie beispielsweise nicht „g_“ oder „s_“, um statische Felder anzugeben.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Framework-Entwurfs Richtlinien](index.md)
- [Benennungs Richtlinien](naming-guidelines.md)
