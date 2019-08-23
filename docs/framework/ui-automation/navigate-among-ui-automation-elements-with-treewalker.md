---
title: Navigieren zwischen Benutzeroberflächenautomatisierungs-Elementen mit TreeWalker
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
ms.openlocfilehash: 506cc4db3fcf255d270f72470a1f0d68e9cca7ce
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966421"
---
# <a name="navigate-among-ui-automation-elements-with-treewalker"></a>Navigieren zwischen Benutzeroberflächenautomatisierungs-Elementen mit TreeWalker
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden [Sie unter Windows Automation-API: Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746)der Benutzeroberfläche.  
  
 Dieses Thema enthält Beispielcode, in dem gezeigt wird, [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] wie Sie mithilfe der <xref:System.Windows.Automation.TreeWalker> -Klasse zwischen Elementen navigieren können.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird <xref:System.Windows.Automation.TreeWalker.GetParent%2A> verwendet, um die [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Struktur zu durchlaufen, bis das Stamm Element (oder der Desktop) gefunden wird. Das direkt untergeordnete Element, das das übergeordnete Fenster des angegebenen Elements ist.  
  
 [!code-csharp[UIAFocusTracker_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFocusTracker_snip/CSharp/FocusTracker.cs#102)]
 [!code-vb[UIAFocusTracker_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFocusTracker_snip/VisualBasic/FocusTracker.vb#102)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> und <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> verwendet, um <xref:System.Windows.Forms.TreeView> eine zu erstellen, die eine gesamte [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Teilstruktur von Elementen anzeigt, die in der Steuerelement Ansicht und aktiviert sind.  
  
 [!code-csharp[UIAClient_snip#174](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#174)]
 [!code-vb[UIAClient_snip#174](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#174)]  
  
## <a name="see-also"></a>Siehe auch

- [Abrufen von Benutzeroberflächenautomatisierungs-Elementen](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
