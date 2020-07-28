---
title: 'Gewusst wie: Erkennen von Änderungen an Text in einem Textfeld'
description: Erfahren Sie, wie Sie mit dem TextChanged-Ereignis eine Methode ausführen, wenn sich der Text in einem TextBox-Steuerelement in einer Windows Presentation Foundation Anwendung ändert.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
ms.openlocfilehash: 1e054380a8c77d32e6bb4adbbcb032e531bbefd0
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166221"
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a><span data-ttu-id="8d531-103">Gewusst wie: Erkennen von Änderungen an Text in einem Textfeld</span><span class="sxs-lookup"><span data-stu-id="8d531-103">How to: Detect When Text in a TextBox Has Changed</span></span>

<span data-ttu-id="8d531-104">Dieses Beispiel zeigt eine Möglichkeit, mit dem- <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> Ereignis eine Methode auszuführen, wenn sich der Text in einem- <xref:System.Windows.Controls.TextBox> Steuerelement geändert hat.</span><span class="sxs-lookup"><span data-stu-id="8d531-104">This example shows one way to use the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event to execute a method whenever the text in a <xref:System.Windows.Controls.TextBox> control has changed.</span></span>

<span data-ttu-id="8d531-105">Fügen Sie in der Code Behind-Klasse für den [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , der das Steuerelement enthält, <xref:System.Windows.Controls.TextBox> das Sie auf Änderungen überwachen möchten, eine Methode ein, die aufgerufen werden soll, wenn das Ereignis ausgelöst wird <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> .</span><span class="sxs-lookup"><span data-stu-id="8d531-105">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="8d531-106">Diese Methode muss über eine Signatur verfügen, die mit dem, was vom Delegaten erwartet wird, übereinstimmt <xref:System.Windows.Controls.TextChangedEventHandler> .</span><span class="sxs-lookup"><span data-stu-id="8d531-106">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>

<span data-ttu-id="8d531-107">Der Ereignishandler wird immer dann aufgerufen, wenn der Inhalt des <xref:System.Windows.Controls.TextBox> Steuer Elements geändert wird, entweder durch einen Benutzer oder Programm gesteuert.</span><span class="sxs-lookup"><span data-stu-id="8d531-107">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>

> [!NOTE]
> <span data-ttu-id="8d531-108">Dieses Ereignis wird ausgelöst, wenn das <xref:System.Windows.Controls.TextBox> Steuerelement erstellt und anfänglich mit Text aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="8d531-108">This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>

## <a name="example"></a><span data-ttu-id="8d531-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8d531-109">Example</span></span>

<span data-ttu-id="8d531-110">Geben Sie in der, die das [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Steuerelement definiert <xref:System.Windows.Controls.TextBox> , das- <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> Attribut mit einem Wert an, der mit dem Namen der Ereignishandlermethode</span><span class="sxs-lookup"><span data-stu-id="8d531-110">In the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that defines your <xref:System.Windows.Controls.TextBox> control, specify the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> attribute with a value that matches the event handler method name.</span></span>

[!code-xaml[TextBox_MiscCode#_TextChangedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]

## <a name="example"></a><span data-ttu-id="8d531-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8d531-111">Example</span></span>

<span data-ttu-id="8d531-112">Fügen Sie in der Code Behind-Klasse für den [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , der das Steuerelement enthält, <xref:System.Windows.Controls.TextBox> das Sie auf Änderungen überwachen möchten, eine Methode ein, die aufgerufen werden soll, wenn das Ereignis ausgelöst wird <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> .</span><span class="sxs-lookup"><span data-stu-id="8d531-112">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="8d531-113">Diese Methode muss über eine Signatur verfügen, die mit dem, was vom Delegaten erwartet wird, übereinstimmt <xref:System.Windows.Controls.TextChangedEventHandler> .</span><span class="sxs-lookup"><span data-stu-id="8d531-113">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>

[!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
[!code-vb[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]

<span data-ttu-id="8d531-114">Der Ereignishandler wird immer dann aufgerufen, wenn der Inhalt des <xref:System.Windows.Controls.TextBox> Steuer Elements geändert wird, entweder durch einen Benutzer oder Programm gesteuert.</span><span class="sxs-lookup"><span data-stu-id="8d531-114">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>

> [!NOTE]
> <span data-ttu-id="8d531-115">Dieses Ereignis wird ausgelöst, wenn das <xref:System.Windows.Controls.TextBox> Steuerelement erstellt und anfänglich mit Text aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="8d531-115">This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>

<span data-ttu-id="8d531-116">Kommentare</span><span class="sxs-lookup"><span data-stu-id="8d531-116">Comments</span></span>

## <a name="see-also"></a><span data-ttu-id="8d531-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d531-117">See also</span></span>

- <xref:System.Windows.Controls.TextChangedEventArgs>
- [<span data-ttu-id="8d531-118">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="8d531-118">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="8d531-119">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="8d531-119">RichTextBox Overview</span></span>](richtextbox-overview.md)
