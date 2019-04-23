---
title: 'Vorgehensweise: Verwenden von Systemschriftartschlüsseln'
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemFonts class
ms.assetid: 036ebea7-5677-4f60-8ba4-56c9f9d9b8bd
ms.openlocfilehash: e924f4c14d98380d9f4c0defe27d9f98c3293114
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59148927"
---
# <a name="how-to-use-system-fonts-keys"></a><span data-ttu-id="6d27a-102">Vorgehensweise: Verwenden von Systemschriftartschlüsseln</span><span class="sxs-lookup"><span data-stu-id="6d27a-102">How to: Use System Fonts Keys</span></span>
<span data-ttu-id="6d27a-103">Systemressourcen machen eine Reihe von Systemmetriken als Ressourcen verfügbar, damit Entwickler visuelle Elemente erstellen können, die mit Systemeinstellungen konsistent sind.</span><span class="sxs-lookup"><span data-stu-id="6d27a-103">System resources expose a number of system metrics as resources to help developers create visuals that are consistent with system settings.</span></span> <span data-ttu-id="6d27a-104"><xref:System.Windows.SystemFonts> eine Klasse, enthält sowohl Systemschriftartwerte und Systemschriftartressourcen, die an die Werte gebunden, ist – z. B. <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> und <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="6d27a-104"><xref:System.Windows.SystemFonts> is a class that contains both system font values and system font resources that bind to the values—for example, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> and <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.</span></span>  
  
 <span data-ttu-id="6d27a-105">Systemschriftarteigenschaften können als statische oder dynamische Ressourcen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6d27a-105">System font metrics can be used as either static or dynamic resources.</span></span> <span data-ttu-id="6d27a-106">Verwenden Sie eine dynamische Ressource, wenn sich die Schriftarteigenschaft während der Ausführung der Anwendung aktualisieren soll; verwenden Sie andernfalls eine statische Ressource.</span><span class="sxs-lookup"><span data-stu-id="6d27a-106">Use a dynamic resource if you want the font metric to update automatically while the application runs; otherwise use a static resource.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d27a-107">Dynamische Ressourcen haben das Schlüsselwort *Schlüssel* an den Eigenschaftennamen angefügt.</span><span class="sxs-lookup"><span data-stu-id="6d27a-107">Dynamic resources have the keyword *Key* appended to the property name.</span></span>  
  
 <span data-ttu-id="6d27a-108">Im folgenden Beispiel wird veranschaulicht, wie Sie auf dynamische Ressourcen der Systemschriftart zugreifen und diese verwenden, um eine Schaltfläche zu formatieren oder anzupassen.</span><span class="sxs-lookup"><span data-stu-id="6d27a-108">The following example shows how to access and use system font dynamic resources to style or customize a button.</span></span> <span data-ttu-id="6d27a-109">Dies [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Beispiel erstellt eine Schaltflächen-Formatvorlage, die weist <xref:System.Windows.SystemFonts> Werte auf eine Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="6d27a-109">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example creates a button style that assigns <xref:System.Windows.SystemFonts> values to a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d27a-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6d27a-110">Example</span></span>  
 [!code-xaml[SystemRes_snip#FontDynamicResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#fontdynamicresources)]  
  
## <a name="see-also"></a><span data-ttu-id="6d27a-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d27a-111">See also</span></span>

- [<span data-ttu-id="6d27a-112">Zeichnen eines Bereichs mit einem Systempinsel</span><span class="sxs-lookup"><span data-stu-id="6d27a-112">Paint an Area with a System Brush</span></span>](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="6d27a-113">Verwenden von SystemParameters</span><span class="sxs-lookup"><span data-stu-id="6d27a-113">Use SystemParameters</span></span>](how-to-use-systemparameters.md)
- [<span data-ttu-id="6d27a-114">Verwenden von SystemFonts</span><span class="sxs-lookup"><span data-stu-id="6d27a-114">Use SystemFonts</span></span>](how-to-use-systemfonts.md)
