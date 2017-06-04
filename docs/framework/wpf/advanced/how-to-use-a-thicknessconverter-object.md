---
title: "Gewusst wie: Verwenden eines ThicknessConverter-Objekts | Microsoft Docs"
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
  - "Rahmenstärke"
  - "ThicknessConverter-Objekt"
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Verwenden eines ThicknessConverter-Objekts
## Beispiel  
 In diesem Beispiel wird erläutert, wie eine Instanz von <xref:System.Windows.ThicknessConverter> erstellt und zum Ändern der Stärke eines Rahmens verwendet wird.  
  
 In diesem Beispiel wird eine benutzerdefinierte Methode mit dem Namen `changeThickness` definiert, die zuerst die Inhalte von einem <xref:System.Windows.Controls.ListBoxItem> \(in einer separaten [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Datei definiert\) in eine Instanz von <xref:System.Windows.Thickness> und anschließend die Inhalte in einen <xref:System.String> konvertiert.  Durch diese Methode wird das <xref:System.Windows.Controls.ListBoxItem> an ein <xref:System.Windows.ThicknessConverter>\-Objekt weitergeleitet, das den <xref:System.Windows.Controls.ContentControl.Content%2A> eines <xref:System.Windows.Controls.ListBoxItem> in eine Instanz von <xref:System.Windows.Thickness> konvertiert.  Dieser Wert wird dann als Wert der <xref:System.Windows.Controls.Border.BorderThickness%2A>\-Eigenschaft vom <xref:System.Windows.Controls.Border> zurückgegeben.  
  
 Dieses Beispiel wird nicht ausgeführt.  
  
 [!code-csharp[ThicknessConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## Siehe auch  
 <xref:System.Windows.Thickness>   
 <xref:System.Windows.ThicknessConverter>   
 <xref:System.Windows.Controls.Border>   
 [How to: Change the Margin Property](http://msdn.microsoft.com/de-de/8a313efd-5f99-4097-b4c1-8fa49d8379a2)   
 [How to: Convert a ListBoxItem to a new Data Type](http://msdn.microsoft.com/de-de/7a080b88-184e-4b27-bb61-d42bafba9727)   
 [Übersicht über Panel\-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)