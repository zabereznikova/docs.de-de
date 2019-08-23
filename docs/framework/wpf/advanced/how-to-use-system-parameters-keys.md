---
title: 'Vorgehensweise: Verwenden von Systemparameterschlüsseln'
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemParameters class
- classes [WPF], SystemParameters
ms.assetid: 77571283-d16c-45bb-9f69-cafbbf72b21e
ms.openlocfilehash: edacb4b98ab01f081f668dc3374f6588492210d9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918371"
---
# <a name="how-to-use-system-parameters-keys"></a><span data-ttu-id="44857-102">Vorgehensweise: Verwenden von Systemparameterschlüsseln</span><span class="sxs-lookup"><span data-stu-id="44857-102">How to: Use System Parameters Keys</span></span>
<span data-ttu-id="44857-103">Systemressourcen machen eine Reihe von Systemmetriken als Ressourcen verfügbar, damit Entwickler visuelle Elemente erstellen können, die mit Systemeinstellungen konsistent sind.</span><span class="sxs-lookup"><span data-stu-id="44857-103">System resources expose a number of system metrics as resources to help developers create visuals that are consistent with system settings.</span></span> <span data-ttu-id="44857-104"><xref:System.Windows.SystemParameters>ist eine Klasse, die sowohl Systemparameter Werte als auch Ressourcen Schlüssel enthält, die an die Werte gebunden werden <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> , <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>z. –. und.</span><span class="sxs-lookup"><span data-stu-id="44857-104"><xref:System.Windows.SystemParameters> is a class that contains both system parameter values and resource keys that bind to the values—for example, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> and <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>.</span></span> <span data-ttu-id="44857-105">Systemparametereigenschaften können als statische oder dynamische Ressourcen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="44857-105">System parameter metrics can be used as either static or dynamic resources.</span></span> <span data-ttu-id="44857-106">Verwenden Sie eine dynamische Ressource, wenn sich die Parametereigenschaft während der Ausführung der Anwendung aktualisieren soll; verwenden Sie andernfalls eine statische Ressource.</span><span class="sxs-lookup"><span data-stu-id="44857-106">Use a dynamic resource if you want the parameter metric to update automatically while the application runs; otherwise use a static resource.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="44857-107">Dynamischen Ressourcen wird der Schlüsselwort *Schlüssel* an den Eigenschaftsnamen angehängt.</span><span class="sxs-lookup"><span data-stu-id="44857-107">Dynamic resources have the keyword *Key* appended to the property name.</span></span>  
  
 <span data-ttu-id="44857-108">Im folgenden Beispiel wird veranschaulicht, wie Sie auf dynamische Ressourcen der Systemparamter zugreifen und diese verwenden, um eine Schaltfläche zu formatieren oder anzupassen.</span><span class="sxs-lookup"><span data-stu-id="44857-108">The following example shows how to access and use system parameter dynamic resources to style or customize a button.</span></span> <span data-ttu-id="44857-109">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] diesem Beispiel wird eine Schaltfläche <xref:System.Windows.SystemParameters> durch Zuweisen von Werten zur Breite und Höhe der Schaltfläche unterschiedlich dargestellt.</span><span class="sxs-lookup"><span data-stu-id="44857-109">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example sizes a button by assigning <xref:System.Windows.SystemParameters> values to the button's width and height.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44857-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="44857-110">Example</span></span>  
 [!code-xaml[SystemRes_snip#ParameterDynamicResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#parameterdynamicresources)]  
  
## <a name="see-also"></a><span data-ttu-id="44857-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44857-111">See also</span></span>

- [<span data-ttu-id="44857-112">Zeichnen eines Bereichs mit einem Systempinsel</span><span class="sxs-lookup"><span data-stu-id="44857-112">Paint an Area with a System Brush</span></span>](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="44857-113">Verwenden von SystemFonts</span><span class="sxs-lookup"><span data-stu-id="44857-113">Use SystemFonts</span></span>](how-to-use-systemfonts.md)
- [<span data-ttu-id="44857-114">Verwenden von SystemParameters</span><span class="sxs-lookup"><span data-stu-id="44857-114">Use SystemParameters</span></span>](how-to-use-systemparameters.md)
