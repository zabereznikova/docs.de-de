---
title: Ereignisentwurf
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48d1ad0f02ae34675c0a910d7651d718c060db60
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575389"
---
# <a name="event-design"></a>Ereignisentwurf
Ereignisse werden am häufigsten verwendete Form von Rückrufen (Konstrukte, die das Framework zum Aufrufen von Benutzercode zu ermöglichen). Andere Rückrufmechanismen enthalten Elemente und Delegaten, virtuelle Member und schnittstellenbasierten-Plug-ins. Daten aus der Verwendbarkeit Studien anzugeben, dass die meisten Entwickler sind nachrichtenorientierten Ereignisse verwenden, als sie die anderen Rückrufmechanismen verwenden. Ereignisse sind gut mit Visual Studio und vielen Sprachen integriert.  
  
 Es ist wichtig zu beachten, dass es zwei Gruppen von Ereignisse gibt: Ereignisse, die ausgelöst wird, bevor ein Status des Systems ändert, aufgerufen wird, vorab auch Ereignisse, die ausgelöst wird, nachdem ein Zustand ändert, sogenannte nach der Ereignisse. Ein Beispiel eines Ereignisses vor wäre `Form.Closing`, der Fehler wird ausgelöst, bevor ein Formular geschlossen wird. Ein Beispiel für ein Ereignis nach der wäre `Form.Closed`, der Fehler wird ausgelöst, nachdem ein Formular geschlossen wird.  
  
 **✓ DO** verwenden Sie den Begriff "Auslösen" Ereignisse anstatt "Feuer" oder "Auslösen" an.  
  
 **✓ DO** verwenden <xref:System.EventHandler%601?displayProperty=nameWithType> statt Sie manuell neue Delegaten als Ereignishandler verwendet werden soll.  
  
 **✓ CONSIDER** verwenden eine Unterklasse von <xref:System.EventArgs> als Ereignisargument, es sei denn, Sie sicher, dass das Ereignis nie zur Übertragung von Daten an die Ereignisbehandlungsmethode müssen sind in diesem Fall können Sie die `EventArgs` direkt eingeben.  
  
 Wenn Sie eine API mit liefern `EventArgs` direkt, Sie werden nie mehr Daten mit dem Ereignis ausgeführt werden, ohne Unterbrechung der Kompatibilität hinzuzufügen. Wenn Sie eine Unterklasse verwenden, auch wenn anfänglich vollständig leer ist, die Unterklasse bei Bedarf Eigenschaften hinzugefügt werden kann.  
  
 **✓ DO** verwenden Sie eine geschützte virtuelle Methode jedes Ereignis ausgelöst werden soll. Dies gilt nur für nicht statische Ereignisse für nicht versiegelte Klassen, nicht für Strukturen, versiegelte Klassen oder statische Ereignisse.  
  
 Der Zweck der Methode ist eine Möglichkeit für eine abgeleitete Klasse für die Ereignisbehandlung mit einer Außerkraftsetzung bereitstellen. Überschreiben ist eine flexiblere, schnellere und besser Möglichkeit zum Basisklassenereignissen in abgeleiteten Klassen zu verarbeiten. Gemäß der Konvention werden der Name der Methode sollte mit "On" beginnen und mit dem Namen des Ereignisses folgen.  
  
 Die abgeleitete Klasse können nicht die grundlegende Implementierung der Methode in der Überschreibung aufrufen. Für diesen vorbereitet werden, ausgenommen Verarbeitungen in der Methode, die für die Basisklasse ordnungsgemäß funktioniert erforderlich ist.  
  
 **✓ DO** akzeptieren einen Parameter für die geschützte Methode, die ein Ereignis auslöst.  
  
 Der Parameter heißen `e` und sollten als Ereignisargumentklasse eingegeben werden.  
  
 **X DO NOT** übergeben Sie null als Sender an, wenn eine nicht statische Ereignis durch das auslösen.  
  
 **✓ DO** übergeben Sie null als Sender an, wenn ein statisches Ereignis auslösen.  
  
 **X DO NOT** übergeben Sie null als Parameter für das Daten, beim Auslösen eines Ereignisses.  
  
 Übergeben Sie `EventArgs.Empty` Wenn keine Daten an die Ereignisbehandlungsmethode übergeben werden sollen. Entwickler erwarten, dass dieser Parameter nicht null sein.  
  
 **✓ CONSIDER** Auslösen von Ereignissen, die der Endbenutzer abbrechen können. Dies gilt nur für Ereignisse vor.  
  
 Verwendung <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> oder seiner Unterklasse als das Ereignisargument für die Endbenutzer zum Abbrechen von Ereignissen ermöglichen.  
  
### <a name="custom-event-handler-design"></a>Entwurf benutzerdefinierter Ereignishandler  
 Es gibt Fälle, in denen `EventHandler<T>` kann nicht verwendet werden, z. B. wenn das Framework benötigt Arbeit mit früheren Versionen der CLR, Generika nicht unterstützt. In solchen Fällen müssen Sie möglicherweise entwerfen und entwickeln einen benutzerdefinierten Ereignishandler-Delegaten.  
  
 **✓ DO** verwenden Sie den Rückgabetyp "void" für den Ereignishandler.  
  
 Ein Ereignishandler kann mehrere Methoden, die möglicherweise bei mehreren Objekten für die Ereignisbehandlung aufrufen. Ereignisbehandlung Methoden zugelassen wird, einen Wert zurückzugeben, wäre mehrere Rückgabewerte für jeden Aufruf des Ereignisses.  
  
 **✓ DO** verwenden `object` als Typ des ersten Parameters der Ereignishandler, und rufen sie `sender`.  
  
 **✓ DO** verwenden <xref:System.EventArgs?displayProperty=nameWithType> oder seiner Unterklasse als Typ des zweiten Parameters der Ereignishandler, und nennen Sie es `e`.  
  
 **X DO NOT** verfügen über mehr als zwei Parameter auf Ereignishandler.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
