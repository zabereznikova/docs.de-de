---
title: Übersicht über die Verwendung eines automatischen Layouts
ms.date: 03/30/2017
helpviewer_keywords:
- layout [WPF], automatic
- automatic layout [WPF]
ms.assetid: 6fed9264-18bb-4d05-8867-1fe356c6f687
ms.openlocfilehash: 74c4e10e8f28fb00a5528c1ab860b88d0caa4303
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2019
ms.locfileid: "58408755"
---
# <a name="use-automatic-layout-overview"></a><span data-ttu-id="69dce-102">Übersicht über die Verwendung eines automatischen Layouts</span><span class="sxs-lookup"><span data-stu-id="69dce-102">Use Automatic Layout Overview</span></span>
<span data-ttu-id="69dce-103">In diesem Thema werden Richtlinien für Entwickler zum Schreiben von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] -Anwendungen mit lokalisierbarem [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69dce-103">This topic introduces guidelines for developers on how to write [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applications with localizable [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)].</span></span> <span data-ttu-id="69dce-104">In der Vergangenheit nahm die Lokalisierung einer Benutzeroberfläche viel Zeit in Anspruch.</span><span class="sxs-lookup"><span data-stu-id="69dce-104">In the past, localization of a UI was a time consuming process.</span></span> <span data-ttu-id="69dce-105">Jede Sprache, die für die Benutzeroberfläche angepasst wurde, benötigt eine pixelweise Anpassung.</span><span class="sxs-lookup"><span data-stu-id="69dce-105">Each language that the UI was adapted for required a pixel by pixel adjustment.</span></span> <span data-ttu-id="69dce-106">Sofort mit dem richtigen Entwurfs- und Codierungsstandards können [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] konstruiert werden kann, sodass Lokalisierer Ändern der Größe und die neupositionierung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="69dce-106">Today with the right design and right coding standards, [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] can be constructed so that localizers have less resizing and repositioning to do.</span></span> <span data-ttu-id="69dce-107">Der Ansatz zum Schreiben von Anwendungen, die einfacher geändert und neu positioniert werden können ist als automatisches Layout bezeichnet und kann erreicht werden, indem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungsentwurf.</span><span class="sxs-lookup"><span data-stu-id="69dce-107">The approach to writing applications that can be more easily resized and repositioned is called automatic layout, and can be achieved by using [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application design.</span></span>  

<a name="advantages_of_autolayout"></a>   
## <a name="advantages-of-using-automatic-layout"></a><span data-ttu-id="69dce-108">Vorteile der Verwendung des automatischen Layouts</span><span class="sxs-lookup"><span data-stu-id="69dce-108">Advantages of Using Automatic Layout</span></span>  
 <span data-ttu-id="69dce-109">Da die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Präsentationssystem ist leistungsfähiger und flexibler, es bietet die Möglichkeit, Elemente in einer Anwendung, die die Anforderungen für verschiedene Sprachen angepasst werden kann.</span><span class="sxs-lookup"><span data-stu-id="69dce-109">Because the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presentation system is powerful and flexible, it provides the ability to layout elements in an application that can be adjusted to fit the requirements of different languages.</span></span> <span data-ttu-id="69dce-110">Die folgende Liste hebt einige der Vorteile des automatischen Layouts hervor.</span><span class="sxs-lookup"><span data-stu-id="69dce-110">The following list points out some of the advantages of automatic layout.</span></span>  

-   <span data-ttu-id="69dce-111">Benutzeroberfläche wird in jeder Sprache gut angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="69dce-111">UI displays well  in any language.</span></span>  

-   <span data-ttu-id="69dce-112">Reduziert nach der Übersetzung des Text die Notwendigkeit der Anpassung von Position und Größe von Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="69dce-112">Reduces the need to readjust position and size of controls after text is translated.</span></span>  
  
-   <span data-ttu-id="69dce-113">Reduziert die Notwendigkeit zur Anpassung der Fenstergröße.</span><span class="sxs-lookup"><span data-stu-id="69dce-113">Reduces the need to readjust window size.</span></span>  

-   <span data-ttu-id="69dce-114">Layout der Benutzeroberfläche, die korrekt in einer beliebigen Sprache gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="69dce-114">UI layout renders properly in any language.</span></span>  

-   <span data-ttu-id="69dce-115">Die Lokalisierung kann bis zu dem Punkt reduziert werden, dass sie nur wenig komplexer als eine Zeichenfolgeübersetzung ist.</span><span class="sxs-lookup"><span data-stu-id="69dce-115">Localization can be reduced to the point that it is little more than string translation.</span></span>  
  
<a name="autolayout_controls"></a>   
## <a name="automatic-layout-and-controls"></a><span data-ttu-id="69dce-116">Automatisches Layout und Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="69dce-116">Automatic Layout and Controls</span></span>  
 <span data-ttu-id="69dce-117">Das automatische Layout ermöglicht einer Anwendung die automatisch Anpassung der Größe eines Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="69dce-117">Automatic layout enables an application to adjust the size of a control automatically.</span></span> <span data-ttu-id="69dce-118">Beispielsweise kann ein Steuerelement so geändert werden, dass es die Länge einer Zeichenfolge aufnimmt.</span><span class="sxs-lookup"><span data-stu-id="69dce-118">For example, a control can change to accommodate the length of a string.</span></span> <span data-ttu-id="69dce-119">Diese Funktion ermöglicht Lokalisierern die Übersetzung der Zeichenfolge. Es ist nicht mehr notwendig, die Größe des Steuerelements an den übersetzten Text anzupassen.</span><span class="sxs-lookup"><span data-stu-id="69dce-119">This capability enables  localizers to translate the string; they no longer need to resize the control to fit the translated text.</span></span> <span data-ttu-id="69dce-120">Im folgende Beispiel wird eine Schaltfläche mit englischen Inhalt erstellt.</span><span class="sxs-lookup"><span data-stu-id="69dce-120">The following example creates a button with English content.</span></span>  
  
 [!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="69dce-121">Alles, was Sie in diesem Beispiel tun müssen, um eine spanische Schaltfläche zu erstellen, ist das Ändern des Texts.</span><span class="sxs-lookup"><span data-stu-id="69dce-121">In the example, all you have to do to make a Spanish button is change the text.</span></span> <span data-ttu-id="69dce-122">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="69dce-122">For example,</span></span>  
  
 [!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="69dce-123">Die folgende Abbildung zeigt die Ausgabe der Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="69dce-123">The following graphic shows the output of the code samples:</span></span>  
  
 ![Die gleiche Schaltfläche mit Text in unterschiedlichen Sprachen](./media/use-automatic-layout-overview/auto-resizable-button.png)  
  
<a name="autolayout_coding"></a>   
## <a name="automatic-layout-and-coding-standards"></a><span data-ttu-id="69dce-125">Automatisches Layout und Codierungsstandards</span><span class="sxs-lookup"><span data-stu-id="69dce-125">Automatic Layout and Coding Standards</span></span>  
 <span data-ttu-id="69dce-126">Verwenden des automatischen layoutansatzes erfordert einen Satz von Programmieren und Entwurfsstandards sowie Regeln, um eine vollständig lokalisierbare Benutzeroberfläche zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="69dce-126">Using the automatic layout approach requires a set of coding and design standards and rules to produce a fully localizable UI.</span></span> <span data-ttu-id="69dce-127">Die folgenden Richtlinien werden Ihnen bei der automatischen Layoutcodierung helfen .</span><span class="sxs-lookup"><span data-stu-id="69dce-127">The following guidelines will aid your automatic layout coding.</span></span>  

<span data-ttu-id="69dce-128">**Verwenden Sie nicht die absolute Positionen**</span><span class="sxs-lookup"><span data-stu-id="69dce-128">**Do not use absolute positions**</span></span>

- <span data-ttu-id="69dce-129">Verwenden Sie keine <xref:System.Windows.Controls.Canvas> , weil dieses Elemente absolut positioniert.</span><span class="sxs-lookup"><span data-stu-id="69dce-129">Do not use <xref:System.Windows.Controls.Canvas> because it positions elements absolutely.</span></span>

- <span data-ttu-id="69dce-130">Verwendung <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel>, und <xref:System.Windows.Controls.Grid> um Steuerelemente zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="69dce-130">Use <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel>, and <xref:System.Windows.Controls.Grid> to position controls.</span></span>

<span data-ttu-id="69dce-131">Weitere Informationen zu verschiedenen Bereichen, finden Sie unter [Panels Overview](../controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="69dce-131">For a discussion about various types of panels, see [Panels Overview](../controls/panels-overview.md).</span></span>

<span data-ttu-id="69dce-132">**Legen Sie eine feste Größe für ein Fenster nicht**</span><span class="sxs-lookup"><span data-stu-id="69dce-132">**Do not set a fixed size for a window**</span></span>

- <span data-ttu-id="69dce-133">Verwenden Sie <xref:System.Windows.Window.SizeToContent%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="69dce-133">Use <xref:System.Windows.Window.SizeToContent%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="69dce-134">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="69dce-134">For example:</span></span>

   [!code-xaml[LocalizationGrid#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)]

<span data-ttu-id="69dce-135">**Hinzufügen einer <xref:System.Windows.FrameworkElement.FlowDirection%2A>**</span><span class="sxs-lookup"><span data-stu-id="69dce-135">**Add a <xref:System.Windows.FrameworkElement.FlowDirection%2A>**</span></span>

- <span data-ttu-id="69dce-136">Hinzufügen einer <xref:System.Windows.FrameworkElement.FlowDirection%2A> auf das Stammelement der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="69dce-136">Add a <xref:System.Windows.FrameworkElement.FlowDirection%2A> to the root element of your application.</span></span>

   <span data-ttu-id="69dce-137">WPF bietet eine praktische Möglichkeit zur Unterstützung von horizontalen, bidirektionalen und vertikalen Layouts.</span><span class="sxs-lookup"><span data-stu-id="69dce-137">WPF provides a convenient way to support horizontal, bidirectional, and vertical layouts.</span></span> <span data-ttu-id="69dce-138">In Präsentationsframework das <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft kann verwendet werden, um das Layout zu definieren.</span><span class="sxs-lookup"><span data-stu-id="69dce-138">In presentation framework, the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property can be used to define layout.</span></span> <span data-ttu-id="69dce-139">Die Muster der Flussrichtung sind:Die flussrichtung Muster sind:</span><span class="sxs-lookup"><span data-stu-id="69dce-139">The flow-direction patterns are:</span></span>
   
     - <span data-ttu-id="69dce-140"><xref:System.Windows.FlowDirection.LeftToRight?displayProperty=nameWithType> (LrTb) — horizontales Layout für Latein, Ostasiatisch usw.</span><span class="sxs-lookup"><span data-stu-id="69dce-140"><xref:System.Windows.FlowDirection.LeftToRight?displayProperty=nameWithType> (LrTb) — horizontal layout for Latin, East Asian, and so forth.</span></span>
     
     - <span data-ttu-id="69dce-141"><xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> (RlTb) — bidirektional für Arabisch, Hebräisch und So weiter.</span><span class="sxs-lookup"><span data-stu-id="69dce-141"><xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> (RlTb) — bidirectional for Arabic, Hebrew, and so forth.</span></span>

<span data-ttu-id="69dce-142">**Verwenden Sie zusammengesetzte Schriftarten anstelle von physischen Schriftarten**</span><span class="sxs-lookup"><span data-stu-id="69dce-142">**Use composite fonts instead of physical fonts**</span></span>

- <span data-ttu-id="69dce-143">Bei zusammengesetzten Schriftarten der <xref:System.Windows.Controls.Control.FontFamily%2A> Eigenschaft muss nicht lokalisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="69dce-143">With composite fonts, the <xref:System.Windows.Controls.Control.FontFamily%2A> property does not need to be localized.</span></span>

- <span data-ttu-id="69dce-144">Entwickler können eine der folgenden Schriftarten verwenden oder ihre eigenen erstellen.</span><span class="sxs-lookup"><span data-stu-id="69dce-144">Developers can use one of the following fonts or create their own.</span></span>

   - <span data-ttu-id="69dce-145">Globale Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="69dce-145">Global User Interface</span></span>
   - <span data-ttu-id="69dce-146">Global San Serif</span><span class="sxs-lookup"><span data-stu-id="69dce-146">Global San Serif</span></span>
   - <span data-ttu-id="69dce-147">Global Serif</span><span class="sxs-lookup"><span data-stu-id="69dce-147">Global Serif</span></span>

<span data-ttu-id="69dce-148">**Fügen Sie XML: lang hinzu.**</span><span class="sxs-lookup"><span data-stu-id="69dce-148">**Add xml:lang**</span></span>

- <span data-ttu-id="69dce-149">Hinzufügen der `xml:lang` Attribut in das Stammelement der Benutzeroberfläche, z. B. `xml:lang="en-US"` für eine englische Anwendung.</span><span class="sxs-lookup"><span data-stu-id="69dce-149">Add the `xml:lang` attribute in the root element of your UI, such as `xml:lang="en-US"` for an English application.</span></span>

- <span data-ttu-id="69dce-150">Da zusammengesetzte Schriftarten `xml:lang` um zu bestimmen, welche Schriftart verwendet, legen Sie diese Eigenschaft zur Unterstützung von mehrsprachigen Szenarios.</span><span class="sxs-lookup"><span data-stu-id="69dce-150">Because composite fonts use `xml:lang` to determine what font to use, set this property to support multilingual scenarios.</span></span>

<a name="autolay_grids"></a>   
## <a name="automatic-layout-and-grids"></a><span data-ttu-id="69dce-151">Automatisches Layout und Raster</span><span class="sxs-lookup"><span data-stu-id="69dce-151">Automatic Layout and Grids</span></span>  
 <span data-ttu-id="69dce-152">Die <xref:System.Windows.Controls.Grid> -Element eignet sich für automatisches Layout, da es die Positionierung von Elementen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="69dce-152">The <xref:System.Windows.Controls.Grid> element, is useful for automatic layout because it enables a developer to position elements.</span></span> <span data-ttu-id="69dce-153">Ein <xref:System.Windows.Controls.Grid> Steuerelement ist in der Lage, den verfügbaren Platz auf seine untergeordneten Elemente, die mit einer Spalten- und zeilenanordnung zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="69dce-153">A <xref:System.Windows.Controls.Grid> control is capable of distributing the available space among its child elements, using a column and row arrangement.</span></span> <span data-ttu-id="69dce-154">Die Elemente der Benutzeroberfläche können mehrere Zellen umfassen, und es ist möglich, verschachtelte Raster aufweisen.</span><span class="sxs-lookup"><span data-stu-id="69dce-154">The UI elements can span multiple cells, and it is possible to have grids within grids.</span></span> <span data-ttu-id="69dce-155">Raster sind sehr hilfreich, da sie Ihnen ermöglichen das Erstellen und positionieren Sie komplexen Benutzeroberflächen.</span><span class="sxs-lookup"><span data-stu-id="69dce-155">Grids are useful because they enable you to create and position complex UI.</span></span> <span data-ttu-id="69dce-156">Im folgende Beispiel wird veranschaulicht, wie mit einem Raster einige Schaltflächen und Text positioniert werden.</span><span class="sxs-lookup"><span data-stu-id="69dce-156">The following example demonstrates using a grid to position some buttons and text.</span></span> <span data-ttu-id="69dce-157">Beachten Sie, die die Höhe und Breite der Zellen, um festgelegt werden <xref:System.Windows.GridUnitType.Auto>daher die Zelle mit der Schaltfläche mit einem Bild passt, das Bild angepasst.</span><span class="sxs-lookup"><span data-stu-id="69dce-157">Notice that the height and width of the cells are set to <xref:System.Windows.GridUnitType.Auto>; therefore, the cell that contains the button with an image adjusts to fit the image.</span></span>  

 [!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="69dce-158">Die folgende Grafik zeigt die vom vorherigen Code erzeugten Raster.</span><span class="sxs-lookup"><span data-stu-id="69dce-158">The following graphic shows the grid produced by the previous code.</span></span>  
  
 <span data-ttu-id="69dce-159">![Rasterbeispiel](./media/glob-grid.png "Glob_grid")</span><span class="sxs-lookup"><span data-stu-id="69dce-159">![Grid example](./media/glob-grid.png "glob_grid")</span></span>  
<span data-ttu-id="69dce-160">Raster</span><span class="sxs-lookup"><span data-stu-id="69dce-160">Grid</span></span>  
  
<a name="autolay_grids_issharedsizescope"></a>   
## <a name="automatic-layout-and-grids-using-the-issharedsizescope-property"></a><span data-ttu-id="69dce-161">Automatisches Layout und Raster mit der IsSharedSizeScope-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="69dce-161">Automatic Layout and Grids Using the IsSharedSizeScope Property</span></span>  
 <span data-ttu-id="69dce-162">Ein <xref:System.Windows.Controls.Grid> Element ist nützlich in lokalisierbaren Anwendungen um Steuerelemente zu erstellen, die an Inhalt anpassen.</span><span class="sxs-lookup"><span data-stu-id="69dce-162">A <xref:System.Windows.Controls.Grid> element is useful in localizable applications to create controls that adjust to fit content.</span></span> <span data-ttu-id="69dce-163">Manchmal ist es jedoch notwendig, dass Steuerelemente unabhängig vom Inhalt eine bestimmte Größe beibehalten.</span><span class="sxs-lookup"><span data-stu-id="69dce-163">However, at times you want controls to maintain a particular size regardless of content.</span></span> <span data-ttu-id="69dce-164">Beispielsweise sollen die Schaltflächen „OK“, „Abbrechen“ und „Durchsuchen“ wahrscheinlich nicht die Größe des Inhalts angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="69dce-164">For example, if you have "OK", "Cancel" and "Browse" buttons you probably do not want the buttons sized to fit the content.</span></span> <span data-ttu-id="69dce-165">In diesem Fall die <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> angefügte Eigenschaft ist nützlich für dieselbe Größe in mehreren Rasterelementen.</span><span class="sxs-lookup"><span data-stu-id="69dce-165">In this case the <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> attached property is useful for sharing the same sizing among multiple grid elements.</span></span> <span data-ttu-id="69dce-166">Im folgende Beispiel wird veranschaulicht, wie Spalten- und Zeilengröße zwischen mehreren Teilen <xref:System.Windows.Controls.Grid> Elemente.</span><span class="sxs-lookup"><span data-stu-id="69dce-166">The following example demonstrates how to share column and row sizing data between multiple <xref:System.Windows.Controls.Grid> elements.</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="69dce-167">**Beachten Sie** das vollständige Codebeispiel finden Sie unter [Freigabe Sizing Eigenschaften zwischen Grids](../controls/how-to-share-sizing-properties-between-grids.md)</span><span class="sxs-lookup"><span data-stu-id="69dce-167">**Note** For the complete code sample, see [Share Sizing Properties Between Grids](../controls/how-to-share-sizing-properties-between-grids.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69dce-168">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69dce-168">See also</span></span>
- [<span data-ttu-id="69dce-169">Globalisierung für WPF</span><span class="sxs-lookup"><span data-stu-id="69dce-169">Globalization for WPF</span></span>](globalization-for-wpf.md)
- [<span data-ttu-id="69dce-170">Verwenden des automatischen Layouts zum Erstellen einer Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="69dce-170">Use Automatic Layout to Create a Button</span></span>](how-to-use-automatic-layout-to-create-a-button.md)
- [<span data-ttu-id="69dce-171">Verwenden eines Rasters für automatisches Layout</span><span class="sxs-lookup"><span data-stu-id="69dce-171">Use a Grid for Automatic Layout</span></span>](how-to-use-a-grid-for-automatic-layout.md)
