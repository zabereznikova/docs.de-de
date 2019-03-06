---
title: 'Vorgehensweise: Verwenden von Systemfarben in einem Farbverlauf'
ms.date: 03/30/2017
helpviewer_keywords:
- gradients [WPF], system colors in
- system colors in gradients [WPF]
ms.assetid: 11942e7e-6300-4b50-8ed1-f50e8d20e7d2
ms.openlocfilehash: 3148a5901ccf64194717e26664ab8b9cbd57db2a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365957"
---
# <a name="how-to-use-system-colors-in-a-gradient"></a><span data-ttu-id="f686c-102">Vorgehensweise: Verwenden von Systemfarben in einem Farbverlauf</span><span class="sxs-lookup"><span data-stu-id="f686c-102">How to: Use System Colors in a Gradient</span></span>
<span data-ttu-id="f686c-103">Um Systemfarben in einem Farbverlauf zu verwenden, verwenden Sie die  *\<SystemColor >* Farbe und  *\<SystemColor >* ColorKey statischen Eigenschaften der der <xref:System.Windows.SystemColors> Klasse zum Abrufen einer Verweis auf die Farbe, in denen  *\<SystemColor >* ist der Name der gewünschten Systemfarbe.</span><span class="sxs-lookup"><span data-stu-id="f686c-103">To use a system color in a gradient, you use the *\<SystemColor>* Color and *\<SystemColor>* ColorKey static properties of the <xref:System.Windows.SystemColors> class to obtain a reference to the color, where *\<SystemColor>* is the name of the desired system color.</span></span> <span data-ttu-id="f686c-104">Verwenden der  *\<SystemColor >* ColorKey-Eigenschaften, wenn Sie einen dynamischen Verweis erstellen, die automatisch die Systemdesigns aktualisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f686c-104">Use the *\<SystemColor>* ColorKey properties when you want to create a dynamic reference that updates automatically as the system theme changes.</span></span> <span data-ttu-id="f686c-105">Verwenden Sie andernfalls die  *\<SystemColor >* Color-Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="f686c-105">Otherwise, use the *\<SystemColor>* Color properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f686c-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f686c-106">Example</span></span>  
 <span data-ttu-id="f686c-107">Im folgenden Beispiel wird ein Farbverlauf mithilfe dynamischer Systemfarbressourcen erstellt.</span><span class="sxs-lookup"><span data-stu-id="f686c-107">The following example uses dynamic system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemColorExample.xaml#graphicsmmdynamicsystemcolorgradientexamplewholepage)]  
  
 <span data-ttu-id="f686c-108">Im nächsten Beispiel wird ein Farbverlauf mithilfe statischer Systemfarbressourcen erstellt.</span><span class="sxs-lookup"><span data-stu-id="f686c-108">The next example uses static system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemColorExample.xaml#graphicsmmstaticsystemcolorgradientexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="f686c-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f686c-109">See also</span></span>
- <xref:System.Windows.SystemColors>
- [<span data-ttu-id="f686c-110">Zeichnen eines Bereichs mit einem Systempinsel</span><span class="sxs-lookup"><span data-stu-id="f686c-110">Paint an Area with a System Brush</span></span>](how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="f686c-111">Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen</span><span class="sxs-lookup"><span data-stu-id="f686c-111">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
