---
title: "Gewusst wie: Registrieren einer angef&#252;gten Eigenschaft | Microsoft Docs"
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
  - "Angefügte Eigenschaften, Registrieren"
  - "Registrieren von angefügten Eigenschaften"
ms.assetid: eb47bd94-0451-4f8d-8fb6-95f7812ac05b
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Registrieren einer angef&#252;gten Eigenschaft
Dieses Beispiel zeigt, wie Sie eine [angefügte Eigenschaft](GTMT) registrieren und öffentliche Accessoren bereitstellen, damit Sie die Eigenschaft in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und Code verwenden können.  Bei angefügten Eigenschaften handelt es sich um einen in der [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] definierten Syntaxbegriff.  Die meisten angefügten Eigenschaften für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Typen werden auch als [Abhängigkeitseigenschaften](GTMT) implementiert.  Sie können [Abhängigkeitseigenschaften](GTMT) für alle <xref:System.Windows.DependencyObject>\-Typen verwenden.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie Sie eine angefügte Eigenschaft als Abhängigkeitseigenschaft registrieren, indem Sie die <xref:System.Windows.DependencyProperty.RegisterAttached%2A>\-Methode verwenden.  Die Anbieterklasse kann bei Bedarf Standardmetadaten für die Eigenschaft bereitstellen, die gelten, wenn die Eigenschaft für eine andere Klasse verwendet wird, es sei denn, diese Klasse überschreibt die Metadaten.  In diesem Beispiel ist der Standardwert der `IsBubbleSource`\-Eigenschaft auf `false` gesetzt.  
  
 Die Anbieterklasse für eine angefügte Eigenschaft \(auch wenn diese nicht als Abhängigkeitseigenschaft registriert ist\) muss statische get\- und set\-Accessoren bereitstellen, für die die Namenskonvention \<`Set`*\[NameDerAngefügtenEigenschaft\]* bzw. `Get`*\[NameDerAngefügtenEigenschaft\]* befolgt wird. Diese Accessoren sind erforderlich, damit der verwendete [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Reader die Eigenschaft in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] als Attribut erkennen und die entsprechenden Typen auflösen kann.  
  
 [!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
 [!code-vb[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]  
  
## Siehe auch  
 <xref:System.Windows.DependencyProperty>   
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)