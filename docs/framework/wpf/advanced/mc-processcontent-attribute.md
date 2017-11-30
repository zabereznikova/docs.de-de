---
title: mc:ProcessContent-Attribut
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aaf83fe66d5367d5e51428cb8f35aa88c12c9c39
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="mcprocesscontent-attribute"></a>mc:ProcessContent-Attribut
Gibt an, welche [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Elemente sollten Inhalte, die vom entsprechenden übergeordneten Elementen verarbeitet weiterhin bestehen, auch wenn das unmittelbar übergeordnete Element von ignoriert werden kann ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor aufgrund angeben [Mc: Ignorierbares Attribut](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) . Die `mc:ProcessContent` Attribut unterstützt Markupkompatibilität für benutzerdefinierte Namespacezuordnung und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versionsverwaltung.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```  
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
|*ignorablePrefix*|Jede gültige Präfixzeichenfolge gemäß der XML 1.0-Spezifikation.|  
|*ignorableUri*|Ein beliebiger gültiger URI zum Angeben eines Namespaces, gemäß der XML 1.0-Spezifikation.|  
|*ThisElementCanBeIgnored*|Ein Element, das vom ignoriert werden sollen, kann [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Implementierungen von ereignissprozessoren, wenn der zugrunde liegende Typ aufgelöst werden kann.|  
|*[Content]*|*ThisElementCanBeIgnored* ignorierbares gekennzeichnet ist. Wenn der Prozessor dieses Element ignoriert *[Inhalt]* wird verarbeitet, indem *Objekt*.|  
  
## <a name="remarks"></a>Hinweise  
 Wird standardmäßig ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor ignoriert Inhalte innerhalb eines Elements wird ignoriert. Sie können ein bestimmtes Element durch angeben `mc:ProcessContent`, und ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor verarbeitet weiterhin den Inhalt innerhalb des Elements wird ignoriert. Dies wird normalerweise verwendet, wenn der Inhalt innerhalb mehrerer Tags geschachtelt ist, mindestens eine der ignorierbares und mindestens eine der nicht ignoriert.  
  
 Mehrere Präfixe können angegeben werden, in das Attribut mit Leerzeichen als Trennzeichen, z. B.: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.  
  
 Die [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] -Namespace definiert, andere Elemente und Attribute, die innerhalb dieses Bereichs, der nicht dokumentiert sind die [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]. Weitere Informationen finden Sie unter [Kompatibilität-Spezifikation für XML-Markup](http://go.microsoft.com/fwlink/?LinkId=73824).  
  
## <a name="see-also"></a>Siehe auch  
 [mc:Ignorable-Attribut](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)  
 [Übersicht über XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
