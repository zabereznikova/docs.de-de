---
title: "Namen von Typmembern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "[Ereignisse [.NET Framework], Namen"
  - "[Methoden [.NET Framework], Namen"
  - "Typmember"
  - "[Eigenschaften [.NET Framework], Namen"
  - "Felder, Namen"
  - "Feldnamen"
  - "[Namen [.NET Framework], Typmember"
  - "[Member [.NET Framework], Typ"
ms.assetid: af5a0903-36af-4c2a-b848-cf959affeaa5
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Namen von Typmembern
Typen von Elementen bestehen: Methoden, Eigenschaften, Ereignisse, Konstruktoren und Felder. In den folgenden Abschnitten werden Richtlinien für die Benennung von Typmembern beschrieben.  
  
## Namen von Methoden  
 Da Methoden die Mittel der Aktion sind, müssen die Entwurfsrichtlinien Methodennamen Verben oder verbale Ausdrücke sein. Befolgen diese Richtlinie auch dient, Eigenschaft und Typnamen, Methodennamen unterscheiden die Nomen oder Adjektiv Ausdrücke sind.  
  
 **✓ führen** Methoden Namen, die Verben oder verbale Ausdrücke sind.  
  
```  
public class String {  
    public int CompareTo(...);  
    public string[] Split(...);  
    public string Trim();  
}  
  
```  
  
## Namen von Eigenschaften  
 Im Gegensatz zu anderen Membern Eigenschaften nominaler Ausdruck oder adjektivische Namen anzugeben. Das liegt daran eine Eigenschaft bezieht sich auf Daten und der Namen der Eigenschaft angibt, die. PascalCasing wird immer Eigenschaftsnamen verwendet werden.  
  
 **✓ führen** benennen Sie Eigenschaften mit einem Substantiv, nominaler Ausdruck oder Adjektiv.  
  
 **X nicht** verfügen über Eigenschaften, die den Namen des "Get"\-Methoden wie im folgenden Beispiel entsprechen:  
  
 `public string TextWriter { get {...} set {...} }`   
 `public string GetTextWriter(int value) { ... }`  
  
 Dieses Muster gibt normalerweise an, dass die Eigenschaft wirklich eine Methode.  
  
 **✓ führen** Namen Auflistungseigenschaften mit einem im plural Ausdruck beschreiben die Elemente in der Auflistung anstelle eines singular Ausdrucks gefolgt von "List" oder "Auflistung".  
  
 **✓ führen** benennen Sie boolesche Eigenschaften mit einem positiven Begriff \(`CanSeek` anstelle von `CantSeek`\). Optional können Sie auch boolesche Eigenschaften Präfix mit "Is", "kann" oder "Hat," jedoch nur, sofern dies sinnvoll.  
  
 **✓ ggf.** mit einer Eigenschaft den gleichen Namen wie der Typ.  
  
 Beispielsweise wird die folgende Eigenschaft ordnungsgemäß und legt einen Enumerationswert, der mit dem Namen `Color`, sodass die Eigenschaft mit dem Namen `Color`:  
  
```  
public enum Color {...}  
public class Control {  
    public Color Color { get {...} set {...} }  
}  
```  
  
## Namen von Ereignissen  
 Ereignisse beziehen sich immer auf eine Aktion ausführen, entweder einen Fehler oder eine, die aufgetreten ist. Daher wie bei Methoden, Ereignisse mit Verben heißen und Verb benannt wird verwendet, um den Zeitpunkt anzugeben, wenn das Ereignis ausgelöst wird.  
  
 **✓ führen** benennen Sie Ereignisse mit einem Verb oder ein Ausdruck.  
  
 Beispiele hierfür sind `Clicked`, `Painting`, `DroppedDown`, und so weiter.  
  
 **✓ führen** weisen Ereignisse Namen durch ein Konzept von vorher und Nachher, mithilfe der Gegenwart und Vergangenheit Zeitformen.  
  
 Beispielsweise würde ein Schließen\-Ereignis, das ausgelöst wird, bevor ein Fenster geschlossen wird aufgerufen werden `Closing`, und eine, die ausgelöst wird, nachdem das Fenster geschlossen wird `Closed`.  
  
 **X nicht** "Before" oder "After"\-Präfixe oder Suffixe an, dass vor und nach der Ereignisse verwenden. Verwenden Sie vorhanden und Vergangenheit Zeitformen wie gerade beschrieben.  
  
 **✓ führen** Ereignishandler \(Delegaten als Typen von Ereignissen verwendet\) mit dem Suffix "EventHandler" nennen, wie im folgenden Beispiel gezeigt:  
  
 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`  
  
 **✓ führen** verwenden zwei Parameter mit dem Namen `sender` und `e` im Ereignishandler.  
  
 Der Parameter Sender stellt das Objekt, das das Ereignis ausgelöst hat. Sender\-Parameter ist in der Regel vom Typ `object`, auch wenn es möglich ist, einen spezifischeren Typ zu verwenden.  
  
 **✓ führen** benennen Sie Ereignisargumentklassen mit dem Suffix "EventArgs".  
  
## Namen von Feldern  
 Die Benennung von Feld\-Richtlinien gelten für statische öffentliche und geschützte Felder. Interne und private Felder fallen nicht unter Richtlinien und öffentliche oder geschützte Instanzfelder dürfen nicht von der [Memberentwurfsrichtlinien](../../../docs/standard/design-guidelines/member.md).  
  
 **✓ führen** PascalCasing in Feldnamen verwenden.  
  
 **✓ führen** benennen Sie Felder mit Substantiven, nominaler Ausdruck oder Adjektiv.  
  
 **X nicht** verwenden Sie ein Präfix für Feldnamen.  
  
 Verwenden Sie z. B. nicht "G\_" oder "S\_" an, dass statische Felder.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)   
 [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)