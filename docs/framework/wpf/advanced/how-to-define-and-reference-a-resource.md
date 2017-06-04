---
title: "Gewusst wie: Definieren einer Ressource und Verweisen auf eine Ressource | Microsoft Docs"
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
  - "Definieren von Ressourcen"
  - "Verweisen auf Ressourcen"
  - "Ressourcen, Definieren"
  - "Ressourcen, Verweisen"
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Definieren einer Ressource und Verweisen auf eine Ressource
Dieses Beispiel zeigt, wie eine Ressource definiert und wie in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] mithilfe eines Attributs auf sie verwiesen wird.  
  
## Beispiel  
 Im folgenden Beispiel werden zwei Typen von Ressourcen definiert: eine <xref:System.Windows.Media.SolidColorBrush>\-Ressource und mehrere <xref:System.Windows.Style>\-Ressourcen.  Mit der <xref:System.Windows.Media.SolidColorBrush>\-Ressource `MyBrush` werden die Werte mehrerer Eigenschaften bereitgestellt, von denen jede einen Wert vom <xref:System.Windows.Media.Brush>\-Typ akzeptiert.  Die <xref:System.Windows.Style>\-Ressourcen `PageBackground`, `TitleText` und `Label` zielen jeweils auf einen bestimmten Steuerelementtyp ab.  Die Stile legen zahlreiche verschiedene Eigenschaften für die Zielsteuerelemente fest, wenn mit einen Ressourcenschlüssel auf diesen Stil verwiesen wird und er zum Festlegen der <xref:System.Windows.FrameworkElement.Style%2A>\-Eigenschaft für mehrere bestimmte Steuerelemente verwendet wird, die in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] definiert sind.  
  
 Beachten Sie, dass eine der Eigenschaften in den Settern des `Label`\-Stils auch auf die bereits definierte `MyBrush`\-Ressource verweist.  Es handelt sich dabei um eine gängige Technik. Sie sollten jedoch nicht vergessen, dass Ressourcen analysiert und in der ihnen zugewiesenen Reihenfolge in ein Ressourcenwörterbuch eingegeben werden.  Ressourcen werden auch in der Reihenfolge angefordert, in der sie im Wörterbuch gefunden werden, wenn Sie mit [StaticResource\-Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) aus einer anderen Ressource auf sie verweisen.  Stellen Sie sicher, dass jede Ressource, auf die Sie verweisen, bereits zuvor in der Ressourcenauflistung definiert sein muss, bevor sie angefordert wird.  Sie können diese strenge Erstellungsreihenfolge der Ressourcenverweise ggf. umgehen, indem Sie stattdessen mit [DynamicResource\-Markuperweiterung](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) zur Laufzeit auf die Ressource verweisen. Diese DynamicResource\-Technik wirkt sich jedoch auf die Leistung aus.  Weitere Informationen finden Sie unter [XAML\-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 [!code-xml[FEResource#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]  
  
## Siehe auch  
 [XAML\-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)