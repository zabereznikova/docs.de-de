---
title: Hinzufügen von Inhalt in einem Textfeld mithilfe von Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
ms.openlocfilehash: fdc52d0b94ce500b6560b60419d409f5cbd73b55
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932648"
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a>Hinzufügen von Inhalt in einem Textfeld mithilfe von Benutzeroberflächenautomatisierung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden [Sie unter Windows Automation-API: Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746)der Benutzeroberfläche.  
  
 Dieses Thema enthält Beispielcode, der veranschaulicht, wie [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] verwendet wird, um Text in ein einzeilige Textfeld einzufügen. Eine alternative Methode wird für mehrzeilige und Rich-Text-Steuer [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Elemente bereitgestellt, bei denen nicht anwendbar ist. Zu Vergleichszwecken veranschaulicht das Beispiel auch, wie Win32-Methoden verwendet werden, um die gleichen Ergebnisse zu erzielen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Sequenz von Text Steuerelementen in einer Zielanwendung durchlaufen. Jedes Text Steuerelement wird getestet, um zu <xref:System.Windows.Automation.ValuePattern> überprüfen, ob ein-Objekt mithilfe <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> der-Methode abgerufen werden kann. Wenn das Text Steuerelement unter <xref:System.Windows.Automation.ValuePattern>stützt, <xref:System.Windows.Automation.ValuePattern.SetValue%2A> wird die-Methode verwendet, um eine benutzerdefinierte Zeichenfolge in das Text Steuerelement einzufügen. Andernfalls wird die <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> -Methode verwendet.  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a>Siehe auch

- [TextPattern-Textbeispiel einfügen](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))
