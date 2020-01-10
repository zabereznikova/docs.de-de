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
ms.openlocfilehash: 96d9904af0106d797c9fc5199bda76da53874451
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709243"
---
# <a name="names-of-classes-structs-and-interfaces"></a>Namen von Klassen, Strukturen und Schnittstellen
Die folgenden Benennungs Richtlinien gelten für die allgemeine Typbenennung.  
  
 **✓ DO** Benennen von Klassen und Strukturen Nomen und nominale Ausdrücke, die unter Verwendung von PascalCasing.  
  
 Dies unterscheidet Typnamen von Methoden, die mit Verb Ausdrücken benannt werden.  
  
 **✓ DO** Schnittstellen mit adjektivische Ausdrücke oder gelegentlich mit Nomen und nominale Ausdrücke benennen.  
  
 Nomen und nominale Ausdrücke sollten in seltenen Fällen verwendet werden, und Sie können darauf hinweisen, dass der Typ eine abstrakte Klasse und keine Schnittstelle sein sollte.  
  
 **X DO NOT** Klassennamen ein Präfix (z. B. "C").  
  
 **✓ CONSIDER** endet der Name der abgeleiteten Klassen mit dem Namen der Basisklasse.  
  
 Dies ist sehr lesbar und erläutert die Beziehung eindeutig. Einige Beispiele hierfür sind: `ArgumentOutOfRangeException`, eine Art `Exception`und `SerializableAttribute`, bei der es sich um eine Art `Attribute`handelt. Es ist jedoch wichtig, bei der Anwendung dieser Richtlinie ein vernünftiges Urteil zu verwenden. die `Button`-Klasse ist beispielsweise eine Art `Control` Ereignisses, obwohl `Control` nicht im Namen angezeigt wird.  
  
 **✓ DO** Schnittstellennamen als Präfix mit dem Buchstaben I, um anzugeben, dass der Typ eine Schnittstelle ist.  
  
 Beispielsweise sind `IComponent` (Beschreibungs Substantiv), `ICustomAttributeProvider` (nominaler Ausdruck) und `IPersistable` (Adjektiv) geeignete Schnittstellennamen. Vermeiden Sie Abkürzungen wie andere Typnamen.  
  
 **✓ DO** stellen Sie sicher, dass die Namen unterscheiden sich nur durch "I" auf der Schnittstellenname Präfix, wenn Sie ein paar Klassenschnittstelle – definieren, wenn die Klasse einer standardmäßigen Implementierung der Schnittstelle befindet.  
  
## <a name="names-of-generic-type-parameters"></a>Namen von generischen Typparametern  
 Generika wurden .NET Framework 2,0 hinzugefügt. Mit der Funktion wurde eine neue Art von Bezeichner namens *Typparameter*eingeführt.  
  
 **✓ DO** generische Typparameter beschreibende Namen weisen Sie nur ein einzigen Buchstaben Namen vollständig selbsterklärend und ein aussagekräftigen Namen, würde kein Wert hinzugefügt.  
  
 **✓ CONSIDER** mit `T` als der Typparametername für Typen mit einem einzelnen Buchstaben Typparameter.  
  
```csharp  
public int IComparer<T> { ... }  
public delegate bool Predicate<T>(T item);  
public struct Nullable<T> where T:struct { ... }  
```  
  
 **✓ DO** beschreibende Typparameternamen mit Präfix `T`.  
  
```csharp  
public interface ISessionChannel<TSession> where TSession : ISession {  
    TSession Session { get; }  
}  
```  
  
 **✓ CONSIDER** , der angibt, Einschränkungen für einen Typparameter, den Namen der Parameter platziert.  
  
 Beispielsweise kann ein Parameter, der auf `ISession` eingeschränkt ist, `TSession`aufgerufen werden.  
  
## <a name="names-of-common-types"></a>Namen allgemeiner Typen  
 **✓ DO** beim Benennen von Typen abgeleitet wurde, oder implementieren bestimmte .NET Framework-Typen in der folgenden Tabelle beschriebenen Richtlinien folgen.  
  
|Basistyp|Abgeleitete/implementierende typrichtlinie|  
|---------------|------------------------------------------|  
|`System.Attribute`|**✓ DO** Namen von benutzerdefinierten Attributklassen das Suffix "Attribute" hinzugefügt.|  
|`System.Delegate`|**✓ DO** fügen Sie das Suffix "EventHandler" in Namen von Delegaten, die in den Ereignissen verwendet werden.<br /><br /> **✓ DO** fügen Sie das Suffix "Callback" in Namen von Delegaten, ausgenommen derer, die als Ereignishandler verwendet.<br /><br /> **X DO NOT** fügen Sie das Suffix "Delegat" an einen Delegaten.|  
|`System.EventArgs`|**✓ DO** fügen Sie das Suffix "EventArgs".|  
|`System.Enum`|**X DO NOT** von dieser Klasse abgeleitet werden; verwenden Sie das Schlüsselwort stattdessen von der Sprache unterstützt; beispielsweise in c# verwenden das `enum` Schlüsselwort.<br /><br /> **X DO NOT** fügen Sie das Suffix "Enum" oder "Flag für"."|  
|`System.Exception`|**✓ DO** fügen Sie das Suffix "Ausnahme".|  
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|**✓ DO** fügen Sie das Suffix "Wörterbuch". Beachten Sie, dass `IDictionary` eine bestimmte Art von Sammlung ist, aber diese Richtlinie hat Vorrang vor den folgenden allgemeinen Auflistungs Richtlinien.|  
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|**✓ DO** fügen Sie das Suffix "Collection".|  
|`System.IO.Stream`|**✓ DO** fügen Sie das Suffix "Stream".|  
|`CodeAccessPermission IPermission`|**✓ DO** fügen Sie das Suffix "Berechtigung".|  
  
## <a name="naming-enumerations"></a>Benennen von Enumerationen  
 Namen von Enumerationstypen (auch als Enumerationen bezeichnet) sollten im Allgemeinen den standardmäßigen typbenennungs Regeln (pascalnaming, usw.) entsprechen. Es gibt jedoch weitere Richtlinien, die speziell für-aufzählen gelten.  
  
 **✓ DO** verwenden Sie einen Namen im singular für eine Enumeration, es sei denn, seine Werte Bitfelder sind.  
  
 **✓ DO** verwenden Sie einen Namen im plural für eine Enumeration mit Bitfelder als Werte, die so genannte Flags-Enumeration.  
  
 **X DO NOT** eine Suffix "Enum" im Namen der Enum-Typen verwenden.  
  
 **X DO NOT** verwenden "Flag" oder "Flags"-Suffixe in Enum-Typnamen.  
  
 **X DO NOT** ein Präfix auf Enumeration Wertnamen (z. B. "Ad" für ADO-Enumerationen.), "Rtf" für rich-Text-Enumerationen usw. verwenden.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)
