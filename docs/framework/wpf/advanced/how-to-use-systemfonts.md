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
ms.openlocfilehash: 305d0cf18db5dc96b2d3cde863cf4ba2ae8dbb96
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544676"
---
# <a name="how-to-use-systemfonts"></a><span data-ttu-id="f8908-102">Gewusst wie: Verwenden von SystemFonts</span><span class="sxs-lookup"><span data-stu-id="f8908-102">How to: Use SystemFonts</span></span>
<span data-ttu-id="f8908-103">In diesem Beispiel wird gezeigt, wie für die Verwendung der statischen Ressourcen von der <xref:System.Windows.SystemFonts> Klasse, um zu formatieren oder Anpassen einer Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="f8908-103">This example shows how to use the static resources of the <xref:System.Windows.SystemFonts> class in order to style or customize a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8908-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f8908-104">Example</span></span>  
 <span data-ttu-id="f8908-105">Systemressourcen machen mehrere vom System festgelegte Werte als Ressourcen und Eigenschaften verfügbar, um visuelle Elemente zu erstellen, mit Systemeinstellungen konsistent sind.</span><span class="sxs-lookup"><span data-stu-id="f8908-105">System resources expose several system-determined values as both resources and properties in order to help you create visuals that are consistent with system settings.</span></span> <span data-ttu-id="f8908-106"><xref:System.Windows.SystemFonts> ist eine Klasse, die beide System Schriftartwerte, als statische Eigenschaften und Eigenschaften, die auf Ressourcenschlüssel verweisen, die verwendet werden können enthält, um diese Werte dynamisch zur Laufzeit zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f8908-106"><xref:System.Windows.SystemFonts> is a class that contains both system font values as static properties, and properties that reference resource keys that can be used to access those values dynamically at run time.</span></span> <span data-ttu-id="f8908-107">Beispielsweise <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> ist ein <xref:System.Windows.SystemFonts> Wert und <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> ist ein entsprechender Ressourcenschlüssel.</span><span class="sxs-lookup"><span data-stu-id="f8908-107">For example, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> is a <xref:System.Windows.SystemFonts> value, and <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> is a corresponding resource key.</span></span>  
  
 <span data-ttu-id="f8908-108">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], können Sie die Mitglieder der <xref:System.Windows.SystemFonts> als Eigenschaften für statischen oder dynamischen Ressourcenverweise (mit der statischen Eigenschaft-Wert als Schlüssel).</span><span class="sxs-lookup"><span data-stu-id="f8908-108">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can use the members of <xref:System.Windows.SystemFonts> as either static properties or dynamic resource references (with the static property value as the key).</span></span> <span data-ttu-id="f8908-109">Verwenden Sie einen dynamischen Ressourcenverweis, wenn sich die Schriftarteigenschaft während der Ausführung der Anwendung automatisch aktualisieren soll; verwenden Sie andernfalls einen statischen Wertverweis.</span><span class="sxs-lookup"><span data-stu-id="f8908-109">Use a dynamic resource reference if you want the font metric to automatically update while the application runs; otherwise, use a static value reference.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8908-110">Die Ressourcenschlüssel verfügen über das Suffix „Key“, das an den Eigenschaftennamen angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="f8908-110">The resource keys have the suffix "Key" appended to the property name.</span></span>  
  
 <span data-ttu-id="f8908-111">Im folgende Beispiel wird gezeigt, wie zugreifen auf und verwenden die Eigenschaften des <xref:System.Windows.SystemFonts> als statische Werte zum Formatieren oder Anpassen einer Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="f8908-111">The following example shows how to access and use the properties of <xref:System.Windows.SystemFonts> as static values in order to style or customize a button.</span></span> <span data-ttu-id="f8908-112">In diesem Markupbeispiel weist <xref:System.Windows.SystemFonts> Werte mit einer Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="f8908-112">This markup example assigns <xref:System.Windows.SystemFonts> values to a button.</span></span>  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 <span data-ttu-id="f8908-113">Verwenden Sie die Werte der <xref:System.Windows.SystemFonts> in Code, Sie müssen nicht um einen statischen Wert oder einen dynamischen Ressourcenverweis zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f8908-113">To use the values of <xref:System.Windows.SystemFonts> in code, you do not have to use either a static value or a dynamic resource reference.</span></span> <span data-ttu-id="f8908-114">Verwenden Sie stattdessen die nicht schlüsselbezogene Eigenschaften von der <xref:System.Windows.SystemFonts> Klasse.</span><span class="sxs-lookup"><span data-stu-id="f8908-114">Instead, use the non-key properties of the <xref:System.Windows.SystemFonts> class.</span></span> <span data-ttu-id="f8908-115">Obwohl die nicht schlüsselbezogene Eigenschaften als statische Eigenschaften, die das Laufzeitverhalten des offensichtlich definiert sind [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] als gehostete durch das System wird neu Auswerten der Eigenschaften in Echtzeit und wird für Benutzer vorgenommene Änderungen Systemwerte ordnungsgemäß berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="f8908-115">Although the non-key properties are apparently defined as static properties, the run-time behavior of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] as hosted by the system will reevaluate the properties in real time and will properly account for user-driven changes to system values.</span></span> <span data-ttu-id="f8908-116">Im folgenden Beispiel wird veranschaulicht, wie die Schriftarteinstellung einer Schaltfläche festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="f8908-116">The following example shows how to specify the font settings of a button.</span></span>  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a><span data-ttu-id="f8908-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8908-117">See Also</span></span>  
 <xref:System.Windows.SystemFonts>  
 [<span data-ttu-id="f8908-118">Zeichnen eines Bereichs mit einem Systempinsel</span><span class="sxs-lookup"><span data-stu-id="f8908-118">Paint an Area with a System Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [<span data-ttu-id="f8908-119">Verwenden von SystemParameters</span><span class="sxs-lookup"><span data-stu-id="f8908-119">Use SystemParameters</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)  
 [<span data-ttu-id="f8908-120">Verwenden von Systemschriftartschlüsseln</span><span class="sxs-lookup"><span data-stu-id="f8908-120">Use System Fonts Keys</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-system-fonts-keys.md)  
 [<span data-ttu-id="f8908-121">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="f8908-121">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)  
 [<span data-ttu-id="f8908-122">x:Statische Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="f8908-122">x:Static Markup Extension</span></span>](../../../../docs/framework/xaml-services/x-static-markup-extension.md)  
 [<span data-ttu-id="f8908-123">XAML-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f8908-123">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="f8908-124">DynamicResource-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="f8908-124">DynamicResource Markup Extension</span></span>](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)
