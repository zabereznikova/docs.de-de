---
title: Namen von Namespaces
description: Verwenden Sie diese Richtlinien für die Benennung von Namespaces als Teil der Richtlinien zum Entwerfen von Bibliotheken, die .NET-Bibliotheken erweitern und mit ihnen interagieren.
ms.date: 10/22/2008
helpviewer_keywords:
- names [.NET Framework], conflicts
- names [.NET Framework], namespaces
- type names, conflicts
- namespaces [.NET Framework], names
- names [.NET Framework], type names
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
ms.openlocfilehash: e435e0281165b4a9f12bbccbeb10401b57375dcb
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290200"
---
# <a name="names-of-namespaces"></a>Namen von Namespaces
Wie bei anderen Benennungs Richtlinien ist das Ziel bei der Benennung von Namespaces, dass der Programmierer, der das Framework verwendet, ausreichend Klarheit schafft, um sofort zu wissen, welcher Inhalt des Namespace wahrscheinlich ist. Die folgende Vorlage gibt die allgemeine Regel für das Benennen von Namespaces an:

 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`

 Hier finden Sie einige Beispiele:

 `Fabrikam.Math` `Litware.Security`

 ✔️ Namen von Namespace Namen mit einem Firmennamen zu versehen, um zu verhindern, dass Namespaces von unterschiedlichen Unternehmen denselben Namen haben.

 ✔️ verwenden einen stabilen, Versions unabhängigen Produktnamen auf der zweiten Ebene eines Namespace namens.

 ❌Verwenden Sie Organisations Hierarchien nicht als Grundlage für Namen in Namespace Hierarchien, da Gruppennamen in Unternehmen tendenziell kurzlebig sind. Organisieren Sie die Hierarchie von Namespaces um Gruppen verwandter Technologien.

 ✔️ eine Pass-/Schreibweise verwenden, und trennen Sie Namespace Komponenten mit Zeiträume (z. b. `Microsoft.Office.PowerPoint` ). Wenn Ihre Marke nicht herkömmliche Schreibweise verwendet, sollten Sie die von Ihrer Marke definierte Groß-/Kleinschreibung befolgen, auch wenn Sie von der normalen Namespace-Schreibweise abweicht.

 ✔️ sollten Sie ggf. Plural Namespace Namen verwenden.

 Verwenden Sie beispielsweise `System.Collections` anstelle von `System.Collection`. Markennamen und Akronyme sind jedoch Ausnahmen für diese Regel. Verwenden Sie beispielsweise `System.IO` anstelle von `System.IOs`.

 ❌Verwenden Sie nicht den gleichen Namen für einen Namespace und einen Typ in diesem Namespace.

 Verwenden Sie z `Debug` . b. nicht als Namespace Name, und geben Sie dann auch eine Klasse `Debug` mit dem Namen im selben Namespace an. Mehrere Compiler erfordern, dass solche Typen voll qualifiziert sind.

### <a name="namespaces-and-type-name-conflicts"></a>Namespaces und Typnamen Konflikte
 ❌Führen Sie keine allgemeinen Typnamen ein, wie z `Element` `Node` . b.,, `Log` und `Message` .

 Es gibt eine sehr hohe Wahrscheinlichkeit, dass dies zu Typnamens Konflikten in gängigen Szenarien führt. Sie sollten die generischen Typnamen qualifizieren ( `FormElement` , `XmlNode` , `EventLog` , `SoapMessage` ).

 Es gibt spezielle Richtlinien zum Vermeiden von Typnamens Konflikten für verschiedene Namespaces-Kategorien.

- **Namespaces des Anwendungs Modells**

     Namespaces, die zu einem einzelnen Anwendungsmodell gehören, werden häufig zusammen verwendet, aber Sie werden fast nie mit Namespaces anderer Anwendungsmodelle verwendet. Beispielsweise wird der- <xref:System.Windows.Forms?displayProperty=nameWithType> Namespace sehr selten in Verbindung mit dem- <xref:System.Web.UI?displayProperty=nameWithType> Namespace verwendet. Im folgenden finden Sie eine Liste bekannter Anwendungsmodell-Namespace Gruppen:

     `System.Windows*` `System.Web.UI*`

     ❌Benennen Sie Typen in Namespaces innerhalb eines einzelnen Anwendungs Modells nicht denselben Namen.

     Fügen Sie z. b. dem-Namespace keinen Typ mit dem Namen hinzu `Page` <xref:System.Web.UI.Adapters?displayProperty=nameWithType> , da der- <xref:System.Web.UI?displayProperty=nameWithType> Namespace bereits einen Typ mit dem Namen enthält `Page` .

- **Infrastructure-Namespaces**

     Diese Gruppe enthält Namespaces, die nur selten während der Entwicklung allgemeiner Anwendungen importiert werden. `.Design`Namespaces werden z. b. hauptsächlich zum Entwickeln von Programmier Tools verwendet. Es ist nicht wichtig, Konflikte mit Typen in diesen Namespaces zu vermeiden.

- **Kernnamespaces**

     Kernnamespaces enthalten alle `System` Namespaces, ausgenommen Namespaces der Anwendungsmodelle und der Infrastructure-Namespaces. Zu den Kernnamespaces zählen unter anderem,,, `System` `System.IO` `System.Xml` und `System.Net` .

     ❌Geben Sie keine Namen für Typen an, die mit einem beliebigen Typ in den Kernnamespaces in Konflikt stehen würden.

     Verwenden Sie z. b `Stream` . niemals als Typnamen. Es würde zu einem Konflikt mit <xref:System.IO.Stream?displayProperty=nameWithType> , einem sehr häufig verwendeten Typ, kommen.

- **Technologie-Namespace Gruppen**

     Diese Kategorie enthält alle Namespaces mit denselben ersten zwei Namespace Knoten `(<Company>.<Technology>*` ), wie z `Microsoft.Build.Utilities` . b `Microsoft.Build.Tasks` . und. Es ist wichtig, dass Typen, die zu einer einzelnen Technologie gehören, nicht miteinander in Konflikt stehen.

     ❌Weisen Sie keine Typnamen zu, die mit anderen Typen in einer einzelnen Technologie in Konflikt stehen.

     ❌Führen Sie keine Typnamen Konflikte zwischen Typen in Technologie Namespaces und einem Anwendungsmodell-Namespace ein (es sei denn, die Technologie ist nicht für die Verwendung mit dem Anwendungsmodell vorgesehen).

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Framework-Entwurfs Richtlinien](index.md)
- [Benennungs Richtlinien](naming-guidelines.md)
