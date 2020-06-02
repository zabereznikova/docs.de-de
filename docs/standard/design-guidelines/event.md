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
ms.openlocfilehash: 852c99b1a41691911f7ae82d3b8104526811757d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289823"
---
# <a name="event-design"></a>Ereignisentwurf
Ereignisse sind die am häufigsten verwendete Form von Rückrufe (-Konstrukte, die dem Framework das Aufrufen von Benutzercode ermöglichen). Andere Rückruf Mechanismen beinhalten Member, die Delegaten, virtuelle Member und Schnittstellen basierte Plug-Ins verwenden. Daten aus Nutzbarkeits Studien zeigen an, dass die Mehrzahl der Entwickler die Verwendung von Ereignissen leichter machen, als Sie die anderen Rückruf Mechanismen verwenden. Ereignisse sind gut in Visual Studio und viele Sprachen integriert.

 Es ist wichtig zu beachten, dass es zwei Gruppen von Ereignissen gibt: Ereignisse, die vor dem Systemwechsel ausgelöst werden, als präereignisse bezeichnet werden, und Ereignisse, die nach einem Zustands Wechsel ausgelöst werden, die als nach Ereignissen bezeichnet werden. Ein Beispiel für ein präereignis wäre `Form.Closing` , das ausgelöst wird, bevor ein Formular geschlossen wird. Ein Beispiel für ein Post-Ereignis wäre `Form.Closed` , das ausgelöst wird, nachdem ein Formular geschlossen wurde.

 ✔️ Verwenden Sie anstelle von "Fire" oder "Trigger" den Begriff "Raise" für Ereignisse.

 ✔️ verwenden <xref:System.EventHandler%601?displayProperty=nameWithType> anstelle von Manuelles Erstellen neuer Delegaten, die als Ereignishandler verwendet werden sollen.

 ✔️ sollten Sie die Verwendung einer Unterklasse von <xref:System.EventArgs> als Ereignis Argument in Erwägung ziehen, es sei denn, Sie sind sicher, dass das Ereignis niemals Daten an die Ereignis Behandlungsmethode übertragen muss. in diesem Fall können Sie den `EventArgs` Typ direkt verwenden.

 Wenn Sie eine API direkt mithilfe `EventArgs` von versenden, können Sie ohne Unterbrechung der Kompatibilität niemals Daten hinzufügen, die mit dem Ereignis übertragen werden. Wenn Sie eine Unterklasse verwenden, können Sie, auch wenn Sie anfänglich vollständig leer ist, bei Bedarf Eigenschaften zur Unterklasse hinzufügen.

 ✔️ eine geschützte virtuelle Methode verwenden, um jedes Ereignis zu erhöhen. Dies gilt nur für nicht statische Ereignisse in nicht versiegelten Klassen, nicht für Strukturen, versiegelte Klassen oder statische Ereignisse.

 Der Zweck der-Methode besteht darin, eine Methode bereitzustellen, mit der eine abgeleitete Klasse das Ereignis mithilfe einer außer Kraft Setzung behandeln kann. Das Überschreiben ist eine flexiblere, schnellere und natürlichere Methode zum Verarbeiten von Basisklassen Ereignissen in abgeleiteten Klassen. Gemäß der Konvention sollte der Name der Methode mit "on" beginnen und mit dem Namen des Ereignisses befolgt werden.

 Die abgeleitete Klasse kann auswählen, dass die Basis Implementierung der Methode nicht in der Überschreibung aufgerufen werden soll. Seien Sie darauf vorbereitet, indem Sie keine Verarbeitung in die-Methode einschließen, die erforderlich ist, damit die Basisklasse ordnungsgemäß funktioniert.

 ✔️ einen Parameter an die geschützte Methode übernehmen, die ein Ereignis auslöst.

 Der-Parameter muss benannt werden `e` und als Ereignis Argument Klasse eingegeben werden.

 ❌Übergeben Sie NULL nicht als Absender, wenn Sie ein nicht statisches Ereignis auslassen.

 ✔️ bei der Erstellung eines statischen Ereignisses NULL als Absender übergeben.

 ❌Übergeben Sie NULL nicht als Ereignisdaten Parameter, wenn Sie ein Ereignis aufrufen.

 Sie sollten übergeben, `EventArgs.Empty` Wenn Sie keine Daten an die Ereignis Behandlungsmethode übergeben möchten. Entwickler erwarten, dass dieser Parameter nicht NULL ist.

 ✔️ sollten Ereignisse in Erwägung ziehen, die der Endbenutzer abbrechen kann. Dies gilt nur für präereignisse.

 Verwenden Sie oder die zugehörige <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> Unterklasse als Ereignis Argument, damit der Endbenutzer Ereignisse abbrechen kann.

### <a name="custom-event-handler-design"></a>Design des benutzerdefinierten Ereignis Handlers
 Es gibt Fälle, in denen nicht `EventHandler<T>` verwendet werden kann, z. b. wenn das Framework mit früheren Versionen der CLR arbeiten muss, die keine Generika unterstützen. In solchen Fällen müssen Sie möglicherweise einen benutzerdefinierten Ereignishandlerdelegaten entwerfen und entwickeln.

 ✔️ den Rückgabetyp "void" für Ereignishandler verwenden.

 Ein Ereignishandler kann mehrere Ereignis Verarbeitungsmethoden aufrufen, möglicherweise auf mehreren Objekten. Wenn Ereignis Behandlungsmethoden einen Wert zurückgeben können, gibt es mehrere Rückgabewerte für jeden Ereignis Aufruf.

 ✔️ verwenden `object` Sie als Typ des ersten Parameters des Ereignis Handlers, und nennen Sie ihn `sender` .

 ✔️ Verwenden Sie oder die zugehörige <xref:System.EventArgs?displayProperty=nameWithType> Unterklasse als Typ des zweiten Parameters des Ereignis Handlers, und nennen Sie Sie `e` .

 ❌Für Ereignishandler sind nicht mehr als zwei Parameter vorhanden.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Entwurfs Richtlinien für Member](member.md)
- [Framework-Entwurfs Richtlinien](index.md)
