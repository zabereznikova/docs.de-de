---
title: "Gewusst wie: Verwenden von Systemparameterschlüsseln"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- resource keys [WPF], SystemParameters class
- classes [WPF], SystemParameters
ms.assetid: 77571283-d16c-45bb-9f69-cafbbf72b21e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b2a7352540456b459428dd87f6c60be0b8bc08b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-system-parameters-keys"></a><span data-ttu-id="080fa-102">Gewusst wie: Verwenden von Systemparameterschlüsseln</span><span class="sxs-lookup"><span data-stu-id="080fa-102">How to: Use System Parameters Keys</span></span>
<span data-ttu-id="080fa-103">Systemressourcen machen eine Reihe von Systemmetriken als Ressourcen verfügbar, damit Entwickler visuelle Elemente erstellen können, die mit Systemeinstellungen konsistent sind.</span><span class="sxs-lookup"><span data-stu-id="080fa-103">System resources expose a number of system metrics as resources to help developers create visuals that are consistent with system settings.</span></span> <span data-ttu-id="080fa-104"><xref:System.Windows.SystemParameters>ist eine Klasse, die System-Parameterwerten und Ressourcenschlüssel, die an die Werte binden enthält – z. B. <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> und <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="080fa-104"><xref:System.Windows.SystemParameters> is a class that contains both system parameter values and resource keys that bind to the values—for example, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> and <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>.</span></span> <span data-ttu-id="080fa-105">Systemparametereigenschaften können als statische oder dynamische Ressourcen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="080fa-105">System parameter metrics can be used as either static or dynamic resources.</span></span> <span data-ttu-id="080fa-106">Verwenden Sie eine dynamische Ressource, wenn sich die Parametereigenschaft während der Ausführung der Anwendung aktualisieren soll; verwenden Sie andernfalls eine statische Ressource.</span><span class="sxs-lookup"><span data-stu-id="080fa-106">Use a dynamic resource if you want the parameter metric to update automatically while the application runs; otherwise use a static resource.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="080fa-107">Dynamische Ressourcen ist das Schlüsselwort *Schlüssel* des Eigenschaftennamens angefügt.</span><span class="sxs-lookup"><span data-stu-id="080fa-107">Dynamic resources have the keyword *Key* appended to the property name.</span></span>  
  
 <span data-ttu-id="080fa-108">Im folgenden Beispiel wird veranschaulicht, wie Sie auf dynamische Ressourcen der Systemparamter zugreifen und diese verwenden, um eine Schaltfläche zu formatieren oder anzupassen.</span><span class="sxs-lookup"><span data-stu-id="080fa-108">The following example shows how to access and use system parameter dynamic resources to style or customize a button.</span></span> <span data-ttu-id="080fa-109">Dies [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Beispiel eine Schaltfläche durch Zuweisen von Größen <xref:System.Windows.SystemParameters> Werte auf der Schaltfläche Breite und Höhe.</span><span class="sxs-lookup"><span data-stu-id="080fa-109">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example sizes a button by assigning <xref:System.Windows.SystemParameters> values to the button's width and height.</span></span>  
  
## <a name="example"></a><span data-ttu-id="080fa-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="080fa-110">Example</span></span>  
 [!code-xaml[SystemRes_snip#ParameterDynamicResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#parameterdynamicresources)]  
  
## <a name="see-also"></a><span data-ttu-id="080fa-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="080fa-111">See Also</span></span>  
 [<span data-ttu-id="080fa-112">Zeichnen eines Bereichs mit einem Systempinsel</span><span class="sxs-lookup"><span data-stu-id="080fa-112">Paint an Area with a System Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [<span data-ttu-id="080fa-113">Verwenden von SystemFonts</span><span class="sxs-lookup"><span data-stu-id="080fa-113">Use SystemFonts</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)  
 [<span data-ttu-id="080fa-114">Verwenden von SystemParameters</span><span class="sxs-lookup"><span data-stu-id="080fa-114">Use SystemParameters</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)
