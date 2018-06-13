---
title: 'Gewusst wie: Zeichnen eines Bereichs mit einem Systempinsel'
ms.date: 03/30/2017
helpviewer_keywords:
- system brushes [WPF], painting with
- painting [WPF], with system brushes
- brushes [WPF], painting with system brushes [WPF]
ms.assetid: 5141a763-9235-42cb-a6bb-afc75513eac7
ms.openlocfilehash: f8a66ffc283016d65a17b33e98ce28fe4cd1c242
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561146"
---
# <a name="how-to-paint-an-area-with-a-system-brush"></a><span data-ttu-id="5d493-102">Gewusst wie: Zeichnen eines Bereichs mit einem Systempinsel</span><span class="sxs-lookup"><span data-stu-id="5d493-102">How to: Paint an Area with a System Brush</span></span>
<span data-ttu-id="5d493-103">Die <xref:System.Windows.SystemColors> Klasse bietet Zugriff auf Systempinsel und Farben, z. B. <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A>, und <xref:System.Windows.SystemColors.DesktopBrush%2A>.</span><span class="sxs-lookup"><span data-stu-id="5d493-103">The <xref:System.Windows.SystemColors> class provides access to system brushes and colors, such as <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A>, and <xref:System.Windows.SystemColors.DesktopBrush%2A>.</span></span> <span data-ttu-id="5d493-104">Ein Systempinsel ist ein <xref:System.Windows.Media.SolidColorBrush> -Objekt, das einen Bereich mit der angegebenen Systemfarbe zeichnet.</span><span class="sxs-lookup"><span data-stu-id="5d493-104">A system brush is a <xref:System.Windows.Media.SolidColorBrush> object that paints an area with the specified system color.</span></span> <span data-ttu-id="5d493-105">Ein Systempinsel erzeugt immer eine Volltonfüllung und kann nicht zur Erstellung eines Farbverlaufs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5d493-105">A system brush always produces a solid fill; it can't be used to create a gradient.</span></span>  
  
 <span data-ttu-id="5d493-106">Sie können Systempinsel als statische oder dynamische Ressource verwenden.</span><span class="sxs-lookup"><span data-stu-id="5d493-106">You can use system brushes as either a static or a dynamic resource.</span></span> <span data-ttu-id="5d493-107">Verwenden Sie eine dynamische Ressource, wenn der Pinsel automatisch aktualisiert werden soll, wenn der Benutzer den Systempinsel bei laufender Anwendung ändert. Verwenden Sie andernfalls eine statische Ressource.</span><span class="sxs-lookup"><span data-stu-id="5d493-107">Use a dynamic resource if you want the brush to update automatically if the user changes the system brush as the application is running; otherwise, use a static resource.</span></span> <span data-ttu-id="5d493-108">Die SystemColors-Klasse enthält eine Vielzahl von statischen Eigenschaften, die einer strengen Namenskonvention folgen:</span><span class="sxs-lookup"><span data-stu-id="5d493-108">The SystemColors class contains a variety of static properties that follow a strict naming convention:</span></span>  
  
-   <span data-ttu-id="5d493-109">*\<SystemColor>* Brush</span><span class="sxs-lookup"><span data-stu-id="5d493-109">*\<SystemColor>* Brush</span></span>  
  
     <span data-ttu-id="5d493-110">Ruft einen statischen Verweis auf eine <xref:System.Windows.Media.SolidColorBrush> der angegebenen Farbe.</span><span class="sxs-lookup"><span data-stu-id="5d493-110">Gets a static reference to a <xref:System.Windows.Media.SolidColorBrush> of the specified system color.</span></span>  
  
-   <span data-ttu-id="5d493-111">*\<SystemColor>* BrushKey</span><span class="sxs-lookup"><span data-stu-id="5d493-111">*\<SystemColor>* BrushKey</span></span>  
  
     <span data-ttu-id="5d493-112">Ruft einen dynamischen Verweis auf eine <xref:System.Windows.Media.SolidColorBrush> der angegebenen Farbe.</span><span class="sxs-lookup"><span data-stu-id="5d493-112">Gets a dynamic reference to a <xref:System.Windows.Media.SolidColorBrush> of the specified system color.</span></span>  
  
