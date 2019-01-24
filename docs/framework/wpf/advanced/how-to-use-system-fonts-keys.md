---
title: 'Vorgehensweise: Verwenden von Systemschriftartschlüsseln'
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemFonts class
ms.assetid: 036ebea7-5677-4f60-8ba4-56c9f9d9b8bd
ms.openlocfilehash: aec3ba8b84836d068b7efcfe53b34b126334b8de
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628707"
---
# <a name="how-to-use-system-fonts-keys"></a><span data-ttu-id="04ecb-102">Vorgehensweise: Verwenden von Systemschriftartschlüsseln</span><span class="sxs-lookup"><span data-stu-id="04ecb-102">How to: Use System Fonts Keys</span></span>
<span data-ttu-id="04ecb-103">Systemressourcen machen eine Reihe von Systemmetriken als Ressourcen verfügbar, damit Entwickler visuelle Elemente erstellen können, die mit Systemeinstellungen konsistent sind.</span><span class="sxs-lookup"><span data-stu-id="04ecb-103">System resources expose a number of system metrics as resources to help developers create visuals that are consistent with system settings.</span></span> <span data-ttu-id="04ecb-104"><xref:System.Windows.SystemFonts> eine Klasse, enthält sowohl Systemschriftartwerte und Systemschriftartressourcen, die an die Werte gebunden, ist – z. B. <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> und <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="04ecb-104"><xref:System.Windows.SystemFonts> is a class that contains both system font values and system font resources that bind to the values—for example, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> and <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.</span></span>  
  
 <span data-ttu-id="04ecb-105">Systemschriftarteigenschaften können als statische oder dynamische Ressourcen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="04ecb-105">System font metrics can be used as either static or dynamic resources.</span></span> <span data-ttu-id="04ecb-106">Verwenden Sie eine dynamische Ressource, wenn sich die Schriftarteigenschaft während der Ausführung der Anwendung aktualisieren soll; verwenden Sie andernfalls eine statische Ressource.</span><span class="sxs-lookup"><span data-stu-id="04ecb-106">Use a dynamic resource if you want the font metric to update automatically while the application runs; otherwise use a static resource.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04ecb-107">Dynamische Ressourcen haben das Schlüsselwort *Schlüssel* an den Eigenschaftennamen angefügt.</span><span class="sxs-lookup"><span data-stu-id="04ecb-107">Dynamic resources have the keyword *Key* appended to the property name.</span></span>  
  
 <span data-ttu-id="04ecb-108">Im folgenden Beispiel wird veranschaulicht, wie Sie auf dynamische Ressourcen der Systemschriftart zugreifen und diese verwenden, um eine Schaltfläche zu formatieren oder anzupassen.</span><span class="sxs-lookup"><span data-stu-id="04ecb-108">The following example shows how to access and use system font dynamic resources to style or customize a button.</span></span> <span data-ttu-id="04ecb-109">Dies [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Beispiel erstellt eine Schaltflächen-Formatvorlage, die weist <xref:System.Windows.SystemFonts> Werte auf eine Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="04ecb-109">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example creates a button style that assigns <xref:System.Windows.SystemFonts> values to a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04ecb-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="04ecb-110">Example</span></span>  
 [!code-xaml[SystemRes_snip#FontDynamicResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#fontdynamicresources)]  
  
## <a name="see-also"></a><span data-ttu-id="04ecb-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04ecb-111">See also</span></span>
- [<span data-ttu-id="04ecb-112">Zeichnen eines Bereichs mit einem Systempinsel</span><span class="sxs-lookup"><span data-stu-id="04ecb-112">Paint an Area with a System Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="04ecb-113">Verwenden von SystemParameters</span><span class="sxs-lookup"><span data-stu-id="04ecb-113">Use SystemParameters</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)
- [<span data-ttu-id="04ecb-114">Verwenden von SystemFonts</span><span class="sxs-lookup"><span data-stu-id="04ecb-114">Use SystemFonts</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)
