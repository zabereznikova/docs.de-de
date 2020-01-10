---
title: Eigenschaftenentwurf
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, properties
- properties [.NET Framework], design guidelines
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
ms.openlocfilehash: 5d5cdbfdb38c7aebaca6cbcdeb63959ac12884e0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709126"
---
# <a name="property-design"></a>Eigenschaftenentwurf
Obwohl die Eigenschaften den Methoden technisch ähnlich ähnlich sind, unterscheiden Sie sich in Bezug auf Ihre Verwendungs Szenarien erheblich. Sie sollten als intelligente Felder betrachtet werden. Sie verfügen über die Aufruf Syntax der Felder und die Flexibilität der Methoden.  
  
 **✓ DO** schreibgeschützte Eigenschaften erstellen, wenn der Aufrufer nicht der Wert der Eigenschaft geändert werden soll.  
  
 Beachten Sie, dass der Eigenschafts Wert auch dann geändert werden kann, wenn es sich bei dem Typ der Eigenschaft um einen änderbaren Referenztyp handelt.  
  
 **X DO NOT** Bereitstellen mit der Setter müssen umfassenderen Zugriff hat als der Getter für eine lesegeschützte Eigenschaften oder Eigenschaften.  
  
 Verwenden Sie z. b. keine Eigenschaften mit einem öffentlichen Setter und einem geschützten Getter.  
  
 Wenn der Getter der Eigenschaft nicht bereitgestellt werden kann, implementieren Sie die Funktionalität stattdessen als Methode. Starten Sie den Methodennamen mit `Set`, und folgen Sie den Anweisungen, die Sie als Eigenschaft bezeichnet haben. <xref:System.AppDomain> hat beispielsweise eine Methode mit dem Namen `SetCachePath`, anstatt eine nur-Eigenschaft mit dem Namen `CachePath`zu verwenden.  
  
 **✓ DO** sensibler Standardwerte für alle Eigenschaften, um sicherzustellen, dass die Standardwerte nicht in einer Sicherheitslücke oder sehr ineffizienten Code führen zur Verfügung gestellt.  
  
 **✓ DO** können Eigenschaften in beliebiger Reihenfolge festgelegt werden, auch wenn dadurch ein temporärer ungültigen Zustand des Objekts.  
  
 Es kommt häufig vor, dass zwei oder mehr Eigenschaften mit einem Punkt verknüpft werden, an dem einige Werte einer Eigenschaft aufgrund der Werte anderer Eigenschaften desselben Objekts möglicherweise ungültig sind. In solchen Fällen sollten Ausnahmen, die sich aus dem ungültigen Zustand ergeben, verschoben werden, bis die miteinander verknüpften Eigenschaften tatsächlich vom Objekt zusammen verwendet werden.  
  
 **✓ DO** den vorherigen Wert beibehalten, wenn ein Eigenschaftensetter eine Ausnahme auslöst.  
  
 **X AVOID** Auslösen von Ausnahmen von den Eigenschaftengetter.  
  
 Eigenschaften Getter sollten einfache Vorgänge sein und sollten keine Vorbedingungen aufweisen. Wenn ein Getter eine Ausnahme auslösen kann, sollte er wahrscheinlich neu gestaltet werden, um eine Methode zu sein. Beachten Sie, dass diese Regel nicht für Indexer gilt, bei denen Ausnahmen aufgrund der Validierung der Argumente erwartet werden.  
  
