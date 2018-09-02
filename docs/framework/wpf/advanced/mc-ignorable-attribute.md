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
ms.openlocfilehash: e8fa4c084ae9c775a18de06c344b2c0b439c2b1b
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43467814"
---
# <a name="mcignorable-attribute"></a>mc:Ignorable-Attribut
Gibt an, welche [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Namespacepräfixe, die bei der ein Markup-Datei können ignoriert werden, indem eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor. Die `mc:Ignorable` Attribut Markupkompatibilität unterstützt, für den benutzerdefinierten Namespace-Zuordnung und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versionsverwaltung.  
  
## <a name="xaml-attribute-usage-single-prefix"></a>XAML-Attributverwendung (einzelnes Adresspräfix)  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a>XAML-Attributverwendung (zwei Präfixe)  
  
```  
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
|*IgnorablePrefix, ignorablePrefix1 usw..*|Jede gültige Präfixzeichenfolge gemäß der XML 1.0-Spezifikation.|  
|*ignorableUri*|Ein beliebiger gültiger URI für das Angeben eines Namespaces, gemäß der XML 1.0-Spezifikation.|  
|*ThisElementCanBeIgnored*|Ein Element, das vom ignoriert werden sollen, kann [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Implementierungen von ereignissprozessoren, wenn der zugrunde liegende Typ nicht aufgelöst werden kann.|  
  
## <a name="remarks"></a>Hinweise  
 Die `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Namespace-Präfix ist die empfohlene Präfix-Konvention zu verwenden, wenn die Zuordnung der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Compatibility-Namespace [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].  
  
 Elemente oder Attribute, die bei der Präfixteil der Elementname als identifiziert `mc:Ignorable` löst keinen Fehler bei der Verarbeitung durch eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor. Wenn dieses Attribut nicht in einen zugrunde liegenden Typ oder einen Programmierungskonstrukt aufgelöst werden konnte, wird dieses Element ignoriert. Beachten Sie jedoch, dass das ignorierte Elemente weiterhin zusätzliche Analysefehler für zusätzliche Containerelement-Anforderungen generieren können, die Nebeneffekte des jeweiligen Elements, das nicht verarbeitet werden. Z. B. möglicherweise ein bestimmtes Elementinhaltsmodell genau ein untergeordnetes Element, jedoch wenn das angegebene untergeordnete Element in wurde einer `mc:Ignorable` Präfix und das angegebene untergeordnete Element konnte nicht in einen Typ aufgelöst werden und dann die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor möglicherweise ein Fehler ausgelöst.  
  
 `mc:Ignorable` gilt nur für den Namespacezuordnungen zu Bezeichnerzeichenfolgen. `mc:Ignorable` gilt nicht für Namespacezuordnungen zu Assemblys, die angeben einer [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Namespace und eine Assembly (oder standardmäßig auf die ausführbare Datei als Assembly).  
  
 Wenn Sie implementieren eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -Prozessor, Ihre-prozessorimplementierung muss nicht auslösen, analysieren oder zu Fehlern auf typauflösung für ein Element oder Attribut, das durch ein Präfix qualifiziert wird, die als identifiziert wird bei der Verarbeitung `mc:Ignorable`. Aber die prozessorimplementierung kann weiterhin Ausnahmen auslösen, die sekundäre eines Elements, das beim Laden oder verarbeitet werden resultieren, beispielsweise eine-untergeordnetes Element weiter oben.  
  
 Standardmäßig eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor ignoriert den Inhalt in einem Element ignoriert. Sie können jedoch zusätzlich das Attribut angeben [MC: ProcessContent-Attribut](../../../../docs/framework/wpf/advanced/mc-processcontent-attribute.md), um die kontinuierliche Verarbeitung des Inhalts in einem ignoriert Element vom nächsten verfügbaren übergeordneten Element erforderlich.  
  
 Mehrere Präfixe können angegeben werden, in das Attribut, wobei eine oder mehrere Leerzeichen als Trennzeichen, z. B.: `mc:Ignorable="ignore1 ignore2"`.  

 Die [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] -Namespace definiert, andere Elemente und Attribute, die in diesem Bereich nicht dokumentiert sind die [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]. Weitere Informationen finden Sie unter [XML-Markup-Compatibility-Spezifikation](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Markup.XamlReader>  
 [PresentationOptions:Freeze-Attribut](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)  
 [Übersicht über XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
