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
ms.openlocfilehash: 408d48856362fa8a77a44e2cc97cb2d5ff608dcf
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046354"
---
# <a name="how-to-open-a-file-that-is-dropped-on-a-richtextbox-control"></a>Vorgehensweise: Öffnen einer Datei, die auf einem RichTextBox-Steuerelement abgelegt ist

In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]verfügen die <xref:System.Windows.Controls.TextBox>Steuer <xref:System.Windows.Controls.RichTextBox>Elemente, <xref:System.Windows.Documents.FlowDocument> und über integrierte Drag & amp; Drop-Funktionen. Die integrierte Funktionalität ermöglicht das Drag & Drop von Text innerhalb von und zwischen den Steuerelementen. Es ist jedoch nicht möglich, eine Datei zu öffnen, indem Sie die Datei auf dem Steuerelement ablegen. Diese Steuerelemente markieren auch die Drag & Drop-Ereignisse als behandelt. Daher können Sie standardmäßig keine eigenen Ereignishandler hinzufügen, um Funktionen zum Öffnen von gelöschten Dateien bereitzustellen.

Wenn Sie zusätzliche Behandlung für Drag & Drop-Ereignisse in diesen Steuerelementen hinzufügen möchten <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> , verwenden Sie die-Methode, um die Ereignishandler für die Drag & amp; Drop-Ereignisse hinzuzufügen. Legen Sie `handledEventsToo` den- `true` Parameter auf fest, damit der angegebene Handler für ein Routing Ereignis aufgerufen wird, das bereits von einem anderen Element auf der Ereignis Route als behandelt markiert wurde.

> [!TIP]
> Sie können die integrierte Drag & amp; Drop-Funktion von <xref:System.Windows.Controls.TextBox>, und <xref:System.Windows.Documents.FlowDocument> ersetzen <xref:System.Windows.Controls.RichTextBox>, indem Sie die Vorschau Versionen der Drag & Drop-Ereignisse behandeln und die Vorschau Ereignisse als behandelt markieren. Dadurch werden jedoch die integrierten Drag & amp; Drop-Funktionen deaktiviert, was nicht empfohlen wird.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie Handler für das- <xref:System.Windows.DragDrop.DragOver> Ereignis <xref:System.Windows.DragDrop.Drop> und das- <xref:System.Windows.Controls.RichTextBox>Ereignis in einem hinzugefügt werden. In diesem Beispiel wird <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> die-Methode verwendet `handledEventsToo` und der `true` -Parameter auf festgelegt, sodass die Ereignis <xref:System.Windows.Controls.RichTextBox> Handler aufgerufen werden, auch wenn diese Ereignisse als behandelt markieren. Der Code in den-Ereignis Handlern fügt Funktionen hinzu, um eine Textdatei zu öffnen, <xref:System.Windows.Controls.RichTextBox>die in gelöscht wird.

Um dieses Beispiel zu testen, ziehen Sie eine Textdatei oder eine RTF-Datei (Rich Textformat) aus Windows <xref:System.Windows.Controls.RichTextBox>-Explorer in das. Die Datei wird im <xref:System.Windows.Controls.RichTextBox>geöffnet. Wenn Sie die UMSCHALTTASTE drücken, bevor Sie die Datei ablegen, wird die Datei als Klartext geöffnet.

[!code-xaml[DragDropSnippets#RtbXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]

[!code-csharp[DragDropSnippets#RtbHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
[!code-vb[DragDropSnippets#RtbHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]
