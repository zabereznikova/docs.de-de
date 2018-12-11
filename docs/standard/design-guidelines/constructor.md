---
title: Konstruktorentwurf
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- default constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
author: KrzysztofCwalina
ms.openlocfilehash: b140be34d9359cfdca1250a924db787563127d19
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53127783"
---
# <a name="constructor-design"></a>Konstruktorentwurf
Es gibt zwei Arten von Konstruktoren: Geben Sie die Konstruktoren und Instanz.  
  
 Typkonstruktoren sind statisch und von der CLR ausgeführt werden, bevor der Typ verwendet wird. Instanzkonstruktoren wird ausgeführt, wenn eine Instanz eines Typs erstellt wird.  
  
 Typen können keine Parameter annimmt. Instanzkonstruktoren können. Instanzkonstruktoren, die Parameter annehmen, nicht werden standardmäßige Konstruktoren häufig bezeichnet werden.  
  
 Konstruktoren sind die beste Möglichkeit zum Erstellen von Instanzen eines Typs. Die meisten Entwickler durchsucht und versuchen, einen Konstruktor zu verwenden, bevor sie alternative Methoden zum Erstellen von Instanzen (z. B. Factorymethoden) in Betracht ziehen.  
  
 **✓ CONSIDER** einfach, im Idealfall Standard, Konstruktoren bereitstellen.  
  
 Eine sehr kleine Anzahl von Parametern über einen einfachen Konstruktor verfügt, und alle Parameter sind primitive oder Enumerationen. Diese einfache Konstruktoren erhöhen Nutzbarkeit des Frameworks.  
  
 **✓ CONSIDER** eine statische Factorymethode statt einen Konstruktor verwenden, wenn die Semantik des gewünschten Vorgangs nicht direkt der Erstellung einer neuen Instanz zugeordnet sind, oder der Konstruktor Entwurfsrichtlinien unnatürlichen idealer.  
  
 **✓ DO** Konstruktorparameter als Tastenkombinationen verwenden, für die wichtigsten Eigenschaften festlegen.  
  
 Es muss kein Unterschied in der Semantik zwischen mit dem leeren Konstruktor gefolgt von einigen Eigenschaftensätze und über einen Konstruktor mit mehreren Argumenten.  
  
 **✓ DO** verwenden Sie denselben Namen für Konstruktorparameter und eine Eigenschaft aus, wenn der Konstruktorparameter verwendet werden, einfach die Eigenschaft festgelegt.  
  
 Der einzige Unterschied zwischen Eigenschaften und solche Parameter muss Groß-/Kleinschreibung unterscheiden.  
  
 **✓ DO** nur minimale Arbeitsschritte im Konstruktor.  
  
 Konstruktoren tun nicht viel Arbeit als Capture Parameter des Konstruktors. Die Kosten für weitere Verarbeitungsschritte muss verzögert werden, bis erforderlich.  
  
 **✓ DO** Ausnahmen von Instanzkonstruktoren, falls zutreffend.  
  
 **✓ DO** in Klassen, die öffentlichen Standardkonstruktor explizit deklariert werden, wenn ein solcher Konstruktor erforderlich ist.  
  
 Wenn Sie für einen Typ explizit keine Konstruktoren deklarieren nicht, werden viele Sprachen (z. B. C# -Referenz) automatisch einen öffentlichen Standardkonstruktor hinzugefügt. (Abstrakte Klassen erhalten einen geschützten Konstruktor.)  
  
 Eine Klasse einen parametrisierten Konstruktor hinzugefügt wird verhindert, dass den Compiler die standardmäßigen Konstruktor hinzufügt. Dies führt häufig zu versehentlichen Änderungen.  
  
 **X AVOID** explizit standardmäßige Konstruktoren für Strukturen definiert.  
  
 Dadurch Arrayerstellung schneller, da der Standardkonstruktor nicht definiert ist, es nicht unbedingt auf alle Slot im Array ausgeführt werden. Beachten Sie, dass viele Compiler, u. a. c#, Strukturen, die aus diesem Grund parameterlose Konstruktoren besitzen nicht zulassen.  
  
 **X AVOID** virtuelle Member für ein Objekt in seinem Konstruktor aufrufen.  
  
 Aufrufen eines virtuellen Members bewirkt die am stärksten abgeleitete Außerkraftsetzung aufgerufen wird, selbst wenn der Konstruktor, der am weitesten abgeleiteten Typ noch vollständig nicht ausgeführt wurde.  
  
### <a name="type-constructor-guidelines"></a>Richtlinien für die Typen-Konstruktor  
 **✓ DO** als statische Konstruktoren privat festlegen.  
  
 Ein statischer Konstruktor auch einen Klassenkonstruktor, genannt wird verwendet, um einen Typ zu initialisieren. Die CLR ruft den statischen Konstruktor aus, bevor die erste Instanz des Typs erstellt oder auf irgendwelche statischen Member für diesen Typ aufgerufen werden. Der Benutzer hat keine Kontrolle darüber, wenn der statische Konstruktor aufgerufen wird. Wenn ein statischer Konstruktor nicht privat ist, kann es durch anderen Code als die CLR aufgerufen werden. Je nach den Operationen, die im Konstruktor ausgeführt wird kann dies unerwartetes Verhalten führen. Der C#-Compiler erzwingt, dass statische Konstruktoren privat sein.  
  
 **X DO NOT** lösen Ausnahmen aus statischen Konstruktoren.  
  
 Wenn von einem Typkonstruktor eine Ausnahme ausgelöst wird, ist der Typ in der aktuellen Anwendungsdomäne nicht verwendet werden.  
  
 **✓ CONSIDER** statische Felder von Inline initialisieren, anstatt explizit statische Konstruktoren zu verwenden, da die Common Language Runtime ist in der Lage, zur Optimierung der Leistung von Typen, die nicht über einen explizit definierten statischen Konstruktor verfügen.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)  
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
