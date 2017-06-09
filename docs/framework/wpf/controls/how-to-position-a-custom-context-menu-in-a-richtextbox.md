---
title: "Gewusst wie: Positionieren eines benutzerdefinierten Kontextmen&#252;s in einem &quot;RichTextBox&quot;-Element | Microsoft Docs"
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
  - "Positionieren von benutzerdefinierten Kontextmenüs"
  - "Positionieren von benutzerdefinierten Kontextmenüs"
  - "Positionieren von benutzerdefinierten Kontextmenüs RichTextBox-Steuerelement"
  - "Positionieren von Kontextmenüs"
ms.assetid: bf77c930-a546-4573-9a56-9af345ba189a
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Positionieren eines benutzerdefinierten Kontextmen&#252;s in einem &quot;RichTextBox&quot;-Element
Dieses Beispiel zeigt das Positionieren eines benutzerdefinierten Kontextmenüs für ein <xref:System.Windows.Controls.RichTextBox>.  
  
 Bei der Implementierung eines benutzerdefinierten Kontextmenüs für ein **RichTextBox**, Sie sind verantwortlich für die Behandlung der Positionierung des Kontextmenüs.  Standardmäßig wird ein benutzerdefiniertes Kontextmenü geöffnet, in der Mitte des der **RichTextBox**.  
  
## <a name="example"></a>Beispiel  
 Um das Standardverhalten für die Platzierung außer Kraft setzen, fügen Sie einen Listener für die <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> Ereignis.  Im folgenden Beispiel wird veranschaulicht, wie zur entsprechenden programmgesteuerten Vorgehensweise.  
  
 [!code-csharp[RichTextBox_ContextMenu#_AddListener](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_addlistener)]
 [!code-vb[RichTextBox_ContextMenu#_AddListener](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_addlistener)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt einer Implementierung der entsprechenden <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> Ereignis-Listener.  
  
 [!code-csharp[RichTextBox_ContextMenu#_ListenerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_listenerbody)]
 [!code-vb[RichTextBox_ContextMenu#_ListenerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_listenerbody)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)   
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)