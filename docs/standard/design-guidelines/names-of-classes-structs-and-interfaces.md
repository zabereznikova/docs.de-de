---
title: Namen von Klassen, Strukturen und Schnittstellen
description: Verwenden Sie diese Richtlinien zum Benennen von Klassen, Strukturen und Schnittstellen als Teil der Richtlinien zum Entwerfen von Bibliotheken, die .NET-Bibliotheken erweitern und interagieren.
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
ms.openlocfilehash: b9de9329cc8e1bfc47a46523c7119bb3b2c244d8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290213"
---
# <a name="names-of-classes-structs-and-interfaces"></a>Namen von Klassen, Strukturen und Schnittstellen
Die folgenden Benennungs Richtlinien gelten für die allgemeine Typbenennung.

 mit der Pass-/Schreibweise von ✔️ Klassen und Strukturen mit Nomen oder nominalen Ausdrücken benannt.

 Dies unterscheidet Typnamen von Methoden, die mit Verb Ausdrücken benannt werden.

 ✔️ Namen Schnittstellen mit Adjektiv Ausdrücken oder gelegentlich mit Nomen oder nominalen Ausdrücken.

 Nomen und nominale Ausdrücke sollten in seltenen Fällen verwendet werden, und Sie können darauf hinweisen, dass der Typ eine abstrakte Klasse und keine Schnittstelle sein sollte.

 ❌Nennen Sie keine Klassennamen als Präfix (z. b. "C").

 ✔️ sollten den Namen abgeleiteter Klassen mit dem Namen der Basisklasse beenden.

 Dies ist sehr lesbar und erläutert die Beziehung eindeutig. Einige Beispiele hierfür sind: `ArgumentOutOfRangeException` , eine Art von `Exception` und `SerializableAttribute` , die eine Art von ist `Attribute` . Es ist jedoch wichtig, bei der Anwendung dieser Richtlinie ein vernünftiges Urteil zu verwenden. Beispielsweise ist die- `Button` Klasse eine Art von `Control` Ereignis, obwohl `Control` nicht im Namen angezeigt wird.

 ✔️ Geben Sie Schnittstellennamen mit dem Buchstaben I an, um anzugeben, dass der Typ eine Schnittstelle ist.

 Beispielsweise `IComponent` sind (beschreibende Substantiv), `ICustomAttributeProvider` (Substantiv Phrase) und `IPersistable` (Adjektiv) geeignete Schnittstellennamen. Vermeiden Sie Abkürzungen wie andere Typnamen.

 Stellen Sie ✔️ sicher, dass sich die Namen nur durch das Präfix "I" für den Schnittstellennamen unterscheiden, wenn Sie ein Klassen –-Schnittstellen Paar definieren, bei dem die Klasse eine Standard Implementierung der Schnittstelle ist.

## <a name="names-of-generic-type-parameters"></a>Namen von generischen Typparametern
 Generika wurden .NET Framework 2,0 hinzugefügt. Mit der Funktion wurde eine neue Art von Bezeichner namens *Typparameter*eingeführt.

 ✔️ Namen generischer Typparameter mit beschreibenden Namen verwenden, es sei denn, ein einzelner Buchstabe ist vollständig selbsterklärend, und ein beschreibender Name würde keinen Wert hinzufügen.

 ✔️ die Verwendung `T` von als Typparameter Name für Typen mit einem Typparameter mit einem einzelnen Buchstaben in Erwägung gezogen.

```csharp
public int IComparer<T> { ... }
public delegate bool Predicate<T>(T item);
public struct Nullable<T> where T:struct { ... }
```

 ✔️ machen beschreibende Typparameter Namen mit Präfix `T` .

```csharp
public interface ISessionChannel<TSession> where TSession : ISession {
    TSession Session { get; }
}
```

 ✔️ in Erwägung gezogen, dass Einschränkungen für einen Typparameter im Namen des Parameters eingefügt werden.

 Beispielsweise kann ein Parameter, der auf eingeschränkt ist, `ISession` aufgerufen werden `TSession` .

## <a name="names-of-common-types"></a>Namen allgemeiner Typen
 ✔️ Befolgen Sie die in der folgenden Tabelle beschriebenen Richtlinien, wenn Sie Typen benennen, die von abgeleitet sind oder bestimmte .NET Framework Typen implementieren.

|Basistyp|Abgeleitete/implementierende typrichtlinie|
|---------------|------------------------------------------|
|`System.Attribute`|Fügen Sie den Namen von benutzerdefinierten Attribut Klassen ✔️ das Suffix "Attribute" hinzu.|
|`System.Delegate`|✔️ Fügen Sie das Suffix "EventHandler" den Namen von Delegaten hinzu, die in Ereignissen verwendet werden.<br /><br /> ✔️ fügen das Suffix "Callback" Namen von Delegaten hinzu, die nicht als Ereignishandler verwendet werden.<br /><br /> ❌Fügen Sie das Suffix "Delegat" nicht zu einem Delegaten hinzu.|
|`System.EventArgs`|Fügen Sie ✔️ das Suffix "EventArgs" hinzu.|
|`System.Enum`|❌Nicht von dieser Klasse ableiten; Verwenden Sie stattdessen das von Ihrer Sprache unterstützte Schlüsselwort; Verwenden Sie z. b. in c# das- `enum` Schlüsselwort.<br /><br /> ❌Fügen Sie das Suffix "Enum" oder "Flag" nicht hinzu.|
|`System.Exception`|Fügen Sie ✔️ das Suffix "Exception" hinzu.|
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|Fügen Sie ✔️ das Suffix "Dictionary" hinzu. Beachten Sie, dass es `IDictionary` sich um einen bestimmten Sammlungstyp handelt. diese Richtlinie hat jedoch Vorrang vor den folgenden allgemeinen Auflistungs Richtlinien.|
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|Fügen Sie ✔️ das Suffix "Collection" hinzu.|
|`System.IO.Stream`|Fügen Sie ✔️ das Suffix "Stream" hinzu.|
|`CodeAccessPermission IPermission`|✔️ Fügen Sie das Suffix "Berechtigung" hinzu.|

## <a name="naming-enumerations"></a>Benennen von Enumerationen
 Namen von Enumerationstypen (auch als Enumerationen bezeichnet) sollten im Allgemeinen den standardmäßigen typbenennungs Regeln (pascalnaming, usw.) entsprechen. Es gibt jedoch weitere Richtlinien, die speziell für-aufzählen gelten.

 ✔️ einen eindeutigen Typnamen für eine Enumeration verwenden, es sei denn, die Werte sind Bitfelder.

 ✔️ einen Plural Typnamen für eine Enumeration mit Bitfeldern als Werte verwenden, die auch als Flags-Enumeration bezeichnet werden.

 ❌Verwenden Sie kein "Enumeration"-Suffix in Enumeration-Typnamen.

 ❌Verwenden Sie keine "Flag"-oder "Flags"-Suffixe in Enumeration-Typnamen.

 ❌Verwenden Sie kein Präfix für enumerationswertnamen (z. b. "AD" für ADO-Enumerationen, "RTF" für Rich-Text-Enumerationen usw.).

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Framework-Entwurfs Richtlinien](index.md)
- [Benennungs Richtlinien](naming-guidelines.md)
