---
title: 'Vorgehensweise: Verwenden von Systemschriftartschlüsseln'
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemFonts class
ms.assetid: 036ebea7-5677-4f60-8ba4-56c9f9d9b8bd
ms.openlocfilehash: 7283e4225b75909322fa312583e9f1a0679762e2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918385"
---
# <a name="how-to-use-system-fonts-keys"></a><span data-ttu-id="00767-102">Vorgehensweise: Verwenden von Systemschriftartschlüsseln</span><span class="sxs-lookup"><span data-stu-id="00767-102">How to: Use System Fonts Keys</span></span>
<span data-ttu-id="00767-103">Systemressourcen machen eine Reihe von Systemmetriken als Ressourcen verfügbar, damit Entwickler visuelle Elemente erstellen können, die mit Systemeinstellungen konsistent sind.</span><span class="sxs-lookup"><span data-stu-id="00767-103">System resources expose a number of system metrics as resources to help developers create visuals that are consistent with system settings.</span></span> <span data-ttu-id="00767-104"><xref:System.Windows.SystemFonts>ist eine Klasse, die sowohl System Schriftart Werte als auch System Schriftart Ressourcen enthält, die an die Werte gebunden werden <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> , <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>z. –. und.</span><span class="sxs-lookup"><span data-stu-id="00767-104"><xref:System.Windows.SystemFonts> is a class that contains both system font values and system font resources that bind to the values—for example, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> and <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.</span></span>  
  
 <span data-ttu-id="00767-105">Systemschriftarteigenschaften können als statische oder dynamische Ressourcen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="00767-105">System font metrics can be used as either static or dynamic resources.</span></span> <span data-ttu-id="00767-106">Verwenden Sie eine dynamische Ressource, wenn sich die Schriftarteigenschaft während der Ausführung der Anwendung aktualisieren soll; verwenden Sie andernfalls eine statische Ressource.</span><span class="sxs-lookup"><span data-stu-id="00767-106">Use a dynamic resource if you want the font metric to update automatically while the application runs; otherwise use a static resource.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="00767-107">Dynamischen Ressourcen wird der Schlüsselwort *Schlüssel* an den Eigenschaftsnamen angehängt.</span><span class="sxs-lookup"><span data-stu-id="00767-107">Dynamic resources have the keyword *Key* appended to the property name.</span></span>  
  
 <span data-ttu-id="00767-108">Im folgenden Beispiel wird veranschaulicht, wie Sie auf dynamische Ressourcen der Systemschriftart zugreifen und diese verwenden, um eine Schaltfläche zu formatieren oder anzupassen.</span><span class="sxs-lookup"><span data-stu-id="00767-108">The following example shows how to access and use system font dynamic resources to style or customize a button.</span></span> <span data-ttu-id="00767-109">Dieses [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Beispiel erstellt einen Schaltflächen Stil, <xref:System.Windows.SystemFonts> der einer Schaltfläche Werte zuweist.</span><span class="sxs-lookup"><span data-stu-id="00767-109">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example creates a button style that assigns <xref:System.Windows.SystemFonts> values to a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00767-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="00767-110">Example</span></span>  
 [!code-xaml[SystemRes_snip#FontDynamicResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#fontdynamicresources)]  
  
## <a name="see-also"></a><span data-ttu-id="00767-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00767-111">See also</span></span>

- [<span data-ttu-id="00767-112">Zeichnen eines Bereichs mit einem Systempinsel</span><span class="sxs-lookup"><span data-stu-id="00767-112">Paint an Area with a System Brush</span></span>](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="00767-113">Verwenden von SystemParameters</span><span class="sxs-lookup"><span data-stu-id="00767-113">Use SystemParameters</span></span>](how-to-use-systemparameters.md)
- [<span data-ttu-id="00767-114">Verwenden von SystemFonts</span><span class="sxs-lookup"><span data-stu-id="00767-114">Use SystemFonts</span></span>](how-to-use-systemfonts.md)
