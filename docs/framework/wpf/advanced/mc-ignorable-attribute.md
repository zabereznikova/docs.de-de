---
title: "mc:Ignorable-Attribut | Microsoft Docs"
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
  - "MC-XML-Namespacepräfix"
  - "mc:Ignorable-Attribut"
  - "mc:ProcessContent-Attribut"
  - "XAML, mc:Ignorable-Attribut"
  - "XAML, mc:ProcessContent-Attribut"
  - "XML, MC-Namespacepräfix"
ms.assetid: acd9a6ef-b7ca-4146-abb6-60f3b366e9ec
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# mc:Ignorable-Attribut
Gibt an, welche [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Namespacepräfixe, die in einer Markupdatei gefunden wurden, möglicherweise von einem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessor ignoriert werden.  Das `mc:Ignorable`\-Attribut unterstützt Markupkompatibilität sowohl für benutzerdefinierte Namespace\-Zuordnungen als auch für die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Versionsverwaltung.  
  
## Verwendung von XAML\-Attributen \(Einzelnes Präfix\)  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## Verwendung von XAML\-Attributen \(Zwei Präfixe\)  
  
```  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|*ignorablePrefix, ignorablePrefix1 usw.*|Eine beliebige gültige Präfixzeichenfolge, gemäß XML 1.0\-Spezifikation.|  
|*ignorableUri*|Ein beliebiger gültiger URI zum Angeben eines Namespaces, gemäß XML 1.0\-Spezifikation.|  
|*ThisElementCanBeIgnored*|Ein Element, das von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Prozessorimplementierungen ignoriert werden kann, wenn der zugrunde liegende Typ nicht aufgelöst werden kann.|  
  
## Hinweise  
 Das `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Namespacepräfix ist die empfohlene Präfixkonvention für die Zuordnung des [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Compatibility\-Namespaces [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].  
  
 Elemente oder Attribute, bei denen der Präfixabschnitt des Elementnamens als `mc:Ignorable` identifiziert wird, lösen keine Fehler aus, wenn sie von einem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessor verarbeitet werden.  Wenn dieses Attribut nicht zu einem zugrunde liegenden Typ oder Programmierkonstrukt aufgelöst werden konnte, wird dieses Element ignoriert.  Beachten Sie jedoch, dass ignorierte Elemente noch immer zusätzliche Analysefehler für weitere Elementanforderungen auslösen können, die Nebeneffekte des nicht verarbeiteten Elements sind.  So erfordert beispielsweise ein bestimmtes Elementinhaltsmodell möglicherweise genau ein untergeordnetes Element. Wenn jedoch das angegebene untergeordnete Element in einem `mc:Ignorable`\-Präfix enthalten war und nicht zu einem Typ aufgelöst werden konnte, löst der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessor möglicherweise einen Fehler aus.  
  
 `mc:Ignorable` gilt nur für Namespacezuordnungen für Bezeichnerzeichenfolgen.  `mc:Ignorable` gilt nicht für Namespacezuordnungen zu Assemblys, die einen [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Namespace und eine Assembly angeben \(oder standardmäßig die ausführbare Datei als Assembly haben\).  
  
 Wenn Sie einen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessor implementieren, darf Ihre Prozessorimplementierung keine Analyse\- oder Verarbeitungsfehler bei der Typauflösung für ein beliebiges Element oder ein Attribut auslösen, das durch ein Präfix als `mc:Ignorable` identifiziert wurde.  Ihre Prozessorimplementierung kann dennoch Ausnahmen auslösen, die Nebeneffekte davon sind, dass ein Element nicht geladen oder verarbeitet werden kann, wie das zuvor genannte untergeordnete Element.  
  
 Standardmäßig ignoriert ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessor Inhalte innerhalb eines ignorierten Elements.  Sie können jedoch ein zusätzliches Attribut angeben, [mc:ProcessContent\-Attribut](../../../../docs/framework/wpf/advanced/mc-processcontent-attribute.md), um festzulegen, dass innerhalb eines ignorierten Elements vom nächsten verfügbaren übergeordneten Element eine kontinuierliche Verarbeitung des Inhalts ausgeführt werden muss.  
  
 Mehrere Präfixe können im Attribut angegeben werden, indem mindestens ein Leerzeichen als Trennzeichen verwendet wird, z. B.: `mc:Ignorable="ignore1 ignore2"`.  
  
 Der [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)]\-Namespace definiert andere Elemente und Attribute, die nicht innerhalb dieses [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]\-Bereichs dokumentiert sind.  Weitere Informationen finden Sie unter [Spezifikation für die XML\-Markupkompatibilität](http://go.microsoft.com/fwlink/?LinkId=73824).  
  
## Siehe auch  
 <xref:System.Windows.Markup.XamlReader>   
 [PresentationOptions:Freeze\-Attribut](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)   
 [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)