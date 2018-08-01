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
ms.openlocfilehash: a1841fbfcb76d5b56681b63ec4b39e9a7418707f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33576141"
---
# <a name="names-of-classes-structs-and-interfaces"></a>Namen von Klassen, Strukturen und Schnittstellen
Benennungskonventionen Richtlinien gelten für die Benennung von Typ "Allgemein".  
  
 **✓ DO** Benennen von Klassen und Strukturen Nomen und nominale Ausdrücke, die unter Verwendung von PascalCasing.  
  
 Dadurch unterscheidet Namen von Methoden, die mit Verb Ausdrücke benannt werden.  
  
 **✓ DO** Schnittstellen mit adjektivische Ausdrücke oder gelegentlich mit Nomen und nominale Ausdrücke benennen.  
  
 Nomen und nominale Ausdrücke sollte nur selten verwendet werden, und sie wird angegeben, dass der Typ eine abstrakte Klasse und keine Schnittstelle sein soll.  
  
 **X DO NOT** Klassennamen ein Präfix (z. B. "C").  
  
 **✓ CONSIDER** endet der Name der abgeleiteten Klassen mit dem Namen der Basisklasse.  
  
 Dies ist sehr gut lesbar und erklärt die Beziehung eindeutig. Beispiele hierzu finden Sie unter Code sind: `ArgumentOutOfRangeException`, also eine Art von `Exception`, und `SerializableAttribute`, also eine Art von `Attribute`. Es ist jedoch mit angemessenen Urteil in diese Richtlinie anwenden; z. B. die `Button` Klasse ist eine Art von `Control` Ereignis, obwohl `Control` nicht in ihrem Namen angezeigt.  
  
 **✓ DO** Schnittstellennamen als Präfix mit dem Buchstaben I, um anzugeben, dass der Typ eine Schnittstelle ist.  
  
 Beispielsweise `IComponent` (beschreibendes Nomen) `ICustomAttributeProvider` (nominaler Ausdruck), und `IPersistable` (Adjektiv) sind die Namen der entsprechenden Schnittstelle. Vermeiden Sie wie bei anderen Typnamen Abkürzungen.  
  
 **✓ DO** stellen Sie sicher, dass die Namen unterscheiden sich nur durch "I" auf der Schnittstellenname Präfix, wenn Sie ein paar Klassenschnittstelle – definieren, wenn die Klasse einer standardmäßigen Implementierung der Schnittstelle befindet.  
  
## <a name="names-of-generic-type-parameters"></a>Namen von generischen Typparametern  
 .NET Framework 2.0 wurden Generika hinzugefügt. Die Funktion eingeführt, eine neue Art von Bezeichner mit dem Namen *Typparameter*.  
  
 **✓ DO** generische Typparameter beschreibende Namen weisen Sie nur ein einzigen Buchstaben Namen vollständig selbsterklärend und ein aussagekräftigen Namen, würde kein Wert hinzugefügt.  
  
 **✓ CONSIDER** mit `T` als der Typparametername für Typen mit einem einzelnen Buchstaben Typparameter.  
  
```  
public int IComparer<T> { ... }  
public delegate bool Predicate<T>(T item);  
public struct Nullable<T> where T:struct { ... }  
```  
  
 **✓ DO** beschreibende Typparameternamen mit Präfix `T`.  
  
```  
public interface ISessionChannel<TSession> where TSession : ISession{  
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
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|**✓ DO** fügen Sie das Suffix "Wörterbuch". Beachten Sie, dass `IDictionary` ist ein spezieller Typ einer Auflistung, aber diese Richtlinie hat Vorrang vor der allgemeineren Sammlungen-Richtlinie, die folgt.|  
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|**✓ DO** fügen Sie das Suffix "Collection".|  
|`System.IO.Stream`|**✓ DO** fügen Sie das Suffix "Stream".|  
|`CodeAccessPermission IPermission`|**✓ DO** fügen Sie das Suffix "Berechtigung".|  
  
## <a name="naming-enumerations"></a>Benennen von Enumerationen  
 Namen von Enumerationstypen (so genannte Enumerationen) sollte im Allgemeinen die Typ-Benennung Standardregeln (PascalCasing, usw.) entsprechen. Es gibt jedoch zusätzliche Richtlinien, die speziell für Enumerationen gelten.  
  
 **✓ DO** verwenden Sie einen Namen im singular für eine Enumeration, es sei denn, seine Werte Bitfelder sind.  
  
 **✓ DO** verwenden Sie einen Namen im plural für eine Enumeration mit Bitfelder als Werte, die so genannte Flags-Enumeration.  
  
 **X DO NOT** eine Suffix "Enum" im Namen der Enum-Typen verwenden.  
  
 **X DO NOT** verwenden "Flag" oder "Flags"-Suffixe in Enum-Typnamen.  
  
 **X DO NOT** ein Präfix auf Enumeration Wertnamen (z. B. "Ad" für ADO-Enumerationen.), "Rtf" für rich-Text-Enumerationen usw. verwenden.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
 [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)
