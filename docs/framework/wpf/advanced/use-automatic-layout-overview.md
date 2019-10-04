---
title: Übersicht über die Verwendung eines automatischen Layouts
ms.date: 03/30/2017
helpviewer_keywords:
- layout [WPF], automatic
- automatic layout [WPF]
ms.assetid: 6fed9264-18bb-4d05-8867-1fe356c6f687
ms.openlocfilehash: 0253c57f080705b648d9f416368d0fe974ac83ab
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834673"
---
# <a name="use-automatic-layout-overview"></a><span data-ttu-id="1d67a-102">Übersicht über die Verwendung eines automatischen Layouts</span><span class="sxs-lookup"><span data-stu-id="1d67a-102">Use Automatic Layout Overview</span></span>

<span data-ttu-id="1d67a-103">In diesem Thema werden Richtlinien für Entwickler zum Schreiben von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Anwendungen mit lokalisierbaren [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)] vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="1d67a-103">This topic introduces guidelines for developers on how to write [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applications with localizable [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)].</span></span> <span data-ttu-id="1d67a-104">In der Vergangenheit war die Lokalisierung einer Benutzeroberfläche ein zeitaufwändiger Prozess.</span><span class="sxs-lookup"><span data-stu-id="1d67a-104">In the past, localization of a UI was a time consuming process.</span></span> <span data-ttu-id="1d67a-105">Jede Sprache, für die die Benutzeroberfläche angepasst wurde, erforderte ein Pixel nach Pixel Anpassung.</span><span class="sxs-lookup"><span data-stu-id="1d67a-105">Each language that the UI was adapted for required a pixel by pixel adjustment.</span></span> <span data-ttu-id="1d67a-106">Mit den richtigen Entwurfs-und richtigen Codierungsstandards können [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] erstellt werden, sodass Lokalisierer weniger Größe und Neupositionierung haben.</span><span class="sxs-lookup"><span data-stu-id="1d67a-106">Today with the right design and right coding standards, [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] can be constructed so that localizers have less resizing and repositioning to do.</span></span> <span data-ttu-id="1d67a-107">Der Ansatz zum Schreiben von Anwendungen, die einfacher geändert und neu positioniert werden können, wird als automatisches Layout bezeichnet und kann mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungsdesign erreicht werden.</span><span class="sxs-lookup"><span data-stu-id="1d67a-107">The approach to writing applications that can be more easily resized and repositioned is called automatic layout, and can be achieved by using [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application design.</span></span>

<a name="advantages_of_autolayout"></a>

## <a name="advantages-of-using-automatic-layout"></a><span data-ttu-id="1d67a-108">Vorteile der Verwendung des automatischen Layouts</span><span class="sxs-lookup"><span data-stu-id="1d67a-108">Advantages of Using Automatic Layout</span></span>

<span data-ttu-id="1d67a-109">Da das Präsentationssystem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] leistungsstark und flexibel ist, bietet es die Möglichkeit, Elemente in einer Anwendung zu erstellen, die an die Anforderungen unterschiedlicher Sprachen angepasst werden können.</span><span class="sxs-lookup"><span data-stu-id="1d67a-109">Because the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presentation system is powerful and flexible, it provides the ability to layout elements in an application that can be adjusted to fit the requirements of different languages.</span></span> <span data-ttu-id="1d67a-110">Die folgende Liste hebt einige der Vorteile des automatischen Layouts hervor.</span><span class="sxs-lookup"><span data-stu-id="1d67a-110">The following list points out some of the advantages of automatic layout.</span></span>

- <span data-ttu-id="1d67a-111">Die Benutzeroberfläche wird in jeder Sprache gut angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1d67a-111">UI displays well  in any language.</span></span>

- <span data-ttu-id="1d67a-112">Reduziert nach der Übersetzung des Text die Notwendigkeit der Anpassung von Position und Größe von Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="1d67a-112">Reduces the need to readjust position and size of controls after text is translated.</span></span>

- <span data-ttu-id="1d67a-113">Reduziert die Notwendigkeit zur Anpassung der Fenstergröße.</span><span class="sxs-lookup"><span data-stu-id="1d67a-113">Reduces the need to readjust window size.</span></span>

