---
title: Ereignisentwurf
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
ms.openlocfilehash: 78d765a7af77b1e6a6ecd483677cea2d4c6b0d5b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709425"
---
# <a name="event-design"></a>Ereignisentwurf
Ereignisse sind die am häufigsten verwendete Form von Rückrufe (-Konstrukte, die dem Framework das Aufrufen von Benutzercode ermöglichen). Andere Rückruf Mechanismen beinhalten Member, die Delegaten, virtuelle Member und Schnittstellen basierte Plug-Ins verwenden. Daten aus Nutzbarkeits Studien zeigen, dass die Mehrzahl der Entwickler die Verwendung von Ereignissen leichter machen, als Sie die anderen Rückruf Mechanismen verwenden. . Ereignisse sind gut in Visual Studio und viele Sprachen integriert.  
  
 Es ist wichtig zu beachten, dass es zwei Gruppen von Ereignissen gibt: Ereignisse, die vor dem Systemwechsel ausgelöst werden, als präereignisse bezeichnet werden, und Ereignisse, die nach einem Zustands Wechsel ausgelöst werden, die als nach Ereignissen bezeichnet werden. Ein Beispiel für ein präereignis wäre `Form.Closing`, das vor dem Schließen eines Formulars ausgelöst wird. Ein Beispiel für ein Post-Ereignis wäre `Form.Closed`, das ausgelöst wird, nachdem ein Formular geschlossen wurde.  
  
 **✓ DO** verwenden Sie den Begriff "Auslösen" Ereignisse anstatt "Feuer" oder "Auslösen" an.  
  
 **✓ DO** verwenden <xref:System.EventHandler%601?displayProperty=nameWithType> statt Sie manuell neue Delegaten als Ereignishandler verwendet werden soll.  
  
 **✓ CONSIDER** verwenden eine Unterklasse von <xref:System.EventArgs> als Ereignisargument, es sei denn, Sie sicher, dass das Ereignis nie zur Übertragung von Daten an die Ereignisbehandlungsmethode müssen sind in diesem Fall können Sie die `EventArgs` direkt eingeben.  
  
 Wenn Sie eine API direkt über `EventArgs` versenden, können Sie niemals Daten hinzufügen, die mit dem Ereignis übertragen werden, ohne dass die Kompatibilität unterbrochen wird. Wenn Sie eine Unterklasse verwenden, können Sie, auch wenn Sie anfänglich vollständig leer ist, bei Bedarf Eigenschaften zur Unterklasse hinzufügen.  
  
 **✓ DO** verwenden Sie eine geschützte virtuelle Methode jedes Ereignis ausgelöst werden soll. Dies gilt nur für nicht statische Ereignisse in nicht versiegelten Klassen, nicht für Strukturen, versiegelte Klassen oder statische Ereignisse.  
  
 Der Zweck der-Methode besteht darin, eine Methode bereitzustellen, mit der eine abgeleitete Klasse das Ereignis mithilfe einer außer Kraft Setzung behandeln kann. Das Überschreiben ist eine flexiblere, schnellere und natürlichere Methode zum Verarbeiten von Basisklassen Ereignissen in abgeleiteten Klassen. Gemäß der Konvention sollte der Name der Methode mit "on" beginnen und mit dem Namen des Ereignisses befolgt werden.  
  
 Die abgeleitete Klasse kann auswählen, dass die Basis Implementierung der Methode nicht in der Überschreibung aufgerufen werden soll. Seien Sie darauf vorbereitet, indem Sie keine Verarbeitung in die-Methode einschließen, die erforderlich ist, damit die Basisklasse ordnungsgemäß funktioniert.  
  
 **✓ DO** akzeptieren einen Parameter für die geschützte Methode, die ein Ereignis auslöst.  
  
 Der-Parameter sollte `e` benannt werden und als Ereignis Argument Klasse eingegeben werden.  
  
 **X DO NOT** übergeben Sie null als Sender an, wenn eine nicht statische Ereignis durch das auslösen.  
  
 **✓ DO** übergeben Sie null als Sender an, wenn ein statisches Ereignis auslösen.  
  
 **X DO NOT** übergeben Sie null als Parameter für das Daten, beim Auslösen eines Ereignisses.  
  
 Sie sollten `EventArgs.Empty` übergeben, wenn Sie keine Daten an die Ereignis Behandlungsmethode übergeben möchten. Entwickler erwarten, dass dieser Parameter nicht NULL ist.  
  
 **✓ CONSIDER** Auslösen von Ereignissen, die der Endbenutzer abbrechen können. Dies gilt nur für präereignisse.  
  
 Verwenden Sie <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> oder die zugehörige Unterklasse als Ereignis Argument, damit der Endbenutzer Ereignisse abbrechen kann.  
  
### <a name="custom-event-handler-design"></a>Design des benutzerdefinierten Ereignis Handlers  
 Es gibt Fälle, in denen `EventHandler<T>` nicht verwendet werden kann, z. b. wenn das Framework mit früheren Versionen der CLR arbeiten muss, die keine Generika unterstützen. In solchen Fällen müssen Sie möglicherweise einen benutzerdefinierten Ereignishandlerdelegaten entwerfen und entwickeln.  
  
 **✓ DO** verwenden Sie den Rückgabetyp "void" für den Ereignishandler.  
  
 Ein Ereignishandler kann mehrere Ereignis Verarbeitungsmethoden aufrufen, möglicherweise auf mehreren Objekten. Wenn Ereignis Behandlungsmethoden einen Wert zurückgeben können, gibt es mehrere Rückgabewerte für jeden Ereignis Aufruf.  
  
 **✓ DO** verwenden `object` als Typ des ersten Parameters der Ereignishandler, und rufen sie `sender`.  
  
 **✓ DO** verwenden <xref:System.EventArgs?displayProperty=nameWithType> oder seiner Unterklasse als Typ des zweiten Parameters der Ereignishandler, und nennen Sie es `e`.  
  
 **X DO NOT** verfügen über mehr als zwei Parameter auf Ereignishandler.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
