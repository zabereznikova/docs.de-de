---
title: 'Vorgehensweise: Abrufen des Offsets eines visuellen Objekts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting offset values from visual objects [WPF]
- offset values [WPF], retrieving from visual objects [WPF]
- visual objects [WPF], retrieving offset values from
- retrieving offset values from visual objects [WPF]
ms.assetid: 889a1dd6-1b11-445a-b351-fbb04c53ee34
ms.openlocfilehash: 4787b771c7e59a8b033b9267079c068a5845a1e6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59093409"
---
# <a name="how-to-get-the-offset-of-a-visual"></a><span data-ttu-id="fb64b-102">Vorgehensweise: Abrufen des Offsets eines visuellen Objekts</span><span class="sxs-lookup"><span data-stu-id="fb64b-102">How to: Get the Offset of a Visual</span></span>
<span data-ttu-id="fb64b-103">Diese Beispiele zeigen, wie Sie den Offsetwert des visuellen Objekts abrufen, die relativ zu seinem übergeordneten Element oder Vorgänger oder Nachfolger ist.</span><span class="sxs-lookup"><span data-stu-id="fb64b-103">These examples show how to retrieve the offset value of a visual object that is relative to its parent, or any ancestor or descendant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb64b-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fb64b-104">Example</span></span>  
 <span data-ttu-id="fb64b-105">Das folgende Markup-Beispiel zeigt eine <xref:System.Windows.Controls.TextBlock> , definiert ist, mit <xref:System.Windows.FrameworkElement.Margin%2A> Wert 4.</span><span class="sxs-lookup"><span data-stu-id="fb64b-105">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is defined with <xref:System.Windows.FrameworkElement.Margin%2A> value of 4.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet1)]  
  
 <span data-ttu-id="fb64b-106">Im folgenden Codebeispiel wird veranschaulicht, wie Sie mit der <xref:System.Windows.Media.VisualTreeHelper.GetOffset%2A> Methode zum Abrufen des Offsets für die <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="fb64b-106">The following code example shows how to use the <xref:System.Windows.Media.VisualTreeHelper.GetOffset%2A> method to retrieve the offset of the <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="fb64b-107">Der Offset-Werte befinden sich in der zurückgegebenen <xref:System.Windows.Vector> Wert.</span><span class="sxs-lookup"><span data-stu-id="fb64b-107">The offset values are contained within the returned <xref:System.Windows.Vector> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet2)]
 [!code-vb[VisualSnippets#VisualSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet2)]  
  
 <span data-ttu-id="fb64b-108">Der Offset berücksichtigt die <xref:System.Windows.FrameworkElement.Margin%2A> Wert.</span><span class="sxs-lookup"><span data-stu-id="fb64b-108">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> value.</span></span> <span data-ttu-id="fb64b-109">In diesem Fall <xref:System.Windows.Vector.X%2A> ist 4. und <xref:System.Windows.Vector.Y%2A> ist 4.</span><span class="sxs-lookup"><span data-stu-id="fb64b-109">In this case, <xref:System.Windows.Vector.X%2A> is 4, and <xref:System.Windows.Vector.Y%2A> is 4.</span></span>  
  
 <span data-ttu-id="fb64b-110">Der Rückgabewert der Offset ist relativ zum übergeordneten von der <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="fb64b-110">The returned offset value is relative to the parent of the <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="fb64b-111">Sollten Sie einen Offset-Wert zurück, die nicht relativ zu das übergeordnete Element ist ein <xref:System.Windows.Media.Visual>, verwenden Sie die <xref:System.Windows.Media.Visual.TransformToAncestor%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="fb64b-111">If you want to return an offset value that is not relative to the parent of a <xref:System.Windows.Media.Visual>, use the <xref:System.Windows.Media.Visual.TransformToAncestor%2A> method.</span></span>  
  
## <a name="getting-the-offset-relative-to-an-ancestor"></a><span data-ttu-id="fb64b-112">Den Offset abrufen relativ zu einem Vorgänger</span><span class="sxs-lookup"><span data-stu-id="fb64b-112">Getting the Offset Relative to an Ancestor</span></span>  
 <span data-ttu-id="fb64b-113">Das folgende Markup-Beispiel zeigt eine <xref:System.Windows.Controls.TextBlock> , zwei geschachtelt ist <xref:System.Windows.Controls.StackPanel> Objekte.</span><span class="sxs-lookup"><span data-stu-id="fb64b-113">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is nested within two <xref:System.Windows.Controls.StackPanel> objects.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window2.xaml#visualsnippet7)]  
  
 <span data-ttu-id="fb64b-114">Die folgende Abbildung zeigt die Ergebnisse des Markups.</span><span class="sxs-lookup"><span data-stu-id="fb64b-114">The following illustration shows the results of the markup.</span></span>  
  
 <span data-ttu-id="fb64b-115">![Versatzwerte für Objekte](./media/visualoffset-01.png "VisualOffset_01")</span><span class="sxs-lookup"><span data-stu-id="fb64b-115">![Offset values of objects](./media/visualoffset-01.png "VisualOffset_01")</span></span>  
<span data-ttu-id="fb64b-116">TextBlock in zwei StackPanels geschachtelt.</span><span class="sxs-lookup"><span data-stu-id="fb64b-116">TextBlock nested within two StackPanels</span></span>  
  
 <span data-ttu-id="fb64b-117">Im folgenden Codebeispiel wird veranschaulicht, wie Sie mit der <xref:System.Windows.Media.Visual.TransformToAncestor%2A> Methode zum Abrufen des Offsets für die <xref:System.Windows.Controls.TextBlock> relativ zum enthaltenden <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="fb64b-117">The following code example shows how to use the <xref:System.Windows.Media.Visual.TransformToAncestor%2A> method to retrieve the offset of the <xref:System.Windows.Controls.TextBlock> relative to the containing <xref:System.Windows.Window>.</span></span> <span data-ttu-id="fb64b-118">Der Offset-Werte befinden sich in der zurückgegebenen <xref:System.Windows.Media.GeneralTransform> Wert.</span><span class="sxs-lookup"><span data-stu-id="fb64b-118">The offset values are contained within the returned <xref:System.Windows.Media.GeneralTransform> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet5)]
 [!code-vb[VisualSnippets#VisualSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet5)]  
  
 <span data-ttu-id="fb64b-119">Der Offset berücksichtigt die <xref:System.Windows.FrameworkElement.Margin%2A> Werte für alle Objekte innerhalb des enthaltenden <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="fb64b-119">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> values for all objects within the containing <xref:System.Windows.Window>.</span></span> <span data-ttu-id="fb64b-120">In diesem Fall <xref:System.Windows.Vector.X%2A> ist 28 (16 + 8 + 4), und <xref:System.Windows.Vector.Y%2A> ist 28.</span><span class="sxs-lookup"><span data-stu-id="fb64b-120">In this case, <xref:System.Windows.Vector.X%2A> is 28 (16 + 8 + 4), and <xref:System.Windows.Vector.Y%2A> is 28.</span></span>  
  
 <span data-ttu-id="fb64b-121">Der Rückgabewert der Offset ist relativ zu den Vorgänger der <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="fb64b-121">The returned offset value is relative to the ancestor of the <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="fb64b-122">Sollten Sie einen Offset-Wert zurück, der relativ zum nachfolgenden Wertes des eine <xref:System.Windows.Media.Visual>, verwenden Sie die <xref:System.Windows.Media.Visual.TransformToDescendant%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="fb64b-122">If you want to return an offset value that is relative to the descendant of a <xref:System.Windows.Media.Visual>, use the <xref:System.Windows.Media.Visual.TransformToDescendant%2A> method.</span></span>  
  
## <a name="getting-the-offset-relative-to-a-descendant"></a><span data-ttu-id="fb64b-123">Den Offset abrufen relativ zu einem Nachfolger</span><span class="sxs-lookup"><span data-stu-id="fb64b-123">Getting the Offset Relative to a Descendant</span></span>  
 <span data-ttu-id="fb64b-124">Das folgende Markup-Beispiel zeigt eine <xref:System.Windows.Controls.TextBlock> , befindet sich innerhalb einer <xref:System.Windows.Controls.StackPanel> Objekt.</span><span class="sxs-lookup"><span data-stu-id="fb64b-124">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is contained within a <xref:System.Windows.Controls.StackPanel> object.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet4)]  
  
 <span data-ttu-id="fb64b-125">Im folgenden Codebeispiel wird veranschaulicht, wie Sie mit der <xref:System.Windows.Media.Visual.TransformToDescendant%2A> Methode zum Abrufen des Offsets für die <xref:System.Windows.Controls.StackPanel> relativ zu dessen untergeordneten <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="fb64b-125">The following code example shows how to use the <xref:System.Windows.Media.Visual.TransformToDescendant%2A> method to retrieve the offset of the <xref:System.Windows.Controls.StackPanel> relative to its child <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="fb64b-126">Der Offset-Werte befinden sich in der zurückgegebenen <xref:System.Windows.Media.GeneralTransform> Wert.</span><span class="sxs-lookup"><span data-stu-id="fb64b-126">The offset values are contained within the returned <xref:System.Windows.Media.GeneralTransform> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet9](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet9)]
 [!code-vb[VisualSnippets#VisualSnippet9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet9)]  
  
 <span data-ttu-id="fb64b-127">Der Offset berücksichtigt die <xref:System.Windows.FrameworkElement.Margin%2A> Werte für alle Objekte.</span><span class="sxs-lookup"><span data-stu-id="fb64b-127">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> values for all objects.</span></span> <span data-ttu-id="fb64b-128">In diesem Fall <xref:System.Windows.Vector.X%2A> ist-4. und <xref:System.Windows.Vector.Y%2A> lautet 4.</span><span class="sxs-lookup"><span data-stu-id="fb64b-128">In this case, <xref:System.Windows.Vector.X%2A> is -4, and <xref:System.Windows.Vector.Y%2A> is -4.</span></span> <span data-ttu-id="fb64b-129">Der Offset-Werte sind negative Werte, da das übergeordnete Objekt relativ zu dessen untergeordneten Objekts negativ versetzt wird.</span><span class="sxs-lookup"><span data-stu-id="fb64b-129">The offset values are negative values, since the parent object is negatively offset relative to its child object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb64b-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb64b-130">See also</span></span>

- <xref:System.Windows.Media.Visual>
- <xref:System.Windows.Media.VisualTreeHelper>
- [<span data-ttu-id="fb64b-131">Übersicht über das WPF-Grafikrendering</span><span class="sxs-lookup"><span data-stu-id="fb64b-131">WPF Graphics Rendering Overview</span></span>](wpf-graphics-rendering-overview.md)
