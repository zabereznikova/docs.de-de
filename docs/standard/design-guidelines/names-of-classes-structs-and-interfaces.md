---
title: Namen von Klassen, Strukturen und Schnittstellen
ms.date: 10/22/2008
helpviewer_keywords:
- type names, guidelines
- classes [.NET Framework], names
- enumerations [.NET Framework], names
- names [.NET Framework], interfaces
- common type names
- names [.NET Framework], type names
- names [.NET Framework], classes
- interfaces [.NET Framework], names
- generic type parameters
ms.assetid: 87a4b0da-ed64-43b1-ac43-968576c444ce
ms.openlocfilehash: 2c528348c0e84037a80df9797c56f03b51c73adc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401238"
---
# <a name="names-of-classes-structs-and-interfaces"></a>Namen von Klassen, Strukturen und Schnittstellen
Die folgenden Benennungsrichtlinien gelten für die allgemeine Typbenennung.

 ✔️ DO-Namensklassen und -Strukturen mit Substantiven oder Nomenphrasen mit PascalCasing.

 Dadurch werden Typnamen von Methoden unterschieden, die mit Verbausdrücken benannt werden.

 ✔️ DO-Namensschnittstellen mit Adjektivphrasen oder gelegentlich mit Substantiven oder Substantiven.

 Nomen und Nomenphrasen sollten selten verwendet werden, und sie können darauf hinweisen, dass der Typ eine abstrakte Klasse und keine Schnittstelle sein sollte.

 ❌Geben Sie Klassennamen KEIN Präfix (z. B. "C").

 ✔️ CONSIDER, der den Namen abgeleiteter Klassen mit dem Namen der Basisklasse beendet.

 Dies ist sehr lesbar und erklärt die Beziehung deutlich. Einige Beispiele dafür im `ArgumentOutOfRangeException`Code sind: , `Exception`was `SerializableAttribute`eine Art von `Attribute`ist, und , das ist eine Art von . Es ist jedoch wichtig, bei der Anwendung dieser Richtlinie ein vernünftiges Urteilsvermögen zu verwenden; Beispielsweise ist `Button` die Klasse eine `Control` Art `Control` Ereignis, obwohl sie nicht in ihrem Namen angezeigt wird.

 ✔️ DO-Präfixschnittstellennamen mit dem Buchstaben I, um anzugeben, dass der Typ eine Schnittstelle ist.

 Beispielsweise `IComponent` sind (deskriptives `ICustomAttributeProvider` Nounon), (Nounphrase) und `IPersistable` (Adjektiv) geeignete Schnittstellennamen. Vermeiden Sie wie bei anderen Typnamen Abkürzungen.

 ✔️ stellen Sie sicher, dass sich die Namen nur durch das Präfix "I" im Schnittstellennamen unterscheiden, wenn Sie ein Klassen-Schnittstellenpaar definieren, bei dem die Klasse eine Standardimplementierung der Schnittstelle ist.

## <a name="names-of-generic-type-parameters"></a>Namen generischer Typparameter
 Generics wurden zu .NET Framework 2.0 hinzugefügt. Die Funktion führte eine neue Art von Bezeichner namens *Typparameter*ein.

 ✔️ DO-Namen generische Typparameter mit beschreibenden Namen, es sei denn, ein Name mit einem Buchstaben ist vollständig selbsterklärend und ein beschreibender Name würde keinen Wert hinzufügen.

 ✔️ CONSIDER `T` als Typparametername für Typen mit einem Einzelbuchstabentypparameter verwenden.

```csharp
public int IComparer<T> { ... }
public delegate bool Predicate<T>(T item);
public struct Nullable<T> where T:struct { ... }
```

 ✔️ DO präskriptiven Typparameternamen mit `T`.

```csharp
public interface ISessionChannel<TSession> where TSession : ISession {
    TSession Session { get; }
}
```

 ✔️ CONSIDER, die Einschränkungen angibt, die für einen Typparameter im Namen des Parameters platziert werden.

 Beispielsweise kann ein Parameter, der eingeschränkt `ISession` ist, aufgerufen `TSession`werden.

## <a name="names-of-common-types"></a>Namen gängiger Typen
 ✔️ befolgen Sie die in der folgenden Tabelle beschriebenen Richtlinien, wenn Sie Typen benennen, die von bestimmten .NET Framework-Typen abgeleitet sind oder diese implementieren.

|Basistyp|Abgeleitete/Implementierenvon Typleitlinie|
|---------------|------------------------------------------|
|`System.Attribute`|✔️ das Suffix "Attribut" zu Namen benutzerdefinierter Attributklassen hinzufügen.|
|`System.Delegate`|✔️ das Suffix "EventHandler" zu den Namen von Delegaten hinzufügen, die in Ereignissen verwendet werden.<br /><br /> ✔️ das Suffix "Callback" zu Namen anderer Delegaten als der als Ereignishandler verwendeten Hinzufügen.<br /><br /> ❌Fügen Sie einem Delegaten NICHT das Suffix "Delegate" hinzu.|
|`System.EventArgs`|✔️ das Suffix "EventArgs" hinzufügen.|
|`System.Enum`|❌Nicht von dieser Klasse ableiten; verwenden Sie stattdessen das von Ihrer Sprache unterstützte Schlüsselwort; Verwenden Sie z. B. `enum` das Schlüsselwort in C.<br /><br /> ❌Fügen Sie NICHT das Suffix "Enum" oder "Flag" hinzu.|
|`System.Exception`|✔️ das Suffix "Ausnahme" hinzufügen.|
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|✔️ das Suffix "Wörterbuch" hinzufügen. Beachten `IDictionary` Sie, dass es sich um einen bestimmten Auflistungstyp handelt, aber diese Richtlinie hat Vorrang vor der allgemeineren Auflistungsrichtlinie, die folgt.|
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|✔️ das Suffix "Collection" hinzufügen.|
|`System.IO.Stream`|✔️ das Suffix "Stream" hinzufügen.|
|`CodeAccessPermission IPermission`|✔️ das Suffix "Berechtigung" hinzufügen.|

## <a name="naming-enumerations"></a>Benennen von Enumerationen
 Namen von Enumerationstypen (auch Enumerationen genannt) sollten im Allgemeinen den Standardregeln für die Typbenennung (PascalCasing usw.) folgen. Es gibt jedoch zusätzliche Richtlinien, die speziell für Enumerungen gelten.

 ✔️ verwenden einen eindeutigen Typnamen für eine Enumeration, es sei denn, seine Werte sind Bitfelder.

 ✔️ DO einen Pluraltypnamen für eine Enumeration mit Bitfeldern als Werte verwenden, die auch als Flags enum bezeichnet werden.

 ❌Verwenden Sie NICHT ein "Enum"-Suffix in Enumerumtypnamen.

 ❌Verwenden Sie NICHT die Suffixe "Flag" oder "Flags" in Enumerumtypnamen.

 ❌Verwenden Sie NICHT ein Präfix für Enumerationswertnamen (z. B. "ad" für ADO-Enumerationen, "rtf" für Rich-Text-Enumerationen usw.).

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Weitere Informationen

- [Framework Design-Richtlinien](../../../docs/standard/design-guidelines/index.md)
- [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)
