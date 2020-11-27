---
title: Verschieben eines Benutzeroberflächenautomatisierungs-Elements
description: Siehe Beispielcode, der zeigt, wie ein Benutzeroberflächenautomatisierungs-Element an eine angegebene Bildschirmposition verschoben wird. Es verwendet die WindowPattern-und TransformPattern-Steuerelement Muster.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- moving elements
- elements, moving
- UI Automation, moving elements
ms.assetid: 4042cb44-e27e-4a03-ac36-9be1eed65b47
ms.openlocfilehash: 847015818a6c916beb5d026cb7f59a86cebd68cd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261188"
---
# <a name="move-a-ui-automation-element"></a><span data-ttu-id="cf6b1-104">Verschieben eines Benutzeroberflächenautomatisierungs-Elements</span><span class="sxs-lookup"><span data-stu-id="cf6b1-104">Move a UI Automation Element</span></span>

> [!NOTE]
> <span data-ttu-id="cf6b1-105">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="cf6b1-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="cf6b1-106">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="cf6b1-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="cf6b1-107">In diesem Beispiel wird das Verschieben eines [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Elements an eine angegebene Bildschirmposition veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="cf6b1-107">This example demonstrates how to move a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element to a specified screen location.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf6b1-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cf6b1-108">Example</span></span>  

 <span data-ttu-id="cf6b1-109">Im folgenden Beispiel wird das <xref:System.Windows.Automation.WindowPattern> -Steuerelement und das- <xref:System.Windows.Automation.TransformPattern> Steuerelement Muster verwendet, um eine Win32-Zielanwendung Programm gesteuert an diskrete Bildschirm Positionen zu verschieben und zu verfolgen <xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty> <xref:System.Windows.Automation.AutomationElement.AutomationPropertyChangedEvent></span><span class="sxs-lookup"><span data-stu-id="cf6b1-109">The following example uses the <xref:System.Windows.Automation.WindowPattern> and <xref:System.Windows.Automation.TransformPattern> control patterns to programmatically move a Win32 target application to discrete screen locations and track the <xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty> <xref:System.Windows.Automation.AutomationElement.AutomationPropertyChangedEvent>.</span></span>  
  
 [!code-csharp[WindowMove#1301](../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowMove/CSharp/WindowMove.cs#1301)]
 [!code-vb[WindowMove#1301](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowMove/VisualBasic/windowmove.vb#1301)]  
[!code-csharp[WindowMove#1300](../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowMove/CSharp/WindowMove.cs#1300)]
[!code-vb[WindowMove#1300](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowMove/VisualBasic/windowmove.vb#1300)]  
  
## <a name="see-also"></a><span data-ttu-id="cf6b1-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cf6b1-110">See also</span></span>

- [<span data-ttu-id="cf6b1-111">WindowPattern-Beispiel</span><span class="sxs-lookup"><span data-stu-id="cf6b1-111">WindowPattern Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/WindowMove)
