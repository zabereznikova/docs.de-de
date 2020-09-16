---
title: Hinzufügen von Inhalt in einem Textfeld mithilfe von Benutzeroberflächenautomatisierung
description: Ein Beispiel zum Hinzufügen von Inhalt zu einem einzeiligen Textfeld finden Sie unter Verwenden der Microsoft-Benutzeroberflächen Automatisierung in .net.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
ms.openlocfilehash: 5e7ab77f1dcc2198e69255013eeb30cc703a235f
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543120"
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a>Hinzufügen von Inhalt in einem Textfeld mithilfe von Benutzeroberflächenautomatisierung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Dieses Thema enthält Beispielcode, der veranschaulicht, wie verwendet wird, [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] um Text in ein einzeilige Textfeld einzufügen. Eine alternative Methode wird für mehrzeilige und Rich-Text-Steuerelemente bereitgestellt, bei denen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] nicht anwendbar ist. Zu Vergleichszwecken veranschaulicht das Beispiel auch, wie Win32-Methoden verwendet werden, um die gleichen Ergebnisse zu erzielen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Sequenz von Text Steuerelementen in einer Zielanwendung durchlaufen. Jedes Text Steuerelement wird getestet, um zu überprüfen, ob ein- <xref:System.Windows.Automation.ValuePattern> Objekt mithilfe der-Methode abgerufen werden kann <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> . Wenn das Text Steuerelement unterstützt <xref:System.Windows.Automation.ValuePattern> , <xref:System.Windows.Automation.ValuePattern.SetValue%2A> wird die-Methode verwendet, um eine benutzerdefinierte Zeichenfolge in das Text Steuerelement einzufügen. Andernfalls wird die- <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> Methode verwendet.  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a>Siehe auch

- [TextPattern-Textbeispiel einfügen](/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))
