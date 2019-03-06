---
title: 'Vorgehensweise: Entfernen eines Adorners aus einem Element'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
ms.openlocfilehash: 0c74fe9ed1e7190ce4ff26a7dbae1413f950ba7e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374075"
---
# <a name="how-to-remove-an-adorner-from-an-element"></a><span data-ttu-id="4df7e-102">Vorgehensweise: Entfernen eines Adorners aus einem Element</span><span class="sxs-lookup"><span data-stu-id="4df7e-102">How to: Remove an Adorner from an Element</span></span>
<span data-ttu-id="4df7e-103">In diesem Beispiel wird gezeigt, wie das programmgesteuerte Entfernen von einem bestimmten Adorner aus einem angegebenen <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="4df7e-103">This example shows how to programmatically remove a specific adorner from a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4df7e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4df7e-104">Example</span></span>  
 <span data-ttu-id="4df7e-105">In diesem ausführlichen Codebeispiel wird der erste Adorner entfernt im Array von Adornern, die vom <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span><span class="sxs-lookup"><span data-stu-id="4df7e-105">This verbose code example removes the first adorner in the array of adorners returned by <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span></span>  <span data-ttu-id="4df7e-106">In diesem Beispiel erfolgt die Funktionsindikatoren abrufen, auf eine <xref:System.Windows.UIElement> mit dem Namen *MyTextBox*.</span><span class="sxs-lookup"><span data-stu-id="4df7e-106">This example happens to retrieve the adorners on a <xref:System.Windows.UIElement> named *myTextBox*.</span></span>  <span data-ttu-id="4df7e-107">Wenn das Element im Aufruf angegeben <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> verfügt über keine Adorner, `null` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4df7e-107">If the element specified in the call to <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> has no adorners, `null` is returned.</span></span>  <span data-ttu-id="4df7e-108">Dieser Code überprüft, ob ein null-Array explizit und eignet sich optimal für Anwendungen, in dem ein null-Array muss relativ häufig werden.</span><span class="sxs-lookup"><span data-stu-id="4df7e-108">This code explicitly checks for a null array, and is best suited for applications where a null array is expected to be relatively common.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## <a name="example"></a><span data-ttu-id="4df7e-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4df7e-109">Example</span></span>  
 <span data-ttu-id="4df7e-110">In diesem Codebeispiel verkürzte ist funktionell gleichwertig mit ausführlichen oben gezeigten Beispiel.</span><span class="sxs-lookup"><span data-stu-id="4df7e-110">This condensed code example is functionally equivalent to the verbose example shown above.</span></span> <span data-ttu-id="4df7e-111">Dieser Code explizit überprüft nicht für ein null-Array, daher ist es möglich, eine <xref:System.NullReferenceException> Ausnahme kann ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="4df7e-111">This code does not explicitly check for a null array, so it is possible that a <xref:System.NullReferenceException> exception may be raised.</span></span>  <span data-ttu-id="4df7e-112">Dieser Code eignet sich optimal für Anwendungen, in denen ist ein null-Array eher selten.</span><span class="sxs-lookup"><span data-stu-id="4df7e-112">This code is best suited for applications where a null array is expected to be rare.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## <a name="see-also"></a><span data-ttu-id="4df7e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4df7e-113">See also</span></span>
- [<span data-ttu-id="4df7e-114">Übersicht über Adorner</span><span class="sxs-lookup"><span data-stu-id="4df7e-114">Adorners Overview</span></span>](adorners-overview.md)
