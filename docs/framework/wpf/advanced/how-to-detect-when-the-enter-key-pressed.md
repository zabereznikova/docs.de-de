---
title: 'Vorgehensweise: Erkennen, wenn die EINGABETASTE gedrückt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: a99da5804bbc31897198b9b6d9e21da9f17dfe26
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204613"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a><span data-ttu-id="07f4b-102">Vorgehensweise: Erkennen, wenn die EINGABETASTE gedrückt</span><span class="sxs-lookup"><span data-stu-id="07f4b-102">How to: Detect When the Enter Key Pressed</span></span>
<span data-ttu-id="07f4b-103">Dieses Beispiel zeigt, wie Sie feststellen, ob die <xref:System.Windows.Input.Key.Enter> Taste auf der Tastatur gedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="07f4b-103">This example shows how to detect when the <xref:System.Windows.Input.Key.Enter> key is pressed on the keyboard.</span></span>  
  
 <span data-ttu-id="07f4b-104">In diesem Beispiel besteht aus einem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und eine CodeBehind-Datei.</span><span class="sxs-lookup"><span data-stu-id="07f4b-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07f4b-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07f4b-105">Example</span></span>  
 <span data-ttu-id="07f4b-106">Wenn der Benutzer drückt die <xref:System.Windows.Input.Key.Enter> -Schlüssel in der <xref:System.Windows.Controls.TextBox>, die Eingabe in das Textfeld angezeigt wird, in einem anderen Bereich von der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07f4b-106">When the user presses the <xref:System.Windows.Input.Key.Enter> key in the <xref:System.Windows.Controls.TextBox>, the input in the text box appears in another area of the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="07f4b-107">Die folgenden [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] erstellt die Benutzeroberfläche besteht aus einem <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.TextBlock>, und ein <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="07f4b-107">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of a <xref:System.Windows.Controls.StackPanel>, a <xref:System.Windows.Controls.TextBlock>, and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 <span data-ttu-id="07f4b-108">Der folgende Code hinter erstellt die <xref:System.Windows.UIElement.KeyDown> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="07f4b-108">The following code behind creates the <xref:System.Windows.UIElement.KeyDown> event handler.</span></span>  <span data-ttu-id="07f4b-109">Wenn der Schlüssel, die gedrückt wird, wird die <xref:System.Windows.Input.Key.Enter> drücken, wird eine Meldung angezeigt, der <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="07f4b-109">If the key that is pressed is the <xref:System.Windows.Input.Key.Enter> key, a message is displayed in the <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a><span data-ttu-id="07f4b-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07f4b-110">See also</span></span>

- [<span data-ttu-id="07f4b-111">Übersicht über die Eingabe</span><span class="sxs-lookup"><span data-stu-id="07f4b-111">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="07f4b-112">Übersicht über Routingereignisse</span><span class="sxs-lookup"><span data-stu-id="07f4b-112">Routed Events Overview</span></span>](routed-events-overview.md)
