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
author: KrzysztofCwalina
ms.openlocfilehash: 530c68ea5342263acd07f8dc8a8c8ce889652503
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026444"
---
# <a name="event-design"></a>Ereignisentwurf
Ereignisse sind am häufigsten verwendeten Form von Rückrufen (Konstrukte, die das Framework für den Aufruf von Benutzercode zu ermöglichen). Andere Rückrufmechanismen enthalten Elemente, die die Delegaten, virtuelle Member und schnittstellenbasierter-Plug-ins. Daten aus Umfragen zur benutzerfreundlichkeit haben anzugeben, dass die meisten Entwickler sind wohler, Ereignisse, als sie die anderen Rückrufmechanismen verwenden. Ereignisse sind in Visual Studio und vielen Sprachen gut integriert.  
  
 Es ist wichtig zu beachten, dass es zwei Gruppen von Ereignisse gibt: Ereignisse, die ausgelöst wird, bevor ein Status des Systems geändert wird, wird aufgerufen, Pre-Ereignisse sowie Ereignisse ausgelöst, nachdem ein Zustand ändert, wird nach der Ereignisse aufgerufen. Ein Beispiel für ein Ereignis vor `Form.Closing`, der Fehler wird ausgelöst, bevor ein Formular geschlossen wird. Ein Beispiel für ein Ereignis nach der `Form.Closed`, der Fehler wird ausgelöst, nachdem ein Formular geschlossen wird.  
  
 **✓ DO** verwenden Sie den Begriff "Auslösen" Ereignisse anstatt "Feuer" oder "Auslösen" an.  
  
 **✓ DO** verwenden <xref:System.EventHandler%601?displayProperty=nameWithType> statt Sie manuell neue Delegaten als Ereignishandler verwendet werden soll.  
  
 **✓ CONSIDER** verwenden eine Unterklasse von <xref:System.EventArgs> als Ereignisargument, es sei denn, Sie sicher, dass das Ereignis nie zur Übertragung von Daten an die Ereignisbehandlungsmethode müssen sind in diesem Fall können Sie die `EventArgs` direkt eingeben.  
  
 Wenn Sie schicken eine API mit `EventArgs` direkt, Sie werden nie Daten mit dem Ereignis ausgeführt werden, ohne wichtige Kompatibilität hinzufügen. Wenn Sie eine Unterklasse verwenden, auch wenn Anfangs vollständig leer ist, Sie Eigenschaften in die Unterklasse, die bei Bedarf hinzufügen können.  
  
 **✓ DO** verwenden Sie eine geschützte virtuelle Methode jedes Ereignis ausgelöst werden soll. Dies gilt nur für nicht statischen Ereignisse, die für nicht versiegelte Klassen nicht statischen Ereignisse, versiegelte Klassen oder Strukturen.  
  
 Der Zweck der Methode ist eine Möglichkeit für eine abgeleitete Klasse zum Behandeln des Ereignisses, das mit einer Außerkraftsetzung. Überschreiben ist eine flexiblere, schneller und natürliche Möglichkeit, Behandeln von Basisklassenereignissen in abgeleiteten Klassen. Gemäß der Konvention der Namen der Methode muss mit "On" beginnen und mit dem Namen des Ereignisses folgen.  
  
 Die abgeleitete Klasse können nicht die grundlegende Implementierung der Methode in der Überschreibung aufrufen. Für dieses vorbereitet werden, dazu eine Verarbeitung nicht in der Methode, die für die Basisklasse ordnungsgemäß ausgeführt werden muss.  
  
 **✓ DO** akzeptieren einen Parameter für die geschützte Methode, die ein Ereignis auslöst.  
  
 Der Parameter heißen `e` und soll als die Ereignisargumentklasse eingegeben werden.  
  
 **X DO NOT** übergeben Sie null als Sender an, wenn eine nicht statische Ereignis durch das auslösen.  
  
 **✓ DO** übergeben Sie null als Sender an, wenn ein statisches Ereignis auslösen.  
  
 **X DO NOT** übergeben Sie null als Parameter für das Daten, beim Auslösen eines Ereignisses.  
  
 Übergeben Sie `EventArgs.Empty` Wenn keine Daten an die Ereignisbehandlungsmethode übergeben werden sollen. Entwickler erwarten, dass dieser Parameter nicht null sein.  
  
 **✓ CONSIDER** Auslösen von Ereignissen, die der Endbenutzer abbrechen können. Dies gilt nur für vorherige Ereignisse.  
  
 Verwendung <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> oder die Unterklasse als das Ereignisargument, das dem Endbenutzer Ereignisse ermöglichen.  
  
### <a name="custom-event-handler-design"></a>Entwurf benutzerdefinierter Ereignishandler  
 Es gibt Fälle, in denen `EventHandler<T>` kann nicht verwendet werden, z. B. wenn das Framework muss mit früheren Versionen der CLR arbeiten, dem keine Generika unterstützt. In solchen Fällen müssen Sie möglicherweise zum Entwerfen und entwickeln ein benutzerdefiniertes Ereignis-Handler-Delegat.  
  
 **✓ DO** verwenden Sie den Rückgabetyp "void" für den Ereignishandler.  
  
 Ein Ereignishandler kann mehrere Methoden, die möglicherweise auf mehrere Objekte für die Ereignisbehandlung aufrufen. Wenn Ereignisbehandlung Methoden zum Zurückgeben eines Werts zulässig wäre, würde Rückgabe mehrerer Werte für jeden Aufruf des Ereignisses vorhanden sein.  
  
 **✓ DO** verwenden `object` als Typ des ersten Parameters der Ereignishandler, und rufen sie `sender`.  
  
 **✓ DO** verwenden <xref:System.EventArgs?displayProperty=nameWithType> oder seiner Unterklasse als Typ des zweiten Parameters der Ereignishandler, und nennen Sie es `e`.  
  
 **X DO NOT** verfügen über mehr als zwei Parameter auf Ereignishandler.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
