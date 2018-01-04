---
title: Namen von Typmembern
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d489d4cf61adfe8550bd16b85cd658e0d545c861
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="names-of-type-members"></a>Namen von Typmembern
Typen von Elementen vorgenommen werden: Methoden, Eigenschaften, Ereignisse, Konstruktoren und Felder. In den folgenden Abschnitten werden die Richtlinien für die Benennung von Typmembern beschrieben.  
  
## <a name="names-of-methods"></a>Namen von Methoden  
 Da Methoden überprüfbarer Aktionen sind, müssen die Entwurfsrichtlinien Methodennamen Verben oder verbale Ausdrücke sein. Befolgen diese Richtlinie auch dient zur Unterscheidung von Methodennamen aus den Namen der Eigenschaft, und geben die Nomen oder Adjektiv Ausdrücke sind.  
  
 **Führen Sie ✓** Geben Sie einen Methodennamen, die Verben oder verbale Ausdrücke sind.  
  
```  
public class String {  
    public int CompareTo(...);  
    public string[] Split(...);  
    public string Trim();  
}  
```  
  
## <a name="names-of-properties"></a>Namen von Eigenschaften  
 Im Gegensatz zu anderen Mitgliedern Eigenschaften nominaler Ausdruck oder adjektivische Namen Unternehmensservern benötigen. Grund hierfür eine Eigenschaft bezieht sich auf Daten und der Namen der Eigenschaft angibt, ist. PascalCasing wird immer für Eigenschaftennamen verwendet.  
  
 **Führen Sie ✓** Benennen von Eigenschaften, die über ein Nomen, nominaler Ausdruck oder Adjektiv.  
  
 **X nicht** verfügen über Eigenschaften, die den Namen des "Get"-Methoden, wie im folgenden Beispiel entsprechen:  
  
 `public string TextWriter { get {...} set {...} }`  
 `public string GetTextWriter(int value) { ... }`  
  
 Dieses Muster gibt normalerweise an, dass die Eigenschaft wirklich ein Methode sein sollte.  
  
 **Führen Sie ✓** benennen Sammlungseigenschaften mit einem im plural Ausdruck beschreiben die Elemente in der Auflistung anstatt im singular Ausdruck gefolgt von "List" oder "Collection".  
  
 **Führen Sie ✓** benennen boolesche Eigenschaften, die mit einem positiven Begriff (`CanSeek` anstelle von `CantSeek`). Optional, Sie können auch das Präfix boolescher Eigenschaften, die mit "Is", "kann" oder "Hat," jedoch nur, sofern der Wert hinzugefügt.  
  
 **✓ GGF.** erteilen einer Eigenschaft den gleichen Namen wie den Typ.  
  
 Beispielsweise ruft die folgende Eigenschaft ordnungsgemäß und legt einen Enumerationswert, der mit dem Namen `Color`, sodass die Eigenschaft heißt `Color`:  
  
```  
public enum Color {...}  
public class Control {  
    public Color Color { get {...} set {...} }  
}  
```  
  
## <a name="names-of-events"></a>Namen von Ereignissen  
 Ereignisse beziehen sich immer auf eine Aktion aus, entweder ein Fehler oder eine, die aufgetreten ist. Daher wie bei Methoden, Ereignisse mit Verben heißen und Verb Zeitformen wird verwendet, um den Zeitpunkt angibt, wann das Ereignis ausgelöst wird.  
  
 **Führen Sie ✓** benennen Sie Ereignisse mit einem Verb oder ein Ausdruck.  
  
 Beispiele hierfür sind `Clicked`, `Painting`, `DroppedDown`und so weiter.  
  
 **Führen Sie ✓** benennen Ereignisse Namen durch ein Konzept von vor und nach, mit der vorhanden und der Vergangenheit Zeitformen.  
  
 Beispielsweise würde ein Schließen-Ereignis, das ausgelöst wird, bevor ein Fenster geschlossen wird aufgerufen werden `Closing`, und eine, die ausgelöst wird, nachdem das Fenster geschlossen wird aufgerufen `Closed`.  
  
 **X nicht** "Before" oder "After"-Präfixe oder Suffixe an, dass vor und nach der Ereignisse verwenden. Verwenden Sie vorhanden und Vergangenheit Zeitformen wie gerade beschrieben.  
  
 **Führen Sie ✓** Ereignishandlerauflistung (Delegaten als Typen von Ereignissen verwendet) mit dem Suffix "EventHandler" nennen, wie im folgenden Beispiel gezeigt:  
  
 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`  
  
 **Führen Sie ✓** verwenden zwei Parameter mit dem Namen `sender` und `e` in den Ereignishandlern.  
  
 Der Parameter Sender stellt das Objekt, das das Ereignis ausgelöst hat. Der Absenderparameter ist in der Regel vom Typ `object`, selbst wenn es möglich ist, einen spezifischeren Typ zu verwenden.  
  
 **Führen Sie ✓** benennen Sie Ereignisargumentklassen mit dem Suffix "EventArgs".  
  
## <a name="names-of-fields"></a>Namen von Feldern  
 Die Benennung von Feld-Richtlinien gelten für statische öffentliche und geschützte Felder. Interne und private Felder werden nicht behandelt, durch die Richtlinien und öffentlichen oder geschützten Instanzfelder sind nicht zulässig, durch die [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md).  
  
 **Führen Sie ✓** PascalCasing in Feldnamen verwenden.  
  
 **Führen Sie ✓** Namen von Feldern an, indem ein Nomen, nominaler Ausdruck oder Adjektiv.  
  
 **X nicht** verwenden Sie ein Präfix für Feldnamen.  
  
 Verwenden Sie z. B. nicht "G_" oder "S_" an, dass statische Felder.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
 [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)
