---
title: "Suchen eines Benutzeroberflächenautomatisierungs-Elements anhand einer Eigenschaftenbedingung"
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
- elements, finding by property conditions
- UI Automation, finding elements by property conditions
ms.assetid: 3acaee5a-6ce8-4c3e-81c8-67e59eb74477
caps.latest.revision: "19"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: cafd84ce3acea80905d686f33f23338e3581a9c4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a>Suchen eines Benutzeroberflächenautomatisierungs-Elements anhand einer Eigenschaftenbedingung
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Beispielcode, der zeigt, wie Suchen eines Elements innerhalb der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Struktur auf Grundlage einer bestimmten Eigenschaft oder Eigenschaften.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel einen Satz von eigenschaftsbedingungen werden angegeben, die kennzeichnen eines bestimmten Elements (oder Elemente), von Interesse sind der <xref:System.Windows.Automation.AutomationElement> Struktur. Eine Suche nach allen übereinstimmenden Elementen mit, erfolgt die <xref:System.Windows.Automation.AutomationElement.FindAll%2A> -Methode, die eine Reihe von umfasst <xref:System.Windows.Automation.AndCondition> boolesche Operationen, um die Anzahl der übereinstimmenden Elemente zu begrenzen.  
  
> [!NOTE]
>  Bei der Suche über die <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, sollten Sie versuchen, erhalten nur direkte untergeordnete Elemente. Eine Suche nach Nachfolgerelementen kann Hunderte oder Tausende von Elementen, was zu einem Stapelüberlauf durchlaufen. Wenn Sie versuchen, ein bestimmtes Element auf einer niedrigeren Ebene abzurufen, sollten Sie die Suche aus dem Anwendungsfenster oder aus einem Container auf niedrigerer Ebene starten.  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a>Siehe auch  
 ["InvokePattern" und ExpandCollapsePattern-Menü-Element-Beispiel](http://msdn.microsoft.com/en-us/b7fa141c-e2d1-4da2-a27f-81a7d1172210)  
 [Abrufen von Benutzeroberflächenautomatisierungs-Elementen](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)  
 [Verwenden der AutomationID-Eigenschaft](../../../docs/framework/ui-automation/use-the-automationid-property.md)
