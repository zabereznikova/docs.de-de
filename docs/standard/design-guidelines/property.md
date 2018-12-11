---
title: Eigenschaftenentwurf
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, properties
- properties [.NET Framework], design guidelines
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
author: KrzysztofCwalina
ms.openlocfilehash: 1d119b48f0524b3e997aa2cb9ea2cbbd855afdf0
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53131455"
---
# <a name="property-design"></a>Eigenschaftenentwurf
Obwohl es sich bei Eigenschaften, Methoden technisch sehr ähnlich sind, sind sie in Bezug auf ihre Szenarien für die Verwendung sehr unterschiedlich. Sie sollten als intelligenter Felder angezeigt. Sie haben die Funktionsaufrufsyntax von Feldern, und die Flexibilität der Methoden.  
  
 **✓ DO** schreibgeschützte Eigenschaften erstellen, wenn der Aufrufer nicht der Wert der Eigenschaft geändert werden soll.  
  
 Bedenken Sie, dass bei den Typ der Eigenschaft einen änderbaren Referenztyp ist, den Wert der Eigenschaft geändert werden kann, selbst wenn die Eigenschaft nur.  
  
 **X DO NOT** Bereitstellen mit der Setter müssen umfassenderen Zugriff hat als der Getter für eine lesegeschützte Eigenschaften oder Eigenschaften.  
  
 Verwenden Sie z. B. nicht Eigenschaften mit einem öffentlichen Setter und eine geschützte Getter.  
  
 Wenn der Eigenschaftengetter kann nicht bereitgestellt werden, implementieren Sie stattdessen die Funktionen wie eine Methode. Beachten Sie, starten den Methodennamen mit `Set` und führen Sie mit, wie Sie die Eigenschaft benannt haben würden. Z. B. <xref:System.AppDomain> verfügt über eine Methode namens `SetCachePath` anstatt eine nur-Eigenschaft namens `CachePath`.  
  
 **✓ DO** sensibler Standardwerte für alle Eigenschaften, um sicherzustellen, dass die Standardwerte nicht in einer Sicherheitslücke oder sehr ineffizienten Code führen zur Verfügung gestellt.  
  
 **✓ DO** können Eigenschaften in beliebiger Reihenfolge festgelegt werden, auch wenn dadurch ein temporärer ungültigen Zustand des Objekts.  
  
 Es ist üblich, dass zwei oder mehr Eigenschaften zu einem Zeitpunkt zusammenhängender sein, in dem einige Werte einer Eigenschaft möglicherweise ungültig, angegebenen Werte anderer Eigenschaften für das gleiche Objekt. In solchen Fällen sollten Ausnahmen, die durch einen ungültigen Zustand verschoben werden, bis die zusammenhängenden Eigenschaften durch das Objekt tatsächlich gemeinsam verwendet werden.  
  
 **✓ DO** den vorherigen Wert beibehalten, wenn ein Eigenschaftensetter eine Ausnahme auslöst.  
  
 **X AVOID** Auslösen von Ausnahmen von den Eigenschaftengetter.  
  
 Eigenschaftengetter sollten einfache Vorgänge sein und müssen keine Vorbedingungen. Wenn eine getter-Methode eine Ausnahme auslösen kann, müssen sie wahrscheinlich als Methode überarbeitet werden. Beachten Sie, dass diese Regel nicht für Indexer gilt, in denen rechnen wir Ausnahmen als Ergebnis der Überprüfung der Argumente.  
  
