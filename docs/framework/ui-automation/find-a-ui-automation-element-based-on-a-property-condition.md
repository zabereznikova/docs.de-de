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
ms.openlocfilehash: 24c236e3d577fd4c9844546b04eefeee9eaf1de8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965141"
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a>Suchen eines Benutzeroberflächenautomatisierungs-Elements anhand einer Eigenschaftenbedingung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden [Sie unter Windows Automation-API: Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746)der Benutzeroberfläche.  
  
 Dieses Thema enthält Beispielcode, in dem gezeigt wird, wie ein Element [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] innerhalb der Struktur auf der Grundlage einer bestimmten Eigenschaft oder Eigenschaften gesucht wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Satz von Eigenschafts Bedingungen angegeben, die ein bestimmtes Element (oder Elemente) in der <xref:System.Windows.Automation.AutomationElement> Struktur identifizieren. Anschließend wird mit der <xref:System.Windows.Automation.AutomationElement.FindAll%2A> -Methode, die eine Reihe von <xref:System.Windows.Automation.AndCondition> booleschen Vorgängen enthält, eine Suche nach allen übereinstimmenden Elementen durchgeführt, um die Anzahl der übereinstimmenden Elemente einzuschränken.  
  
> [!NOTE]
> Beim Durchsuchen von <xref:System.Windows.Automation.AutomationElement.RootElement%2A>sollten Sie versuchen, nur direkt untergeordnete Elemente zu erhalten. Eine Suche nach Nachfolgern kann Hunderte oder sogar Tausende von Elementen durchlaufen, was möglicherweise zu einem Stapelüberlauf führt. Wenn Sie versuchen, ein bestimmtes Element auf einer niedrigeren Ebene abzurufen, sollten Sie die Suche aus dem Anwendungsfenster oder aus einem Container auf niedrigerer Ebene starten.  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a>Siehe auch

- [Beispiel für das Menü Element "InvokePattern" und "expandredusepattern"](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))
- [Abrufen von Benutzeroberflächenautomatisierungs-Elementen](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
- [Verwenden der AutomationID-Eigenschaft](../../../docs/framework/ui-automation/use-the-automationid-property.md)
