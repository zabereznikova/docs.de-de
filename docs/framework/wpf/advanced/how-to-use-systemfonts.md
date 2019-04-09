---
title: 'Vorgehensweise: Verwenden von SystemFonts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
ms.openlocfilehash: 5976bc0cb8b34e68d5e89dd70a608d7e52ded332
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216781"
---
# <a name="how-to-use-systemfonts"></a><span data-ttu-id="4f29b-102">Vorgehensweise: Verwenden von SystemFonts</span><span class="sxs-lookup"><span data-stu-id="4f29b-102">How to: Use SystemFonts</span></span>
<span data-ttu-id="4f29b-103">Dieses Beispiel zeigt, wie Sie mit der statischen Ressourcen der der <xref:System.Windows.SystemFonts> Klasse zum Formatieren oder Anpassen einer Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="4f29b-103">This example shows how to use the static resources of the <xref:System.Windows.SystemFonts> class in order to style or customize a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f29b-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4f29b-104">Example</span></span>  
 <span data-ttu-id="4f29b-105">Systemressourcen machen mehrere vom System festgelegte Werte als Ressourcen und Eigenschaften verfügbar, um visuelle Elemente zu erstellen, mit Systemeinstellungen konsistent sind.</span><span class="sxs-lookup"><span data-stu-id="4f29b-105">System resources expose several system-determined values as both resources and properties in order to help you create visuals that are consistent with system settings.</span></span> <xref:System.Windows.SystemFonts> <span data-ttu-id="4f29b-106">ist eine Klasse, die enthält sowohl als statische Eigenschaften und Eigenschaften, die auf Ressourcenschlüssel verweisen, die verwendet werden können, um diese Werte dynamisch zur Laufzeit zugreifen.</span><span class="sxs-lookup"><span data-stu-id="4f29b-106">is a class that contains both system font values as static properties, and properties that reference resource keys that can be used to access those values dynamically at run time.</span></span> <span data-ttu-id="4f29b-107">Z. B. <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> ist eine <xref:System.Windows.SystemFonts> Wert und <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> ist ein entsprechender Ressourcenschlüssel.</span><span class="sxs-lookup"><span data-stu-id="4f29b-107">For example, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> is a <xref:System.Windows.SystemFonts> value, and <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> is a corresponding resource key.</span></span>  
  
 <span data-ttu-id="4f29b-108">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], können Sie die Mitglieder der <xref:System.Windows.SystemFonts> als statische Eigenschaften oder dynamische Ressourcenverweise (mit dem statischen Eigenschaftswert als Schlüssel).</span><span class="sxs-lookup"><span data-stu-id="4f29b-108">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can use the members of <xref:System.Windows.SystemFonts> as either static properties or dynamic resource references (with the static property value as the key).</span></span> <span data-ttu-id="4f29b-109">Verwenden Sie einen dynamischen Ressourcenverweis, wenn sich die Schriftarteigenschaft während der Ausführung der Anwendung automatisch aktualisieren soll; verwenden Sie andernfalls einen statischen Wertverweis.</span><span class="sxs-lookup"><span data-stu-id="4f29b-109">Use a dynamic resource reference if you want the font metric to automatically update while the application runs; otherwise, use a static value reference.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f29b-110">Die Ressourcenschlüssel verfügen über das Suffix „Key“, das an den Eigenschaftennamen angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="4f29b-110">The resource keys have the suffix "Key" appended to the property name.</span></span>  
  
 <span data-ttu-id="4f29b-111">Das folgende Beispiel zeigt, wie Sie den Zugriff auf und verwenden Sie die Eigenschaften der <xref:System.Windows.SystemFonts> als statische Werte zum Formatieren oder Anpassen einer Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="4f29b-111">The following example shows how to access and use the properties of <xref:System.Windows.SystemFonts> as static values in order to style or customize a button.</span></span> <span data-ttu-id="4f29b-112">Dieses Markupbeispiel weist <xref:System.Windows.SystemFonts> Werte auf eine Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="4f29b-112">This markup example assigns <xref:System.Windows.SystemFonts> values to a button.</span></span>  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 <span data-ttu-id="4f29b-113">Verwenden Sie die Werte der <xref:System.Windows.SystemFonts> in Code, Sie müssen keinen statischen Wert oder einen dynamischen Ressourcenverweis zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4f29b-113">To use the values of <xref:System.Windows.SystemFonts> in code, you do not have to use either a static value or a dynamic resource reference.</span></span> <span data-ttu-id="4f29b-114">Verwenden Sie stattdessen die Nichtschlüsseleigenschaften der der <xref:System.Windows.SystemFonts> Klasse.</span><span class="sxs-lookup"><span data-stu-id="4f29b-114">Instead, use the non-key properties of the <xref:System.Windows.SystemFonts> class.</span></span> <span data-ttu-id="4f29b-115">Obwohl die Nichtschlüsseleigenschaften scheinbar als statische Eigenschaften, die das Laufzeitverhalten des definiert sind [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wie von gehostet wird das System Systemwerten die Eigenschaften in Echtzeit und benutzergesteuerte Änderungen von ordnungsgemäß berücksichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="4f29b-115">Although the non-key properties are apparently defined as static properties, the run-time behavior of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] as hosted by the system will reevaluate the properties in real time and will properly account for user-driven changes to system values.</span></span> <span data-ttu-id="4f29b-116">Im folgenden Beispiel wird veranschaulicht, wie die Schriftarteinstellung einer Schaltfläche festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="4f29b-116">The following example shows how to specify the font settings of a button.</span></span>  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a><span data-ttu-id="4f29b-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f29b-117">See also</span></span>

- <xref:System.Windows.SystemFonts>
- [<span data-ttu-id="4f29b-118">Zeichnen eines Bereichs mit einem Systempinsel</span><span class="sxs-lookup"><span data-stu-id="4f29b-118">Paint an Area with a System Brush</span></span>](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="4f29b-119">Verwenden von SystemParameters</span><span class="sxs-lookup"><span data-stu-id="4f29b-119">Use SystemParameters</span></span>](how-to-use-systemparameters.md)
- [<span data-ttu-id="4f29b-120">Verwenden von Systemschriftartschlüsseln</span><span class="sxs-lookup"><span data-stu-id="4f29b-120">Use System Fonts Keys</span></span>](how-to-use-system-fonts-keys.md)
- [<span data-ttu-id="4f29b-121">Gewusst wie-Themen</span><span class="sxs-lookup"><span data-stu-id="4f29b-121">How-to Topics</span></span>](resources-how-to-topics.md)
- [<span data-ttu-id="4f29b-122">x:Statische Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="4f29b-122">x:Static Markup Extension</span></span>](../../xaml-services/x-static-markup-extension.md)
- [<span data-ttu-id="4f29b-123">XAML-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="4f29b-123">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="4f29b-124">DynamicResource-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="4f29b-124">DynamicResource Markup Extension</span></span>](dynamicresource-markup-extension.md)
