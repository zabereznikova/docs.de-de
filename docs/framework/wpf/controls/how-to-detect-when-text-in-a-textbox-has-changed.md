---
title: 'Vorgehensweise: Erkennen von Textänderungen in einem TextBox-Objekt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
ms.openlocfilehash: 1adadb0f071815930d34f40ddf244ffc8c19131b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091147"
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a><span data-ttu-id="d0663-102">Vorgehensweise: Erkennen von Textänderungen in einem TextBox-Objekt</span><span class="sxs-lookup"><span data-stu-id="d0663-102">How to: Detect When Text in a TextBox Has Changed</span></span>
<span data-ttu-id="d0663-103">Dieses Beispiel zeigt eine Möglichkeit zur Verwendung der <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> Ereignis zum Ausführen einer Methode immer den Text in eine <xref:System.Windows.Controls.TextBox> -Steuerelements geändert hat.</span><span class="sxs-lookup"><span data-stu-id="d0663-103">This example shows one way to use the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event to execute a method whenever the text in a <xref:System.Windows.Controls.TextBox> control has changed.</span></span>  
  
 <span data-ttu-id="d0663-104">In der CodeBehind-Klasse für den [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , enthält die <xref:System.Windows.Controls.TextBox> -Steuerelement, das Sie überwachen möchten, Änderungen, fügen Sie eine Methode aufruft, wenn die <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> -Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="d0663-104">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="d0663-105">Diese Methode müssen eine Signatur, die entspricht Erwartungen erfüllt werden die <xref:System.Windows.Controls.TextChangedEventHandler> delegieren.</span><span class="sxs-lookup"><span data-stu-id="d0663-105">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>  
  
 <span data-ttu-id="d0663-106">Der Ereignishandler wird aufgerufen, wenn der Inhalt des der <xref:System.Windows.Controls.TextBox> Steuerelement geändert werden, entweder von einem Benutzer oder programmgesteuert.</span><span class="sxs-lookup"><span data-stu-id="d0663-106">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>  
  
 <span data-ttu-id="d0663-107">**Hinweis**: Dieses Ereignis wird ausgelöst, wenn die <xref:System.Windows.Controls.TextBox> -Steuerelement erstellt und erstmals mit Text aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="d0663-107">**Note:** This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0663-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d0663-108">Example</span></span>  
 <span data-ttu-id="d0663-109">In der [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , definiert Ihr <xref:System.Windows.Controls.TextBox> geben die <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> Attribut mit einem Wert, der den Methodennamen des ereignishandlers übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="d0663-109">In the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that defines your <xref:System.Windows.Controls.TextBox> control, specify the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> attribute with a value that matches the event handler method name.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextChangedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]  
  
## <a name="example"></a><span data-ttu-id="d0663-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d0663-110">Example</span></span>  
 <span data-ttu-id="d0663-111">In der CodeBehind-Klasse für den [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , enthält die <xref:System.Windows.Controls.TextBox> -Steuerelement, das Sie überwachen möchten, Änderungen, fügen Sie eine Methode aufruft, wenn die <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> -Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="d0663-111">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="d0663-112">Diese Methode müssen eine Signatur, die entspricht Erwartungen erfüllt werden die <xref:System.Windows.Controls.TextChangedEventHandler> delegieren.</span><span class="sxs-lookup"><span data-stu-id="d0663-112">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
 [!code-vb[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]  
  
 <span data-ttu-id="d0663-113">Der Ereignishandler wird aufgerufen, wenn der Inhalt des der <xref:System.Windows.Controls.TextBox> Steuerelement geändert werden, entweder von einem Benutzer oder programmgesteuert.</span><span class="sxs-lookup"><span data-stu-id="d0663-113">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>  
  
 <span data-ttu-id="d0663-114">**Hinweis**: Dieses Ereignis wird ausgelöst, wenn die <xref:System.Windows.Controls.TextBox> -Steuerelement erstellt und erstmals mit Text aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="d0663-114">**Note:** This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>  
  
 <span data-ttu-id="d0663-115">Kommentare</span><span class="sxs-lookup"><span data-stu-id="d0663-115">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0663-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0663-116">See also</span></span>

- <xref:System.Windows.Controls.TextChangedEventArgs>
- [<span data-ttu-id="d0663-117">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="d0663-117">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="d0663-118">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="d0663-118">RichTextBox Overview</span></span>](richtextbox-overview.md)
