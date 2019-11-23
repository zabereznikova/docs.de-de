---
title: Durchlaufen von Text mit Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, traversing text
- text, traversing
- traversing text
ms.assetid: 3ddb3b7b-1d6b-4dba-8678-5a68e868aadb
ms.openlocfilehash: 71df7c8f9dde388ffc4445389e105a4ad686539f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441876"
---
# <a name="traverse-text-using-ui-automation"></a>Durchlaufen von Text mit Benutzeroberflächenautomatisierung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 In diesem Thema wird die Verwendung der [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] zum Durchlaufen des Textinhalts eines Dokuments durch <xref:System.Windows.Automation.Text.TextUnit> -Inkremente veranschaulicht.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird gezeigt, wie der Inhalt eines Benutzeroberflächenautomatisierungs-Textanbieters durchlaufen wird. Die <xref:System.Windows.Automation.Text.TextPatternRange.Move%2A> -Methode verschiebt die <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.Start> - und <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End> -Endpunkte eines <xref:System.Windows.Automation.Text.TextPatternRange>. Dieser Textbereich ist üblicherweise ein degenerierter Bereich, der die Einfügemarke darstellt.  
  
> [!NOTE]
> Da nur textbasierte eingebettete Objekte als Teil des Textstreams betrachtet werden, haben eingebettete Objekte keine Auswirkung auf `Move` oder dessen Rückgabewert.  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#Navigate](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#navigate)]
[!code-vb[FindText#Navigate](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#navigate)]  
  
 Jede Methode, die <xref:System.Windows.Automation.Text.TextUnit> verwendet, wird bis zur nächstgrößeren unterstützten <xref:System.Windows.Automation.Text.TextUnit> zurückgestellt, wenn die angegebene <xref:System.Windows.Automation.Text.TextUnit> vom Steuerelement nicht unterstützt wird.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über TextPattern für die Benutzeroberflächenautomatisierung](ui-automation-textpattern-overview.md)
- [Hinzufügen von Inhalt in einem Textfeld mithilfe von Benutzeroberflächenautomatisierung](add-content-to-a-text-box-using-ui-automation.md)
- [Suchen und Hervorheben von Text durch Benutzeroberflächenautomatisierung](find-and-highlight-text-using-ui-automation.md)
- [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](ui-automation-control-patterns-overview.md)
- [Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients](ui-automation-control-patterns-for-clients.md)
