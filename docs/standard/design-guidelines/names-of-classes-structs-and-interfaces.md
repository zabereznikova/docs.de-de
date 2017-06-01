---
title: "Namen von Klassen, Strukturen und Schnittstellen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Typnamen Richtlinien"
  - "[Klassen [.NET Framework], Namen"
  - "[Enumerationen [.NET Framework], Namen"
  - "[Namen [.NET Framework], Schnittstellen"
  - "Allgemeine Typnamen"
  - "[Namen [.NET Framework], Namen"
  - "[Namen [.NET Framework], Klassen"
  - "[Schnittstellen [.NET Framework], Namen"
  - "Generische Typparameter"
ms.assetid: 87a4b0da-ed64-43b1-ac43-968576c444ce
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# Namen von Klassen, Strukturen und Schnittstellen
Die Benennungskonventionen folgenden Richtlinien gelten für die Benennung von allgemeinen Typs.  
  
 **✓ führen** Benennen von Klassen und Strukturen Nomen und nominale Ausdrücke, die unter Verwendung von PascalCasing.  
  
 Dadurch unterscheidet Geben Sie die Namen von Methoden, die mit Verb benannt werden.  
  
 **✓ führen** benennen Sie Schnittstellen mit adjektivische Ausdrücke oder gelegentlich mit Nomen und nominale Ausdrücke.  
  
 Nomen und nominale Ausdrücke sollte nur selten verwendet werden, und sie wird angegeben, dass der Typ eine abstrakte Klasse und keine Schnittstelle sein sollte.  
  
 **X nicht** Klassennamen ein Präfix \(z. B. "C"\).  
  
 **✓ ggf.** endet der Name der abgeleiteten Klassen mit dem Namen der Basisklasse.  
  
 Dies ist sehr gut lesbar und erklärt die Beziehung eindeutig. Beispiele hierzu finden Sie in Code sind: `ArgumentOutOfRangeException`, also eine Art von `Exception`, und `SerializableAttribute`, also eine Art von `Attribute`. Allerdings ist es wichtig, sinnvolle Entscheidung bei der Anwendung dieser Richtlinie verwenden; z. B. die `Button` Klasse ist eine Art von `Control` Ereignis zwar `Control` nicht auf seinen Namen angezeigt.  
  
 **✓ führen** Schnittstellennamen als Präfix mit dem Buchstaben I, um anzugeben, dass der Typ eine Schnittstelle ist.  
  
 Z. B. `IComponent` \(beschreibendes Substantiv\), `ICustomAttributeProvider` \(nominaler Ausdruck\), und `IPersistable` \(Adjektiv\) sind geeignete Schnittstellennamen. Vermeiden Sie wie bei anderen Typnamen Abkürzungen.  
  
 **✓ führen** stellen Sie sicher, dass die Namen unterscheiden sich nur durch "I" auf den Schnittstellennamen Präfix, wenn Sie ein paar Klasse\-Schnittstelle definieren, in dem die Klasse ein standard\-Implementierung der Schnittstelle ist.  
  
## Namen von generischen Typparametern  
 Generika wurden in .NET Framework 2.0 hinzugefügt. Die Funktion eingeführt, eine neue Art von Bezeichner mit dem Namen *Typparameter*.  
  
 **✓ führen** generische Typparameter beschreibende Namen geben Sie ein Namen für die einzelnen Buchstaben ist vollkommen selbsterklärend, und ein beschreibender Name ist ohne zusätzlichen Wert.  
  
 **✓ ggf.** mit `T` als Typparameternamen für Typen mit einem einzigen Buchstaben Parameter.  
  
```  
public int IComparer<T> { ... }  
public delegate bool Predicate<T>(T item);  
public struct Nullable<T> where T:struct { ... }  
```  
  
 **✓ führen** beschreibende Parameternamen mit Präfix `T`.  
  
```  
public interface ISessionChannel<TSession> where TSession : ISession{  
    TSession Session { get; }  
}  
```  
  
 **✓ ggf.** der angibt, Einschränkungen für einen Typ\-Parameter den Namen der Parameter platziert.  
  
 Z. B. ein Parameter eingeschränkt auf `ISession` aufgerufen werden könnte `TSession`.  
  
## Namen allgemeiner Typen  
 **✓ führen** befolgen Sie die Richtlinien in der folgenden Tabelle beschrieben werden, beim Benennen von Typen abgeleitet oder bestimmte .NET Framework\-Typen implementieren.  
  
|Basistyp|Abgeleitete Implementierung\/Typ\-Richtlinie|  
|--------------|--------------------------------------------------|  
|`System.Attribute`|**✓ führen** Namen von benutzerdefinierten Attributklassen das Suffix "Attribute" hinzugefügt. Fügen Sie das Suffix "Attribute" Namen der benutzerdefinierten Attributklassen.|  
|`System.Delegate`|**✓ führen** fügen Sie das Suffix "EventHandler" Namen von Delegaten, die Ereignisse verwendet werden.<br /><br /> **✓ führen** fügen Sie das Suffix "Callback" auf den Namen des Delegaten, ausgenommen derer, die als Ereignishandler verwendet.<br /><br /> **X nicht** das Suffix "Delegate" zu einem Delegaten hinzufügen.|  
|`System.EventArgs`|**✓ führen** fügen Sie das Suffix "EventArgs".|  
|`System.Enum`|**X nicht** von dieser Klasse ableiten, verwenden Sie das Schlüsselwort stattdessen von der Sprache unterstützt, verwenden, z. B. Enum\-Schlüsselwort in c\#.<br /><br /> **X nicht** fügen Sie das Suffix "Enum" oder "Flag".|  
|`System.Exception`|**✓ führen** fügen Sie das Suffix "Ausnahme".|  
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|**✓ führen** fügen Sie das Suffix "Wörterbuch". Beachten Sie, dass `IDictionary` ist ein spezieller Typ der Auflistung, aber diese Richtlinie hat Vorrang vor der allgemeineren Sammlungen\-Richtlinie, die folgt.|  
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|**✓ führen** fügen Sie das Suffix "Sammlung".|  
|`System.IO.Stream`|**✓ führen** fügen Sie das Suffix "Stream".|  
|`CodeAccessPermission IPermission`|**✓ führen** fügen Sie das Suffix "Berechtigung".|  
  
## Benennen von Enumerationen  
 Namen von Enumerationstypen \(auch als Enumerationen\) sollte im Allgemeinen die Typ Benennung Standardregeln \(PascalCasing usw.\) folgen. Es gibt jedoch zusätzliche Richtlinien, die speziell für Enumerationen gelten.  
  
 **✓ führen** einen Namen im singular für eine Enumeration verwenden, es sei denn, seine Werte Bitfelder sind.  
  
 **✓ führen** verwenden Sie einen Namen im plural für eine Enumeration mit Bitfelder als Werte, die so genannte Flags\-Enumeration.  
  
 **X nicht** eine Suffix "Enum" im Namen der Enum\-Typ verwenden.  
  
 **X nicht** "Flag" oder "Flags" Suffixe in der Enumeration geben Sie Namen.  
  
 **X nicht** ein Präfix für Namen von Enumerationswerten \(z. B. "Ad" für ADO\-Enumerationen.\), "Rtf" für rich\-Text\-Enumerationen usw. verwenden.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)   
 [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)