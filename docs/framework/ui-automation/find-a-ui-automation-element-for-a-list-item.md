---
title: "Suchen eines Benutzeroberflächenautomatisierungs-Elements für ein Listenelement"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
caps.latest.revision: "5"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: a00019e5aaaefaddd94689bd192973d5d5ad175a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a>Suchen eines Benutzeroberflächenautomatisierungs-Elements für ein Listenelement
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In diesem Thema wird gezeigt, wie zum Abrufen einer <xref:System.Windows.Automation.AutomationElement> für ein Element in einer Liste, wenn der Index des Elements bekannt ist.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt zwei Möglichkeiten zum Abrufen eines angegebenen Elements aus einer Liste, einen solchen mithilfe <xref:System.Windows.Automation.TreeWalker> und den anderen Using <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.  
  
 Das erste Verfahren ist für schnellere voraussichtlich [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] Steuerelemente, aber die zweite kann er schneller [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)] Steuerelemente.  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a>Siehe auch  
 [Abrufen von Benutzeroberflächenautomatisierungs-Elementen](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
