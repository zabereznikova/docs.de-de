---
title: 'Vorgehensweise: Öffnen einer Datei, die auf einem RichTextBox-Steuerelement abgelegt ist'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], RichTextBox
- RichTextBox [WPF], drag-and-drop
- drag-and-drop [WPF], open a dropped file
ms.assetid: 6bb8bb54-f576-41db-a9a7-24102ddeb490
ms.openlocfilehash: 8ffa4c9919788060dc4524e127c181ee8282e6f9
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378914"
---
# <a name="how-to-open-a-file-that-is-dropped-on-a-richtextbox-control"></a>Vorgehensweise: Öffnen einer Datei, die auf einem RichTextBox-Steuerelement abgelegt ist
In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, und <xref:System.Windows.Documents.FlowDocument> steuert den gesamten haben integrierte Drag & Drop-Funktionalität. Die integrierte Funktionen kann Drag & Drop von Text innerhalb und zwischen den Steuerelementen. Es wird jedoch nicht aktiviert das Öffnen einer Datei durch die Datei auf das Steuerelement ablegen. Diese Steuerelemente werden auch die Drag & Drop-Ereignisse als behandelt markieren. Standardmäßig können nicht Sie daher Ihre eigenen Ereignishandler, um Funktionen zum Öffnen von gelöschter Dateien bereitzustellen hinzufügen.  
  
 Verwenden Sie zum Hinzufügen zusätzlichen Schritt für Drag & Drop-Ereignisse in diesen Steuerelementen die <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> Methode, um Ihre Ereignishandler für die Drag & Drop-Ereignisse hinzuzufügen. Legen Sie die `handledEventsToo` Parameter `true` fest, damit der angegebene Handler für ein Routingereignis aufgerufen werden, die bereits von einem anderen Element auf der Ereignisroute als behandelt markiert wurde.  
  
> [!TIP]
>  Sie können die integrierte Drag & Drop-Funktionalität von ersetzen <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, und <xref:System.Windows.Documents.FlowDocument> durch die Preview-Versionen der Drag & Drop-Ereignisse behandeln, und markieren die Vorschauereignisse als behandelt. Aber dies wird die integrierte Drag & Drop-Funktionalität deaktiviert, und wird nicht empfohlen.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, wie Hinzufügen von Ereignishandlern für die <xref:System.Windows.DragDrop.DragOver> und <xref:System.Windows.DragDrop.Drop> Ereignisse auf einer <xref:System.Windows.Controls.RichTextBox>. Dieses Beispiel verwendet die <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> -Methode und legt die `handledEventsToo` Parameter, um `true` , damit die Ereignishandler, obwohl aufgerufen werden, die <xref:System.Windows.Controls.RichTextBox> kennzeichnet diese Ereignisse behandelt. Der Code in den Ereignishandlern über zusätzliche Funktionen zum Öffnen einer Textdatei, die auf abgelegt wird die <xref:System.Windows.Controls.RichTextBox>.  
  
 Zum Testen dieses Beispiels, ziehen Sie eine Textdatei oder eine rich-Text-Format (RTF)-Datei aus Windows Explorer, um die <xref:System.Windows.Controls.RichTextBox>. Die Datei wird geöffnet werden, der <xref:System.Windows.Controls.RichTextBox>. Drücken Sie die UMSCHALTTASTE vor dem Ablegen der Datei, die Datei wird als nur-Text geöffnet werden.  
  
 [!code-xaml[DragDropSnippets#RtbXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]  
  
 [!code-csharp[DragDropSnippets#RtbHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
 [!code-vb[DragDropSnippets#RtbHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]
