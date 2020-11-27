---
title: Abrufen des Umschaltstatus eines Kontrollkästchens mithilfe von Benutzeroberflächenautomatisierung
description: Ein Codebeispiel, das zeigt, wie Sie den UMSCHALT Zustand eines Steuer Elements (z. b. ein Kontrollkästchen) mithilfe der Microsoft-Benutzeroberflächen Automatisierung erhalten.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, getting toggle states of check boxes
- check boxes, getting toggle states of
- getting, toggle states of check boxes
ms.assetid: 84fc31a3-175f-4e93-90a0-dd29d89b77ce
ms.openlocfilehash: 2ec0cc996461b13d0ddc3453188eeb3287a56be7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276437"
---
# <a name="get-the-toggle-state-of-a-check-box-using-ui-automation"></a>Abrufen des Umschaltstatus eines Kontrollkästchens mithilfe von Benutzeroberflächenautomatisierung

> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 In diesem Thema wird gezeigt, wie verwendet wird, [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] um den UMSCHALT Zustand eines-Steuer Elements zu erhalten.  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird die <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> -Methode der- <xref:System.Windows.Automation.AutomationElement> Klasse verwendet, um ein <xref:System.Windows.Automation.TogglePattern> -Objekt von einem Steuerelement abzurufen und seine-Eigenschaft zurückzugeben <xref:System.Windows.Automation.ToggleState> .  
  
 [!code-csharp[NavigatingWithTreeWalker#1200](../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigatingWithTreeWalker/CSharp/ClientClass.cs#1200)]
 [!code-vb[NavigatingWithTreeWalker#1200](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigatingWithTreeWalker/visualbasic/clientclass.vb#1200)]
