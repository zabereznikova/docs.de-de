---
title: "Gewusst wie: &#214;ffnen einer Datei, die auf einem RichTextBox-Steuerelement abgelegt ist | Microsoft Docs"
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
  - "Drag & Drop [WPF], Öffnen einer abgelegten Datei"
  - "Drag & Drop [WPF], RichTextBox"
  - "RichTextBox [WPF], Drag &amp; Drop"
ms.assetid: 6bb8bb54-f576-41db-a9a7-24102ddeb490
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: &#214;ffnen einer Datei, die auf einem RichTextBox-Steuerelement abgelegt ist
In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] verfügen die <xref:System.Windows.Controls.TextBox>\-, <xref:System.Windows.Controls.RichTextBox>\- und <xref:System.Windows.Documents.FlowDocument>\-Steuerelemente über eine integrierte Drag & Drop\-Funktion.  Die integrierte Funktion ermöglicht das Drag & Drop von Text in und zwischen den Steuerelementen.  Es ist jedoch nicht möglich, eine Datei durch Ablegen auf dem Steuerelement zu öffnen.  Diese Steuerelemente markieren auch die Drag & Drop\-Ereignisse als behandelt.  Daher können Sie standardmäßig keine eigenen Ereignishandler hinzufügen, um Funktionen zum Öffnen abgelegter Dateien bereitzustellen.  
  
 Um eine zusätzliche Behandlung für Drag & Drop\-Ereignisse in diesen Steuerelementen hinzuzufügen, fügen Sie die Ereignishandler für die Drag & Drop\-Ereignisse mithilfe der <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29>\-Methode hinzu.  Legen Sie den `handledEventsToo`\-Parameter auf `true` fest, damit der angegebene Handle für ein Routingereignis aufgerufen wird, das bereits von einem anderen Element auf der Ereignisroute als behandelt markiert wurde.  
  
> [!TIP]
>  Sie können die integrierte Drag & Drop\-Funktion von <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox> und <xref:System.Windows.Documents.FlowDocument> ersetzen, indem Sie die Vorschauversionen der Drag & Drop\-Ereignisse behandeln und die Vorschauereignisse als behandelt markieren.  Da dadurch jedoch die integrierte Drag & Drop\-Funktion deaktiviert wird, wird diese Vorgehensweise nicht empfohlen.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie Handler für die <xref:System.Windows.DragDrop.Drop>\- und <xref:System.Windows.DragDrop.DragOver>\-Ereignisse eines <xref:System.Windows.Controls.RichTextBox> hinzugefügt werden.  In diesem Beispiel wird die <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29>\-Methode verwendet und der `handledEventsToo`\-Parameter auf `true` festgelegt, sodass die Ereignishandler aufgerufen werden, obwohl das <xref:System.Windows.Controls.RichTextBox> diese Ereignisse als behandelt markiert.  Durch den Code in den Ereignishandlern werden Funktionen zum Öffnen einer auf dem <xref:System.Windows.Controls.RichTextBox> abgelegten Textdatei hinzugefügt.  
  
 Um dieses Beispiel zu testen, ziehen Sie eine Textdatei oder eine RTF\-Datei von Windows\-Explorer auf das <xref:System.Windows.Controls.RichTextBox>.  Die Datei wird im <xref:System.Windows.Controls.RichTextBox> geöffnet.  Wenn Sie die UMSCHALTTASTE vor dem Ablegen der Datei drücken, wird die Datei als Nur\-Text geöffnet.  
  
 [!code-xml[DragDropSnippets#RtbXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]  
  
 [!code-csharp[DragDropSnippets#RtbHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
 [!code-vb[DragDropSnippets#RtbHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]