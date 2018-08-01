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
ms.openlocfilehash: 9e0b6c5ac60474cfe984b3802e880eb58b017722
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33576431"
---
# <a name="names-of-namespaces"></a>Namen von Namespaces
Als ist mit anderen Benennungsrichtlinien das Ziel beim Benennen von Namespaces erstellen ausreichend Klarheit für Programmierer, die mithilfe des Frameworks sofort zu wissen, was der Inhalt des Namespaces wahrscheinlich ist. Die folgende Vorlage gibt an, die in der Regel für die Benennung von Namespaces:  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 Es folgen Beispiele für:  
  
 `Fabrikam.Math`  
 `Litware.Security`  
  
 **✓ DO** Präfix Namespacenamen mit einem Firmennamen, um zu verhindern, dass Namespaces aus verschiedenen Unternehmen über den gleichen Namen verfügen.  
  
 **✓ DO** ein stabiler, versionsunabhängige Produktname auf der zweiten Ebene eine Namespace-Namen verwenden.  
  
 **X DO NOT** Organisationseinheit Hierarchien für Namen in Namespacehierarchien, als Grundlage verwenden, da Gruppennamen in Unternehmen häufig kurzlebig sind. Organisieren Sie die Hierarchie von Namespaces, um Gruppen von verwandten Technologien.  
  
 **✓ DO** PascalCasing und abgetrennten Namespacekomponenten mit Zeiträumen verwenden (z. B. `Microsoft.Office.PowerPoint`). Wenn Ihre Marke traditionelle Groß-/Kleinschreibung verwendet, sollten Sie die Groß-/Kleinschreibung definiert Ihre Marke folgen, selbst wenn er von der normalen Namespace Groß-/Kleinschreibung abweicht.  
  
 **✓ CONSIDER** plural Namespacenamen verwenden, falls zutreffend.  
  
 Verwenden Sie z. B. `System.Collections` anstelle von `System.Collection`. Markennamen und Akronyme sind jedoch Ausnahmen von dieser Regel. Verwenden Sie z. B. `System.IO` anstelle von `System.IOs`.  
  
 **X DO NOT** denselben Namen für einen Namespace und einen Typ in diesem Namespace verwenden.  
  
 Verwenden Sie z. B. nicht `Debug` wie ein Namespace benennen, und geben Sie dann auch eine Klasse namens `Debug` im selben Namespace. Einige Compiler erfordern, dass solche Typen vollqualifiziert sein.  
  
### <a name="namespaces-and-type-name-conflicts"></a>Namespaces und Typnamenskonflikte  
 **X DO NOT** führen Sie die generischen Namen wie z. B. `Element`, `Node`, `Log`, und `Message`.  
  
 Es ist ein sehr hoher Wahrscheinlichkeit, dass dies hätte, führen um zu eingeben gemeinsame Szenarien steht in Konflikt. Sie sollten die generischen Namen qualifizieren (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).  
  
 Es gibt spezielle Richtlinien für die Typ-Namenskonflikte für verschiedene Kategorien von Namespaces zu vermeiden.  
  
-   **Application-Modell-namespaces**  
  
     Namespaces, gehören zu einem einzelnen Anwendungsmodell werden häufig zusammen verwendet werden, aber sie fast nie mit Namespaces anderer Modelle der Anwendung verwendet werden. Z. B. die <xref:System.Windows.Forms?displayProperty=nameWithType> Namespace wird sehr selten verwendet werden, zusammen mit den <xref:System.Web.UI?displayProperty=nameWithType> Namespace. Im folgenden finden eine Liste der bekannten Anwendung Namespace Modellgruppen:  
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     **X DO NOT** weisen den gleichen Namen auf Typen in Namespaces in einem einzigen Anwendungsmodell.  
  
     Z. B. einen Typ mit dem Namen nicht hinzufügen `Page` auf die <xref:System.Web.UI.Adapters?displayProperty=nameWithType> Namespace, da die <xref:System.Web.UI?displayProperty=nameWithType> -Namespace enthält bereits einen Typ mit dem Namen `Page`.  
  
-   **Infrastrukturnamespaces**  
  
     Diese Gruppe enthält die Namespaces, die nur selten während der Entwicklung der Anwendung importiert werden. Beispielsweise `.Design` Namespaces werden hauptsächlich verwendet, bei der Entwicklung, Programmierung tools. Vermeiden von Konflikten mit Typen aus den Namespaces ist unerheblich.  
  
-   **Core-namespaces**  
  
     Core-Namespaces enthalten alle `System` Namespaces, die ausschließlich Namespaces und die Anwendungsmodelle und der Infrastruktur-Namespaces. Core-Namespaces enthalten, u. a. `System`, `System.IO`, `System.Xml`, und `System.Net`.  
  
     **X DO NOT** erteilen, die in Konflikt stehenden Namen mit einem beliebigen Typ in den Core-Namespaces Typen.  
  
     Verwenden Sie z. B. niemals `Stream` als Typname. Es steht in Konflikt mit <xref:System.IO.Stream?displayProperty=nameWithType>, eine sehr häufig verwendete Typ.  
  
-   **Technologie Namespace Gruppen**  
  
     Diese Kategorie umfasst alle Namespaces mit den gleichen ersten beiden Namespaceknoten `(<Company>.<Technology>*`), wie z. B. `Microsoft.Build.Utilities` und `Microsoft.Build.Tasks`. Es ist wichtig, dass Typen, die auf eine einzelne Technologie gehören nicht miteinander in Konflikt stehen.  
  
     **X DO NOT** Typnamen, die in Konflikt stehen würde mit anderen Typen in einer einzelnen Technologie zuweisen.  
  
     **X DO NOT** einführen Typnamenskonflikte zwischen Typen in Technologienamespaces und eine Anwendungsmodellnamespace (es sei denn, die Technologie nicht mit dem Anwendungsmodell verwendet werden sollen).  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
 [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)
