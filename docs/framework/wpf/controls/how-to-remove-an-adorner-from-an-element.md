---
title: 'Gewusst wie: Entfernen eines Adorners aus einem Element'
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
helpviewer_keywords: adorners [WPF], removing
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fe11dc8df1a29518ba05792877bd26670f96b29d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-remove-an-adorner-from-an-element"></a><span data-ttu-id="a2416-102">Gewusst wie: Entfernen eines Adorners aus einem Element</span><span class="sxs-lookup"><span data-stu-id="a2416-102">How to: Remove an Adorner from an Element</span></span>
<span data-ttu-id="a2416-103">In diesem Beispiel wird gezeigt, wie So entfernen Sie einen bestimmten Adorner programmgesteuert aus einem angegebenen <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="a2416-103">This example shows how to programmatically remove a specific adorner from a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2416-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a2416-104">Example</span></span>  
 <span data-ttu-id="a2416-105">Dieses Codebeispiel ausführliche entfernt ersten Funktionsindikator im Array von Adornern zurückgegebenes <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span><span class="sxs-lookup"><span data-stu-id="a2416-105">This verbose code example removes the first adorner in the array of adorners returned by <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span></span>  <span data-ttu-id="a2416-106">In diesem Beispiel erfolgt, Abrufen von Adorner auf eine <xref:System.Windows.UIElement> mit dem Namen *MyTextBox*.</span><span class="sxs-lookup"><span data-stu-id="a2416-106">This example happens to retrieve the adorners on a <xref:System.Windows.UIElement> named *myTextBox*.</span></span>  <span data-ttu-id="a2416-107">Wenn das Element im Aufruf angegeben <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> verfügt über keine Adorner `null` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a2416-107">If the element specified in the call to <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> has no adorners, `null` is returned.</span></span>  <span data-ttu-id="a2416-108">Dieser Code überprüft, ob ein null-Array explizit und eignet sich optimal für Anwendungen, in denen ein null-Array erwartet wird, relativ häufig verwendet.</span><span class="sxs-lookup"><span data-stu-id="a2416-108">This code explicitly checks for a null array, and is best suited for applications where a null array is expected to be relatively common.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## <a name="example"></a><span data-ttu-id="a2416-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a2416-109">Example</span></span>  
 <span data-ttu-id="a2416-110">Dieser verkürzte Codebeispiel ist funktionell gleichwertig mit der oben gezeigten ausführlichen Beispiel.</span><span class="sxs-lookup"><span data-stu-id="a2416-110">This condensed code example is functionally equivalent to the verbose example shown above.</span></span> <span data-ttu-id="a2416-111">Dieser Code explizit überprüft nicht für ein null-Array, daher ist es möglich, eine <xref:System.NullReferenceException> Ausnahme kann ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="a2416-111">This code does not explicitly check for a null array, so it is possible that a <xref:System.NullReferenceException> exception may be raised.</span></span>  <span data-ttu-id="a2416-112">Dieser Code eignet sich optimal für Anwendungen, in denen ist ein null-Array eher selten.</span><span class="sxs-lookup"><span data-stu-id="a2416-112">This code is best suited for applications where a null array is expected to be rare.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## <a name="see-also"></a><span data-ttu-id="a2416-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2416-113">See Also</span></span>  
 [<span data-ttu-id="a2416-114">Übersicht über Adorner</span><span class="sxs-lookup"><span data-stu-id="a2416-114">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
