---
title: "Gewusst wie: Programmgesteuertes &#196;ndern der TextWrapping-Eigenschaft | Microsoft Docs"
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
  - "Dokumente, Programmgesteuertes Ändern der TextWrapping-Eigenschaft"
  - "TextWrapping-Eigenschaft, Programmgesteuertes Ändern"
ms.assetid: 30d25554-4c82-4df9-a8d6-35683a4a13bb
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Programmgesteuertes &#196;ndern der TextWrapping-Eigenschaft
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie der Wert der <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>\-Eigenschaft programmgesteuert geändert wird.  
  
 Drei <xref:System.Windows.Controls.Button>\-Elemente werden innerhalb eines <xref:System.Windows.Controls.StackPanel>\-Elements in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] eingefügt. Jedes <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignis für eine <xref:System.Windows.Controls.Button> entspricht einem Ereignishandler im Code.  Die Ereignishandler verwenden den gleichen Namen wie der <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>\-Wert, den sie auf `txt2` anwenden, wenn auf die Schaltfläche geklickt wird.  Außerdem wird der Text in `txt1`\(ein <xref:System.Windows.Controls.TextBlock>\-Element, das im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] nicht angezeigt wird\) aktualisiert, um die Änderung in der Eigenschaft zu reflektieren.  
  
 [!code-xml[TextWrapProperty#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml#1)]  
  
 [!code-csharp[TextWrapProperty#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextWrapProperty/CSharp/Window1.xaml.cs#2)]
 [!code-vb[TextWrapProperty#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml.vb#2)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>   
 <xref:System.Windows.TextWrapping>