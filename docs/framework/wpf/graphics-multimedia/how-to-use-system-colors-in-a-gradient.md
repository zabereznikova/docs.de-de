---
title: 'Vorgehensweise: Verwenden von Systemfarben in einem Farbverlauf'
ms.date: 03/30/2017
helpviewer_keywords:
- gradients [WPF], system colors in
- system colors in gradients [WPF]
ms.assetid: 11942e7e-6300-4b50-8ed1-f50e8d20e7d2
ms.openlocfilehash: 55c99640907a0c372f8c7bbc50b9b45c9f15ef3c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769238"
---
# <a name="how-to-use-system-colors-in-a-gradient"></a><span data-ttu-id="0a21b-102">Vorgehensweise: Verwenden von Systemfarben in einem Farbverlauf</span><span class="sxs-lookup"><span data-stu-id="0a21b-102">How to: Use System Colors in a Gradient</span></span>
<span data-ttu-id="0a21b-103">Um Systemfarben in einem Farbverlauf zu verwenden, verwenden Sie die  *\<SystemColor >* Farbe und  *\<SystemColor >* ColorKey statischen Eigenschaften der der <xref:System.Windows.SystemColors> Klasse zum Abrufen einer Verweis auf die Farbe, in denen  *\<SystemColor >* ist der Name der gewünschten Systemfarbe.</span><span class="sxs-lookup"><span data-stu-id="0a21b-103">To use a system color in a gradient, you use the *\<SystemColor>* Color and *\<SystemColor>* ColorKey static properties of the <xref:System.Windows.SystemColors> class to obtain a reference to the color, where *\<SystemColor>* is the name of the desired system color.</span></span> <span data-ttu-id="0a21b-104">Verwenden der  *\<SystemColor >* ColorKey-Eigenschaften, wenn Sie einen dynamischen Verweis erstellen, die automatisch die Systemdesigns aktualisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0a21b-104">Use the *\<SystemColor>* ColorKey properties when you want to create a dynamic reference that updates automatically as the system theme changes.</span></span> <span data-ttu-id="0a21b-105">Verwenden Sie andernfalls die  *\<SystemColor >* Color-Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="0a21b-105">Otherwise, use the *\<SystemColor>* Color properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a21b-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0a21b-106">Example</span></span>  
 <span data-ttu-id="0a21b-107">Im folgenden Beispiel wird ein Farbverlauf mithilfe dynamischer Systemfarbressourcen erstellt.</span><span class="sxs-lookup"><span data-stu-id="0a21b-107">The following example uses dynamic system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemColorExample.xaml#graphicsmmdynamicsystemcolorgradientexamplewholepage)]  
  
 <span data-ttu-id="0a21b-108">Im nächsten Beispiel wird ein Farbverlauf mithilfe statischer Systemfarbressourcen erstellt.</span><span class="sxs-lookup"><span data-stu-id="0a21b-108">The next example uses static system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemColorExample.xaml#graphicsmmstaticsystemcolorgradientexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="0a21b-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a21b-109">See also</span></span>

- <xref:System.Windows.SystemColors>
- [<span data-ttu-id="0a21b-110">Zeichnen eines Bereichs mit einem Systempinsel</span><span class="sxs-lookup"><span data-stu-id="0a21b-110">Paint an Area with a System Brush</span></span>](how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="0a21b-111">Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen</span><span class="sxs-lookup"><span data-stu-id="0a21b-111">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
