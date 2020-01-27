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
ms.openlocfilehash: b44ee5933f8629b4dddbf3be1b79b2e77b0254f7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741691"
---
# <a name="event-design"></a>Ereignisentwurf
Ereignisse sind die am häufigsten verwendete Form von Rückrufe (-Konstrukte, die dem Framework das Aufrufen von Benutzercode ermöglichen). Andere Rückruf Mechanismen beinhalten Member, die Delegaten, virtuelle Member und Schnittstellen basierte Plug-Ins verwenden. Daten aus Nutzbarkeits Studien zeigen, dass die Mehrzahl der Entwickler die Verwendung von Ereignissen leichter machen, als Sie die anderen Rückruf Mechanismen verwenden. . Ereignisse sind gut in Visual Studio und viele Sprachen integriert.

 Es ist wichtig zu beachten, dass es zwei Gruppen von Ereignissen gibt: Ereignisse, die vor dem Systemwechsel ausgelöst werden, als präereignisse bezeichnet werden, und Ereignisse, die nach einem Zustands Wechsel ausgelöst werden, die als nach Ereignissen bezeichnet werden. Ein Beispiel für ein präereignis wäre `Form.Closing`, das vor dem Schließen eines Formulars ausgelöst wird. Ein Beispiel für ein Post-Ereignis wäre `Form.Closed`, das ausgelöst wird, nachdem ein Formular geschlossen wurde.

 ✔️ Verwenden Sie anstelle von "Fire" oder "Trigger" den Begriff "Raise" für Ereignisse.

 ✔️ Verwenden Sie <xref:System.EventHandler%601?displayProperty=nameWithType> anstelle von manueller Erstellung neuer Delegaten, die als Ereignishandler verwendet werden sollen.

 ✔️ sollten Sie die Verwendung einer Unterklasse von <xref:System.EventArgs> als Ereignis Argument in Erwägung ziehen, es sei denn, Sie sind sicher, dass das Ereignis niemals Daten an die Ereignis Behandlungsmethode übertragen muss. in diesem Fall können Sie den `EventArgs` Typ direkt verwenden.

 Wenn Sie eine API direkt über `EventArgs` versenden, können Sie niemals Daten hinzufügen, die mit dem Ereignis übertragen werden, ohne dass die Kompatibilität unterbrochen wird. Wenn Sie eine Unterklasse verwenden, können Sie, auch wenn Sie anfänglich vollständig leer ist, bei Bedarf Eigenschaften zur Unterklasse hinzufügen.

 ✔️ eine geschützte virtuelle Methode verwenden, um jedes Ereignis zu erhöhen. Dies gilt nur für nicht statische Ereignisse in nicht versiegelten Klassen, nicht für Strukturen, versiegelte Klassen oder statische Ereignisse.

 Der Zweck der-Methode besteht darin, eine Methode bereitzustellen, mit der eine abgeleitete Klasse das Ereignis mithilfe einer außer Kraft Setzung behandeln kann. Das Überschreiben ist eine flexiblere, schnellere und natürlichere Methode zum Verarbeiten von Basisklassen Ereignissen in abgeleiteten Klassen. Gemäß der Konvention sollte der Name der Methode mit "on" beginnen und mit dem Namen des Ereignisses befolgt werden.

 Die abgeleitete Klasse kann auswählen, dass die Basis Implementierung der Methode nicht in der Überschreibung aufgerufen werden soll. Seien Sie darauf vorbereitet, indem Sie keine Verarbeitung in die-Methode einschließen, die erforderlich ist, damit die Basisklasse ordnungsgemäß funktioniert.

 ✔️ einen Parameter an die geschützte Methode übernehmen, die ein Ereignis auslöst.

 Der-Parameter sollte `e` benannt werden und als Ereignis Argument Klasse eingegeben werden.

 ❌ nicht NULL als Absender übergeben, wenn ein nicht statisches Ereignis aussteht.

 ✔️ bei der Erstellung eines statischen Ereignisses NULL als Absender übergeben.

 ❌ beim Aufrufen eines Ereignisses NULL nicht als Ereignisdaten Parameter übergeben.

 Sie sollten `EventArgs.Empty` übergeben, wenn Sie keine Daten an die Ereignis Behandlungsmethode übergeben möchten. Entwickler erwarten, dass dieser Parameter nicht NULL ist.

 ✔️ sollten Ereignisse in Erwägung ziehen, die der Endbenutzer abbrechen kann. Dies gilt nur für präereignisse.

 Verwenden Sie <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> oder die zugehörige Unterklasse als Ereignis Argument, damit der Endbenutzer Ereignisse abbrechen kann.

### <a name="custom-event-handler-design"></a>Design des benutzerdefinierten Ereignis Handlers
 Es gibt Fälle, in denen `EventHandler<T>` nicht verwendet werden kann, z. b. wenn das Framework mit früheren Versionen der CLR arbeiten muss, die keine Generika unterstützen. In solchen Fällen müssen Sie möglicherweise einen benutzerdefinierten Ereignishandlerdelegaten entwerfen und entwickeln.

 ✔️ den Rückgabetyp "void" für Ereignishandler verwenden.

 Ein Ereignishandler kann mehrere Ereignis Verarbeitungsmethoden aufrufen, möglicherweise auf mehreren Objekten. Wenn Ereignis Behandlungsmethoden einen Wert zurückgeben können, gibt es mehrere Rückgabewerte für jeden Ereignis Aufruf.

 ✔️ Verwenden Sie `object` als Typ des ersten Parameters des Ereignis Handlers, und nennen Sie ihn `sender`.

 ✔️ Verwenden Sie <xref:System.EventArgs?displayProperty=nameWithType> oder seine Unterklasse als Typ des zweiten Parameters des Ereignis Handlers, und nennen Sie ihn `e`.

 ❌ haben nicht mehr als zwei Parameter für Ereignishandler.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
