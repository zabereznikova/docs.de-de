---
title: Konstruktorentwurf
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d7ca279dc1626cd526910af93326280bcd8301d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575556"
---
# <a name="constructor-design"></a>Konstruktorentwurf
Es gibt zwei Arten von Konstruktoren: Geben Sie die Konstruktoren und Instanz.  
  
 Typkonstruktoren sind statisch und werden von der CLR ausgeführt, bevor der Typ verwendet wird. Instanzkonstruktoren wird ausgeführt, wenn eine Instanz eines Typs erstellt wird.  
  
 Typkonstruktoren können keine Parameter annimmt. Instanzkonstruktoren können. Instanzkonstruktoren, die keine Parameter werden häufig Standardkonstruktoren bezeichnet.  
  
 Konstruktoren sind die meisten natürliche Möglichkeit zum Erstellen von Instanzen eines Typs. Die meisten Entwickler suchen und versuchen, einen Konstruktor verwenden, bevor sie alternative Methoden zum Erstellen von Instanzen (z. B. Factorymethoden) in Betracht ziehen.  
  
 **✓ GGF.** einfach, im Idealfall Standard, Konstruktoren bereitstellen.  
  
 Ein einfache Konstruktor hat eine sehr kleine Anzahl von Parametern, und alle Parameter sind primitive Typen oder Enumerationen. Diese einfache Konstruktoren Verwendbarkeit des Frameworks.  
  
 **✓ GGF.** eine statische Factorymethode statt einen Konstruktor verwenden, wenn die Semantik des gewünschten Vorgangs nicht direkt der Erstellung einer neuen Instanz zugeordnet sind, oder der Konstruktor Entwurfsrichtlinien unnatürlichen idealer.  
  
 **Führen Sie ✓** Konstruktorparameter als Tastenkombinationen verwenden, für die wichtigsten Eigenschaften festlegen.  
  
 Es darf kein Unterschied in der Semantik zwischen mit dem leeren Konstruktor gefolgt von einigen Eigenschaftensätze und mit einem Konstruktor mit mehreren Argumenten.  
  
 **Führen Sie ✓** verwenden Sie denselben Namen für Konstruktorparameter und eine Eigenschaft aus, wenn der Konstruktorparameter verwendet werden, einfach die Eigenschaft festgelegt.  
  
 Der einzige Unterschied zwischen Eigenschaften und solche Parameter sollten Groß-/Kleinschreibung.  
  
 **Führen Sie ✓** nur minimale Arbeitsschritte im Konstruktor.  
  
 Konstruktoren tun nicht viel Arbeit als Capture die Konstruktorparametern. Die Kosten für weitere Verarbeitungsschritte sollten verzögert werden, bis die erforderlich sind.  
  
 **Führen Sie ✓** Ausnahmen von Instanzkonstruktoren, falls zutreffend.  
  
 **Führen Sie ✓** in Klassen, die öffentlichen Standardkonstruktor explizit deklariert werden, wenn ein solcher Konstruktor erforderlich ist.  
  
 Wenn Sie keine Konstruktoren explizit auf einen Typ deklarieren nicht, werden viele Sprachen (z. B. c#) einen öffentlichen Standardkonstruktor automatisch hinzugefügt. (Abstrakte Klassen get einen geschützten Konstruktor.)  
  
 Eine Klasse einen parametrisierten Konstruktor hinzugefügt wird verhindert, dass den Compiler den Standardkonstruktor hinzufügen. Dadurch wird häufig eine versehentliche Änderungen.  
  
 **X vermeiden** explizit standardmäßige Konstruktoren für Strukturen definiert.  
  
 Dadurch Arrayerstellung schneller, da der Standardkonstruktor nicht definiert ist, nicht enthalten ist jeder Steckplatz im Array ausgeführt werden. Beachten Sie, dass Strukturen parameterlose Konstruktoren aus diesem Grund haben viele Compiler, z. B. c#, nicht.  
  
 **X vermeiden** virtuelle Member für ein Objekt in seinem Konstruktor aufrufen.  
  
 Aufrufen eines virtuellen Members bewirkt die am stärksten abgeleitete Außerkraftsetzung, die aufgerufen wird, auch wenn Sie der Konstruktor des am weitesten abgeleiteten Typ noch vollständig nicht ausgeführt wurde.  
  
### <a name="type-constructor-guidelines"></a>Richtlinien-Konstruktor  
 **Führen Sie ✓** als statische Konstruktoren privat festlegen.  
  
 Ein statischer Konstruktor, der einen Klassenkonstruktor, so genannte wird verwendet, Initialisierung eines Typs. Die CLR ruft den statischen Konstruktor auf, bevor die erste Instanz des Typs erzeugt wird bzw. irgendwelche statischen Member für diesen Typ aufgerufen werden. Der Benutzer hat keine Kontrolle darüber, wann der statische Konstruktor aufgerufen wird. Wenn ein statischer Konstruktor nicht privat ist, kann er von anderen Codes als die CLR aufgerufen werden. Je nach den Operationen, die im Konstruktor ausgeführt wird kann dies unerwartetem Verhalten führen. Der C#-Compiler erzwingt, dass statische Konstruktoren privat sein.  
  
 **X nicht** lösen Ausnahmen aus statischen Konstruktoren.  
  
 Wenn eine Ausnahme aus eines Konstruktors eines Typs ausgelöst wird, ist der Typ nicht in der aktuellen Anwendungsdomäne verwendet werden kann.  
  
 **✓ GGF.** statische Felder von Inline initialisieren, anstatt explizit statische Konstruktoren zu verwenden, da die Common Language Runtime ist in der Lage, zur Optimierung der Leistung von Typen, die nicht über einen explizit definierten statischen Konstruktor verfügen.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
