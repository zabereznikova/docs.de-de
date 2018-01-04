---
title: "Gewusst wie: Verwenden von Systemschriftartschlüsseln"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: resource keys [WPF], SystemFonts class
ms.assetid: 036ebea7-5677-4f60-8ba4-56c9f9d9b8bd
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 53538c64d2af5d8407f79848ddcd01f7665303c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-system-fonts-keys"></a><span data-ttu-id="05b75-102">Gewusst wie: Verwenden von Systemschriftartschlüsseln</span><span class="sxs-lookup"><span data-stu-id="05b75-102">How to: Use System Fonts Keys</span></span>
<span data-ttu-id="05b75-103">Systemressourcen machen eine Reihe von Systemmetriken als Ressourcen verfügbar, damit Entwickler visuelle Elemente erstellen können, die mit Systemeinstellungen konsistent sind.</span><span class="sxs-lookup"><span data-stu-id="05b75-103">System resources expose a number of system metrics as resources to help developers create visuals that are consistent with system settings.</span></span> <span data-ttu-id="05b75-104"><xref:System.Windows.SystemFonts>ist eine Klasse, die Schriftart Systemwerte und Schriftart Systemressourcen, die an die Werte binden enthält – z. B. <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> und <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="05b75-104"><xref:System.Windows.SystemFonts> is a class that contains both system font values and system font resources that bind to the values—for example, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> and <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.</span></span>  
  
 <span data-ttu-id="05b75-105">Systemschriftarteigenschaften können als statische oder dynamische Ressourcen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="05b75-105">System font metrics can be used as either static or dynamic resources.</span></span> <span data-ttu-id="05b75-106">Verwenden Sie eine dynamische Ressource, wenn sich die Schriftarteigenschaft während der Ausführung der Anwendung aktualisieren soll; verwenden Sie andernfalls eine statische Ressource.</span><span class="sxs-lookup"><span data-stu-id="05b75-106">Use a dynamic resource if you want the font metric to update automatically while the application runs; otherwise use a static resource.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="05b75-107">Dynamische Ressourcen ist das Schlüsselwort *Schlüssel* des Eigenschaftennamens angefügt.</span><span class="sxs-lookup"><span data-stu-id="05b75-107">Dynamic resources have the keyword *Key* appended to the property name.</span></span>  
  
 <span data-ttu-id="05b75-108">Im folgenden Beispiel wird veranschaulicht, wie Sie auf dynamische Ressourcen der Systemschriftart zugreifen und diese verwenden, um eine Schaltfläche zu formatieren oder anzupassen.</span><span class="sxs-lookup"><span data-stu-id="05b75-108">The following example shows how to access and use system font dynamic resources to style or customize a button.</span></span> <span data-ttu-id="05b75-109">Dies [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Beispiel erstellt eine Vorlage, die weist <xref:System.Windows.SystemFonts> Werte mit einer Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="05b75-109">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example creates a button style that assigns <xref:System.Windows.SystemFonts> values to a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05b75-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="05b75-110">Example</span></span>  
 [!code-xaml[SystemRes_snip#FontDynamicResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#fontdynamicresources)]  
  
## <a name="see-also"></a><span data-ttu-id="05b75-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05b75-111">See Also</span></span>  
 [<span data-ttu-id="05b75-112">Zeichnen eines Bereichs mit einem Systempinsel</span><span class="sxs-lookup"><span data-stu-id="05b75-112">Paint an Area with a System Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [<span data-ttu-id="05b75-113">Verwenden von SystemParameters</span><span class="sxs-lookup"><span data-stu-id="05b75-113">Use SystemParameters</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)  
 [<span data-ttu-id="05b75-114">Verwenden von SystemFonts</span><span class="sxs-lookup"><span data-stu-id="05b75-114">Use SystemFonts</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)
