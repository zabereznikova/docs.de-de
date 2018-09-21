---
title: Suchen eines Benutzeroberflächenautomatisierungs-Elements für ein Listenelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: b569b43d83e8a7f1b0fa82b79bc1fc40977b72ba
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2018
ms.locfileid: "46518168"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a>Suchen eines Benutzeroberflächenautomatisierungs-Elements für ein Listenelement
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: UI-Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In diesem Thema wird gezeigt, wie zum Abrufen einer <xref:System.Windows.Automation.AutomationElement> für ein Element in einer Liste, wenn der Index des Elements unbekannt ist.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt zwei Möglichkeiten zum Abrufen eines angegebenen Elements aus einer Liste mit <xref:System.Windows.Automation.TreeWalker> und der andere mit <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.  
  
 Das erste Verfahren ist meist schneller für [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] Steuerelemente, aber die zweite ist für Windows Presentation Foundation (WPF)-Steuerelemente schneller.  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a>Siehe auch  
 [Abrufen von Benutzeroberflächenautomatisierungs-Elementen](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
