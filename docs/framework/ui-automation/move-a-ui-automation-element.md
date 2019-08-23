---
title: Verschieben eines Benutzeroberflächenautomatisierungs-Elements
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- moving elements
- elements, moving
- UI Automation, moving elements
ms.assetid: 4042cb44-e27e-4a03-ac36-9be1eed65b47
ms.openlocfilehash: 43b1e005cdb499fae920a0999feaa56c5409f653
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964694"
---
# <a name="move-a-ui-automation-element"></a><span data-ttu-id="02850-102">Verschieben eines Benutzeroberflächenautomatisierungs-Elements</span><span class="sxs-lookup"><span data-stu-id="02850-102">Move a UI Automation Element</span></span>
> [!NOTE]
> <span data-ttu-id="02850-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="02850-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="02850-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden [Sie unter Windows Automation-API: Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746)der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="02850-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="02850-105">In diesem Beispiel wird das Verschieben eines [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Elements an eine angegebene Bildschirmposition veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="02850-105">This example demonstrates how to move a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element to a specified screen location.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02850-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="02850-106">Example</span></span>  
 <span data-ttu-id="02850-107">Im folgenden Beispiel werden die Steuerelementmuster <xref:System.Windows.Automation.WindowPattern> und <xref:System.Windows.Automation.TransformPattern> dazu verwendet, um eine [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] target application to discrete screen locations und track the <xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty> <xref:System.Windows.Automation.AutomationElement.AutomationPropertyChangedEvent>nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="02850-107">The following example uses the <xref:System.Windows.Automation.WindowPattern> and <xref:System.Windows.Automation.TransformPattern> control patterns to programmatically move a [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] target application to discrete screen locations and track the <xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty> <xref:System.Windows.Automation.AutomationElement.AutomationPropertyChangedEvent>.</span></span>  
  
 [!code-csharp[WindowMove#1301](../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowMove/CSharp/WindowMove.cs#1301)]
 [!code-vb[WindowMove#1301](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowMove/VisualBasic/windowmove.vb#1301)]  
[!code-csharp[WindowMove#1300](../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowMove/CSharp/WindowMove.cs#1300)]
[!code-vb[WindowMove#1300](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowMove/VisualBasic/windowmove.vb#1300)]  
  
## <a name="see-also"></a><span data-ttu-id="02850-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02850-108">See also</span></span>

- [<span data-ttu-id="02850-109">WindowPattern-Beispiel</span><span class="sxs-lookup"><span data-stu-id="02850-109">WindowPattern Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/WindowMove)
