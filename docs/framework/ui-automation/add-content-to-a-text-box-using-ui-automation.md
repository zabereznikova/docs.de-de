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
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 4b3179333119d1ff516c6176298fa25514a9ba66
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a>Hinzufügen von Inhalt in einem Textfeld mithilfe von Benutzeroberflächenautomatisierung
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Beispielcode, der veranschaulicht [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] zum Einfügen von Text in einem einzeiligen Textfeld. Eine alternative Methode für mehrzeilige und rich-Text-Steuerelemente bereitgestellt wird, in dem [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ist nicht anwendbar. Für Vergleichszwecke können veranschaulicht das Beispiel auch Win32-Methoden verwenden, um die gleichen Ergebnisse zu erreichen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel Durchlaufen einer Sequenz von Textsteuerelementen eine Zielanwendung. Jedes Textfeld-Steuerelement wird daraufhin überprüft, ob eine <xref:System.Windows.Automation.ValuePattern> -Objekt abgerufen werden kann, mithilfe der <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> Methode. Wenn im Textsteuerelement ein unterstützt <xref:System.Windows.Automation.ValuePattern>die <xref:System.Windows.Automation.ValuePattern.SetValue%2A> Methode wird verwendet, um eine benutzerdefinierte Zeichenfolge in das Textfeld-Steuerelement einfügen. Andernfalls die <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> Methode wird verwendet.  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a>Siehe auch  
 [Einfügen von TextPattern-Text (Beispiel)](http://msdn.microsoft.com/library/67353f93-7ee2-42f2-ab76-5c078cf6ca16)
