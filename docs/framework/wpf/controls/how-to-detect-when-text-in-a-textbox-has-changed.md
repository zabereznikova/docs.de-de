---
title: "Gewusst wie: Erkennen von Änderungen an Text in einem Textfeld"
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
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ef1da879026d8cbefd6ef1baeb6c315e0ea1c02
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a><span data-ttu-id="dad26-102">Gewusst wie: Erkennen von Änderungen an Text in einem Textfeld</span><span class="sxs-lookup"><span data-stu-id="dad26-102">How to: Detect When Text in a TextBox Has Changed</span></span>
<span data-ttu-id="dad26-103">Dieses Beispiel zeigt eine Möglichkeit zum Verwenden der <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> Ereignis zur Ausführung einer Methode immer den Text in einem <xref:System.Windows.Controls.TextBox> -Steuerelements geändert hat.</span><span class="sxs-lookup"><span data-stu-id="dad26-103">This example shows one way to use the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event to execute a method whenever the text in a <xref:System.Windows.Controls.TextBox> control has changed.</span></span>  
  
 <span data-ttu-id="dad26-104">In der CodeBehind-Klasse für die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , enthält die <xref:System.Windows.Controls.TextBox> Steuerelement, das Sie überwachen möchten, damit die Änderungen, fügen Sie eine Methode aufrufen, wenn die <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> -Ereignis ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="dad26-104">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="dad26-105">Diese Methode benötigen eine Signatur, die von entspricht dem <xref:System.Windows.Controls.TextChangedEventHandler> delegieren.</span><span class="sxs-lookup"><span data-stu-id="dad26-105">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>  
  
 <span data-ttu-id="dad26-106">Der Ereignishandler wird aufgerufen, wenn der Inhalt des der <xref:System.Windows.Controls.TextBox> Steuerelement verwendet werden, von einem Benutzer oder programmgesteuert geändert.</span><span class="sxs-lookup"><span data-stu-id="dad26-106">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>  
  
 <span data-ttu-id="dad26-107">**Hinweis:** dieses Ereignis wird ausgelöst, wenn die <xref:System.Windows.Controls.TextBox> Steuerelement erstellt und erstmals mit Text aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="dad26-107">**Note:** This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dad26-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dad26-108">Example</span></span>  
 <span data-ttu-id="dad26-109">In der [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , definiert die <xref:System.Windows.Controls.TextBox> geben die <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> Attribut mit einem Wert, der den Namen Ereignishandlermethode entspricht.</span><span class="sxs-lookup"><span data-stu-id="dad26-109">In the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that defines your <xref:System.Windows.Controls.TextBox> control, specify the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> attribute with a value that matches the event handler method name.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextChangedXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]  
  
## <a name="example"></a><span data-ttu-id="dad26-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dad26-110">Example</span></span>  
 <span data-ttu-id="dad26-111">In der CodeBehind-Klasse für die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , enthält die <xref:System.Windows.Controls.TextBox> Steuerelement, das Sie überwachen möchten, damit die Änderungen, fügen Sie eine Methode aufrufen, wenn die <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> -Ereignis ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="dad26-111">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="dad26-112">Diese Methode benötigen eine Signatur, die von entspricht dem <xref:System.Windows.Controls.TextChangedEventHandler> delegieren.</span><span class="sxs-lookup"><span data-stu-id="dad26-112">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
 [!code-vb[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]  
  
 <span data-ttu-id="dad26-113">Der Ereignishandler wird aufgerufen, wenn der Inhalt des der <xref:System.Windows.Controls.TextBox> Steuerelement verwendet werden, von einem Benutzer oder programmgesteuert geändert.</span><span class="sxs-lookup"><span data-stu-id="dad26-113">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>  
  
 <span data-ttu-id="dad26-114">**Hinweis:** dieses Ereignis wird ausgelöst, wenn die <xref:System.Windows.Controls.TextBox> Steuerelement erstellt und erstmals mit Text aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="dad26-114">**Note:** This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>  
  
 <span data-ttu-id="dad26-115">Kommentare</span><span class="sxs-lookup"><span data-stu-id="dad26-115">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dad26-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dad26-116">See Also</span></span>  
 <xref:System.Windows.Controls.TextChangedEventArgs>  
 [<span data-ttu-id="dad26-117">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="dad26-117">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="dad26-118">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="dad26-118">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
