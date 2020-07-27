---
title: Abrufen von unterstützten Steuerelementmustern für Benutzeroberflächenautomatisierung
description: Ein Beispiel für das Abrufen von unterstützten Steuerelement Muster Objekten aus Benutzeroberflächenautomatisierungs-Elementen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, getting
- UI Automation, getting control patterns
- getting, control patterns
ms.assetid: 006c54c9-50bf-48d9-a855-9d62eb95603a
ms.openlocfilehash: f2905b81a1af2f86c78b082f0241e2181c384d25
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164153"
---
# <a name="get-supported-ui-automation-control-patterns"></a>Abrufen von unterstützten Steuerelementmustern für Benutzeroberflächenautomatisierung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 In diesem Thema wird gezeigt, wie Steuerelementmusterobjekte aus [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Elementen abgerufen werden.  
  
### <a name="obtain-all-control-patterns"></a>Abrufen aller Steuerelementmuster  
  
1. Rufen Sie das <xref:System.Windows.Automation.AutomationElement>-Objekt ab, an dessen Steuerelementmustern Sie interessiert sind.  
  
2. Rufen Sie <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> auf, um alle Steuerelementmuster aus dem Element abzurufen.  
  
> [!CAUTION]
> Ein Client sollte auf keinen Fall <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> verwenden. Die Leistung kann schwerwiegend beeinträchtigt werden, da diese Methode intern <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> für jedes vorhandene Steuerelementmuster aufruft. Wenn möglich sollte ein Client <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> für die gewünschten Steuerelementmuster aufrufen.  
  
### <a name="obtain-a-specific-control-pattern"></a>Abrufen eines bestimmten Steuerelementmusters  
  
1. Rufen Sie das <xref:System.Windows.Automation.AutomationElement>-Objekt ab, an dessen Steuerelementmustern Sie interessiert sind.  
  
2. Rufen Sie <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> oder <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> auf, um auf ein bestimmtes Muster abzufragen. Diese Methoden ähneln sich, wenn das Muster aber nicht gefunden wird, löst <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> eine Ausnahme aus, während <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> den Wert `false` zurückgibt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Windows.Automation.AutomationElement> für ein Listenelement und aus diesem Element ein <xref:System.Windows.Automation.SelectionItemPattern> abgerufen.  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients](ui-automation-control-patterns-for-clients.md)
