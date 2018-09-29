---
title: Namen von Klassen, Strukturen und Schnittstellen
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c56f840bc5ebd5070c9b686384751acab3f0203
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/29/2018
ms.locfileid: "47454327"
---
# <a name="names-of-classes-structs-and-interfaces"></a>Namen von Klassen, Strukturen und Schnittstellen
Die Benennungsrichtlinien, die Folgen gelten für die Benennung von "Allgemein".  
  
 **✓ DO** Benennen von Klassen und Strukturen Nomen und nominale Ausdrücke, die unter Verwendung von PascalCasing.  
  
 Dies unterscheidet Namen von Methoden, die mit den Verb Meldungen benannt werden.  
  
 **✓ DO** Schnittstellen mit adjektivische Ausdrücke oder gelegentlich mit Nomen und nominale Ausdrücke benennen.  
  
 Nomen und nominale Ausdrücke sollte nur selten verwendet werden, und sie wird angegeben, dass der Typ eine abstrakte Klasse, und keine Schnittstelle sein soll.  
  
 **X DO NOT** Klassennamen ein Präfix (z. B. "C").  
  
 **✓ CONSIDER** endet der Name der abgeleiteten Klassen mit dem Namen der Basisklasse.  
  
 Dies ist sehr gut lesbar und deutlich erklärt die Beziehung. Sind einige Beispiele hierfür im Code: `ArgumentOutOfRangeException`, d.h. eine Art von `Exception`, und `SerializableAttribute`, d.h. eine Art von `Attribute`. Allerdings ist es wichtig, sinnvolle Entscheidung bei der Anwendung von dieser Richtlinie zu verwenden; z. B. die `Button` Klasse ist eine Art von `Control` Ereignis zwar `Control` nicht in ihrem Namen angezeigt.  
  
 **✓ DO** Schnittstellennamen als Präfix mit dem Buchstaben I, um anzugeben, dass der Typ eine Schnittstelle ist.  
  
 Z. B. `IComponent` (beschreibendes Nomen) `ICustomAttributeProvider` (nominaler Ausdruck), und `IPersistable` (Adjektiv) werden die Namen der entsprechenden Schnittstellen. Wie bei anderen Namen, vermeiden Sie Abkürzungen.  
  
 **✓ DO** stellen Sie sicher, dass die Namen unterscheiden sich nur durch "I" auf der Schnittstellenname Präfix, wenn Sie ein paar Klassenschnittstelle – definieren, wenn die Klasse einer standardmäßigen Implementierung der Schnittstelle befindet.  
  
## <a name="names-of-generic-type-parameters"></a>Namen von generischen Typparametern  
 Generika wurden in .NET Framework 2.0 hinzugefügt. Das Feature eingeführt, eine neue Art von Bezeichner mit dem Namen *Typparameter*.  
  
 **✓ DO** generische Typparameter beschreibende Namen weisen Sie nur ein einzigen Buchstaben Namen vollständig selbsterklärend und ein aussagekräftigen Namen, würde kein Wert hinzugefügt.  
  
 **✓ CONSIDER** mit `T` als der Typparametername für Typen mit einem einzelnen Buchstaben Typparameter.  
  
```  
public int IComparer<T> { ... }  
public delegate bool Predicate<T>(T item);  
public struct Nullable<T> where T:struct { ... }  
```  
  
 **✓ DO** beschreibende Typparameternamen mit Präfix `T`.  
  
```  
public interface ISessionChannel<TSession> where TSession : ISession {  
    TSession Session { get; }  
}  
```  
  
 **✓ CONSIDER** , der angibt, Einschränkungen für einen Typparameter, den Namen der Parameter platziert.  
  
 Z. B. ein Parameter beschränkt auf `ISession` aufgerufen werden könnte `TSession`.  
  
## <a name="names-of-common-types"></a>Namen von allgemeinen Typen  
 **✓ DO** beim Benennen von Typen abgeleitet wurde, oder implementieren bestimmte .NET Framework-Typen in der folgenden Tabelle beschriebenen Richtlinien folgen.  
  
|Basistyp|Typ-Richtlinie abgeleitet/implementieren|  
|---------------|------------------------------------------|  
|`System.Attribute`|**✓ DO** Namen von benutzerdefinierten Attributklassen das Suffix "Attribute" hinzugefügt.|  
|`System.Delegate`|**✓ DO** fügen Sie das Suffix "EventHandler" in Namen von Delegaten, die in den Ereignissen verwendet werden.<br /><br /> **✓ DO** fügen Sie das Suffix "Callback" in Namen von Delegaten, ausgenommen derer, die als Ereignishandler verwendet.<br /><br /> **X DO NOT** fügen Sie das Suffix "Delegat" an einen Delegaten.|  
|`System.EventArgs`|**✓ DO** fügen Sie das Suffix "EventArgs".|  
|`System.Enum`|**X DO NOT** von dieser Klasse abgeleitet werden; verwenden Sie das Schlüsselwort stattdessen von der Sprache unterstützt; beispielsweise in c# verwenden das `enum` Schlüsselwort.<br /><br /> **X DO NOT** fügen Sie das Suffix "Enum" oder "Flag für"."|  
|`System.Exception`|**✓ DO** fügen Sie das Suffix "Ausnahme".|  
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|**✓ DO** fügen Sie das Suffix "Wörterbuch". Beachten Sie, dass `IDictionary` ist ein spezieller Typ der Auflistung, aber diese Richtlinie hat Vorrang vor mehr Auflistungen grundsätzlich, das folgt.|  
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|**✓ DO** fügen Sie das Suffix "Collection".|  
|`System.IO.Stream`|**✓ DO** fügen Sie das Suffix "Stream".|  
|`CodeAccessPermission IPermission`|**✓ DO** fügen Sie das Suffix "Berechtigung".|  
  
## <a name="naming-enumerations"></a>Benennen von Enumerationen  
 Namen von Enumerationstypen (auch als "Enumerationen" bezeichnet) sollten im allgemeinen Typ Namen Standardregeln (PascalCasing usw.) befolgen. Es gibt jedoch zusätzliche Richtlinien, die speziell für Enumerationen gelten.  
  
 **✓ DO** verwenden Sie einen Namen im singular für eine Enumeration, es sei denn, seine Werte Bitfelder sind.  
  
 **✓ DO** verwenden Sie einen Namen im plural für eine Enumeration mit Bitfelder als Werte, die so genannte Flags-Enumeration.  
  
 **X DO NOT** eine Suffix "Enum" im Namen der Enum-Typen verwenden.  
  
 **X DO NOT** verwenden "Flag" oder "Flags"-Suffixe in Enum-Typnamen.  
  
 **X DO NOT** ein Präfix auf Enumeration Wertnamen (z. B. "Ad" für ADO-Enumerationen.), "Rtf" für rich-Text-Enumerationen usw. verwenden.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
- [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)