-   <span data-ttu-id="5d493-113">*\<SystemColor>* Color</span><span class="sxs-lookup"><span data-stu-id="5d493-113">*\<SystemColor>* Color</span></span>  
  
     <span data-ttu-id="5d493-114">Ruft einen statischen Verweis auf eine <xref:System.Windows.Media.Color> Struktur der angegebenen Farbe.</span><span class="sxs-lookup"><span data-stu-id="5d493-114">Gets a static reference to a <xref:System.Windows.Media.Color> structure of the specified system color.</span></span>  
  
-   <span data-ttu-id="5d493-115">*\<SystemColor>* ColorKey</span><span class="sxs-lookup"><span data-stu-id="5d493-115">*\<SystemColor>* ColorKey</span></span>  
  
     <span data-ttu-id="5d493-116">Ruft einen dynamischen Verweis auf die <xref:System.Windows.Media.Color> Struktur der angegebenen Farbe.</span><span class="sxs-lookup"><span data-stu-id="5d493-116">Gets a dynamic reference to the <xref:System.Windows.Media.Color> structure of the specified system color.</span></span>  
  
 <span data-ttu-id="5d493-117">Eine Systemfarbe ist eine <xref:System.Windows.Media.Color> -Struktur, die zur Konfiguration eines Pinsels verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="5d493-117">A system color is a <xref:System.Windows.Media.Color> structure that can be used to configure a brush.</span></span> <span data-ttu-id="5d493-118">Sie können z. B. einen Farbverlauf mit Systemfarben einstellen Erstellen der <xref:System.Windows.Media.GradientStop.Color%2A> Eigenschaften einer <xref:System.Windows.Media.LinearGradientBrush> objektspezifischen Farbverlaufsstopps mit Systemfarben.</span><span class="sxs-lookup"><span data-stu-id="5d493-118">For example, you can create a gradient using system colors by setting the <xref:System.Windows.Media.GradientStop.Color%2A> properties of a <xref:System.Windows.Media.LinearGradientBrush> object's gradient stops with system colors.</span></span> <span data-ttu-id="5d493-119">Ein Beispiel finden Sie unter [Systemfarben in einem Farbverlauf verwenden](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).</span><span class="sxs-lookup"><span data-stu-id="5d493-119">For an example, see [Use System Colors in a Gradient](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d493-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5d493-120">Example</span></span>  
 <span data-ttu-id="5d493-121">Im folgenden Beispiel wird ein dynamischer Verweis auf einen Systempinsel verwendet, um den Hintergrund einer Schaltfläche festzulegen.</span><span class="sxs-lookup"><span data-stu-id="5d493-121">The following example uses a dynamic system brush reference to set the Background of a button.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorDesktopBrushKeyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemBrushExample.xaml#graphicsmmdynamicsystemcolordesktopbrushkeyexamplewholepage)]  
  
 <span data-ttu-id="5d493-122">Im nächsten Beispiel wird ein statischer Verweis auf einen Systempinsel verwendet, um den Hintergrund einer Schaltfläche festzulegen.</span><span class="sxs-lookup"><span data-stu-id="5d493-122">The next example uses a static system brush reference to set the Background of a button.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorDesktopBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemBrushExample.xaml#graphicsmmstaticsystemcolordesktopbrushexamplewholepage)]  
  
 <span data-ttu-id="5d493-123">Ein Beispiel zum Verwenden einer Systemfarbe in einem Farbverlauf, finden Sie unter [Systemfarben verwenden, in einem Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).</span><span class="sxs-lookup"><span data-stu-id="5d493-123">For an example showing how to use a system color in a gradient, see [Use System Colors in a Gradient](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d493-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d493-124">See Also</span></span>  
 [<span data-ttu-id="5d493-125">Verwenden von Systemfarben in einem Farbverlauf</span><span class="sxs-lookup"><span data-stu-id="5d493-125">Use System Colors in a Gradient</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md)  
 [<span data-ttu-id="5d493-126">Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen</span><span class="sxs-lookup"><span data-stu-id="5d493-126">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
