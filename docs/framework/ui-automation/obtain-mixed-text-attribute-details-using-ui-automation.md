---
title: Abrufen verschiedener Textattributdetails mithilfe der Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d0e4c005-abd1-42bb-92a4-5faf87097311
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: b425aa4194e688a3814570cc47b8aa3b7ea97ee8
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47087410"
---
# <a name="obtain-mixed-text-attribute-details-using-ui-automation"></a>Abrufen verschiedener Textattributdetails mithilfe der Benutzeroberflächenautomatisierung
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: UI-Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In diesem Thema wird gezeigt, wie [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] verwendet wird, um Textattributdetails aus einem Textbereich abzurufen, der mehrere Attributwerte umfasst. Ein Textbereich kann der aktuellen Position der Einfügemarke (oder der degenerierten Auswahl) in einem Dokument, einer zusammenhängenden Auswahl von Text, einer Reihe nicht zusammenhängender ausgewählter Textstellen oder dem gesamten Text eines Dokuments entsprechen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie <xref:System.Windows.Automation.TextPattern.FontNameAttribute> aus einem Textbereich abgerufen wird, wobei <xref:System.Windows.Automation.Text.TextPatternRange.GetAttributeValue%2A> ein <xref:System.Windows.Automation.TextPattern.MixedAttributeValue> -Objekt zurückgibt.  
  
 [!code-csharp[FindText#RetrieveMixedAttributes](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#retrievemixedattributes)]
 [!code-vb[FindText#RetrieveMixedAttributes](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#retrievemixedattributes)]  
  
 Das <xref:System.Windows.Automation.TextPattern> -Steuerelementmuster unterstützt zusammen mit der <xref:System.Windows.Automation.Text.TextPatternRange> -Klasse grundlegende Textattribute, Eigenschaften und Methoden. Für steuerelementspezifische Funktionalität, die von <xref:System.Windows.Automation.TextPattern> oder <xref:System.Windows.Automation.Text.TextPatternRange>nicht unterstützt wird, stellt die <xref:System.Windows.Automation.AutomationElement> -Klasse Methoden für einen Benutzeroberflächenautomatisierungs-Client zur Verfügung, um auf das entsprechende systemeigene Objektmodell zuzugreifen.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über TextPattern für die Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-textpattern-overview.md)  
 [Hinzufügen von Inhalt in einem Textfeld mithilfe von Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/add-content-to-a-text-box-using-ui-automation.md)  
 [Suchen und Hervorheben von Text durch Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)  
 [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [Abrufen von Textattributen mithilfe der Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/obtain-text-attributes-using-ui-automation.md)
