---
title: 'Gewusst wie: Erkennen, wenn die EINGABETASTE gedrückt wird'
description: Erkennen, wenn die Eingabetaste auf der Tastatur in Windows Presentation Foundation ausgewählt ist. Dieses Beispiel besteht aus XAML und einer Code Behind-Datei.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: a955f52ec7bf93b32c70259b27fb51747664ac2e
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163189"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a><span data-ttu-id="9763a-104">Gewusst wie: Erkennen, wenn die EINGABETASTE gedrückt wird</span><span class="sxs-lookup"><span data-stu-id="9763a-104">How to: Detect When the Enter Key Pressed</span></span>
<span data-ttu-id="9763a-105">Dieses Beispiel zeigt, wie Sie erkennen können, wann der <xref:System.Windows.Input.Key.Enter> Schlüssel auf der Tastatur gedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="9763a-105">This example shows how to detect when the <xref:System.Windows.Input.Key.Enter> key is pressed on the keyboard.</span></span>  
  
 <span data-ttu-id="9763a-106">Dieses Beispiel besteht aus einer [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Datei und einer Code Behind-Datei.</span><span class="sxs-lookup"><span data-stu-id="9763a-106">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9763a-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9763a-107">Example</span></span>  
 <span data-ttu-id="9763a-108">Wenn der Benutzer die <xref:System.Windows.Input.Key.Enter> Taste in drückt <xref:System.Windows.Controls.TextBox> , wird die Eingabe im Textfeld in einem anderen Bereich des angezeigt [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9763a-108">When the user presses the <xref:System.Windows.Input.Key.Enter> key in the <xref:System.Windows.Controls.TextBox>, the input in the text box appears in another area of the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="9763a-109">Der folgende XAML-Code erstellt die Benutzeroberfläche, die aus <xref:System.Windows.Controls.StackPanel> , <xref:System.Windows.Controls.TextBlock> und besteht <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="9763a-109">The following XAML creates the user interface, which consists of a <xref:System.Windows.Controls.StackPanel>, a <xref:System.Windows.Controls.TextBlock>, and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 <span data-ttu-id="9763a-110">Der folgende Code Behind erstellt den- <xref:System.Windows.UIElement.KeyDown> Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="9763a-110">The following code behind creates the <xref:System.Windows.UIElement.KeyDown> event handler.</span></span>  <span data-ttu-id="9763a-111">Wenn die gedrückte Taste der Schlüssel ist <xref:System.Windows.Input.Key.Enter> , wird eine Meldung in der angezeigt <xref:System.Windows.Controls.TextBlock> .</span><span class="sxs-lookup"><span data-stu-id="9763a-111">If the key that is pressed is the <xref:System.Windows.Input.Key.Enter> key, a message is displayed in the <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a><span data-ttu-id="9763a-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9763a-112">See also</span></span>

- [<span data-ttu-id="9763a-113">Übersicht über die Eingabe</span><span class="sxs-lookup"><span data-stu-id="9763a-113">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="9763a-114">Übersicht über Routingereignisse</span><span class="sxs-lookup"><span data-stu-id="9763a-114">Routed Events Overview</span></span>](routed-events-overview.md)
