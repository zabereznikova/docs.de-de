---
title: mc:ProcessContent-Attribut
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: bcf55668bdc70902e346c401549a88f6ccb9072e
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095124"
---
# <a name="mcprocesscontent-attribute"></a>mc:ProcessContent-Attribut
Gibt an, welche [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Elemente weiterhin Inhalte haben sollen, die durch relevante übergeordnete Elemente verarbeitet werden sollen, auch wenn das unmittelbare übergeordnete Element von einem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor aufgrund der Angabe des [MC: Ignorable-Attributs](mc-ignorable-attribute.md)ignoriert werden kann. Das `mc:ProcessContent`-Attribut unterstützt Markup Kompatibilität sowohl für die Zuordnung von benutzerdefinierten Namespaces als auch für [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Versionsverwaltung.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...  
  mc:ProcessContent="ignorablePrefix:ThisElementCanBeIgnored"  
>  
    <ignorablePrefix:ThisElementCanBeIgnored>  
        [content]  
    </ignorablePrefix:ThisElementCanBeIgnored>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|*ignorablePrefix*|Eine beliebige gültige Präfix Zeichenfolge gemäß der XML 1,0-Spezifikation.|  
|*ignorableuri*|Ein beliebiger gültiger URI zum Festlegen eines Namespaces gemäß der XML 1,0-Spezifikation.|  
|*ThisElementCanBeIgnored*|Ein Element, das von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Prozessor Implementierungen ignoriert werden kann, wenn der zugrunde liegende Typ nicht aufgelöst werden kann.|  
|*inhaltliche*|" *ThisElementCanBeIgnored* " ist als "Ignorable" gekennzeichnet. Wenn der Prozessor dieses Element ignoriert, wird *[Content]* vom *Objekt*verarbeitet.|  
  
## <a name="remarks"></a>Bemerkungen  
 Standardmäßig ignoriert ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor Inhalt innerhalb eines ignorierten Elements. Sie können ein bestimmtes Element angeben, indem Sie `mc:ProcessContent`, und ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor verarbeitet weiterhin den Inhalt im ignorierten Element. Dies wird normalerweise verwendet, wenn der Inhalt in mehreren Tags geschachtelt ist, mindestens einer von einem Ignorable-Element, das nicht Ignorable ist.  
  
 Im-Attribut können mehrere Präfixe mit einem Leerzeichen angegeben werden, z. b. `mc:ProcessContent="ignore:Element1 ignore:Element2"`.  
  
 Der `http://schemas.openxmlformats.org/markup-compatibility/2006`-Namespace definiert andere Elemente und Attribute, die in diesem Bereich des SDK nicht dokumentiert sind. Weitere Informationen finden Sie unter [XML Markup Compatibility Specification](https://docs.microsoft.com/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).  
  
## <a name="see-also"></a>Weitere Informationen

- [mc:Ignorable-Attribut](mc-ignorable-attribute.md)
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
