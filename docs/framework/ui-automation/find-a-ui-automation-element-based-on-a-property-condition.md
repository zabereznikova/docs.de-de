---
title: Suchen eines Benutzeroberflächenautomatisierungs-Elements anhand einer Eigenschaftenbedingung
description: Suchen eines Benutzeroberflächenautomatisierungs-Elements auf der Grundlage einer Eigenschafts Bedingung Suchen Sie ein Element innerhalb der Benutzeroberflächenautomatisierungs-Struktur auf Grundlage einer bestimmten Eigenschaft oder Eigenschaften.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements, finding by property conditions
- UI Automation, finding elements by property conditions
ms.assetid: 3acaee5a-6ce8-4c3e-81c8-67e59eb74477
ms.openlocfilehash: 112f38d6bef726f92dbf13da70b88732929175dd
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557683"
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a><span data-ttu-id="51886-104">Suchen eines Benutzeroberflächenautomatisierungs-Elements anhand einer Eigenschaftenbedingung</span><span class="sxs-lookup"><span data-stu-id="51886-104">Find a UI Automation Element Based on a Property Condition</span></span>
> [!NOTE]
> <span data-ttu-id="51886-105">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="51886-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="51886-106">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="51886-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="51886-107">Dieses Thema enthält Beispielcode, in dem gezeigt wird, wie ein Element innerhalb der Struktur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] auf der Grundlage einer bestimmten Eigenschaft oder Eigenschaften gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="51886-107">This topic contains example code that shows how to locate an element within the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree based on a specific property or properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51886-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="51886-108">Example</span></span>  
 <span data-ttu-id="51886-109">Im folgenden Beispiel wird ein Satz von Eigenschafts Bedingungen angegeben, die ein bestimmtes Element (oder Elemente) in der Struktur identifizieren <xref:System.Windows.Automation.AutomationElement> .</span><span class="sxs-lookup"><span data-stu-id="51886-109">In the following example, a set of property conditions are specified that identify a certain element (or elements) of interest in the <xref:System.Windows.Automation.AutomationElement> tree.</span></span> <span data-ttu-id="51886-110">Anschließend wird mit der- <xref:System.Windows.Automation.AutomationElement.FindAll%2A> Methode, die eine Reihe von booleschen Vorgängen enthält, eine Suche nach allen übereinstimmenden Elementen durchgeführt, <xref:System.Windows.Automation.AndCondition> um die Anzahl der übereinstimmenden Elemente einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="51886-110">A search for all matching elements is then performed with the <xref:System.Windows.Automation.AutomationElement.FindAll%2A> method that incorporates a series of <xref:System.Windows.Automation.AndCondition> boolean operations to limit the number of matching elements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="51886-111">Beim Durchsuchen von <xref:System.Windows.Automation.AutomationElement.RootElement%2A> sollten Sie versuchen, nur direkt untergeordnete Elemente zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="51886-111">When searching from the <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, you should try to obtain only direct children.</span></span> <span data-ttu-id="51886-112">Eine Suche nach Nachfolgern kann Hunderte oder sogar Tausende von Elementen durchlaufen, was möglicherweise zu einem Stapelüberlauf führt.</span><span class="sxs-lookup"><span data-stu-id="51886-112">A search for descendants might iterate through hundreds or even thousands of elements, possibly resulting in a stack overflow.</span></span> <span data-ttu-id="51886-113">Wenn Sie versuchen, ein bestimmtes Element auf einer niedrigeren Ebene abzurufen, sollten Sie die Suche aus dem Anwendungsfenster oder aus einem Container auf niedrigerer Ebene starten.</span><span class="sxs-lookup"><span data-stu-id="51886-113">If you are attempting to obtain a specific element at a lower level, you should start your search from the application window or from a container at a lower level.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a><span data-ttu-id="51886-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51886-114">See also</span></span>

- <span data-ttu-id="51886-115">[Beispiel für das Menü Element "InvokePattern" und "expandredusepattern"](/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="51886-115">[InvokePattern and ExpandCollapsePattern Menu Item Sample](/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))</span></span>
- [<span data-ttu-id="51886-116">Abrufen von Benutzeroberflächenautomatisierungs-Elementen</span><span class="sxs-lookup"><span data-stu-id="51886-116">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
- [<span data-ttu-id="51886-117">Verwenden der AutomationID-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="51886-117">Use the AutomationID Property</span></span>](use-the-automationid-property.md)
