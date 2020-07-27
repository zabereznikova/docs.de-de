---
title: Navigieren zwischen Benutzeroberflächenautomatisierungs-Elementen mit TreeWalker
description: Ein Codebeispiel, das zeigt, wie Sie mithilfe der TreeWalker-Klasse zwischen Benutzeroberflächenautomatisierungs-Elementen navigieren können.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes, TreeWalker
- TreeWalker class
- elements, navigating among
- UI Automation, navigating among elements
ms.assetid: afcd21dc-2ffa-48c9-9332-51269f44b7e9
ms.openlocfilehash: e1784862433083f15d600ea2ec39aee2323bbd12
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168025"
---
# <a name="navigate-among-ui-automation-elements-with-treewalker"></a>Navigieren zwischen Benutzeroberflächenautomatisierungs-Elementen mit TreeWalker
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Dieses Thema enthält Beispielcode, in dem gezeigt wird, wie [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Sie mithilfe der-Klasse zwischen Elementen navigieren können <xref:System.Windows.Automation.TreeWalker> .  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel <xref:System.Windows.Automation.TreeWalker.GetParent%2A> wird verwendet, um die Struktur zu durchlaufen [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] , bis das Stamm Element (oder der Desktop) gefunden wird. Das direkt untergeordnete Element, das das übergeordnete Fenster des angegebenen Elements ist.  
  
 [!code-csharp[UIAFocusTracker_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFocusTracker_snip/CSharp/FocusTracker.cs#102)]
 [!code-vb[UIAFocusTracker_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFocusTracker_snip/VisualBasic/FocusTracker.vb#102)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> werden und verwendet <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> , um eine zu erstellen <xref:System.Windows.Forms.TreeView> , die eine gesamte Teilstruktur von [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Elementen anzeigt, die in der Steuerelement Ansicht und aktiviert sind.  
  
 [!code-csharp[UIAClient_snip#174](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#174)]
 [!code-vb[UIAClient_snip#174](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#174)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Abrufen von Benutzeroberflächenautomatisierungs-Elementen](obtaining-ui-automation-elements.md)
