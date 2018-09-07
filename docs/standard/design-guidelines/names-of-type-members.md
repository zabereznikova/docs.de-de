---
title: Namen von Typmembern
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0541f100f208543c796de7238e68ea6f90c7b299
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44077108"
---
# <a name="names-of-type-members"></a>Namen von Typmembern
Typen bestehen aus Membern: Methoden, Eigenschaften, Ereignisse, Konstruktoren und Felder. In den folgenden Abschnitten werden die Richtlinien zum Benennen von Typmembern beschrieben.  
  
## <a name="names-of-methods"></a>Namen von Methoden  
 Da Methoden das Ausführen von Aktionen ermöglichen, erfordern die Entwurfsrichtlinien, dass Methodennamen Verben oder Verbalphrasen sind. Mit dieser Richtlinie ist es auch möglich, Methodennamen von Eigenschafts- und Typnamen zu unterscheiden, die Nominal- oder Adjektivphrasen sind.  
  
 **✓ DO**: Geben Sie Methodennamen an, die Verben oder Verbalphrasen sind.  
  
```  
public class String {  
    public int CompareTo(...);  
    public string[] Split(...);  
    public string Trim();  
}  
```  
  
## <a name="names-of-properties"></a>Namen von Eigenschaften  
 Anders als andere Member sollten Eigenschaften mit Substantivphrasen oder Adjektivnamen benannt werden. Das liegt daran, dass eine Eigenschaft auf Daten verweist, und der Name der Eigenschaft gibt dies wieder. Für Eigenschaftsnamen wird immer PascalCasing verwendet.  
  
 **✓ DO**: Benennen Sie Eigenschaften mit einem Nomen, einer Nominalphrase oder einem Adjektiv.  
  
 **X DO NOT**: Nutzen Sie keine Eigenschaften, die mit dem Namen von „Get“-Methoden übereinstimmen, so wie in folgendem Beispiel dargestellt:  
  
 `public string TextWriter { get {...} set {...} }`  
 `public string GetTextWriter(int value) { ... }`  
  
 Dieses Muster gibt normalerweise an, dass die Eigenschaft eigentlich eine Methode sein soll.  
  
 **✓ DO**: Benennen Sie Sammlungseigenschaften mit einer Phrase im Plural, mit dem die Elemente in der Sammlung beschrieben werden, anstatt mit einer Phrase im Singular, gefolgt von „List“ oder „Collection“.  
  
 **✓ DO**: Benennen Sie boolesche Eigenschaften mit einem positiven Ausdruck (`CanSeek` anstelle von `CantSeek`). Optional können Sie auch booleschen Eigenschaften „Is,“, „Can,“ oder „Has,“ voranstellen, jedoch nur, wo es Sinn ergibt.  
  
 **✓ CONSIDER**: Ziehen Sie in Betracht, einer Eigenschaft den gleichen Namen wie ihrem Typ zu geben.  
  
 Die folgende Eigenschaft ruft ordnungsgemäß einen Enumerationswert namens `Color` ab und legt ihn fest. Die Eigenschaft heißt also `Color`:  
  
```  
public enum Color {...}  
public class Control {  
    public Color Color { get {...} set {...} }  
}  
```  
  
## <a name="names-of-events"></a>Namen von Ereignissen  
 Ereignisse beziehen sich immer auf Aktionen, also entweder auf eine Aktion, die gerade passiert oder eine, die in der Vergangenheit liegt. Deshalb werden Ereignisse mit Verben benannt (wie Methoden auch), und die Verbkonjugation wird genutzt, um den Zeitpunkt anzugeben, wann das Ereignis ausgelöst wird.  
  
 **✓ DO**: Benennen Sie Ereignisse mit einem Verb oder einer Verbalphrase.  
  
 Beispiele dafür sind `Clicked`, `Painting`, `DroppedDown` usw.  
  
 **✓ DO**: Geben Sie Ereignissen Namen, die sich auf Vergangenheit und Zukunft beziehen. Verwenden Sie dazu Gegenwarts- und Vergangenheitsformen.  
  
 Beispielsweise wird ein Schließereignis, das ausgelöst wird, bevor ein Fenster geschlossen wird, als `Closing` bezeichnet. Ein Ereignis, das nach dem Schließen des Fensters ausgelöst wird, wird als `Closed` bezeichnet.  
  
 **X DO NOT**: Verwenden Sie keine „Before“- und „After“-Präfixe und -Postfixe, um eine Aktion vor oder nach Ereignissen anzugeben. Verwenden Sie wie oben beschrieben die Gegenwarts- und Vergangenheitsformen.  
  
 **✓ DO**: Benennen Sie Ereignishandler (Delegaten, die als Typen von Ereignissen verwendet werden) mit dem Suffix „EventHandler“, wie in folgendem Beispiel dargestellt:  
  
 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`  
  
 **✓ DO**: Verwenden Sie in Ereignishandlern zwei Parameter mit der Bezeichnung `sender` und `e`.  
  
 Der sender-Parameter stellt das Objekt dar, das das Ereignis ausgelöst hat. Der sender-Parameter ist in der Regel vom Typ `object`, auch wenn es möglich ist, einen spezifischeren Typ zu verwenden.  
  
 **✓ DO**: Benennen Sie Ereignisargumentklassen mit dem Suffix „EventArgs“.  
  
## <a name="names-of-fields"></a>Feldnamen  
 Die Richtlinien für die Benennung von Feldern gelten für statische öffentliche und geschützte Felder. Interne und private Felder sind nicht Gegenstand von Richtlinien, und öffentliche oder geschützte Instanzfelder sind laut den [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md) nicht zulässig.  
  
 **✓ DO**: Verwenden Sie die Pascal-Schreibweise in Feldnamen.  
  
 **✓ DO**: Benennen Sie Felder mit einem Nomen, einer Nominalphrase oder einem Adjektiv.  
  
 **X DO NOT**: Verwenden Sie kein Präfix für Feldnamen.  
  
 Verwenden Sie beispielsweise nicht „g_“ oder „s_“, um statische Felder anzugeben.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
- [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)
