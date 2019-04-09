---
title: 'Vorgehensweise: Verwenden von Systemparameterschlüsseln'
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemParameters class
- classes [WPF], SystemParameters
ms.assetid: 77571283-d16c-45bb-9f69-cafbbf72b21e
ms.openlocfilehash: 147f65b4bb214c12317309081c345251d7426cd6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59147331"
---
# <a name="how-to-use-system-parameters-keys"></a><span data-ttu-id="5b3b1-102">Vorgehensweise: Verwenden von Systemparameterschlüsseln</span><span class="sxs-lookup"><span data-stu-id="5b3b1-102">How to: Use System Parameters Keys</span></span>
<span data-ttu-id="5b3b1-103">Systemressourcen machen eine Reihe von Systemmetriken als Ressourcen verfügbar, damit Entwickler visuelle Elemente erstellen können, die mit Systemeinstellungen konsistent sind.</span><span class="sxs-lookup"><span data-stu-id="5b3b1-103">System resources expose a number of system metrics as resources to help developers create visuals that are consistent with system settings.</span></span> <xref:System.Windows.SystemParameters> <span data-ttu-id="5b3b1-104">ist eine Klasse, die sowohl Systemparameterwerte und Ressourcenschlüssel, der an die Werte gebunden enthält – z. B. <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> und <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="5b3b1-104">is a class that contains both system parameter values and resource keys that bind to the values—for example, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> and <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>.</span></span> <span data-ttu-id="5b3b1-105">Systemparametereigenschaften können als statische oder dynamische Ressourcen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5b3b1-105">System parameter metrics can be used as either static or dynamic resources.</span></span> <span data-ttu-id="5b3b1-106">Verwenden Sie eine dynamische Ressource, wenn sich die Parametereigenschaft während der Ausführung der Anwendung aktualisieren soll; verwenden Sie andernfalls eine statische Ressource.</span><span class="sxs-lookup"><span data-stu-id="5b3b1-106">Use a dynamic resource if you want the parameter metric to update automatically while the application runs; otherwise use a static resource.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b3b1-107">Dynamische Ressourcen haben das Schlüsselwort *Schlüssel* an den Eigenschaftennamen angefügt.</span><span class="sxs-lookup"><span data-stu-id="5b3b1-107">Dynamic resources have the keyword *Key* appended to the property name.</span></span>  
  
 <span data-ttu-id="5b3b1-108">Im folgenden Beispiel wird veranschaulicht, wie Sie auf dynamische Ressourcen der Systemparamter zugreifen und diese verwenden, um eine Schaltfläche zu formatieren oder anzupassen.</span><span class="sxs-lookup"><span data-stu-id="5b3b1-108">The following example shows how to access and use system parameter dynamic resources to style or customize a button.</span></span> <span data-ttu-id="5b3b1-109">Dies [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Beispiel die Größe einer Schaltfläche durch Zuweisen von <xref:System.Windows.SystemParameters> Werte für Breite und Höhe der Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="5b3b1-109">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example sizes a button by assigning <xref:System.Windows.SystemParameters> values to the button's width and height.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b3b1-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5b3b1-110">Example</span></span>  
 [!code-xaml[SystemRes_snip#ParameterDynamicResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#parameterdynamicresources)]  
  
## <a name="see-also"></a><span data-ttu-id="5b3b1-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b3b1-111">See also</span></span>

- [<span data-ttu-id="5b3b1-112">Zeichnen eines Bereichs mit einem Systempinsel</span><span class="sxs-lookup"><span data-stu-id="5b3b1-112">Paint an Area with a System Brush</span></span>](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="5b3b1-113">Verwenden von SystemFonts</span><span class="sxs-lookup"><span data-stu-id="5b3b1-113">Use SystemFonts</span></span>](how-to-use-systemfonts.md)
- [<span data-ttu-id="5b3b1-114">Verwenden von SystemParameters</span><span class="sxs-lookup"><span data-stu-id="5b3b1-114">Use SystemParameters</span></span>](how-to-use-systemparameters.md)
