---
title: 'Vorgehensweise: Anwenden einer Transformation auf ein Element beim Auftreten eines Ereignisses'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], transformations as event responses
- properties [WPF], LayoutTransform
- transformations as event responses [WPF]
- properties [WPF], RenderTransform
- LayoutTransform property [WPF]
ms.assetid: 71e4327e-ca57-444c-a3cf-09fb381491a0
ms.openlocfilehash: 8f04db274432c0e89c6839bef825976c8a2f853c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64630757"
---
# <a name="how-to-apply-a-transform-to-an-element-when-an-event-occurs"></a><span data-ttu-id="cf9f0-102">Vorgehensweise: Anwenden einer Transformation auf ein Element beim Auftreten eines Ereignisses</span><span class="sxs-lookup"><span data-stu-id="cf9f0-102">How to: Apply a Transform to an Element When an Event Occurs</span></span>
<span data-ttu-id="cf9f0-103">Dieses Beispiel veranschaulicht das Anwenden einer <xref:System.Windows.Media.ScaleTransform> bei Auftreten eines Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="cf9f0-103">This example shows how to apply a <xref:System.Windows.Media.ScaleTransform> when an event occurs.</span></span> <span data-ttu-id="cf9f0-104">Mithilfe des hier dargestellten Konzepts können Sie auch andere Transformationstypen anwenden.</span><span class="sxs-lookup"><span data-stu-id="cf9f0-104">The concept that is shown here is the same that you use for applying other types of transformations.</span></span> <span data-ttu-id="cf9f0-105">Weitere Informationen zu den verfügbaren Arten von Transformationen, finden Sie unter den <xref:System.Windows.Media.Transform> Klasse oder [Übersicht über Transformationen](transforms-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cf9f0-105">For more information about the available types of transformations, see the <xref:System.Windows.Media.Transform> class or [Transforms Overview](transforms-overview.md).</span></span>  
  
 <span data-ttu-id="cf9f0-106">Sie können mit einem der folgenden beiden Verfahren eine Transformation auf ein Element anwenden:</span><span class="sxs-lookup"><span data-stu-id="cf9f0-106">You can apply a transform to an element in either of these two ways:</span></span>  
  
- <span data-ttu-id="cf9f0-107">Wenn Sie dies tun *nicht* die Transformation verwenden, um auf das Layout auswirken soll die <xref:System.Windows.UIElement.RenderTransform%2A> -Eigenschaft des Elements.</span><span class="sxs-lookup"><span data-stu-id="cf9f0-107">If you do *not* want the transform to affect layout, use the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span>  
  
- <span data-ttu-id="cf9f0-108">Wenn Sie mit der Transformation auf das Layout auswirken soll, verwenden Sie die <xref:System.Windows.FrameworkElement.LayoutTransform%2A> -Eigenschaft des Elements.</span><span class="sxs-lookup"><span data-stu-id="cf9f0-108">If you do want the transform to affect layout, use the <xref:System.Windows.FrameworkElement.LayoutTransform%2A> property of the element.</span></span>  
  
 <span data-ttu-id="cf9f0-109">Im folgenden Beispiel wird eine <xref:System.Windows.Media.ScaleTransform> auf die <xref:System.Windows.UIElement.RenderTransform%2A> -Eigenschaft einer Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="cf9f0-109">The following example applies a <xref:System.Windows.Media.ScaleTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of a button.</span></span> <span data-ttu-id="cf9f0-110">Wenn die Maus über die Schaltfläche bewegt die <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> und <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> Eigenschaften der <xref:System.Windows.Media.ScaleTransform> festgelegt `2`, die bewirkt, dass die Schaltfläche immer größer werden.</span><span class="sxs-lookup"><span data-stu-id="cf9f0-110">When the mouse moves over the button, the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties of the <xref:System.Windows.Media.ScaleTransform> are set to `2`, which causes the button to become larger.</span></span> <span data-ttu-id="cf9f0-111">Wenn die Maus der Schaltfläche weg bewegt <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> und <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> festgelegt `1`, die bewirkt, dass der Schaltfläche, um auf seine ursprüngliche Größe zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="cf9f0-111">When the mouse moves off the button, <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> are set to `1`, which causes the button to return to its original size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf9f0-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cf9f0-112">Example</span></span>  
 [!code-xaml[ButtonTransform#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml#1)]  
  
 [!code-csharp[ButtonTransform#1cb](~/samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml.cs#1cb)]
 [!code-vb[ButtonTransform#1cb](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ButtonTransform/VisualBasic/ButtonTransformExample.xaml.vb#1cb)]  
  
## <a name="see-also"></a><span data-ttu-id="cf9f0-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf9f0-113">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [<span data-ttu-id="cf9f0-114">Übersicht über Transformationen</span><span class="sxs-lookup"><span data-stu-id="cf9f0-114">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="cf9f0-115">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="cf9f0-115">How-to Topics</span></span>](transformations-how-to-topics.md)
- [<span data-ttu-id="cf9f0-116">Übersicht über Routingereignisse</span><span class="sxs-lookup"><span data-stu-id="cf9f0-116">Routed Events Overview</span></span>](../advanced/routed-events-overview.md)
