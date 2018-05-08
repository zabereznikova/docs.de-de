---
title: Eigenschaftenentwurf
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, properties
- properties [.NET Framework], design guidelines
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a4aec965753fe8f89b8bd89469f8dc5739a6a7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="property-design"></a>Eigenschaftenentwurf
Obwohl die Eigenschaften, Methoden technisch sehr ähnlich sind, sind sie sehr unterschiedliche im Hinblick auf ihre Szenarien für die Verwendung. Sie sollte als intelligente Felder angezeigt werden. Sie verfügen über die Funktionsaufrufsyntax von Feldern und die Flexibilität der Methoden.  
  
 **Führen Sie ✓** schreibgeschützte Eigenschaften erstellen, wenn der Aufrufer nicht der Wert der Eigenschaft geändert werden soll.  
  
 Bedenken Sie, dass bei den Typ der Eigenschaft einen änderbaren Referenztyp ist, den Wert der Eigenschaft kann geändert werden, auch wenn die Eigenschaft nur Get-ist.  
  
 **X nicht** Bereitstellen mit der Setter müssen umfassenderen Zugriff hat als der Getter für eine lesegeschützte Eigenschaften oder Eigenschaften.  
  
 Verwenden Sie z. B. Eigenschaften nicht mit einem öffentlichen Setter und einen geschützten Getter.  
  
 Wenn der Getter für eine Eigenschaft kann nicht bereitgestellt werden, implementieren Sie stattdessen die Funktionen wie eine Methode. Beachten Sie, beginnend mit den Methodennamen `Set` und führen Sie mit, was Sie die Eigenschaft mit dem Namen verfügen würde. Beispielsweise <xref:System.AppDomain> verfügt über eine Methode namens `SetCachePath` anstatt eine lesegeschützte Eigenschaft mit dem Namen `CachePath`.  
  
 **Führen Sie ✓** sensibler Standardwerte für alle Eigenschaften, um sicherzustellen, dass die Standardwerte nicht in einer Sicherheitslücke oder sehr ineffizienten Code führen zur Verfügung gestellt.  
  
 **Führen Sie ✓** können Eigenschaften in beliebiger Reihenfolge festgelegt werden, auch wenn dadurch ein temporärer ungültigen Zustand des Objekts.  
  
 Es ist üblich für zwei oder mehr Eigenschaften zu einem Zeitpunkt zusammenhängende sein, in denen einige Werte einer Eigenschaft möglicherweise ungültig, die Werte der anderen Eigenschaften für das gleiche Objekt angegeben. In solchen Fällen sollten aufgrund von ungültigen Status ausgelösten Ausnahmen verschoben werden, bis die zusammenhängenden Eigenschaften zusammen tatsächlich vom Objekt verwendet werden.  
  
 **Führen Sie ✓** den vorherigen Wert beibehalten, wenn ein Eigenschaftensetter eine Ausnahme auslöst.  
  
 **X vermeiden** Auslösen von Ausnahmen von den Eigenschaftengetter.  
  
 Eigenschaftengetter darf sollten einfache Operationen sein und keine Vorbedingungen. Wenn eine getter-Methode eine Ausnahme auslösen kann, sollte es eine Methode wahrscheinlich überarbeitet. Beachten Sie, dass diese Regel nicht für Indexer ist gilt, in dem wir Ausnahmen als Ergebnis überprüft die Argumente erwarten.  
  
