---
title: "Inlinestile und -vorlagen | Microsoft Docs"
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
  - "Inlinestile"
  - "Inlinevorlagen"
  - "Formate, inline"
  - "Vorlagen, inline"
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Inlinestile und -vorlagen
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt <xref:System.Windows.Style>\-Objekte und \-Vorlagenobjekte \(<xref:System.Windows.FrameworkTemplate> subclasses\) zur Definition des Erscheinungsbilds eines Elements in Ressourcen bereit, sodass sie mehrmals verwendet werden können.  Aus diesem Grund enthalten Attribute in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] mit den Typen <xref:System.Windows.Style> und <xref:System.Windows.FrameworkTemplate> fast immer Ressourcenverweise auf vorhandene Stile und Vorlagen, statt neue zu definieren.  
  
## Einschränkungen für Inlinestile und \-vorlagen  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] gibt es technisch zwei Möglichkeiten zum Festlegen von Stil\- und Vorlageneigenschaften.  Sie können mit Attributsyntax auf einen Stil verweisen, der in einer Ressource definiert wurde, z. B. `<`*object*`Style="{StaticResource`*myResourceKey*`}" .../>`.  Oder Sie können Eigenschaftenelementsyntax verwenden, um einen Inlinestil zu definieren. Beispiel:  
  
 `<` *Objekt* `>`  
  
 `<` *Objekt* `.Style>`  
  
 `<` `Style`  `.../>`  
  
 `</` *Objekt* `.Style>`  
  
 `</` *Objekt* `>`  
  
 Viel häufiger werden Attribute verwendet.  Ein inline definierter Stil, der nicht in Ressourcen definiert ist, ist auf das darin enthaltene Element beschränkt und kann nicht so einfach wiederverwendet werden, da er nicht über einen Ressourcenschlüssel verfügt.  In der Regel ist ein Ressourcen\-definierter Stil vielseitiger verwendbar und entspricht eher dem allgemeinen Prinzip des [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Programmiermodells, Programmlogik in Code von Entwurfslogik in Markup zu trennen.  
  
 Normalerweise liegt keine Notwendigkeit vor, einen Stil oder eine Vorlage inline zu definieren, selbst wenn Sie den Stil bzw. die Vorlage nur an der betreffenden Position verwenden möchten.  Die meisten Elemente, die Stile und Vorlagen unterstützen, unterstützen auch Inhaltseigenschaften und Inhaltsmodelle.  Wenn Sie die logische Struktur für den Stil oder die Vorlage nur einmal verwenden, ist es einfacher, im direkten Markup die entsprechenden untergeordneten Elemente in die Inhaltseigenschaft einzufügen.  Hierdurch umgehen Sie die Stil\- und Vorlagenmechanismen vollständig.  
  
 Des Weiteren können Sie für Stile und Vorlagen andere Syntaxarten verwenden, die durch Markuperweiterungen aktiviert werden.  Zwei dieser Erweiterungen mit möglichen Szenarios sind [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) und <xref:System.Windows.Data.Binding>.  
  
## Siehe auch  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)