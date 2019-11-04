---
title: mc:Ignorable-Attribut
ms.date: 03/30/2017
helpviewer_keywords:
- mc XML namespace prefix [WPF]
- mc:Ignorable attribute
- XML [WPF], mc namespace prefix
- XAML [WPF], mc:Ignorable attribute
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: acd9a6ef-b7ca-4146-abb6-60f3b366e9ec
ms.openlocfilehash: d8fdeec8784c9a44c9b272a0a5a8b9c56ace5230
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458829"
---
# <a name="mcignorable-attribute"></a>mc:Ignorable-Attribut
Gibt an, welche [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Namespace Präfixe, die in einer Markup Datei gefunden werden, von einem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor ignoriert werden können. Das `mc:Ignorable`-Attribut unterstützt Markup Kompatibilität sowohl für die Zuordnung von benutzerdefinierten Namespaces als auch für [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Versionsverwaltung.  
  
## <a name="xaml-attribute-usage-single-prefix"></a>Verwendung von XAML-Attributen (einzelnes Präfix)  
  
```xaml  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a>Verwendung von XAML-Attributen (zwei Präfixe)  
  
```xaml  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|*ignorablePrefix, ignorablePrefix1 usw.*|Eine beliebige gültige Präfix Zeichenfolge gemäß der XML 1,0-Spezifikation.|  
|*ignorableuri*|Ein beliebiger gültiger URI zum Festlegen eines Namespaces gemäß der XML 1,0-Spezifikation.|  
|*ThisElementCanBeIgnored*|Ein Element, das von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Prozessor Implementierungen ignoriert werden kann, wenn der zugrunde liegende Typ nicht aufgelöst werden kann.|  
  
## <a name="remarks"></a>Hinweise  
 Die `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Namespace-Präfix ist die empfohlene Präfix Konvention, die beim Mapping des [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Compatibility-Namespace `http://schemas.openxmlformats.org/markup-compatibility/2006`verwendet wird.  
  
 Elemente oder Attribute, bei denen der Präfix Teil des Element namens als `mc:Ignorable` identifiziert wird, werden bei der Verarbeitung durch einen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor keine Fehler hervorrufen. Wenn dieses Attribut nicht in einen zugrunde liegenden Typ oder ein zugrunde liegendes Programmierkonstrukt aufgelöst werden konnte, wird dieses Element ignoriert. Beachten Sie jedoch, dass ignorierte Elemente möglicherweise weiterhin zusätzliche Analyse-Fehler für zusätzliche Element Anforderungen generieren, die Nebeneffekte dieses Elements sind, die nicht verarbeitet werden. Beispielsweise kann ein bestimmtes Element Inhalts Modell genau ein untergeordnetes Element erfordern, aber wenn das angegebene untergeordnete Element in einem `mc:Ignorable` Präfix war und das angegebene untergeordnete Element nicht in einen Typ aufgelöst werden konnte, kann der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor einen Fehler hervorrufen.  
  
 `mc:Ignorable` gilt nur für Namespace Zuordnungen zu Bezeichnerzeichenfolgen. `mc:Ignorable` gilt nicht für Namespace Zuordnungen in Assemblys, die einen CLR-Namespace und eine Assembly angeben (oder standardmäßig die aktuelle ausführbare Datei als Assembly).  
  
 Wenn Sie einen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor implementieren, darf die Prozessor Implementierung keine Analyse-oder Verarbeitungsfehler bei der Typauflösung für ein Element oder Attribut, das durch ein als `mc:Ignorable`bezeichnetes Präfix qualifiziert ist, lösen. Die Prozessor Implementierung kann jedoch weiterhin Ausnahmen verursachen, bei denen es sich um ein sekundäres Ergebnis eines Elements handelt, das nicht geladen oder verarbeitet werden kann, z. b. das zuvor angegebene Beispiel mit einem untergeordneten Element.  
  
 Standardmäßig ignoriert ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor Inhalt innerhalb eines ignorierten Elements. Sie können jedoch ein zusätzliches Attribut, [MC: ProcessContent-Attribut](mc-processcontent-attribute.md), angeben, um die fortgesetzte Verarbeitung von Inhalt innerhalb eines ignorierten Elements durch das nächste verfügbare übergeordnete Element zu erfordern.  
  
 Mehrere Präfixe können im-Attribut angegeben werden, wobei mindestens ein Leerzeichen als Trennzeichen verwendet wird, z. b. `mc:Ignorable="ignore1 ignore2"`.  

 Der `http://schemas.openxmlformats.org/markup-compatibility/2006`-Namespace definiert andere Elemente und Attribute, die in diesem Bereich des SDK nicht dokumentiert sind. Weitere Informationen finden Sie unter [XML Markup Compatibility Specification](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Markup.XamlReader>
- [PresentationOptions:Freeze-Attribut](presentationoptions-freeze-attribute.md)
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Dokumente in WPF](documents-in-wpf.md)