### <a name="indexed-property-design"></a>Indizierte Eigenschaftenentwurf  
 Eine indizierte Eigenschaft ist eine spezielle Eigenschaft, die Parameter und kann mit speziellen Syntax ähnelt derjenigen Arrayindizierung aufgerufen werden.  
  
 Indizierte Eigenschaften werden häufig als Indexer bezeichnet. Indexer sollte nur in-APIs verwendet werden, die Zugriff auf Elemente in einer logischen Auflistung bereitstellen. Eine Zeichenfolge ist z. B. eine Auflistung von Zeichen oder der Indexer auf <xref:System.String?displayProperty=nameWithType> wurde hinzugefügt, um die Zeichen zugreifen.  
  
 **✓ GGF.** Verwenden von Indexern für den Zugriff auf Daten in einem internen Array gespeichert.  
  
 **✓ GGF.** bereitstellen Indexer auf Typen, die Auflistungen von Elementen darstellt.  
  
 **X vermeiden** mit indizierten Eigenschaften mit mehreren Parametern.  
  
 Wenn der Entwurf mehrere Parameter erfordert, überdenken Sie, ob die Eigenschaft wirklich einen Accessor einer logischen Auflistung darstellt. Wenn dies nicht der Fall ist, verwenden Sie stattdessen die Methoden. Beachten Sie, beginnend mit den Methodennamen `Get` oder `Set`.  
  
 **X vermeiden** Indexer mit Parametertypen außer <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, oder eine Enumeration.  
  
 Wenn der Entwurf andere Parametertypen erfordert, auswerten Sie stark neu, ob die API tatsächlich einen Accessor einer logischen Auflistung darstellt. Wenn dies nicht der Fall ist, verwenden Sie eine Methode an. Beachten Sie, beginnend mit den Methodennamen `Get` oder `Set`.  
  
 **Führen Sie ✓** verwenden Sie den Namen `Item` für indizierte Eigenschaften, es sei denn, es ein deutlich besserer Name ist (z. B. finden Sie unter der <xref:System.String.Chars%2A> Eigenschaft auf `System.String`).  
  
 Sind Indexer in c# ist standardmäßig mit dem Namen Element. Die <xref:System.Runtime.CompilerServices.IndexerNameAttribute> zum Anpassen dieses Namens verwendet werden können.  
  
 **X nicht** Geben Sie einen Indexer und Methoden, die semantisch gleichwertig sind.  
  
 **X nicht** bieten mehr als eine Familie von überladene Indexer in einem Typ.  
  
 Dies wird vom C#-Compiler erzwungen.  
  
 **X nicht** verwenden nicht standardmäßiger indizierte Eigenschaften.  
  
 Dies wird vom C#-Compiler erzwungen.  
  
### <a name="property-change-notification-events"></a>Eigenschaftenänderungsereignisse-Benachrichtigung  
 Manchmal ist es nützlich, um ein Ereignis informiert den Benutzer über Änderungen eines Eigenschaftswerts bereitstellen. Beispielsweise `System.Windows.Forms.Control` löst eine `TextChanged` Ereignis nach dem Wert von dessen `Text` -Eigenschaft geändert hat.  
  
 **✓ GGF.** auslösen ändern Benachrichtigungsereignisse Wenn Eigenschaftswerte in allgemeine APIs (in der Regel Designer-Komponenten) geändert werden.  
  
 Ist ein gutes Szenario für Benutzer erkennt, wenn eine Eigenschaft eines Objekts geändert wird, sollte das Objekt eine änderungsbenachrichtigung für die Eigenschaft auslösen.  
  
 Allerdings ist es unwahrscheinlich, lohnt des Mehraufwands für solche Ereignisse auslösen, für die Low-Level-APIs wie z. B. Basistypen oder Auflistungen sein. Beispielsweise <xref:System.Collections.Generic.List%601> solche Ereignisse aus, wenn der Liste ein neues Element hinzugefügt wird nicht ausgelöst werden soll und die `Count` -Eigenschaft ändert.  
  
 **✓ GGF.** Auslösen von Benachrichtigungsereignissen, wenn der Wert einer Eigenschaft über externe erzwingt ändert ändern.  
  
 Wenn Sie ein Eigenschaftswert über einige externe Force (in einer Weise als durch Aufrufen von Methoden für das Objekt) geändert wird, löst Ereignisse für den Entwickler anzugeben, dass der Wert ändert sich und geändert hat. Ein gutes Beispiel ist die `Text` Eigenschaft für ein Textfeld-Steuerelement. Wenn der Benutzer eingibt Text in einem `TextBox`, der Eigenschaftswert automatisch geändert.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
