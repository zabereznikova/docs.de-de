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
ms.openlocfilehash: a80ca015a3bed202e80a93f487d37278ed03439d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54740384"
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a>Suchen eines Benutzeroberflächenautomatisierungs-Elements anhand einer Eigenschaftenbedingung
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Beispielcode, der zeigt, wie Sie das Suchen eines Elements in der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] baumbasierte auf eine bestimmte Eigenschaft oder Eigenschaften.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel ein Satz von eigenschaftsbedingungen werden angegeben, die Identifizieren eines bestimmten Elements (oder Elemente), von Interesse sind der <xref:System.Windows.Automation.AutomationElement> Struktur. Eine Suche nach allen übereinstimmenden Elementen erfolgt dann mit der <xref:System.Windows.Automation.AutomationElement.FindAll%2A> Methode, die eine Reihe von beinhaltet <xref:System.Windows.Automation.AndCondition> boolesche Operationen, um die Anzahl der übereinstimmenden Elemente beschränken.  
  
> [!NOTE]
>  Bei der Suche über die <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, sollten Sie versuchen, erhalten nur direkte untergeordnete Elemente. Eine Suche nach Nachfolgerelementen kann Hunderte oder sogar Tausende von Elementen, was möglicherweise zu einem Stapelüberlauf durchlaufen. Wenn Sie versuchen, ein bestimmtes Element auf einer niedrigeren Ebene abzurufen, sollten Sie die Suche aus dem Anwendungsfenster oder aus einem Container auf niedrigerer Ebene starten.  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a>Siehe auch
- ["InvokePattern" und ExpandCollapsePattern-Menü-Element-Beispiel](https://msdn.microsoft.com/library/b7fa141c-e2d1-4da2-a27f-81a7d1172210)
- [Abrufen von Benutzeroberflächenautomatisierungs-Elementen](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
- [Verwenden der AutomationID-Eigenschaft](../../../docs/framework/ui-automation/use-the-automationid-property.md)