### <a name="indexed-property-design"></a>Indizierte Eigenschaftenentwurf  
 Eine indizierte Eigenschaft ist eine spezielle Eigenschaft, die kann Parameter und kann mit speziellen Syntax ähnelt der Array-Indizierung aufgerufen werden.  
  
 Indizierte Eigenschaften werden häufig als Indexer bezeichnet. Indexer sollte nur in den APIs verwendet werden, die Zugriff auf Elemente in einer logischen Auflistung bereitstellen. Eine Zeichenfolge ist z. B. eine Auflistung von Zeichen und den Indexer nach <xref:System.String?displayProperty=nameWithType> wurde hinzugefügt, um die Zeichen zugreifen.  
  
 **✓ CONSIDER** Verwenden von Indexern für den Zugriff auf Daten in einem internen Array gespeichert.  
  
 **✓ CONSIDER** bereitstellen Indexer auf Typen, die Auflistungen von Elementen darstellt.  
  
 **X AVOID** mit indizierten Eigenschaften mit mehreren Parametern.  
  
 Wenn der Entwurf mehrere Parameter erfordert, überdenken Sie, ob die Eigenschaft wirklich einen Accessor für eine logische Sammlung darstellt. Wenn dies nicht der Fall ist, verwenden Sie stattdessen die Methoden. Beachten Sie, starten den Methodennamen mit `Get` oder `Set`.  
  
 **X AVOID** Indexer mit Parametertypen außer <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, oder eine Enumeration.  
  
 Wenn der Entwurf auf andere Typen der Parameter erfordert, auswerten Sie stark erneut, ob die API tatsächlich einen Accessor für eine logische Sammlung darstellt. Wenn dies nicht der Fall ist, verwenden Sie eine Methode an. Beachten Sie, starten den Methodennamen mit `Get` oder `Set`.  
  
 **✓ DO** verwenden Sie den Namen `Item` für indizierte Eigenschaften, es sei denn, es ein deutlich besserer Name ist (z. B. finden Sie unter der <xref:System.String.Chars%2A> Eigenschaft auf `System.String`).  
  
 Sind Indexer in c# wird standardmäßig mit dem Namen Element. Die <xref:System.Runtime.CompilerServices.IndexerNameAttribute> können verwendet werden, um diesen Namen anpassen.  
  
 **X DO NOT** Geben Sie einen Indexer und Methoden, die semantisch gleichwertig sind.  
  
 **X DO NOT** bieten mehr als eine Familie von überladene Indexer in einem Typ.  
  
 Dies wird durch den C#-Compiler erzwungen.  
  
 **X DO NOT** verwenden nicht standardmäßiger indizierte Eigenschaften.  
  
 Dies wird durch den C#-Compiler erzwungen.  
  
### <a name="property-change-notification-events"></a>Benachrichtigung für Eigenschaftenänderungsereignisse  
 Manchmal ist es nützlich, um ein Ereignis benachrichtigt den Benutzer über Änderungen eines Eigenschaftswerts bereitstellen. Z. B. `System.Windows.Forms.Control` löst eine `TextChanged` Ereignis nach dem Wert des der `Text` -Eigenschaft geändert hat.  
  
 **✓ CONSIDER** auslösen ändern Benachrichtigungsereignisse Wenn Eigenschaftswerte in allgemeine APIs (in der Regel Designer-Komponenten) geändert werden.  
  
 Ist ein gutes Szenario für einen Benutzer wissen, wenn eine Eigenschaft eines Objekts geändert wird, sollte das Objekt ein Änderungsereignis für die Eigenschaft auszulösen.  
  
 Allerdings ist es unwahrscheinlich ist, sollte der Aufwand zum Auslösen von solchen Ereignissen für Low-Level-APIs wie z. B. Basistypen oder Auflistungen sein. Z. B. <xref:System.Collections.Generic.List%601> würde nicht auslösen, solche Ereignisse aus, wenn die Liste ein neues Element hinzugefügt wird und die `Count` eigenschaftenänderungen.  
  
 **✓ CONSIDER** Auslösen von Benachrichtigungsereignissen, wenn der Wert einer Eigenschaft über externe erzwingt ändert ändern.  
  
 Wenn die Änderung eines Eigenschaftswerts über einige externe erzwingen (in einer Weise als durch Aufrufen von Methoden für das Objekt), löst Ereignisse für den Entwickler zeigen an, dass der Wert ändert, und hat sich geändert. Ein gutes Beispiel ist die `Text` Eigenschaft von einem Textfeld-Steuerelement. Wenn der Benutzer Text eingibt eine `TextBox`, den Wert der Eigenschaft automatisch geändert wird.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)  
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
