---
title: Aufrufen eines Steuerelements mithilfe von Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking controls
- UI Automation, invoking controls
- controls, invoking
ms.assetid: 5ee2de3f-256c-43ec-b64c-62ace91f9983
ms.openlocfilehash: e1b489e8daaaf9f5b8c0cb46374fa54bf165d49c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447000"
---
# <a name="invoke-a-control-using-ui-automation"></a>Aufrufen eines Steuerelements mithilfe von Benutzeroberflächenautomatisierung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Dieses Thema veranschaulicht das Ausführen der folgenden Aufgaben:  
  
- Suchen Sie ein Steuerelement, das bestimmten Eigenschaftsbedingungen entspricht, indem Sie die Steuerelementansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur für die Anwendung durchlaufen.  
  
- Erstellen Sie für jedes Steuerelement ein <xref:System.Windows.Automation.AutomationElement> .  
  
- Rufen Sie ein <xref:System.Windows.Automation.InvokePattern> -Objekt von jedem gefundenen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Element ab, das das <xref:System.Windows.Automation.InvokePattern> -Steuerelementmuster unterstützt.  
  
- Verwenden Sie <xref:System.Windows.Automation.InvokePattern.Invoke%2A> zum Aufrufen des Steuerelements über einen Clientereignishandler.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> -Methode der <xref:System.Windows.Automation.AutomationElement> -Klasse, um ein <xref:System.Windows.Automation.InvokePattern> -Objekt zu generieren und mithilfe der <xref:System.Windows.Automation.InvokePattern.Invoke%2A> -Methode ein Steuerelement aufzurufen.  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
[!code-csharp[InvokePatternApp#1102](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1102)]
[!code-vb[InvokePatternApp#1102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1102)]  
  
## <a name="see-also"></a>Siehe auch

- [InvokePattern, ExpandCollapsePattern, and TogglePattern Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/InvokePattern)
