---
title: "Gewusst wie: Öffnen einer Datei, die auf einem RichTextBox-Steuerelement abgelegt ist"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], RichTextBox
- RichTextBox [WPF], drag-and-drop
- drag-and-drop [WPF], open a dropped file
ms.assetid: 6bb8bb54-f576-41db-a9a7-24102ddeb490
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7dfb5f0f442b18159c18a6e5345f6757674fbb90
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-open-a-file-that-is-dropped-on-a-richtextbox-control"></a><span data-ttu-id="a25b2-102">Gewusst wie: Öffnen einer Datei, die auf einem RichTextBox-Steuerelement abgelegt ist</span><span class="sxs-lookup"><span data-stu-id="a25b2-102">How to: Open a File That is Dropped on a RichTextBox Control</span></span>
<span data-ttu-id="a25b2-103">In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, und <xref:System.Windows.Documents.FlowDocument> steuert den gesamten über integrierte Drag-and-Drop-Funktionalität verfügen.</span><span class="sxs-lookup"><span data-stu-id="a25b2-103">In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], the <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, and <xref:System.Windows.Documents.FlowDocument> controls all have built-in drag-and-drop functionality.</span></span> <span data-ttu-id="a25b2-104">Die integrierte Funktion ermöglicht die Drag & Drop von Text innerhalb und zwischen den Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="a25b2-104">The built-in functionality enables drag-and-drop of text within and between the controls.</span></span> <span data-ttu-id="a25b2-105">Es wird jedoch nicht aktiviert das Öffnen einer Datei durch das Löschen der Datei auf das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a25b2-105">However, it does not enable opening a file by dropping the file on the control.</span></span> <span data-ttu-id="a25b2-106">Diese Steuerelemente werden auch die Drag & Drop-Ereignisse als behandelt markiert.</span><span class="sxs-lookup"><span data-stu-id="a25b2-106">These controls also mark the drag-and-drop events as handled.</span></span> <span data-ttu-id="a25b2-107">Standardmäßig können nicht Sie daher Ihren eigenen--Ereignishandler, um die Funktionalität zum Öffnen von abgelegten Dateien hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a25b2-107">As a result, by default, you cannot add your own event handlers to provide functionality to open dropped files.</span></span>  
  
 <span data-ttu-id="a25b2-108">Verwenden Sie zum Hinzufügen zusätzlichen Schritt für Drag & Drop-Ereignisse in diesen Steuerelementen die <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> Methode, um die Ereignishandler für die Drag & Drop-Ereignisse hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a25b2-108">To add additional handling for drag-and-drop events in these controls, use the <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> method to add your event handlers for the drag-and-drop events.</span></span> <span data-ttu-id="a25b2-109">Legen Sie die `handledEventsToo` Parameter `true` fest, damit der angegebene Handler für ein Routingereignis aufgerufen werden, die bereits von einem anderen Element auf der Ereignisroute als behandelt markiert wurde.</span><span class="sxs-lookup"><span data-stu-id="a25b2-109">Set the `handledEventsToo` parameter to `true` to have the specified handler be invoked for a routed event that has already been marked as handled by another element along the event route.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="a25b2-110">Sie können die integrierte Drag-and-Drop-Funktionalität der ersetzen <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, und <xref:System.Windows.Documents.FlowDocument> durch die Preview-Versionen der Drag & Drop-Ereignisse behandeln, und markieren die Vorschauereignisse als behandelt.</span><span class="sxs-lookup"><span data-stu-id="a25b2-110">You can replace the built-in drag-and-drop functionality of <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, and <xref:System.Windows.Documents.FlowDocument> by handling the preview versions of the drag-and-drop events and marking the preview events as handled.</span></span> <span data-ttu-id="a25b2-111">Allerdings wird die integrierte Drag-and-Drop-Funktionalität deaktiviert, es wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="a25b2-111">However, this will disable the built-in drag-and-drop functionality, and is not recommended.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a25b2-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a25b2-112">Example</span></span>  
 <span data-ttu-id="a25b2-113">Im folgenden Beispiel wird veranschaulicht, wie das hinzuzufügende Handler für das <xref:System.Windows.DragDrop.DragOver> und <xref:System.Windows.DragDrop.Drop> Ereignisse auf einem <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="a25b2-113">The following example demonstrates how to add handlers for the <xref:System.Windows.DragDrop.DragOver> and <xref:System.Windows.DragDrop.Drop> events on a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="a25b2-114">Dieses Beispiel verwendet die <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> -Methode und legt die `handledEventsToo` Parameter `true` so, dass, obwohl die Ereignishandler aufgerufen werden die <xref:System.Windows.Controls.RichTextBox> diese Ereignisse als behandelt markiert.</span><span class="sxs-lookup"><span data-stu-id="a25b2-114">This example uses the <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> method and sets the `handledEventsToo` parameter to `true` so that the events handlers will be invoked even though the <xref:System.Windows.Controls.RichTextBox> marks these events as handled.</span></span> <span data-ttu-id="a25b2-115">Der Code in den Ereignishandlern fügt Funktionen, um eine Textdatei öffnen, die auf abgelegt wird die <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="a25b2-115">The code in the event handlers adds functionality to open a text file that is dropped on the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="a25b2-116">Ziehen Sie zum Testen dieses Beispiels eine Textdatei oder eine rich-Text-Format (RTF)-Datei von Windows-Explorer, um die <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="a25b2-116">To test this example, drag a text file or a rich text format (RTF) file from Windows Explorer to the <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="a25b2-117">Die Datei wird geöffnet, der <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="a25b2-117">The file will be opened in the <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="a25b2-118">Wenn Sie die UMSCHALT-vor dem Ablegen Taste der Datei, die Datei wird als nur-Text geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="a25b2-118">If you press the SHIFT key before the dropping the file, the file will be opened as plain text.</span></span>  
  
 [!code-xaml[DragDropSnippets#RtbXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]  
  
 [!code-csharp[DragDropSnippets#RtbHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
 [!code-vb[DragDropSnippets#RtbHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]
