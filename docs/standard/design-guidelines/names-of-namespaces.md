---
title: "Namen von Namespaces | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "[Namen [.NET Framework], Konflikte"
  - "[Namen [.NET Framework], namespaces"
  - "Typnamen, Konflikte"
  - "[Namespaces [.NET Framework], Namen"
  - "[Namen [.NET Framework], Namen"
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Namen von Namespaces
Da mit anderen Benennungsrichtlinien erstellen das Ziel bei der Benennung von Namespaces ausreichend Klarheit für Programmierer, die mit dem Framework sofort wissen, was der Inhalt des Namespace wahrscheinlich ist. Die folgende Vorlage gibt die allgemeine Regel für die Benennung von Namespaces an:  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 Die folgenden Beispiele:  
  
 `Fabrikam.Math`   
 `Litware.Security`  
  
 **✓ führen** Präfix Namespacenamen mit einem Firmennamen Namespaces aus unterschiedlichen Unternehmen aus den gleichen Namen zu verhindern.  
  
 **✓ führen** verwenden einen stabilen, versionsunabhängigen Produktnamen auf der zweiten Ebene des Namespace ein.  
  
 **X nicht** verwenden Sie Organisationshierarchien als Grundlage für Namen in Namespacehierarchien, weil Gruppennamen in Unternehmen häufig kurzlebig sind. Organisieren Sie die Hierarchie der Namespaces, um Gruppen von verwandten Technologien.  
  
 **✓ führen** PascalCasing und separaten Namespace\-Komponenten mit Punkten verwendet \(z. B. `Microsoft.Office.PowerPoint`\). Wenn Ihre Marke nicht traditionelle Groß\-\/Kleinschreibung verwendet, sollten Sie die Groß\-\/Kleinschreibung, Ihre Marke definierte folgen, selbst wenn es von der normalen Schreibweise für Namespaces abweicht.  
  
 **✓ ggf.** mit plural Namespacenamen gegebenenfalls.  
  
 Verwenden Sie z. B. `System.Collections` anstelle von `System.Collection`. Markennamen und Akronyme sind jedoch Ausnahmen von dieser Regel. Verwenden Sie z. B. `System.IO` anstelle von `System.IOs`.  
  
 **X nicht** verwenden Sie denselben Namen für einen Namespace und einen Typ im Namespace.  
  
 Verwenden Sie z. B. nicht `Debug` als Namespace benennen, und geben Sie dann auch eine Klasse namens `Debug` im selben Namespace. Einige Compiler erfordern, dass solche Typen vollqualifiziert sein.  
  
### Namespaces und Typnamenskonflikte  
 **X nicht** führen Sie generische Typnamen wie z. B. `Element`, `Node`, `Log`, und `Message`.  
  
 Es gibt eine sehr hohe Wahrscheinlichkeit, dass dies hätte zur Folge hat, geben Sie den Namen in gängigen Szenarien Konflikt steht. Sie sollten die generischen Typnamen qualifizieren \(`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`\).  
  
 Es gibt spezielle Richtlinien zur Vermeidung von Namenskonflikten für verschiedene Kategorien von Namespaces Typ.  
  
-   **Application Model\-namespaces**  
  
     Namespaces für eine einzelne Anwendungsmodell werden sehr häufig zusammen verwendet werden, aber sie werden fast nie mit Namespaces anderer Modelle der Anwendung verwendet. Z. B. der <xref:System.Windows.Forms?displayProperty=fullName> \-Namespace werden nur sehr selten zusammen mit den <xref:System.Web.UI?displayProperty=fullName> Namespace. Im folgenden finden eine Liste der bekannten Modell Namespace Anwendungsgruppen:  
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     **X nicht** Typen in Namespaces in einem einzigen Anwendungsmodell den gleichen Namen zuweisen.  
  
     Z. B. einen Typ mit dem Namen nicht hinzufügen `Page` auf der <xref:System.Web.UI.Adapters?displayProperty=fullName> \-Namespace, da die <xref:System.Web.UI?displayProperty=fullName> \-Namespace enthält bereits einen Typ mit dem Namen `Page`.  
  
-   **Infrastrukturnamespaces**  
  
     Diese Gruppe enthält die Namespaces, die nur selten während der Entwicklung der Anwendung importiert werden. Z. B. `.Design` Namespaces werden hauptsächlich verwendet, wenn tools entwickeln programmieren. Vermeiden von Konflikten mit Typen in diesen Namespaces ist unerheblich.  
  
-   **Core\-namespaces**  
  
     Core\-Namespaces enthalten alle `System` Namespaces, ohne Namespaces der Anwendungsmodelle und die Infrastruktur\-Namespaces. Core\-Namespaces enthalten, u. a. `System`, `System.IO`, `System.Xml`, und `System.Net`.  
  
     **X nicht** Geben Sie Namen, die in Konflikt stehen würde mit einem Typ in den Kernnamespaces Typen.  
  
     Verwenden Sie z. B. niemals `Stream` als Typname. Es steht in Konflikt mit <xref:System.IO.Stream?displayProperty=fullName>, häufig verwendete Typ.  
  
-   **Technologie\-Namespace\-Gruppen**  
  
     Diese Kategorie umfasst alle Namespaces mit derselben ersten beiden Namespaceknoten `(<Company>.<Technology>*`\), wie z. B. `Microsoft.Build.Utilities` und `Microsoft.Build.Tasks`. Es ist wichtig, dass Typen, die für eine einzelne Technologie nicht miteinander in Konflikt stehen.  
  
     **X nicht** zuweisen, die in Konflikt stehenden Namen zusammen mit anderen Typen in einer einzelnen Technologie.  
  
     **X nicht** Typnamenskonflikte zwischen Typen in Technologienamespaces und einer Anwendungsmodellnamespace einführen, \(es sei denn, die Technologie nicht mit dem Anwendungsmodell verwendet werden soll\).  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)   
 [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)