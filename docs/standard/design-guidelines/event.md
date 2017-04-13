---
title: "Ereignisentwurf | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Vorherige Ereignisse"
  - "[Ereignisse [.NET Framework], Entwurfsrichtlinien"
  - "Entwurfsrichtlinien für Member, Ereignisse"
  - "Ereignishandler [.NET Framework], ereignisentwurfsrichtlinien"
  - "spätere Ereignisse"
  - "Signaturen-Ereignisbehandlung"
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Ereignisentwurf
Ereignisse sind die am häufigsten verwendeten Form von Rückrufen \(Konstrukten, mit denen das Framework in Benutzercode aufruft\). Andere Rückrufmechanismen enthalten Elemente übernehmen, Delegaten und virtuelle Member\-basierten\-Plug\-ins. Daten aus Benutzerstudien Teil darauf hinweisen, dass die meisten Entwickler sind komfortabler als mit die anderen Rückrufmechanismen sind das Verwenden von Ereignissen. Ereignisse sind gut in Visual Studio und vielen Sprachen integriert.  
  
 Es ist wichtig zu beachten, dass es zwei Gruppen von Ereignisse: Ereignisse ausgelöst, bevor ein Status des Systems ändert, Namens vor auch Ereignisse ausgelöst, nachdem ein Zustand ändert, nach der Ereignisse aufgerufen. Ein Beispiel für ein Ereignis vor wäre `Form.Closing`, die wird ausgelöst, bevor ein Formular geschlossen wird. Ein Beispiel für ein Ereignis nach der wäre `Form.Closed`, die wird ausgelöst, nachdem ein Formular geschlossen wird.  
  
 **✓ führen** verwenden den Begriff "heraufstufen" für Ereignisse statt "Feuer" oder "trigger".  
  
 **✓ führen** verwenden <xref:System.EventHandler%601?displayProperty=fullName> anstelle der manuellen Erstellung von neuen Delegaten, die als Ereignishandler verwendet werden.  
  
 **✓ ggf.** verwenden eine Unterklasse von <xref:System.EventArgs> als Ereignisargument, es sei denn, Sie sicher, dass das Ereignis müssen nie zum Übertragen von Daten an die Ereignisbehandlungsmethode sind in diesem Fall können Sie die `EventArgs` direkt eingeben.  
  
 Wenn Sie eine API mit liefern `EventArgs` direkt, Sie werden nie von Daten, die mit dem Ereignis ausgeführt werden, ohne die Kompatibilität hinzufügen. Wenn Sie eine Unterklasse verwenden, auch wenn Anfangs vollständig leer ist, die Unterklasse bei Bedarf Eigenschaften hinzugefügt werden kann.  
  
 **✓ führen** eine geschützte virtuelle Methode zum Auslösen jedes Ereignisses verwenden. Dies gilt nur für nicht statische Ereignisse in unversiegelten Klassen, nicht für Strukturen, versiegelte Klassen oder statische Ereignisse.  
  
 Der Zweck der Methode ist für eine abgeleitete Klasse zum Behandeln des Ereignisses mit einer Überschreibung zu ermöglichen. Überschreiben ist eine flexiblere, schnellere und einfachere Möglichkeit zum Behandeln von Basisklassenereignissen in abgeleiteten Klassen. Gemäß der Konvention wird der Name der Methode beginnen mit "On" und mit dem Namen des Ereignisses folgen.  
  
 Die abgeleitete Klasse können nicht die grundlegende Implementierung der Methode in der Überschreibung aufrufen. Bereiten Sie sich für diese dazu Verarbeitungsvorgänge nicht in der Methode, die für die Basisklasse ordnungsgemäß funktioniert.  
  
 **✓ führen** akzeptieren einen Parameter für die geschützte Methode, die ein Ereignis auslöst.  
  
 Der Parameter sollte heißen `e` und muss als die Ereignisargumentklasse eingegeben werden.  
  
 **X nicht** als Absender null übergeben, wenn ein nicht statisches Ereignis auslösen.  
  
 **✓ führen** als Absender null übergeben, wenn ein statisches Ereignis auslösen.  
  
 **X nicht** beim Auslösen eines Ereignisses wird als Parameter für das Data null übergeben.  
  
 Übergeben Sie `EventArgs.Empty` wenn Sie keine Daten an die Ereignisbehandlungsmethode übergeben möchten. Entwickler erwarten, dass dieser Parameter nicht null sein.  
  
 **✓ ggf.** Auslösen von Ereignissen, die der Endbenutzer abbrechen können. Dies gilt nur für vorherige Ereignisse.  
  
 Verwendung <xref:System.ComponentModel.CancelEventArgs?displayProperty=fullName> oder dessen Unterklasse als Ereignisargument an den Endbenutzer Ereignisse ermöglichen.  
  
### Entwurf benutzerdefinierter Ereignishandler  
 Es gibt Fälle, in denen `EventHandler<T>` kann nicht verwendet werden, z. B. wenn das Framework mit früheren Versionen der CLR arbeiten, das keine Generika unterstützen muss. In solchen Fällen müssen Sie zum Entwerfen und entwickeln ein benutzerdefiniertes Ereignis\-Handler\-Delegat.  
  
 **✓ führen** verwenden Sie für Ereignishandler einen Rückgabetyp "void".  
  
 Ein Ereignishandler kann mehrere Ereignisbehandlungsmethoden möglicherweise auf mehrere Objekte aufrufen. Ereignisbehandlungsmethoden zugelassen wird, einen Wert zurückzugeben, wäre mehrere Rückgabewerte für jeden Aufruf des Ereignisses.  
  
 **✓ führen** verwenden `object` als Typ des ersten Parameters für den Ereignishandler, und nennen Sie es `sender`.  
  
 **✓ führen** verwenden <xref:System.EventArgs?displayProperty=fullName> oder dessen Unterklasse als Typ des zweiten Parameters im Ereignishandler, und nennen Sie es `e`.  
  
 **X nicht** verfügen über mehr als zwei Parameter auf Ereignishandler.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)   
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)