- <span data-ttu-id="1d67a-114">Das Layout der Benutzeroberfläche wird in jeder beliebigen Sprache ordnungsgemäß</span><span class="sxs-lookup"><span data-stu-id="1d67a-114">UI layout renders properly in any language.</span></span>

- <span data-ttu-id="1d67a-115">Die Lokalisierung kann bis zu dem Punkt reduziert werden, dass sie nur wenig komplexer als eine Zeichenfolgeübersetzung ist.</span><span class="sxs-lookup"><span data-stu-id="1d67a-115">Localization can be reduced to the point that it is little more than string translation.</span></span>

<a name="autolayout_controls"></a>

## <a name="automatic-layout-and-controls"></a><span data-ttu-id="1d67a-116">Automatisches Layout und Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="1d67a-116">Automatic Layout and Controls</span></span>

<span data-ttu-id="1d67a-117">Das automatische Layout ermöglicht einer Anwendung die automatisch Anpassung der Größe eines Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="1d67a-117">Automatic layout enables an application to adjust the size of a control automatically.</span></span> <span data-ttu-id="1d67a-118">Beispielsweise kann ein Steuerelement so geändert werden, dass es die Länge einer Zeichenfolge aufnimmt.</span><span class="sxs-lookup"><span data-stu-id="1d67a-118">For example, a control can change to accommodate the length of a string.</span></span> <span data-ttu-id="1d67a-119">Diese Funktion ermöglicht Lokalisierern die Übersetzung der Zeichenfolge. Es ist nicht mehr notwendig, die Größe des Steuerelements an den übersetzten Text anzupassen.</span><span class="sxs-lookup"><span data-stu-id="1d67a-119">This capability enables  localizers to translate the string; they no longer need to resize the control to fit the translated text.</span></span> <span data-ttu-id="1d67a-120">Im folgende Beispiel wird eine Schaltfläche mit englischen Inhalt erstellt.</span><span class="sxs-lookup"><span data-stu-id="1d67a-120">The following example creates a button with English content.</span></span>

[!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]

<span data-ttu-id="1d67a-121">Alles, was Sie in diesem Beispiel tun müssen, um eine spanische Schaltfläche zu erstellen, ist das Ändern des Texts.</span><span class="sxs-lookup"><span data-stu-id="1d67a-121">In the example, all you have to do to make a Spanish button is change the text.</span></span> <span data-ttu-id="1d67a-122">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="1d67a-122">For example,</span></span>

[!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]

<span data-ttu-id="1d67a-123">Die folgende Grafik zeigt die Ausgabe der Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="1d67a-123">The following graphic shows the output of the code samples:</span></span>

![Die gleiche Schaltfläche mit Text in unterschiedlichen Sprachen](./media/use-automatic-layout-overview/auto-resizable-button.png)

<a name="autolayout_coding"></a>

## <a name="automatic-layout-and-coding-standards"></a><span data-ttu-id="1d67a-125">Automatisches Layout und Codierungsstandards</span><span class="sxs-lookup"><span data-stu-id="1d67a-125">Automatic Layout and Coding Standards</span></span>

<span data-ttu-id="1d67a-126">Die Verwendung des automatischen Layoutansatzes erfordert eine Reihe von Codierungs-und Entwurfs Standards und Regeln, um eine vollständig lokalisierbare Benutzeroberfläche zu erstellen</span><span class="sxs-lookup"><span data-stu-id="1d67a-126">Using the automatic layout approach requires a set of coding and design standards and rules to produce a fully localizable UI.</span></span> <span data-ttu-id="1d67a-127">Die folgenden Richtlinien werden Ihnen bei der automatischen Layoutcodierung helfen .</span><span class="sxs-lookup"><span data-stu-id="1d67a-127">The following guidelines will aid your automatic layout coding.</span></span>

<span data-ttu-id="1d67a-128">**Keine absoluten Positionen verwenden**</span><span class="sxs-lookup"><span data-stu-id="1d67a-128">**Do not use absolute positions**</span></span>

