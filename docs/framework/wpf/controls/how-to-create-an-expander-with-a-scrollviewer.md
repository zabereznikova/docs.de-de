---
title: "Gewusst wie: Erstellen eines Expanders mit einem ScrollViewer | Microsoft Docs"
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
  - "Steuerelemente [WPF], Expander"
  - "Steuerelemente [WPF], ScrollViewer"
  - "Expander-Steuerelement, Erstellen"
  - "ScrollViewer-Steuerelement, Mit Expander-Steuerelement"
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Erstellen eines Expanders mit einem ScrollViewer
In diesem Beispiel wird das Erstellen eines <xref:System.Windows.Controls.Expander>\-Steuerelements veranschaulicht, das komplexen Inhalt, etwa ein Bild und Text, enthält.  Dieses Beispiel enthält auch den Inhalt vom <xref:System.Windows.Controls.Expander> in einem <xref:System.Windows.Controls.ScrollViewer>\-Steuerelement.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie einen <xref:System.Windows.Controls.Expander> erstellen.  Im Beispiel wird ein <xref:System.Windows.Controls.Primitives.BulletDecorator>\-Steuerelement verwendet, das ein Bild und Text enthält, um den <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> zu definieren.  Ein <xref:System.Windows.Controls.ScrollViewer>\-Steuerelement stellt eine Methode bereit, mit der Sie einen Bildlauf durch den erweiterten Inhalt durchführen können.  
  
 Beachten Sie, dass im Beispiel die <xref:System.Windows.FrameworkElement.Height%2A>\-Eigenschaft für den <xref:System.Windows.Controls.ScrollViewer>, nicht für den Inhalt festgelegt wird.  Wenn die <xref:System.Windows.FrameworkElement.Height%2A> für den Inhalt festgelegt wird, kann der Benutzer mit dem <xref:System.Windows.Controls.ScrollViewer> keinen Bildlauf durch den Inhalt durchführen.  Die <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft wird für das <xref:System.Windows.Controls.Expander>\-Steuerelement festgelegt, und diese Einstellung gilt für den <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> und den erweiterten Inhalt.  
  
 [!code-xml[ExpanderRichContent#CreateExpander](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.Expander>   
 [Übersicht über Expander\-Steuerelemente](../../../../docs/framework/wpf/controls/expander-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)