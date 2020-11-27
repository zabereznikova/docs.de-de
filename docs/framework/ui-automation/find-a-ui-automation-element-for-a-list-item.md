---
title: Suchen eines Benutzeroberflächenautomatisierungs-Elements für ein Listenelement
description: Sehen Sie sich ein Beispiel an, das zeigt, wie Sie ein Benutzeroberflächenautomatisierungs-Element für ein Listenelement suchen, wenn der Index des Elements bekannt ist.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
ms.openlocfilehash: 95f6b558cc53b00701232f247f8de7f8c603e3ac
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276476"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a>Suchen eines Benutzeroberflächenautomatisierungs-Elements für ein Listenelement

> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 In diesem Thema wird gezeigt, wie ein- <xref:System.Windows.Automation.AutomationElement> Objekt für ein Element in einer Liste abgerufen wird, wenn der Index des Elements bekannt ist.  
  
## <a name="example"></a>Beispiel  

 Das folgende Beispiel zeigt zwei Möglichkeiten, ein angegebenes Element aus einer Liste abzurufen, wobei eine mit <xref:System.Windows.Automation.TreeWalker> und die andere mithilfe von verwendet wird <xref:System.Windows.Automation.AutomationElement.FindAll%2A> .  
  
 Das erste Verfahren ist tendenziell für Win32-Steuerelemente schneller, aber das zweite ist schneller für Windows Presentation Foundation (WPF)-Steuerelemente.  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Abrufen von Benutzeroberflächenautomatisierungs-Elementen](obtaining-ui-automation-elements.md)
