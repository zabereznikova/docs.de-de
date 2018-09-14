---
title: Namen von Namespaces
ms.date: 03/30/2017
helpviewer_keywords:
- names [.NET Framework], conflicts
- names [.NET Framework], namespaces
- type names, conflicts
- namespaces [.NET Framework], names
- names [.NET Framework], type names
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d68966f60c5039fd67195a03facc1586b9ed154
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45591723"
---
# <a name="names-of-namespaces"></a>Namen von Namespaces
Wie wird mit anderen Benennungsrichtlinien, das Ziel bei der Benennung von Namespaces erstellt ausreichend Klarheit für den Programmierer mit dem Framework sofort wissen, was der Inhalt des Namespace wahrscheinlich ist. Die folgende Vorlage gibt die allgemeine Regel für die Benennung von Namespaces an:  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 Es folgen Beispiele für:  
  
 `Fabrikam.Math`  
 `Litware.Security`  
  
 **✓ DO** Präfix Namespacenamen mit einem Firmennamen, um zu verhindern, dass Namespaces aus verschiedenen Unternehmen über den gleichen Namen verfügen.  
  
 **✓ DO** ein stabiler, versionsunabhängige Produktname auf der zweiten Ebene eine Namespace-Namen verwenden.  
  
 **X DO NOT** Organisationseinheit Hierarchien für Namen in Namespacehierarchien, als Grundlage verwenden, da Gruppennamen in Unternehmen häufig kurzlebig sind. Organisieren Sie die Hierarchie der Namespaces, um Gruppen von verwandten Technologien.  
  
 **✓ DO** PascalCasing und abgetrennten Namespacekomponenten mit Zeiträumen verwenden (z. B. `Microsoft.Office.PowerPoint`). Wenn Ihre Marke zwar Groß-/Kleinschreibung verwendet, sollten Sie die Groß-/Kleinschreibung, Ihre Marke definiert folgen, selbst wenn es sich von normalen Namespace Groß-/Kleinschreibung abweicht.  
  
 **✓ CONSIDER** plural Namespacenamen verwenden, falls zutreffend.  
  
 Verwenden Sie z. B. `System.Collections` anstelle von `System.Collection`. Markennamen und Akronyme sind jedoch Ausnahmen von dieser Regel. Verwenden Sie z. B. `System.IO` anstelle von `System.IOs`.  
  
 **X DO NOT** denselben Namen für einen Namespace und einen Typ in diesem Namespace verwenden.  
  
 Verwenden Sie z. B. nicht `Debug` als Namespace benennen, und geben Sie dann auch eine Klasse namens `Debug` im selben Namespace. Einige Compiler erfordern, dass solche Typen vollständig qualifiziert werden.  
  
### <a name="namespaces-and-type-name-conflicts"></a>Namespaces und Namenstypkonflikten  
 **X DO NOT** führen Sie die generischen Namen wie z. B. `Element`, `Node`, `Log`, und `Message`.  
  
 Es ist eine sehr hohe Wahrscheinlichkeit, dass dies zur Folge hat, geben Sie den Namen in gängigen Szenarien steht in Konflikt. Sie sollten den Namen des generischen Typs zu qualifizieren (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).  
  
 Es gibt bestimmte Richtlinien zum Vermeiden von namenstypkonflikten für verschiedene Kategorien von Namespaces.  
  
-   **Application-Modell-namespaces**  
  
     Namespaces für ein einziges Anwendungsmodell werden sehr häufig zusammen verwendet werden, aber sie werden fast nie mit Namespaces anderer Modelle für die Anwendung verwendet. Z. B. die <xref:System.Windows.Forms?displayProperty=nameWithType> -Namespace werden nur sehr selten zusammen mit den <xref:System.Web.UI?displayProperty=nameWithType> Namespace. Im folgenden finden eine Liste der bekannten Modell Namespace Anwendungsgruppen:  
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     **X DO NOT** weisen den gleichen Namen auf Typen in Namespaces in einem einzigen Anwendungsmodell.  
  
     Z. B. nicht auf einen Typ mit dem Namen hinzufügen `Page` auf die <xref:System.Web.UI.Adapters?displayProperty=nameWithType> -Namespace, da die <xref:System.Web.UI?displayProperty=nameWithType> -Namespace enthält bereits einen Typ namens `Page`.  
  
-   **Infrastrukturnamespaces**  
  
     Diese Gruppe enthält die Namespaces, die nur selten während der Entwicklung häufig genutzte Anwendungen importiert werden. Z. B. `.Design` Namespaces werden hauptsächlich verwendet, wenn das tools entwickeln, Programmieren. Vermeiden von Konflikten mit Typen aus den Namespaces ist unerheblich.  
  
-   **Core-namespaces**  
  
     Core-Namespaces enthalten alle `System` Namespaces, mit Ausnahme von Namespaces der Anwendungsmodelle und die Infrastruktur-Namespaces. Core-Namespaces einschließen, u. a. `System`, `System.IO`, `System.Xml`, und `System.Net`.  
  
     **X DO NOT** erteilen, die in Konflikt stehenden Namen mit einem beliebigen Typ in den Core-Namespaces Typen.  
  
     Verwenden Sie z. B. niemals `Stream` als Typname. Es steht in Konflikt mit <xref:System.IO.Stream?displayProperty=nameWithType>, ein sehr häufig verwendete Typ.  
  
-   **Technologie-Namespace-Gruppen**  
  
     Diese Kategorie enthält alle Namespaces mit den gleichen Namespaceknoten der ersten beiden `(<Company>.<Technology>*`), wie z. B. `Microsoft.Build.Utilities` und `Microsoft.Build.Tasks`. Es ist wichtig, dass Typen, die auf eine einzelne Technologie gehören nicht miteinander in Konflikt stehen.  
  
     **X DO NOT** Typnamen, die in Konflikt stehen würde mit anderen Typen in einer einzelnen Technologie zuweisen.  
  
     **X DO NOT** einführen Typnamenskonflikte zwischen Typen in Technologienamespaces und eine Anwendungsmodellnamespace (es sei denn, die Technologie nicht mit dem Anwendungsmodell verwendet werden sollen).  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
- [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)
