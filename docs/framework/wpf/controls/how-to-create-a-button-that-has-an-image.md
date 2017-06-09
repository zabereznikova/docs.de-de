---
title: "Gewusst wie: Erstellen einer Schaltfl&#228;che mit einem Bild | Microsoft Docs"
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
  - "Button-Steuerelemente [WPF], Erstellen"
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Erstellen einer Schaltfl&#228;che mit einem Bild
In diesem Beispiel ist dargestellt, wie ein Bild in ein <xref:System.Windows.Controls.Button>\-Steuerelement eingebunden wird.  
  
## Beispiel  
 Im folgenden Beispiel werden zwei <xref:System.Windows.Controls.Button>\-Steuerelemente erstellt.  Eines der <xref:System.Windows.Controls.Button>\-Steuerelemente enthält Text, das andere ein Bild.  Das Bild befindet sich in einem Ordner mit dem Namen "data", der ein Unterordner des Projektordners des Beispiels ist.  Wenn der Benutzer auf das <xref:System.Windows.Controls.Button>\-Steuerelement mit dem Bild klickt, ändert sich der Hintergrund und der Text des anderen <xref:System.Windows.Controls.Button>\-Steuerelements.  
  
 In diesem Beispiel werden <xref:System.Windows.Controls.Button>\-Steuerelemente unter Verwendung von Markup erstellt, zum Schreiben der <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignishandler wird jedoch Code verwendet.  
  
 [!code-xml[BtnColor#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## Siehe auch  
 [Steuerelemente](../../../../docs/framework/wpf/controls/index.md)   
 [Steuerelementbibliothek](../../../../docs/framework/wpf/controls/control-library.md)