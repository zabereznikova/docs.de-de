---
title: 'Vorgehensweise: Abrufen oder Festlegen von Canvas-Positionierungseigenschaften'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Canvas control [WPF], setting positioning properties
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
ms.openlocfilehash: 06508e1198736ccb1cbda41641dff4bc634ef82b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194408"
---
# <a name="how-to-get-or-set-canvas-positioning-properties"></a><span data-ttu-id="b04f0-102">Vorgehensweise: Abrufen oder Festlegen von Canvas-Positionierungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="b04f0-102">How to: Get or Set Canvas Positioning Properties</span></span>
<span data-ttu-id="b04f0-103">In diesem Beispiel wird gezeigt, wie die Positionierung Methoden der Verwendung der <xref:System.Windows.Controls.Canvas> Element, um untergeordneten Inhalt zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="b04f0-103">This example shows how to use the positioning methods of the <xref:System.Windows.Controls.Canvas> element to position child content.</span></span> <span data-ttu-id="b04f0-104">Dieses Beispiel verwendet den Inhalt in einem <xref:System.Windows.Controls.ListBoxItem> zur Darstellung Positionierung Werte und konvertiert die Werte in Instanzen von <xref:System.Double>, dies ist ein erforderliches Argument für die Positionierung.</span><span class="sxs-lookup"><span data-stu-id="b04f0-104">This example uses content in a <xref:System.Windows.Controls.ListBoxItem> to represent positioning values and converts the values into instances of <xref:System.Double>, which is a required argument for positioning.</span></span> <span data-ttu-id="b04f0-105">Die Werte dann wieder in Zeichenfolgen konvertiert und als Text in eine <xref:System.Windows.Controls.TextBlock> -Element mithilfe der <xref:System.Windows.Controls.Canvas.GetLeft%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="b04f0-105">The values are then converted back into strings and displayed as text in a <xref:System.Windows.Controls.TextBlock> element by using the <xref:System.Windows.Controls.Canvas.GetLeft%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b04f0-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b04f0-106">Example</span></span>  
 <span data-ttu-id="b04f0-107">Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.ListBox> Element, das elf ausgewählt verfügt <xref:System.Windows.Controls.ListBoxItem> Elemente.</span><span class="sxs-lookup"><span data-stu-id="b04f0-107">The following example creates a <xref:System.Windows.Controls.ListBox> element that has eleven selectable <xref:System.Windows.Controls.ListBoxItem> elements.</span></span> <span data-ttu-id="b04f0-108">Die <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> Ereignistrigger das `ChangeLeft` benutzerdefinierte Methode, die des nachfolgenden Codeblocks definiert.</span><span class="sxs-lookup"><span data-stu-id="b04f0-108">The <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event triggers the `ChangeLeft` custom method, which the subsequent code block defines.</span></span>  
  
 <span data-ttu-id="b04f0-109">Jede <xref:System.Windows.Controls.ListBoxItem> stellt eine <xref:System.Double> -Wert, der eines der Argumente ist, die die <xref:System.Windows.Controls.Canvas.SetLeft%2A> -Methode der <xref:System.Windows.Controls.Canvas> akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="b04f0-109">Each <xref:System.Windows.Controls.ListBoxItem> represents a <xref:System.Double> value, which is one of the arguments that the <xref:System.Windows.Controls.Canvas.SetLeft%2A> method of <xref:System.Windows.Controls.Canvas> accepts.</span></span> <span data-ttu-id="b04f0-110">Um verwenden eine <xref:System.Windows.Controls.ListBoxItem> zur Darstellung einer Instanz von <xref:System.Double>, Sie müssen zuerst konvertieren die <xref:System.Windows.Controls.ListBoxItem> in den richtigen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="b04f0-110">In order to use a <xref:System.Windows.Controls.ListBoxItem> to represent an instance of <xref:System.Double>, you must first convert the <xref:System.Windows.Controls.ListBoxItem> to the correct data type.</span></span>  
  
 [!code-xaml[CanvasPositioningProperties#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="b04f0-111">Wenn ein Benutzer ändert die <xref:System.Windows.Controls.ListBox> Auswahl, ruft er die `ChangeLeft` benutzerdefinierte Methode.</span><span class="sxs-lookup"><span data-stu-id="b04f0-111">When a user changes the <xref:System.Windows.Controls.ListBox> selection, it invokes the `ChangeLeft` custom method.</span></span> <span data-ttu-id="b04f0-112">Diese Methode übergibt der <xref:System.Windows.Controls.ListBoxItem> auf eine <xref:System.Windows.LengthConverter> -Objekt, das konvertiert die <xref:System.Windows.Controls.ContentControl.Content%2A> von eine <xref:System.Windows.Controls.ListBoxItem> mit einer Instanz von <xref:System.Double> (Beachten Sie, die diesen Wert bereits in konvertiert wurde eine <xref:System.String> mithilfe der <xref:System.Windows.Controls.Control.ToString%2A> (Methode).</span><span class="sxs-lookup"><span data-stu-id="b04f0-112">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.LengthConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Double> (notice that this value has already been converted to a <xref:System.String> by using the <xref:System.Windows.Controls.Control.ToString%2A> method).</span></span> <span data-ttu-id="b04f0-113">Dieser Wert wird dann zurück zum Übergeben der <xref:System.Windows.Controls.Canvas.SetLeft%2A> und <xref:System.Windows.Controls.Canvas.GetLeft%2A> Methoden der <xref:System.Windows.Controls.Canvas> um die Position des Ändern der `text1` Objekt.</span><span class="sxs-lookup"><span data-stu-id="b04f0-113">This value is then passed back to the <xref:System.Windows.Controls.Canvas.SetLeft%2A> and <xref:System.Windows.Controls.Canvas.GetLeft%2A> methods of <xref:System.Windows.Controls.Canvas> in order to change the position of the `text1` object.</span></span>  
  
 [!code-csharp[CanvasPositioningProperties#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="b04f0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b04f0-114">See also</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.ListBoxItem>
- <xref:System.Windows.LengthConverter>
- [<span data-ttu-id="b04f0-115">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="b04f0-115">Panels Overview</span></span>](panels-overview.md)
