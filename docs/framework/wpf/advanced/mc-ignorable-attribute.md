---
title: mc:Ignorable-Attribut
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- mc XML namespace prefix [WPF]
- mc:Ignorable attribute
- XML [WPF], mc namespace prefix
- XAML [WPF], mc:Ignorable attribute
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: acd9a6ef-b7ca-4146-abb6-60f3b366e9ec
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9767b721321b34030a2f276a90c618c658645207
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="mcignorable-attribute"></a>mc:Ignorable-Attribut
Gibt an, welche [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Namespacepräfixe, die in einer Markupdatei gefunden können ignoriert werden, indem eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor. Die `mc:Ignorable` Attribut unterstützt Markupkompatibilität für benutzerdefinierte Namespacezuordnung und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versionsverwaltung.  
  
## <a name="xaml-attribute-usage-single-prefix"></a>Verwendung von XAML-Attributen (Präfix)  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a>Verwendung von XAML-Attributen (zwei Präfixe)  
  
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
|*ignorableUri*|Ein beliebiger gültiger URI zum Angeben eines Namespaces, gemäß der XML 1.0-Spezifikation.|  
|*ThisElementCanBeIgnored*|Ein Element, das vom ignoriert werden sollen, kann [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Implementierungen von ereignissprozessoren, wenn der zugrunde liegende Typ aufgelöst werden kann.|  
  
## <a name="remarks"></a>Hinweise  
 Die `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Namespacepräfix ist die empfohlene Präfix Konvention, die zu verwendende Zuordnung der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Kompatibilität Namespace [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].  
  
 Elemente oder Attribute, in denen die Präfixteil des Elementnamens als prognostiziert `mc:Ignorable` löst keine Fehler bei der Verarbeitung einer [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor. Wenn dieses Attribut nicht in einen zugrunde liegenden Typ oder einen Programmiermodell aufgelöst werden konnte, wird dieses Element ignoriert. Beachten Sie jedoch, dass ignorierter Elemente möglicherweise noch weitere Analysefehler für zusätzliche Element Anforderungen generiert, die Nebeneffekte des jeweiligen Elements, das nicht verarbeitet werden. Beispielsweise kann ein bestimmtes Elementinhaltsmodell erfordern genau ein untergeordnetes Element, wenn das angegebene untergeordnete Element in wurde einer `mc:Ignorable` Präfix und das angegebene untergeordnete Element konnte nicht in einen Typ aufgelöst werden und dann die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor möglicherweise ein Fehler ausgelöst.  
  
 `mc:Ignorable`gilt nur für Namespacezuordnungen in Bezeichnerzeichenfolgen. `mc:Ignorable`gilt nicht für Namespacezuordnungen, die in Assemblys, die angeben einer [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Namespace und eine Assembly (oder standardmäßig auf die aktuelle ausführbare Datei, wie die Assembly befinden).  
  
 Wenn Sie implementieren eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor, wird Ihre-prozessorimplementierung muss nicht ausgelöst, analysieren oder Verarbeitungsfehlern auf typauflösung für ein Element oder Attribut, das durch ein Präfix gekennzeichnet werden, die als identifiziert wird `mc:Ignorable`. Aber Ihre-prozessorimplementierung kann weiterhin, die ein sekundäres Ergebnis eines Elements, das wegen eines Fehlers beim Laden oder verarbeitet werden, z. B. das ein untergeordnetes Element Beispiel weiter oben genannten Ausnahmen auslösen.  
  
 Wird standardmäßig ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor ignoriert Inhalte innerhalb eines Elements wird ignoriert. Sie können jedoch ein zusätzliches Attribut angeben [MC: ProcessContent Attribut](../../../../docs/framework/wpf/advanced/mc-processcontent-attribute.md), kontinuierliche Verarbeitung von Inhalten innerhalb eines ignorierten Elements vom nächsten verfügbaren übergeordneten Element erforderlich.  
  
 Mehrere Präfixe können im Attribut, z. B. über eine oder mehrere Leerzeichen als Trennzeichen, angegeben werden: `mc:Ignorable="ignore1 ignore2"`.  
  
 Die [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] -Namespace definiert, andere Elemente und Attribute, die innerhalb dieses Bereichs, der nicht dokumentiert sind die [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]. Weitere Informationen finden Sie unter [Kompatibilität-Spezifikation für XML-Markup](http://go.microsoft.com/fwlink/?LinkId=73824).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Markup.XamlReader>  
 [PresentationOptions:Freeze-Attribut](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)  
 [Übersicht über XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