- <span data-ttu-id="1d67a-129">Verwenden Sie <xref:System.Windows.Controls.Canvas> nicht, da Elemente absolut positioniert werden.</span><span class="sxs-lookup"><span data-stu-id="1d67a-129">Do not use <xref:System.Windows.Controls.Canvas> because it positions elements absolutely.</span></span>

- <span data-ttu-id="1d67a-130">Verwenden Sie <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel> und <xref:System.Windows.Controls.Grid>, um Steuerelemente zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="1d67a-130">Use <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel>, and <xref:System.Windows.Controls.Grid> to position controls.</span></span>

<span data-ttu-id="1d67a-131">Eine Erläuterung zu den verschiedenen Arten von Panels finden Sie unter [Übersicht über Panels](../controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1d67a-131">For a discussion about various types of panels, see [Panels Overview](../controls/panels-overview.md).</span></span>

<span data-ttu-id="1d67a-132">**Legen Sie keine festgelegte Größe für ein Fenster fest.**</span><span class="sxs-lookup"><span data-stu-id="1d67a-132">**Do not set a fixed size for a window**</span></span>

- <span data-ttu-id="1d67a-133">Verwenden Sie <xref:System.Windows.Window.SizeToContent%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1d67a-133">Use <xref:System.Windows.Window.SizeToContent%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1d67a-134">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1d67a-134">For example:</span></span>

  [!code-xaml[LocalizationGrid#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)]

<span data-ttu-id="1d67a-135">**Hinzufügen einer <xref:System.Windows.FrameworkElement.FlowDirection%2A>**</span><span class="sxs-lookup"><span data-stu-id="1d67a-135">**Add a <xref:System.Windows.FrameworkElement.FlowDirection%2A>**</span></span>

- <span data-ttu-id="1d67a-136">Fügen Sie dem Stamm Element der Anwendung eine <xref:System.Windows.FrameworkElement.FlowDirection%2A> hinzu.</span><span class="sxs-lookup"><span data-stu-id="1d67a-136">Add a <xref:System.Windows.FrameworkElement.FlowDirection%2A> to the root element of your application.</span></span>

  <span data-ttu-id="1d67a-137">WPF bietet eine bequeme Möglichkeit zur Unterstützung von horizontalen, bidirektionalen und vertikalen Layouts.</span><span class="sxs-lookup"><span data-stu-id="1d67a-137">WPF provides a convenient way to support horizontal, bidirectional, and vertical layouts.</span></span> <span data-ttu-id="1d67a-138">In Presentation Framework kann die <xref:System.Windows.FrameworkElement.FlowDirection%2A>-Eigenschaft verwendet werden, um das Layout zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1d67a-138">In presentation framework, the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property can be used to define layout.</span></span> <span data-ttu-id="1d67a-139">Die Muster der Flussrichtung sind:Die flussrichtung Muster sind:</span><span class="sxs-lookup"><span data-stu-id="1d67a-139">The flow-direction patterns are:</span></span>

  - <span data-ttu-id="1d67a-140"><xref:System.Windows.FlowDirection.LeftToRight?displayProperty=nameWithType> (LrTb) – horizontales Layout für Lateinisch, ostasiatisch usw.</span><span class="sxs-lookup"><span data-stu-id="1d67a-140"><xref:System.Windows.FlowDirection.LeftToRight?displayProperty=nameWithType> (LrTb) — horizontal layout for Latin, East Asian, and so forth.</span></span>

  - <span data-ttu-id="1d67a-141"><xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> (RLTB) – bidirektional für Arabisch, Hebräisch usw.</span><span class="sxs-lookup"><span data-stu-id="1d67a-141"><xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> (RlTb) — bidirectional for Arabic, Hebrew, and so forth.</span></span>

<span data-ttu-id="1d67a-142">**Verwenden von zusammengesetzten Schriftarten anstelle physischer Schriftarten**</span><span class="sxs-lookup"><span data-stu-id="1d67a-142">**Use composite fonts instead of physical fonts**</span></span>

- <span data-ttu-id="1d67a-143">Bei zusammengesetzten Schriftarten muss die <xref:System.Windows.Controls.Control.FontFamily%2A>-Eigenschaft nicht lokalisiert werden.</span><span class="sxs-lookup"><span data-stu-id="1d67a-143">With composite fonts, the <xref:System.Windows.Controls.Control.FontFamily%2A> property does not need to be localized.</span></span>

- <span data-ttu-id="1d67a-144">Entwickler können eine der folgenden Schriftarten verwenden oder ihre eigenen erstellen.</span><span class="sxs-lookup"><span data-stu-id="1d67a-144">Developers can use one of the following fonts or create their own.</span></span>

  - <span data-ttu-id="1d67a-145">Globale Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="1d67a-145">Global User Interface</span></span>
  - <span data-ttu-id="1d67a-146">Global San Serif</span><span class="sxs-lookup"><span data-stu-id="1d67a-146">Global San Serif</span></span>
  - <span data-ttu-id="1d67a-147">Global Serif</span><span class="sxs-lookup"><span data-stu-id="1d67a-147">Global Serif</span></span>

<span data-ttu-id="1d67a-148">**XML hinzufügen: lang**</span><span class="sxs-lookup"><span data-stu-id="1d67a-148">**Add xml:lang**</span></span>

- <span data-ttu-id="1d67a-149">Fügen Sie das `xml:lang`-Attribut im Root-Element ihrer Benutzeroberfläche hinzu, z. b. `xml:lang="en-US"` für eine englische Anwendung.</span><span class="sxs-lookup"><span data-stu-id="1d67a-149">Add the `xml:lang` attribute in the root element of your UI, such as `xml:lang="en-US"` for an English application.</span></span>

- <span data-ttu-id="1d67a-150">Da zusammengesetzte Schriftarten `xml:lang` verwenden, um zu bestimmen, welche Schriftart verwendet werden soll, legen Sie diese Eigenschaft fest, um mehrsprachige Szenarien</span><span class="sxs-lookup"><span data-stu-id="1d67a-150">Because composite fonts use `xml:lang` to determine what font to use, set this property to support multilingual scenarios.</span></span>

<a name="autolay_grids"></a>

## <a name="automatic-layout-and-grids"></a><span data-ttu-id="1d67a-151">Automatisches Layout und Raster</span><span class="sxs-lookup"><span data-stu-id="1d67a-151">Automatic Layout and Grids</span></span>

<span data-ttu-id="1d67a-152">Das <xref:System.Windows.Controls.Grid>-Element ist für das automatische Layout nützlich, da es einem Entwickler ermöglicht, Elemente zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="1d67a-152">The <xref:System.Windows.Controls.Grid> element, is useful for automatic layout because it enables a developer to position elements.</span></span> <span data-ttu-id="1d67a-153">Ein <xref:System.Windows.Controls.Grid>-Steuerelement ist in der Lage, mithilfe einer Spalten-und Zeilen Anordnung den verfügbaren Platz unter seinen untergeordneten Elementen zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="1d67a-153">A <xref:System.Windows.Controls.Grid> control is capable of distributing the available space among its child elements, using a column and row arrangement.</span></span> <span data-ttu-id="1d67a-154">Die Benutzeroberflächen Elemente können mehrere Zellen umfassen, und es ist möglich, Raster in Raster zu haben.</span><span class="sxs-lookup"><span data-stu-id="1d67a-154">The UI elements can span multiple cells, and it is possible to have grids within grids.</span></span> <span data-ttu-id="1d67a-155">Raster sind nützlich, da Sie Ihnen ermöglichen, eine komplexe Benutzeroberfläche zu erstellen und zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="1d67a-155">Grids are useful because they enable you to create and position complex UI.</span></span> <span data-ttu-id="1d67a-156">Im folgende Beispiel wird veranschaulicht, wie mit einem Raster einige Schaltflächen und Text positioniert werden.</span><span class="sxs-lookup"><span data-stu-id="1d67a-156">The following example demonstrates using a grid to position some buttons and text.</span></span> <span data-ttu-id="1d67a-157">Beachten Sie, dass die Höhe und Breite der Zellen auf "<xref:System.Windows.GridUnitType.Auto>" festgelegt ist. Daher wird die Zelle, die die Schaltfläche mit einem Bild enthält, an das Bild angepasst.</span><span class="sxs-lookup"><span data-stu-id="1d67a-157">Notice that the height and width of the cells are set to <xref:System.Windows.GridUnitType.Auto>; therefore, the cell that contains the button with an image adjusts to fit the image.</span></span>

[!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]

<span data-ttu-id="1d67a-158">Die folgende Grafik zeigt die vom vorherigen Code erzeugten Raster.</span><span class="sxs-lookup"><span data-stu-id="1d67a-158">The following graphic shows the grid produced by the previous code.</span></span>

<span data-ttu-id="1d67a-159">![Raster Beispiel](./media/glob-grid.png "glob_grid") Raster</span><span class="sxs-lookup"><span data-stu-id="1d67a-159">![Grid example](./media/glob-grid.png "glob_grid") Grid</span></span>

<a name="autolay_grids_issharedsizescope"></a>

## <a name="automatic-layout-and-grids-using-the-issharedsizescope-property"></a><span data-ttu-id="1d67a-160">Automatisches Layout und Raster mit der IsSharedSizeScope-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1d67a-160">Automatic Layout and Grids Using the IsSharedSizeScope Property</span></span>

<span data-ttu-id="1d67a-161">Ein <xref:System.Windows.Controls.Grid>-Element ist in lokalisierbaren Anwendungen hilfreich, um Steuerelemente zu erstellen, die an den Inhalt angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="1d67a-161">A <xref:System.Windows.Controls.Grid> element is useful in localizable applications to create controls that adjust to fit content.</span></span> <span data-ttu-id="1d67a-162">Manchmal ist es jedoch notwendig, dass Steuerelemente unabhängig vom Inhalt eine bestimmte Größe beibehalten.</span><span class="sxs-lookup"><span data-stu-id="1d67a-162">However, at times you want controls to maintain a particular size regardless of content.</span></span> <span data-ttu-id="1d67a-163">Beispielsweise sollen die Schaltflächen „OK“, „Abbrechen“ und „Durchsuchen“ wahrscheinlich nicht die Größe des Inhalts angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="1d67a-163">For example, if you have "OK", "Cancel" and "Browse" buttons you probably do not want the buttons sized to fit the content.</span></span> <span data-ttu-id="1d67a-164">In diesem Fall ist die angefügte <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType>-Eigenschaft für die gemeinsame Nutzung derselben Größe in mehreren Raster Elementen nützlich.</span><span class="sxs-lookup"><span data-stu-id="1d67a-164">In this case the <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> attached property is useful for sharing the same sizing among multiple grid elements.</span></span> <span data-ttu-id="1d67a-165">Im folgenden Beispiel wird veranschaulicht, wie Spalten-und Zeilen Größendaten zwischen mehreren <xref:System.Windows.Controls.Grid>-Elementen gemeinsam genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="1d67a-165">The following example demonstrates how to share column and row sizing data between multiple <xref:System.Windows.Controls.Grid> elements.</span></span>

[!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]

> [!NOTE]
> <span data-ttu-id="1d67a-166">Das Codebeispiel für den gesamten Code finden Sie unter [Freigeben von Größen Eigenschaften zwischen](../controls/how-to-share-sizing-properties-between-grids.md)Rastern.</span><span class="sxs-lookup"><span data-stu-id="1d67a-166">For the complete code sample, see [Share Sizing Properties Between Grids](../controls/how-to-share-sizing-properties-between-grids.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1d67a-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d67a-167">See also</span></span>

- [<span data-ttu-id="1d67a-168">Globalisierung für WPF</span><span class="sxs-lookup"><span data-stu-id="1d67a-168">Globalization for WPF</span></span>](globalization-for-wpf.md)
- [<span data-ttu-id="1d67a-169">Verwenden des automatischen Layouts zum Erstellen einer Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="1d67a-169">Use Automatic Layout to Create a Button</span></span>](how-to-use-automatic-layout-to-create-a-button.md)
- [<span data-ttu-id="1d67a-170">Verwenden eines Rasters für automatisches Layout</span><span class="sxs-lookup"><span data-stu-id="1d67a-170">Use a Grid for Automatic Layout</span></span>](how-to-use-a-grid-for-automatic-layout.md)
