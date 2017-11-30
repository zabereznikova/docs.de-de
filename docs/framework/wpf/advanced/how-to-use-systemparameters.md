---
title: 'Gewusst wie: Verwenden von SystemParameters'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: classes [WPF], SystemParameters
ms.assetid: 02e7a5de-94eb-4953-b91c-52e6c872ad5b
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f4b2ee3956017e10da8adda52fa9a0ec31cb19ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-systemparameters"></a><span data-ttu-id="8b68b-102">Gewusst wie: Verwenden von SystemParameters</span><span class="sxs-lookup"><span data-stu-id="8b68b-102">How to: Use SystemParameters</span></span>
<span data-ttu-id="8b68b-103">In diesem Beispiel wird gezeigt, wie zugreifen auf und verwenden die Eigenschaften des <xref:System.Windows.SystemParameters> um formatieren oder Anpassen einer Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="8b68b-103">This example shows how to access and use the properties of <xref:System.Windows.SystemParameters> in order to style or customize a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b68b-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8b68b-104">Example</span></span>  
 <span data-ttu-id="8b68b-105">Systemressourcen machen mehrere systembasierte Einstellungen als Ressourcen verfügbar, um visuelle Elemente zu erstellen, die mit Systemeinstellungen konsistent sind.</span><span class="sxs-lookup"><span data-stu-id="8b68b-105">System resources expose several system based settings as resources in order to help you create visuals that are consistent with system settings.</span></span> <span data-ttu-id="8b68b-106"><xref:System.Windows.SystemParameters>ist eine Klasse, die sowohl Systemparametern und Ressourcenschlüssel, das Binden an die Werte enthält.</span><span class="sxs-lookup"><span data-stu-id="8b68b-106"><xref:System.Windows.SystemParameters> is a class that contains both system parameter value properties, and resource keys that bind to the values.</span></span> <span data-ttu-id="8b68b-107">Beispielsweise <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> ist ein <xref:System.Windows.SystemParameters> Eigenschaftswert und <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> wird der entsprechende Ressourcenschlüssel.</span><span class="sxs-lookup"><span data-stu-id="8b68b-107">For example, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> is a <xref:System.Windows.SystemParameters> property value and <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> is the corresponding resource key.</span></span>  
  
 <span data-ttu-id="8b68b-108">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], können Sie die Mitglieder der <xref:System.Windows.SystemParameters> als statische Eigenschaft oder eine dynamische Ressourcenverweise (mit der statischen Eigenschaft-Wert als Schlüssel).</span><span class="sxs-lookup"><span data-stu-id="8b68b-108">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can use the members of <xref:System.Windows.SystemParameters> as either a static property usage, or a dynamic resource references (with the static property value as the key).</span></span> <span data-ttu-id="8b68b-109">Verwenden Sie einen dynamischen Ressourcenverweis, wenn der systembasierte Wert automatisch beim Ausführen der Anwendung aktualisiert werden soll; verwenden Sie andernfalls einen statischen Verweis.</span><span class="sxs-lookup"><span data-stu-id="8b68b-109">Use a dynamic resource reference if you want the system based value to update automatically while the application runs; otherwise, use a static reference.</span></span> <span data-ttu-id="8b68b-110">/ / Ressourcenschlüssel haben das Suffix `Key` des Eigenschaftennamens angefügt.</span><span class="sxs-lookup"><span data-stu-id="8b68b-110">Resource keys have the suffix `Key` appended to the property name.</span></span>  
  
 <span data-ttu-id="8b68b-111">Im folgende Beispiel wird gezeigt, wie zugreifen auf und verwenden die statische Werte der <xref:System.Windows.SystemParameters> zu formatieren oder Anpassen einer Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="8b68b-111">The following example shows how to access and use the static values of <xref:System.Windows.SystemParameters> to style or customize a button.</span></span> <span data-ttu-id="8b68b-112">In diesem Markupbeispiel Größen eine Schaltfläche durch Anwenden von <xref:System.Windows.SystemParameters> Werte mit einer Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="8b68b-112">This markup example sizes a button by applying <xref:System.Windows.SystemParameters> values to a button.</span></span>  
  
 [!code-xaml[SystemRes_snip#ParameterStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#parameterstaticresources)]  
  
 <span data-ttu-id="8b68b-113">Verwenden Sie die Werte der <xref:System.Windows.SystemParameters> in Code können Sie keine statische Verweise oder dynamische Ressourcenverweise zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8b68b-113">To use the values of <xref:System.Windows.SystemParameters> in code, you do not have to use either static references or dynamic resource references.</span></span> <span data-ttu-id="8b68b-114">Verwenden Sie stattdessen die Werte der <xref:System.Windows.SystemParameters> Klasse.</span><span class="sxs-lookup"><span data-stu-id="8b68b-114">Instead, use the values of the <xref:System.Windows.SystemParameters> class.</span></span> <span data-ttu-id="8b68b-115">Obwohl die nicht schlüsselbezogene Eigenschaften als statische Eigenschaften, die das Laufzeitverhalten des offensichtlich definiert sind [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] als gehostete vom System wird, wertet die Eigenschaften in Echtzeit und ordnungsgemäß ein Konto, damit Benutzer vorgenommene Änderungen Systemwerte wird.</span><span class="sxs-lookup"><span data-stu-id="8b68b-115">Although the non-key properties are apparently defined as static properties, the runtime behavior of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] as hosted by the system will reevaluate the properties in realtime, and will properly account for user-driven changes to system values.</span></span> <span data-ttu-id="8b68b-116">Im folgende Beispiel wird gezeigt, wie die Breite und Höhe einer Schaltfläche festlegen, indem <xref:System.Windows.SystemParameters> Werte.</span><span class="sxs-lookup"><span data-stu-id="8b68b-116">The following example shows how to set the width and height of a button by using <xref:System.Windows.SystemParameters> values.</span></span>  
  
 [!code-csharp[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#parameterresourcescode)]
 [!code-vb[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#parameterresourcescode)]  
  
## <a name="see-also"></a><span data-ttu-id="8b68b-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b68b-117">See Also</span></span>  
 <xref:System.Windows.SystemParameters>  
 [<span data-ttu-id="8b68b-118">Zeichnen eines Bereichs mit einem Systempinsel</span><span class="sxs-lookup"><span data-stu-id="8b68b-118">Paint an Area with a System Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [<span data-ttu-id="8b68b-119">Verwenden von SystemFonts</span><span class="sxs-lookup"><span data-stu-id="8b68b-119">Use SystemFonts</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)  
 [<span data-ttu-id="8b68b-120">Verwenden von Systemparameterschlüsseln</span><span class="sxs-lookup"><span data-stu-id="8b68b-120">Use System Parameters Keys</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-system-parameters-keys.md)  
 [<span data-ttu-id="8b68b-121">Themen zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="8b68b-121">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)
