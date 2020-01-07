---
title: 'Gewusst wie: Verwenden von SystemFonts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
ms.openlocfilehash: 157565ceb9057049aef8b2bf274847d58c6b8dc8
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559962"
---
# <a name="how-to-use-systemfonts"></a><span data-ttu-id="8c28e-102">Gewusst wie: Verwenden von SystemFonts</span><span class="sxs-lookup"><span data-stu-id="8c28e-102">How to: Use SystemFonts</span></span>
<span data-ttu-id="8c28e-103">In diesem Beispiel wird gezeigt, wie die statischen Ressourcen der <xref:System.Windows.SystemFonts>-Klasse verwendet werden, um eine Schaltfläche zu formatieren oder anzupassen.</span><span class="sxs-lookup"><span data-stu-id="8c28e-103">This example shows how to use the static resources of the <xref:System.Windows.SystemFonts> class in order to style or customize a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c28e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8c28e-104">Example</span></span>  
 <span data-ttu-id="8c28e-105">Systemressourcen machen mehrere vom System festgelegte Werte als Ressourcen und Eigenschaften verfügbar, um visuelle Elemente zu erstellen, mit Systemeinstellungen konsistent sind.</span><span class="sxs-lookup"><span data-stu-id="8c28e-105">System resources expose several system-determined values as both resources and properties in order to help you create visuals that are consistent with system settings.</span></span> <span data-ttu-id="8c28e-106"><xref:System.Windows.SystemFonts> ist eine Klasse, die sowohl System Schriftart Werte als statische Eigenschaften als auch Eigenschaften enthält, die auf Ressourcen Schlüssel verweisen, die für den dynamischen Zugriff auf diese Werte zur Laufzeit verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="8c28e-106"><xref:System.Windows.SystemFonts> is a class that contains both system font values as static properties, and properties that reference resource keys that can be used to access those values dynamically at run time.</span></span> <span data-ttu-id="8c28e-107">Beispielsweise ist <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> ein <xref:System.Windows.SystemFonts> Wert, und <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> ist ein entsprechender Ressourcen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="8c28e-107">For example, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> is a <xref:System.Windows.SystemFonts> value, and <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> is a corresponding resource key.</span></span>  
  
 <span data-ttu-id="8c28e-108">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]können Sie die Member von <xref:System.Windows.SystemFonts> entweder als statische Eigenschaften oder als dynamische Ressourcen Verweise (mit dem statischen Eigenschafts Wert als Schlüssel) verwenden.</span><span class="sxs-lookup"><span data-stu-id="8c28e-108">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can use the members of <xref:System.Windows.SystemFonts> as either static properties or dynamic resource references (with the static property value as the key).</span></span> <span data-ttu-id="8c28e-109">Verwenden Sie einen dynamischen Ressourcenverweis, wenn sich die Schriftarteigenschaft während der Ausführung der Anwendung automatisch aktualisieren soll; verwenden Sie andernfalls einen statischen Wertverweis.</span><span class="sxs-lookup"><span data-stu-id="8c28e-109">Use a dynamic resource reference if you want the font metric to automatically update while the application runs; otherwise, use a static value reference.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8c28e-110">Die Ressourcenschlüssel verfügen über das Suffix „Key“, das an den Eigenschaftennamen angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="8c28e-110">The resource keys have the suffix "Key" appended to the property name.</span></span>  
  
 <span data-ttu-id="8c28e-111">Im folgenden Beispiel wird gezeigt, wie Sie auf die Eigenschaften von <xref:System.Windows.SystemFonts> als statische Werte zugreifen und diese verwenden, um eine Schaltfläche zu formatieren oder anzupassen.</span><span class="sxs-lookup"><span data-stu-id="8c28e-111">The following example shows how to access and use the properties of <xref:System.Windows.SystemFonts> as static values in order to style or customize a button.</span></span> <span data-ttu-id="8c28e-112">In diesem Markup Beispiel werden einer Schaltfläche <xref:System.Windows.SystemFonts> Werte zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="8c28e-112">This markup example assigns <xref:System.Windows.SystemFonts> values to a button.</span></span>  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 <span data-ttu-id="8c28e-113">Wenn Sie die Werte von <xref:System.Windows.SystemFonts> im Code verwenden möchten, müssen Sie weder einen statischen Wert noch einen dynamischen Ressourcen Verweis verwenden.</span><span class="sxs-lookup"><span data-stu-id="8c28e-113">To use the values of <xref:System.Windows.SystemFonts> in code, you do not have to use either a static value or a dynamic resource reference.</span></span> <span data-ttu-id="8c28e-114">Verwenden Sie stattdessen die nicht Schlüsseleigenschaften der <xref:System.Windows.SystemFonts>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="8c28e-114">Instead, use the non-key properties of the <xref:System.Windows.SystemFonts> class.</span></span> <span data-ttu-id="8c28e-115">Obwohl die nicht Schlüsseleigenschaften scheinbar als statische Eigenschaften definiert sind, wertet das Laufzeitverhalten von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], wie vom System gehostet, die Eigenschaften in Echtzeit neu aus und berücksichtigt benutzergesteuerte Änderungen an System Werten ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="8c28e-115">Although the non-key properties are apparently defined as static properties, the run-time behavior of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] as hosted by the system will reevaluate the properties in real time and will properly account for user-driven changes to system values.</span></span> <span data-ttu-id="8c28e-116">Im folgenden Beispiel wird veranschaulicht, wie die Schriftarteinstellung einer Schaltfläche festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="8c28e-116">The following example shows how to specify the font settings of a button.</span></span>  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a><span data-ttu-id="8c28e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c28e-117">See also</span></span>

- <xref:System.Windows.SystemFonts>
- [<span data-ttu-id="8c28e-118">Zeichnen eines Bereichs mit einem Systempinsel</span><span class="sxs-lookup"><span data-stu-id="8c28e-118">Paint an Area with a System Brush</span></span>](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="8c28e-119">Verwenden von SystemParameters</span><span class="sxs-lookup"><span data-stu-id="8c28e-119">Use SystemParameters</span></span>](how-to-use-systemparameters.md)
- [<span data-ttu-id="8c28e-120">Verwenden von Systemschriftartschlüsseln</span><span class="sxs-lookup"><span data-stu-id="8c28e-120">Use System Fonts Keys</span></span>](how-to-use-system-fonts-keys.md)
- [<span data-ttu-id="8c28e-121">Gewusst wie-Themen</span><span class="sxs-lookup"><span data-stu-id="8c28e-121">How-to Topics</span></span>](resources-how-to-topics.md)
- [<span data-ttu-id="8c28e-122">x:Statische Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="8c28e-122">x:Static Markup Extension</span></span>](../../../desktop-wpf/xaml-services/xstatic-markup-extension.md)
- [<span data-ttu-id="8c28e-123">XAML-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="8c28e-123">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="8c28e-124">DynamicResource-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="8c28e-124">DynamicResource Markup Extension</span></span>](dynamicresource-markup-extension.md)
