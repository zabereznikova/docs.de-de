---
title: 'Gewusst wie: Implementieren eines Adorners'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 76bceae5b69fad4c217127617309484edcf18108
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-an-adorner"></a><span data-ttu-id="11323-102">Gewusst wie: Implementieren eines Adorners</span><span class="sxs-lookup"><span data-stu-id="11323-102">How to: Implement an Adorner</span></span>
<span data-ttu-id="11323-103">Dieses Beispiel zeigt eine minimale Adornerimplementierung.</span><span class="sxs-lookup"><span data-stu-id="11323-103">This example shows a minimal adorner implementation.</span></span>  
  
## <a name="notes-for-implementers"></a><span data-ttu-id="11323-104">Hinweise für Implementierer</span><span class="sxs-lookup"><span data-stu-id="11323-104">Notes for Implementers</span></span>  
 <span data-ttu-id="11323-105">Beachten Sie, dass für Adorner kein Renderingverhalten festgelegt ist. Damit wird sichergestellt, dass für das Rendering die Adorner-Implementierung verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="11323-105">It is important to note that adorners do not include any inherent rendering behavior; ensuring that an adorner renders is the responsibility of the adorner implementer.</span></span>   <span data-ttu-id="11323-106">Ist eine allgemeine Möglichkeit zum Implementieren von Renderingverhalten überschreiben die <xref:System.Windows.UIElement.OnRender%2A> -Methode, und verwenden Sie eine oder mehrere <xref:System.Windows.Media.DrawingContext> Objekte zum Rendern der Funktionsindikator visuelle Elemente nach Bedarf (wie im folgenden Beispiel gezeigt).</span><span class="sxs-lookup"><span data-stu-id="11323-106">A common way of implementing rendering behavior is to override the <xref:System.Windows.UIElement.OnRender%2A> method and use one or more <xref:System.Windows.Media.DrawingContext> objects to render the adorner's visuals as needed (as shown in this example).</span></span>  
  
## <a name="example"></a><span data-ttu-id="11323-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="11323-107">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="11323-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11323-108">Description</span></span>  
 <span data-ttu-id="11323-109">Ein benutzerdefinierter Adorner wird erstellt, durch die Implementierung einer Klasse, die von der abstrakten erbt <xref:System.Windows.Documents.Adorner> Klasse.</span><span class="sxs-lookup"><span data-stu-id="11323-109">A custom adorner is created by implementing a class that inherits from the abstract <xref:System.Windows.Documents.Adorner> class.</span></span>  <span data-ttu-id="11323-110">Beispieladorner werden einfach die Ecken des eine <xref:System.Windows.UIElement> mit Kreisen durch Überschreiben der <xref:System.Windows.UIElement.OnRender%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="11323-110">The example adorner simply adorns the corners of a <xref:System.Windows.UIElement> with circles by overriding the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="11323-111">Code</span><span class="sxs-lookup"><span data-stu-id="11323-111">Code</span></span>  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a><span data-ttu-id="11323-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11323-112">See Also</span></span>  
 [<span data-ttu-id="11323-113">Übersicht über Adorner</span><span class="sxs-lookup"><span data-stu-id="11323-113">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
