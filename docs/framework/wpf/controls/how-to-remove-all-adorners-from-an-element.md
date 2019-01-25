---
title: 'Vorgehensweise: Entfernen aller Adorner aus einem Element'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: fe5303a3-b76e-4643-aafb-51419032b47b
ms.openlocfilehash: 310b0249c215801b2634d51a1a1117bd7df83526
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680188"
---
# <a name="how-to-remove-all-adorners-from-an-element"></a><span data-ttu-id="c41b2-102">Vorgehensweise: Entfernen aller Adorner aus einem Element</span><span class="sxs-lookup"><span data-stu-id="c41b2-102">How to: Remove all Adorners from an Element</span></span>
<span data-ttu-id="c41b2-103">Dieses Beispiel zeigt, wie Sie das Entfernen aller Adorner aus einem angegebenen programmgesteuert <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="c41b2-103">This example shows how to programmatically remove all adorners from a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c41b2-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c41b2-104">Example</span></span>  
 <span data-ttu-id="c41b2-105">Dieses ausführliche Codebeispiel entfernt alle Adorner in das Array von Adornern, die vom <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span><span class="sxs-lookup"><span data-stu-id="c41b2-105">This verbose code example removes all of the adorners in the array of adorners returned by <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span></span>  <span data-ttu-id="c41b2-106">In diesem Beispiel erfolgt die Funktionsindikatoren abrufen, auf eine <xref:System.Windows.UIElement> mit dem Namen *MyTextBox*.</span><span class="sxs-lookup"><span data-stu-id="c41b2-106">This example happens to retrieve the adorners on a <xref:System.Windows.UIElement> named *myTextBox*.</span></span>  <span data-ttu-id="c41b2-107">Wenn das Element im Aufruf angegeben <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> verfügt über keine Adorner, `null` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c41b2-107">If the element specified in the call to <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> has no adorners, `null` is returned.</span></span>  <span data-ttu-id="c41b2-108">Dieser Code überprüft, ob ein null-Array explizit und eignet sich optimal für Anwendungen, in dem ein null-Array muss relativ häufig werden.</span><span class="sxs-lookup"><span data-stu-id="c41b2-108">This code explicitly checks for a null array, and is best suited for applications where a null array is expected to be relatively common.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornerslong)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornerslong)]  
  
## <a name="example"></a><span data-ttu-id="c41b2-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c41b2-109">Example</span></span>  
 <span data-ttu-id="c41b2-110">In diesem Codebeispiel verkürzte ist funktionell gleichwertig mit ausführlichen oben gezeigten Beispiel.</span><span class="sxs-lookup"><span data-stu-id="c41b2-110">This condensed code example is functionally equivalent to the verbose example shown above.</span></span> <span data-ttu-id="c41b2-111">Dieser Code explizit überprüft nicht für ein null-Array, daher ist es möglich, eine <xref:System.NullReferenceException> Ausnahme kann ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="c41b2-111">This code does not explicitly check for a null array, so it is possible that a <xref:System.NullReferenceException> exception may be raised.</span></span>  <span data-ttu-id="c41b2-112">Dieser Code eignet sich optimal für Anwendungen, in denen ist ein null-Array eher selten.</span><span class="sxs-lookup"><span data-stu-id="c41b2-112">This code is best suited for applications where a null array is expected to be rare.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornersshort)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornersshort)]  
  
## <a name="see-also"></a><span data-ttu-id="c41b2-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c41b2-113">See also</span></span>
- [<span data-ttu-id="c41b2-114">Übersicht über Adorner</span><span class="sxs-lookup"><span data-stu-id="c41b2-114">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
