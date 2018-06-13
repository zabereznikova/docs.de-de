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
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: da455b10425c9e0b20a644679358dde469ed92e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400756"
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a><span data-ttu-id="41b45-102">Suchen eines Benutzeroberflächenautomatisierungs-Elements anhand einer Eigenschaftenbedingung</span><span class="sxs-lookup"><span data-stu-id="41b45-102">Find a UI Automation Element Based on a Property Condition</span></span>
> [!NOTE]
>  <span data-ttu-id="41b45-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="41b45-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="41b45-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="41b45-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="41b45-105">Dieses Thema enthält Beispielcode, der zeigt, wie Suchen eines Elements innerhalb der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Struktur auf Grundlage einer bestimmten Eigenschaft oder Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="41b45-105">This topic contains example code that shows how to locate an element within the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree based on a specific property or properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41b45-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="41b45-106">Example</span></span>  
 <span data-ttu-id="41b45-107">Im folgenden Beispiel einen Satz von eigenschaftsbedingungen werden angegeben, die kennzeichnen eines bestimmten Elements (oder Elemente), von Interesse sind der <xref:System.Windows.Automation.AutomationElement> Struktur.</span><span class="sxs-lookup"><span data-stu-id="41b45-107">In the following example, a set of property conditions are specified that identify a certain element (or elements) of interest in the <xref:System.Windows.Automation.AutomationElement> tree.</span></span> <span data-ttu-id="41b45-108">Eine Suche nach allen übereinstimmenden Elementen mit, erfolgt die <xref:System.Windows.Automation.AutomationElement.FindAll%2A> -Methode, die eine Reihe von umfasst <xref:System.Windows.Automation.AndCondition> boolesche Operationen, um die Anzahl der übereinstimmenden Elemente zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="41b45-108">A search for all matching elements is then performed with the <xref:System.Windows.Automation.AutomationElement.FindAll%2A> method that incorporates a series of <xref:System.Windows.Automation.AndCondition> boolean operations to limit the number of matching elements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41b45-109">Bei der Suche über die <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, sollten Sie versuchen, erhalten nur direkte untergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="41b45-109">When searching from the <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, you should try to obtain only direct children.</span></span> <span data-ttu-id="41b45-110">Eine Suche nach Nachfolgerelementen kann Hunderte oder Tausende von Elementen, was zu einem Stapelüberlauf durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="41b45-110">A search for descendants might iterate through hundreds or even thousands of elements, possibly resulting in a stack overflow.</span></span> <span data-ttu-id="41b45-111">Wenn Sie versuchen, ein bestimmtes Element auf einer niedrigeren Ebene abzurufen, sollten Sie die Suche aus dem Anwendungsfenster oder aus einem Container auf niedrigerer Ebene starten.</span><span class="sxs-lookup"><span data-stu-id="41b45-111">If you are attempting to obtain a specific element at a lower level, you should start your search from the application window or from a container at a lower level.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a><span data-ttu-id="41b45-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41b45-112">See Also</span></span>  
 [<span data-ttu-id="41b45-113">"InvokePattern" und ExpandCollapsePattern-Menü-Element-Beispiel</span><span class="sxs-lookup"><span data-stu-id="41b45-113">InvokePattern and ExpandCollapsePattern Menu Item Sample</span></span>](http://msdn.microsoft.com/library/b7fa141c-e2d1-4da2-a27f-81a7d1172210)  
 [<span data-ttu-id="41b45-114">Abrufen von Benutzeroberflächenautomatisierungs-Elementen</span><span class="sxs-lookup"><span data-stu-id="41b45-114">Obtaining UI Automation Elements</span></span>](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)  
 [<span data-ttu-id="41b45-115">Verwenden der AutomationID-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="41b45-115">Use the AutomationID Property</span></span>](../../../docs/framework/ui-automation/use-the-automationid-property.md)
