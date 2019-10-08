---
title: 'Vorgehensweise: Erkennen, wenn die EINGABETASTE gedrückt wurde'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: e2337826077c836696937f91541d6d261f1270aa
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004824"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a><span data-ttu-id="63d16-102">Vorgehensweise: Erkennen, wenn die EINGABETASTE gedrückt wurde</span><span class="sxs-lookup"><span data-stu-id="63d16-102">How to: Detect When the Enter Key Pressed</span></span>
<span data-ttu-id="63d16-103">Dieses Beispiel zeigt, wie Sie erkennen können, wenn die <xref:System.Windows.Input.Key.Enter>-Taste auf der Tastatur gedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="63d16-103">This example shows how to detect when the <xref:System.Windows.Input.Key.Enter> key is pressed on the keyboard.</span></span>  
  
 <span data-ttu-id="63d16-104">Dieses Beispiel besteht aus einer [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]-Datei und einer Code Behind-Datei.</span><span class="sxs-lookup"><span data-stu-id="63d16-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63d16-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="63d16-105">Example</span></span>  
 <span data-ttu-id="63d16-106">Wenn der Benutzer den <xref:System.Windows.Input.Key.Enter>-Schlüssel im <xref:System.Windows.Controls.TextBox> drückt, wird die Eingabe im Textfeld in einem anderen Bereich des [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] angezeigt.</span><span class="sxs-lookup"><span data-stu-id="63d16-106">When the user presses the <xref:System.Windows.Input.Key.Enter> key in the <xref:System.Windows.Controls.TextBox>, the input in the text box appears in another area of the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="63d16-107">Der folgende XAML-Code erstellt die Benutzeroberfläche, die aus einer <xref:System.Windows.Controls.StackPanel>, einer <xref:System.Windows.Controls.TextBlock> und einem <xref:System.Windows.Controls.TextBox> besteht.</span><span class="sxs-lookup"><span data-stu-id="63d16-107">The following XAML creates the user interface, which consists of a <xref:System.Windows.Controls.StackPanel>, a <xref:System.Windows.Controls.TextBlock>, and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 <span data-ttu-id="63d16-108">Der folgende Code Behind erstellt den <xref:System.Windows.UIElement.KeyDown>-Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="63d16-108">The following code behind creates the <xref:System.Windows.UIElement.KeyDown> event handler.</span></span>  <span data-ttu-id="63d16-109">Wenn die gedrückte Taste der <xref:System.Windows.Input.Key.Enter>-Taste ist, wird eine Meldung in der <xref:System.Windows.Controls.TextBlock> angezeigt.</span><span class="sxs-lookup"><span data-stu-id="63d16-109">If the key that is pressed is the <xref:System.Windows.Input.Key.Enter> key, a message is displayed in the <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a><span data-ttu-id="63d16-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63d16-110">See also</span></span>

- [<span data-ttu-id="63d16-111">Übersicht über die Eingabe</span><span class="sxs-lookup"><span data-stu-id="63d16-111">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="63d16-112">Übersicht über Routingereignisse</span><span class="sxs-lookup"><span data-stu-id="63d16-112">Routed Events Overview</span></span>](routed-events-overview.md)
