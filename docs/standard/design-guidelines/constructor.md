---
title: "Konstruktorentwurf | Microsoft Docs"
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
  - "Entwurfsrichtlinien für Member, Konstruktoren"
  - "Konstruktoren, Entwurfsrichtlinien"
  - "Instanzkonstruktoren"
  - "Typkonstruktoren"
  - "Virtuelle Member"
  - "Konstruktoren, Typen"
  - "Standardkonstruktoren"
  - "Statische Konstruktoren"
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Konstruktorentwurf
Es gibt zwei Arten von Konstruktoren: Zeilenkonstruktoren und Instanz geben.  
  
 Typkonstruktoren sind statisch und werden von der CLR ausgeführt, bevor der Typ verwendet wird. Instanzkonstruktoren ausgeführt, wenn eine Instanz eines Typs erstellt wird.  
  
 Typkonstruktoren können keine Parameter annimmt. Instanzkonstruktoren können. Instanzkonstruktoren, die keine Parameter werden häufig Standardkonstruktoren bezeichnet.  
  
 Konstruktoren sind die beste Möglichkeit zum Erstellen von Instanzen eines Typs. Die meisten Entwickler zu suchen und versuchen, einen Konstruktor zu verwenden, bevor sie alternative Methoden zum Erstellen von Instanzen \(z. B. Factorymethoden\) in Betracht ziehen.  
  
 **✓ ggf.** einfach, im Idealfall Standard, Konstruktoren bereitstellen.  
  
 Eine sehr kleine Anzahl von Parametern über einen einfachen Konstruktor verfügt, und alle Parameter sind primitive Typen oder Enumerationen. Diese einfache Konstruktoren Verwendbarkeit des Frameworks.  
  
 **✓ ggf.** verwenden eine statische Factorymethode anstelle eines Konstruktors, wenn die Semantik der gewünschten Operation nicht direkt der Erstellung einer neuen Instanz zugeordnet sind oder befolgen die Richtlinien unnatürlichen ist.  
  
 **✓ führen** Konstruktorparameter als Tastenkombinationen verwenden, zum Festlegen von Haupteigenschaften.  
  
 Es gibt keinen Unterschied in der Semantik zwischen sollte mit dem leeren Konstruktor gefolgt von einigen Eigenschaftensätze und mehrere Argumente eines Konstruktors mit.  
  
 **✓ führen** verwenden Sie denselben Namen für Konstruktorparameter und eine Eigenschaft, wenn Parameter des Konstruktors verwendet werden, um einfach die Eigenschaft festzulegen.  
  
 Der einzige Unterschied zwischen Eigenschaften und solche Parameter sollten Groß\-\/Kleinschreibung unterscheiden.  
  
 **✓ führen** minimale dem Konstruktor arbeiten.  
  
 Konstruktoren sollten viel Arbeit als Capture Parameter des Konstruktors nicht. Die Kosten für weitere Verarbeitungsschritte sollten verzögert werden, bis erforderlich.  
  
 **✓ führen** Ausnahmen von Instanzkonstruktoren, falls zutreffend.  
  
 **✓ führen** den öffentlichen Standardkonstruktor in Klassen explizit deklarieren, wenn ein solcher Konstruktor erforderlich ist.  
  
 Wenn Sie keine Konstruktoren für einen Typ explizit deklarieren nicht, werden viele Sprachen \(z. B. c\#\) einen öffentlichen Standardkonstruktor automatisch hinzugefügt. \(Abstrakte Klassen erhalten einen geschützten Konstruktor.\)  
  
 Eine Klasse einen parametrisierten Konstruktor hinzugefügt wird verhindert, dass den Compiler den Standardkonstruktor hinzufügen. Dies führt häufig unbeabsichtigte Änderungen.  
  
 **X vermeiden** Standardkonstruktoren für Strukturen explizit definieren.  
  
 Dies beschleunigt Arrayerstellung, da der Standardkonstruktor nicht definiert ist, es nicht für die Ausführung auf jedem Steckplatz im Array. Beachten Sie, dass Strukturen parameterlose Konstruktoren aus diesem Grund haben viele Compiler, u. a. c\# nicht.  
  
 **X vermeiden** virtuelle Member für ein Objekt in seinem Konstruktor aufrufen.  
  
 Aufrufen eines virtuellen Members bewirkt, die am stärksten abgeleitete Überschreibung aufgerufen werden, selbst wenn der Konstruktor der am weitesten abgeleiteten Typ noch vollständig nicht ausgeführt wurde.  
  
### Richtlinien für Konstruktor  
 **✓ führen** statische Konstruktoren nicht freizugeben.  
  
 Statische Konstruktoren, auch als bezeichnet einen Klassenkonstruktor wird zum Initialisieren eines Typs verwendet. Die CLR ruft den statischen Konstruktor auf, bevor die erste Instanz des Typs erstellt oder auf irgendwelche statischen Member für den Typ aufgerufen werden. Der Benutzer hat keine Kontrolle darüber, wenn der statische Konstruktor aufgerufen wird. Wenn ein statischer Konstruktor nicht privat ist, kann er von Code als die CLR aufgerufen werden. Je nach den Operationen im Konstruktor ausgeführt wird kann dies unerwartetem Verhalten führen. Der C\#\-Compiler erzwingt statische Konstruktoren privat sein soll.  
  
 **X nicht** Ausnahmen von statischen Konstruktoren.  
  
 Wenn von einem Typkonstruktor eine Ausnahme ausgelöst wird, kann der Typ nicht in der aktuellen Anwendungsdomäne verwendet werden.  
  
 **✓ ggf.** statische Felder Inline initialisieren, anstatt explizit mithilfe von statischen Konstruktoren, da die Common Language Runtime werden zur Optimierung der Leistung von Typen, die einen explizit definierten statischen Konstruktor verfügen kann.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)   
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)