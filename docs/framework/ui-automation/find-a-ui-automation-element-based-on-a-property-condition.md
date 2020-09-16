---
title: Suchen eines Benutzeroberflächenautomatisierungs-Elements anhand einer Eigenschaftenbedingung
description: Suchen eines Benutzeroberflächenautomatisierungs-Elements auf der Grundlage einer Eigenschafts Bedingung Suchen Sie ein Element innerhalb der Benutzeroberflächenautomatisierungs-Struktur auf Grundlage einer bestimmten Eigenschaft oder Eigenschaften.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements, finding by property conditions
- UI Automation, finding elements by property conditions
ms.assetid: 3acaee5a-6ce8-4c3e-81c8-67e59eb74477
ms.openlocfilehash: 112f38d6bef726f92dbf13da70b88732929175dd
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557683"
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a>Suchen eines Benutzeroberflächenautomatisierungs-Elements anhand einer Eigenschaftenbedingung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Dieses Thema enthält Beispielcode, in dem gezeigt wird, wie ein Element innerhalb der Struktur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] auf der Grundlage einer bestimmten Eigenschaft oder Eigenschaften gesucht wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Satz von Eigenschafts Bedingungen angegeben, die ein bestimmtes Element (oder Elemente) in der Struktur identifizieren <xref:System.Windows.Automation.AutomationElement> . Anschließend wird mit der- <xref:System.Windows.Automation.AutomationElement.FindAll%2A> Methode, die eine Reihe von booleschen Vorgängen enthält, eine Suche nach allen übereinstimmenden Elementen durchgeführt, <xref:System.Windows.Automation.AndCondition> um die Anzahl der übereinstimmenden Elemente einzuschränken.  
  
> [!NOTE]
> Beim Durchsuchen von <xref:System.Windows.Automation.AutomationElement.RootElement%2A> sollten Sie versuchen, nur direkt untergeordnete Elemente zu erhalten. Eine Suche nach Nachfolgern kann Hunderte oder sogar Tausende von Elementen durchlaufen, was möglicherweise zu einem Stapelüberlauf führt. Wenn Sie versuchen, ein bestimmtes Element auf einer niedrigeren Ebene abzurufen, sollten Sie die Suche aus dem Anwendungsfenster oder aus einem Container auf niedrigerer Ebene starten.  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a>Siehe auch

- [Beispiel für das Menü Element "InvokePattern" und "expandredusepattern"](/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))
- [Abrufen von Benutzeroberflächenautomatisierungs-Elementen](obtaining-ui-automation-elements.md)
- [Verwenden der AutomationID-Eigenschaft](use-the-automationid-property.md)
