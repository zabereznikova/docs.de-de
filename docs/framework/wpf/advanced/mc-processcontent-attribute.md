---
title: "mc:ProcessContent-Attribut | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "mc:ProcessContent-Attribut"
  - "XAML, mc:ProcessContent-Attribut"
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# mc:ProcessContent-Attribut
Gibt an, welche [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Elemente weiterhin über Inhalte verfügen sollten, die durch relevante übergeordnete Parameter verarbeitet werden, auch wenn das unmittelbar übergeordnete Element durch einen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessor ignoriert werden kann, weil [mc:Ignorable\-Attribut](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) angegeben ist.  Das `mc:ProcessContent`\-Attribut unterstützt Markupkompatibilität sowohl für benutzerdefinierte Namespace\-Zuordnungen als auch für die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Versionsverwaltung.  
  
## Verwendung von XAML\-Attributen  
  
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
  
## XAML\-Werte  
  
|||  
|-|-|  
|*ignorablePrefix*|Eine beliebige gültige Präfixzeichenfolge, gemäß XML 1.0\-Spezifikation.|  
|*ignorableUri*|Ein beliebiger gültiger URI zum Angeben eines Namespaces, gemäß XML 1.0\-Spezifikation.|  
|*ThisElementCanBeIgnored*|Ein Element, das von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Prozessorimplementierungen ignoriert werden kann, wenn der zugrunde liegende Typ nicht aufgelöst werden kann.|  
|*\[Inhalt\]*|*ThisElementCanBeIgnored* ist als ignorierbar gekennzeichnet.  Wenn der Prozessor dieses Element ignoriert, wird *\[Inhalt\]* nach *Objekt* verarbeitet.|  
  
## Hinweise  
 Standardmäßig ignoriert ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessor Inhalte innerhalb eines ignorierten Elements.  Sie können ein bestimmtes Element nach `mc:ProcessContent` angeben. Ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessor wird dann weiterhin den Inhalt innerhalb des ignorierten Elements verarbeiten.  Dieses Vorgehen wird normalerweise verwendet, wenn der Inhalt innerhalb mehrerer Tags verschachtelt ist, von denen mindestens eines ignorierbar und mindestens eines nicht ignorierbar ist.  
  
 In dem Attribut können mehrere Präfixe angegeben werden, unter Verwendung Leerzeichen als Trennzeichen \(z. B.: `mc:ProcessContent="ignore:Element1 ignore:Element2"`\).  
  
 Der [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)]\-Namespace definiert andere Elemente und Attribute, die nicht innerhalb dieses [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]\-Bereichs dokumentiert sind.  Weitere Informationen finden Sie unter [Spezifikation für die XML\-Markupkompatibilität](http://go.microsoft.com/fwlink/?LinkId=73824).  
  
## Siehe auch  
 [mc:Ignorable\-Attribut](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)   
 [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)