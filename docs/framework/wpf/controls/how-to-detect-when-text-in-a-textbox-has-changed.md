---
title: 'Vorgehensweise: Erkennen von Änderungen an Text in einem Textfeld'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
ms.openlocfilehash: 8c7744e9e61b8ba796802e54435c0bf9fdbee50e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855623"
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a><span data-ttu-id="cf070-102">Vorgehensweise: Erkennen von Änderungen an Text in einem Textfeld</span><span class="sxs-lookup"><span data-stu-id="cf070-102">How to: Detect When Text in a TextBox Has Changed</span></span>

<span data-ttu-id="cf070-103">Dieses Beispiel zeigt eine Möglichkeit, mit dem <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> -Ereignis eine Methode auszuführen, wenn sich der Text <xref:System.Windows.Controls.TextBox> in einem-Steuerelement geändert hat.</span><span class="sxs-lookup"><span data-stu-id="cf070-103">This example shows one way to use the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event to execute a method whenever the text in a <xref:System.Windows.Controls.TextBox> control has changed.</span></span>

<span data-ttu-id="cf070-104">Fügen Sie in der Code Behind-Klasse [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] für den, <xref:System.Windows.Controls.TextBox> der das Steuerelement enthält, das Sie auf Änderungen überwachen möchten, eine Methode <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> ein, die aufgerufen werden soll, wenn das Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="cf070-104">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="cf070-105">Diese Methode muss über eine Signatur verfügen, die mit dem <xref:System.Windows.Controls.TextChangedEventHandler> , was vom Delegaten erwartet wird, übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="cf070-105">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>

<span data-ttu-id="cf070-106">Der Ereignishandler wird immer dann aufgerufen, wenn der <xref:System.Windows.Controls.TextBox> Inhalt des Steuer Elements geändert wird, entweder durch einen Benutzer oder Programm gesteuert.</span><span class="sxs-lookup"><span data-stu-id="cf070-106">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>

> [!NOTE]
> <span data-ttu-id="cf070-107">Dieses Ereignis wird ausgelöst, <xref:System.Windows.Controls.TextBox> wenn das Steuerelement erstellt und anfänglich mit Text aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="cf070-107">This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>

## <a name="example"></a><span data-ttu-id="cf070-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cf070-108">Example</span></span>

<span data-ttu-id="cf070-109">Geben Sie [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] <xref:System.Windows.Controls.TextBox> in der, die das Steuerelement <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> definiert, das-Attribut mit einem Wert an, der mit dem Namen der Ereignishandlermethode</span><span class="sxs-lookup"><span data-stu-id="cf070-109">In the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that defines your <xref:System.Windows.Controls.TextBox> control, specify the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> attribute with a value that matches the event handler method name.</span></span>

[!code-xaml[TextBox_MiscCode#_TextChangedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]

## <a name="example"></a><span data-ttu-id="cf070-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cf070-110">Example</span></span>

<span data-ttu-id="cf070-111">Fügen Sie in der Code Behind-Klasse [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] für den, <xref:System.Windows.Controls.TextBox> der das Steuerelement enthält, das Sie auf Änderungen überwachen möchten, eine Methode <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> ein, die aufgerufen werden soll, wenn das Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="cf070-111">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="cf070-112">Diese Methode muss über eine Signatur verfügen, die mit dem <xref:System.Windows.Controls.TextChangedEventHandler> , was vom Delegaten erwartet wird, übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="cf070-112">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>

[!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
[!code-vb[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]

<span data-ttu-id="cf070-113">Der Ereignishandler wird immer dann aufgerufen, wenn der <xref:System.Windows.Controls.TextBox> Inhalt des Steuer Elements geändert wird, entweder durch einen Benutzer oder Programm gesteuert.</span><span class="sxs-lookup"><span data-stu-id="cf070-113">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>

> [!NOTE]
> <span data-ttu-id="cf070-114">Dieses Ereignis wird ausgelöst, <xref:System.Windows.Controls.TextBox> wenn das Steuerelement erstellt und anfänglich mit Text aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="cf070-114">This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>

<span data-ttu-id="cf070-115">Kommentare</span><span class="sxs-lookup"><span data-stu-id="cf070-115">Comments</span></span>

## <a name="see-also"></a><span data-ttu-id="cf070-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf070-116">See also</span></span>

- <xref:System.Windows.Controls.TextChangedEventArgs>
- [<span data-ttu-id="cf070-117">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="cf070-117">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="cf070-118">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="cf070-118">RichTextBox Overview</span></span>](richtextbox-overview.md)
