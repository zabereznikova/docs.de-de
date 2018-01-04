---
title: 'Gewusst wie: Verwenden von Systemfarben in einem Farbverlauf'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- gradients [WPF], system colors in
- system colors in gradients [WPF]
ms.assetid: 11942e7e-6300-4b50-8ed1-f50e8d20e7d2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: acf0f2c63e0b176f28d611183aab1abecc8f1678
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-system-colors-in-a-gradient"></a><span data-ttu-id="8b8ef-102">Gewusst wie: Verwenden von Systemfarben in einem Farbverlauf</span><span class="sxs-lookup"><span data-stu-id="8b8ef-102">How to: Use System Colors in a Gradient</span></span>
<span data-ttu-id="8b8ef-103">Um eine Systemfarbe in einem Farbverlauf zu verwenden, verwenden Sie die  *\<SystemColor >*Farbe und  *\<SystemColor >*ColorKey statische Eigenschaften der der <xref:System.Windows.SystemColors> Klasse zum Abrufen einer Verweis auf die Farbe, in denen  *\<SystemColor >* ist der Name des gewünschten Systemfarbe.</span><span class="sxs-lookup"><span data-stu-id="8b8ef-103">To use a system color in a gradient, you use the *\<SystemColor>*Color and *\<SystemColor>*ColorKey static properties of the <xref:System.Windows.SystemColors> class to obtain a reference to the color, where *\<SystemColor>* is the name of the desired system color.</span></span> <span data-ttu-id="8b8ef-104">Verwenden der  *\<SystemColor >*ColorKey-Eigenschaften, wenn Sie einen dynamischen Verweis erstellen, die das System Design ändert automatisch aktualisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8b8ef-104">Use the *\<SystemColor>*ColorKey properties when you want to create a dynamic reference that updates automatically as the system theme changes.</span></span> <span data-ttu-id="8b8ef-105">Verwenden Sie andernfalls die  *\<SystemColor >*Color-Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="8b8ef-105">Otherwise, use the *\<SystemColor>*Color properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b8ef-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8b8ef-106">Example</span></span>  
 <span data-ttu-id="8b8ef-107">Im folgenden Beispiel wird ein Farbverlauf mithilfe dynamischer Systemfarbressourcen erstellt.</span><span class="sxs-lookup"><span data-stu-id="8b8ef-107">The following example uses dynamic system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemColorExample.xaml#graphicsmmdynamicsystemcolorgradientexamplewholepage)]  
  
 <span data-ttu-id="8b8ef-108">Im nächsten Beispiel wird ein Farbverlauf mithilfe statischer Systemfarbressourcen erstellt.</span><span class="sxs-lookup"><span data-stu-id="8b8ef-108">The next example uses static system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemColorExample.xaml#graphicsmmstaticsystemcolorgradientexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="8b8ef-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b8ef-109">See Also</span></span>  
 <xref:System.Windows.SystemColors>  
 [<span data-ttu-id="8b8ef-110">Zeichnen eines Bereichs mit einem Systempinsel</span><span class="sxs-lookup"><span data-stu-id="8b8ef-110">Paint an Area with a System Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [<span data-ttu-id="8b8ef-111">Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen</span><span class="sxs-lookup"><span data-stu-id="8b8ef-111">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
