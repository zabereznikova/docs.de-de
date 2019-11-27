---
title: Suchen und Hervorheben von Text durch Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text, highlighting
- finding text
- text, finding
- UI automation, highlighting text
- UI automation, finding text
- highlighting text
ms.assetid: b77693f5-87bb-4b29-a297-05ff882e2044
ms.openlocfilehash: 0e5f856c69fab45a4c92e12746f357320d2e323c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435750"
---
# <a name="find-and-highlight-text-using-ui-automation"></a>Suchen und Hervorheben von Text durch Benutzeroberflächenautomatisierung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 In diesem Thema wird veranschaulicht, wie Sie das Vorkommen einer Zeichenfolge im Inhalt eines Text Steuer Elements mithilfe von [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]sequenziell suchen und hervorheben.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Windows.Automation.TextPattern> Objekt aus einem Text-Steuerelement abgerufen. Ein <xref:System.Windows.Automation.Text.TextPatternRange>-Objekt, das den Text Inhalt des gesamten Dokuments darstellt, wird dann mit der <xref:System.Windows.Automation.TextPattern.DocumentRange%2A>-Eigenschaft dieser <xref:System.Windows.Automation.TextPattern>erstellt. Zwei zusätzliche <xref:System.Windows.Automation.Text.TextPatternRange> Objekte werden dann für die sequenzielle Such-und Hervorhebungs Funktionalität erstellt.  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#SearchTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#searchtarget)]
[!code-vb[FindText#SearchTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#searchtarget)]  
  
## <a name="see-also"></a>Siehe auch

- [Suchen und Hervorheben von Text durch Benutzeroberflächenautomatisierung](find-and-highlight-text-using-ui-automation.md)
