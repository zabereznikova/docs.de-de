---
title: "Gewusst wie: Positionieren des Cursors am Anfang oder Ende von Text in einem &quot;TextBox&quot;-Steuerelement | Microsoft Docs"
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
  - "Positionieren des Cursors"
  - "TextBox-Steuerelement, Positionieren des Cursors"
  - "Cursor, Positionierung"
ms.assetid: c771a0b8-c6b4-4240-aecd-a21d0ba51a2e
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Positionieren des Cursors am Anfang oder Ende von Text in einem &quot;TextBox&quot;-Steuerelement
In diesem Beispiel wird veranschaulicht, wie zur Positionierung des Cursors am Anfang oder Ende des Textinhalts einer <xref:System.Windows.Controls.TextBox> Steuerelement.  
  
## <a name="example"></a>Beispiel  
 Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Code beschreibt einen <xref:System.Windows.Controls.TextBox> steuern und weist ihr einen Namen.  
  
 [!code-xml[TextBox_MiscCode#_MoveCursorXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_movecursorxaml)]  
  
## <a name="example"></a>Beispiel  
 Zur Positionierung des Cursors am Anfang des Inhalts einer <xref:System.Windows.Controls.TextBox> steuern, rufen Sie die <xref:System.Windows.Controls.TextBox.Select%2A> Methode und geben Sie die Auswahl Position 0 und eine Auswahllänge von 0.  
  
 [!code-csharp[TextBox_MiscCode#_CursorToStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortostart)]
 [!code-vb[TextBox_MiscCode#_CursorToStart](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortostart)]  
  
## <a name="example"></a>Beispiel  
 Positionieren Sie den Cursor am Ende des Inhalts eine <xref:System.Windows.Controls.TextBox> steuern, rufen Sie die <xref:System.Windows.Controls.TextBox.Select%2A> Methode und geben den Wert an, der die Länge des Textinhalts 0 Anfangsposition.  
  
 [!code-csharp[TextBox_MiscCode#_CursorToEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortoend)]
 [!code-vb[TextBox_MiscCode#_CursorToEnd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortoend)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)