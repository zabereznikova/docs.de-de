---
title: 'Gewusst wie: Positionieren des Cursors am Anfang oder Ende von Text in einem "TextBox"-Steuerelement'
description: Erfahren Sie, wie Sie den Cursor am Anfang oder Ende des Text Inhalts eines Windows Presentation Foundation TextBox-Steuer Elements positionieren.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- positioning cursor [WPF]
- TextBox control [WPF], positioning cursor
- cursor [WPF], positioning
ms.assetid: c771a0b8-c6b4-4240-aecd-a21d0ba51a2e
ms.openlocfilehash: afe8b11d032b5d61fa91cbf324f02cd8415d2ea8
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167511"
---
# <a name="how-to-position-the-cursor-at-the-beginning-or-end-of-text-in-a-textbox-control"></a>Gewusst wie: Positionieren des Cursors am Anfang oder Ende von Text in einem "TextBox"-Steuerelement
In diesem Beispiel wird gezeigt, wie der Cursor am Anfang oder Ende des Text Inhalts eines-Steuer Elements positioniert wird <xref:System.Windows.Controls.TextBox> .  
  
## <a name="example"></a>Beispiel  
 Der folgende [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Code beschreibt ein <xref:System.Windows.Controls.TextBox> -Steuerelement und weist ihm einen Namen zu.  
  
 [!code-xaml[TextBox_MiscCode#_MoveCursorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_movecursorxaml)]  
  
## <a name="example"></a>Beispiel  
 Um den Cursor am Anfang des Inhalts eines-Steuer Elements zu positionieren, müssen Sie <xref:System.Windows.Controls.TextBox> die <xref:System.Windows.Controls.TextBox.Select%2A> -Methode und die Startposition der Auswahl 0 und eine Auswahl Länge von 0 (null) angeben.  
  
 [!code-csharp[TextBox_MiscCode#_CursorToStart](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortostart)]
 [!code-vb[TextBox_MiscCode#_CursorToStart](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortostart)]  
  
## <a name="example"></a>Beispiel  
 Um den Cursor am Ende des Inhalts eines-Steuer Elements zu positionieren, müssen Sie <xref:System.Windows.Controls.TextBox> die <xref:System.Windows.Controls.TextBox.Select%2A> -Methode und die Startposition der Auswahl gleich der Länge des Text Inhalts und eine Auswahl Länge von 0 (null) angeben.  
  
 [!code-csharp[TextBox_MiscCode#_CursorToEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortoend)]
 [!code-vb[TextBox_MiscCode#_CursorToEnd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortoend)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über TextBox](textbox-overview.md)
- [Übersicht über RichTextBox](richtextbox-overview.md)
