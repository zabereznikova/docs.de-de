---
title: Suchen eines Benutzeroberflächenautomatisierungs-Elements anhand einer Eigenschaftenbedingung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements, finding by property conditions
- UI Automation, finding elements by property conditions
ms.assetid: 3acaee5a-6ce8-4c3e-81c8-67e59eb74477
ms.openlocfilehash: 24c236e3d577fd4c9844546b04eefeee9eaf1de8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965141"
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a><span data-ttu-id="e2bd4-102">Suchen eines Benutzeroberflächenautomatisierungs-Elements anhand einer Eigenschaftenbedingung</span><span class="sxs-lookup"><span data-stu-id="e2bd4-102">Find a UI Automation Element Based on a Property Condition</span></span>
> [!NOTE]
> <span data-ttu-id="e2bd4-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e2bd4-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="e2bd4-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden [Sie unter Windows Automation-API: Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746)der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="e2bd4-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="e2bd4-105">Dieses Thema enthält Beispielcode, in dem gezeigt wird, wie ein Element [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] innerhalb der Struktur auf der Grundlage einer bestimmten Eigenschaft oder Eigenschaften gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="e2bd4-105">This topic contains example code that shows how to locate an element within the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree based on a specific property or properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2bd4-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e2bd4-106">Example</span></span>  
 <span data-ttu-id="e2bd4-107">Im folgenden Beispiel wird ein Satz von Eigenschafts Bedingungen angegeben, die ein bestimmtes Element (oder Elemente) in der <xref:System.Windows.Automation.AutomationElement> Struktur identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e2bd4-107">In the following example, a set of property conditions are specified that identify a certain element (or elements) of interest in the <xref:System.Windows.Automation.AutomationElement> tree.</span></span> <span data-ttu-id="e2bd4-108">Anschließend wird mit der <xref:System.Windows.Automation.AutomationElement.FindAll%2A> -Methode, die eine Reihe von <xref:System.Windows.Automation.AndCondition> booleschen Vorgängen enthält, eine Suche nach allen übereinstimmenden Elementen durchgeführt, um die Anzahl der übereinstimmenden Elemente einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="e2bd4-108">A search for all matching elements is then performed with the <xref:System.Windows.Automation.AutomationElement.FindAll%2A> method that incorporates a series of <xref:System.Windows.Automation.AndCondition> boolean operations to limit the number of matching elements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e2bd4-109">Beim Durchsuchen von <xref:System.Windows.Automation.AutomationElement.RootElement%2A>sollten Sie versuchen, nur direkt untergeordnete Elemente zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e2bd4-109">When searching from the <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, you should try to obtain only direct children.</span></span> <span data-ttu-id="e2bd4-110">Eine Suche nach Nachfolgern kann Hunderte oder sogar Tausende von Elementen durchlaufen, was möglicherweise zu einem Stapelüberlauf führt.</span><span class="sxs-lookup"><span data-stu-id="e2bd4-110">A search for descendants might iterate through hundreds or even thousands of elements, possibly resulting in a stack overflow.</span></span> <span data-ttu-id="e2bd4-111">Wenn Sie versuchen, ein bestimmtes Element auf einer niedrigeren Ebene abzurufen, sollten Sie die Suche aus dem Anwendungsfenster oder aus einem Container auf niedrigerer Ebene starten.</span><span class="sxs-lookup"><span data-stu-id="e2bd4-111">If you are attempting to obtain a specific element at a lower level, you should start your search from the application window or from a container at a lower level.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a><span data-ttu-id="e2bd4-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2bd4-112">See also</span></span>

- <span data-ttu-id="e2bd4-113">[Beispiel für das Menü Element "InvokePattern" und "expandredusepattern"](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="e2bd4-113">[InvokePattern and ExpandCollapsePattern Menu Item Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))</span></span>
- [<span data-ttu-id="e2bd4-114">Abrufen von Benutzeroberflächenautomatisierungs-Elementen</span><span class="sxs-lookup"><span data-stu-id="e2bd4-114">Obtaining UI Automation Elements</span></span>](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
- [<span data-ttu-id="e2bd4-115">Verwenden der AutomationID-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e2bd4-115">Use the AutomationID Property</span></span>](../../../docs/framework/ui-automation/use-the-automationid-property.md)