### <a name="indexed-property-design"></a>Design der indizierten Eigenschaft  
 Eine indizierte Eigenschaft ist eine spezielle Eigenschaft, die über Parameter verfügen kann und mit spezieller Syntax ähnlich der Array Indizierung aufgerufen werden kann.  
  
 Indizierte Eigenschaften werden im Allgemeinen als Indexer bezeichnet. Indexer sollten nur in APIs verwendet werden, die den Zugriff auf Elemente in einer logischen Auflistung ermöglichen. Beispielsweise ist eine Zeichenfolge eine Auflistung von Zeichen, und der Indexer auf <xref:System.String?displayProperty=nameWithType> wurde hinzugefügt, um auf seine Zeichen zuzugreifen.  
  
 **✓ CONSIDER** Verwenden von Indexern für den Zugriff auf Daten in einem internen Array gespeichert.  
  
 **✓ CONSIDER** bereitstellen Indexer auf Typen, die Auflistungen von Elementen darstellt.  
  
 **X AVOID** mit indizierten Eigenschaften mit mehreren Parametern.  
  
 Wenn der Entwurf mehrere Parameter erfordert, überdenken Sie, ob die-Eigenschaft tatsächlich einen Accessor für eine logische Auflistung darstellt. Wenn dies nicht der Fall ist, verwenden Sie stattdessen-Methoden. Sie sollten den Methodennamen ggf. mit `Get` oder `Set`beginnen.  
  
 **X AVOID** Indexer mit Parametertypen außer <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, oder eine Enumeration.  
  
 Wenn der Entwurf andere Typen von Parametern erfordert, sollten Sie nachdrücklich neu auswerten, ob die API tatsächlich einen Accessor für eine logische Auflistung darstellt. Wenn dies nicht der Fall ist, verwenden Sie eine-Methode. Sie sollten den Methodennamen ggf. mit `Get` oder `Set`beginnen.  
  
 **✓ DO** verwenden Sie den Namen `Item` für indizierte Eigenschaften, es sei denn, es ein deutlich besserer Name ist (z. B. finden Sie unter der <xref:System.String.Chars%2A> Eigenschaft auf `System.String`).  
  
 In C#sind Indexer standardmäßig benannte Elemente. Der <xref:System.Runtime.CompilerServices.IndexerNameAttribute> kann zum Anpassen dieses Namens verwendet werden.  
  
 **X DO NOT** Geben Sie einen Indexer und Methoden, die semantisch gleichwertig sind.  
  
 **X DO NOT** bieten mehr als eine Familie von überladene Indexer in einem Typ.  
  
 Dies wird vom C# Compiler erzwungen.  
  
 **X DO NOT** verwenden nicht standardmäßiger indizierte Eigenschaften.  
  
 Dies wird vom C# Compiler erzwungen.  
  
### <a name="property-change-notification-events"></a>Benachrichtigungs Ereignisse für Eigenschafts Änderungen  
 Manchmal ist es hilfreich, ein Ereignis anzugeben, das den Benutzer über Änderungen in einem Eigenschafts Wert benachrichtigt. `System.Windows.Forms.Control` löst z. b. ein `TextChanged`-Ereignis aus, nachdem sich der Wert der `Text`-Eigenschaft geändert hat.  
  
 **✓ CONSIDER** auslösen ändern Benachrichtigungsereignisse Wenn Eigenschaftswerte in allgemeine APIs (in der Regel Designer-Komponenten) geändert werden.  
  
 Wenn ein Benutzer ein gutes Szenario kennt, wenn eine Eigenschaft eines Objekts geändert wird, sollte das Objekt ein Änderungs Benachrichtigungs Ereignis für die Eigenschaft angeben.  
  
 Es ist jedoch unwahrscheinlich, dass Sie den Aufwand für die Anwendung solcher Ereignisse für APIs auf niedriger Ebene, wie z. b. Basis Typen oder Sammlungen, erhöhen sollten. Beispielsweise würden <xref:System.Collections.Generic.List%601> solche Ereignisse nicht aufschlagen, wenn der Liste ein neues Element hinzugefügt wird und die `Count`-Eigenschaft geändert wird.  
  
 **✓ CONSIDER** Auslösen von Benachrichtigungsereignissen, wenn der Wert einer Eigenschaft über externe erzwingt ändert ändern.  
  
 Wenn sich ein Eigenschafts Wert über eine externe Kraft ändert (anders als durch Aufrufen von Methoden für das Objekt), geben Sie Ereignisse an den Entwickler an, dass sich der Wert ändert und sich geändert hat. Ein gutes Beispiel hierfür ist die `Text`-Eigenschaft eines Textfeld-Steuer Elements. Wenn der Benutzer Text in einem `TextBox`eingibt, ändert sich der Eigenschafts Wert automatisch.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
