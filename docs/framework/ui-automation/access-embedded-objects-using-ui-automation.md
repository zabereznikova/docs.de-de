---
title: Zugreifen auf eingebettete Objekte mit Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- embedded objects, accessing
- accessing embedded objects
- UI Automation, accessing embedded objects
ms.assetid: a5b513ec-7fa6-4460-869f-c18ff04f7cf2
ms.openlocfilehash: 75c63360eab2cde95698bdaded5c5249a3ca89fd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447266"
---
# <a name="access-embedded-objects-using-ui-automation"></a>Zugreifen auf eingebettete Objekte mit Benutzeroberflächenautomatisierung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 In diesem Thema wird gezeigt, wie Sie mithilfe von [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Objekte verfügbar machen können, die im Inhalt eines Textsteuerelements eingebettet sind.  
  
> [!NOTE]
> Bei eingebetteten Objekten kann es sich um Bilder, Links, Schaltflächen, Tabellen oder ActiveX-Steuerelemente handeln.  
  
 Eingebettete Objekte werden als untergeordnete Elemente des [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Textanbieters angesehen Dadurch können sie über dieselbe Benutzeroberflächenautomatisierungs-Struktur wie alle anderen [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] -Elemente verfügbar gemacht werden. Funktionen werden dagegen über die Steuerelementmuster verfügbar gemacht, die üblicherweise für den Steuerelementtyp der eingebetteten Objekte erforderlich sind (Links sind beispielsweise textbasiert und unterstützen daher <xref:System.Windows.Automation.TextPattern>).  
  
 ![Embedded objects in a text container.](./media/uia-textpattern-embeddedobjects.PNG "UIA_TextPattern_EmbeddedObjects")  
A sample document with textual content, ("Did You Know?"…) and two embedded objects (a picture of a whale and a text hyperlink), used as a target for the code examples.  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden Beispielcode wird veranschaulicht, wie eine Auflistung eingebetteter Objekte aus einem [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Textanbieter abgerufen werden kann. Wenn Sie das Beispieldokument aus der Einführung verwenden, werden zwei Objekte zurückgegeben (ein Bild- und ein Textelement).  
  
> [!NOTE]
> Das Bildelement sollte ihm zugeordneten Text haben, der das Bild beschreibt und üblicherweise in der <xref:System.Windows.Automation.AutomationElement.NameProperty> des Bildelements (z. B. „Ein blauer Wal“) steht. Wenn jedoch ein Textbereich abgerufen wird, der das Bildobjekt umfasst, werden weder das Bild noch dieser beschreibende Text im Textstream zurückgegeben.  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#GetChildren](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#getchildren)]
[!code-vb[FindText#GetChildren](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#getchildren)]  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden Beispielcode wird veranschaulicht, wie ein Textbereich aus einem eingebetteten Objekt in einem [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Textanbieter abgerufen werden kann. Der abgerufene Textbereich ist ein leerer Bereich, dessen Startpunkt auf das Leerzeichen in „… ocean.(Leerzeichen)" folgt und dessen Endpunkt vor dem abschließenden "." positioniert ist und der den eingebetteten Link darstellt (siehe Abbildung in der Einführung). Obwohl dies ein leerer Bereich ist, wird er nicht als degenerierter Bereich angesehen, da er eine Spanne ungleich null hat.  
  
> [!NOTE]
> <xref:System.Windows.Automation.TextPattern> kann ein eingebettetes Textobjekt, etwa einen Link, abrufen. Allerdings muss ein sekundäres <xref:System.Windows.Automation.TextPattern> aus dem eingebetteten Objekt abgerufen werden, um dessen gesamte Funktionalität verfügbar zu machen.  
  
 [!code-csharp[UIATextPattern_snip#GetRangeFromChild](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#getrangefromchild)]
 [!code-vb[UIATextPattern_snip#GetRangeFromChild](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#getrangefromchild)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über TextPattern für die Benutzeroberflächenautomatisierung](ui-automation-textpattern-overview.md)
- [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](ui-automation-control-patterns-overview.md)
- [Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients](ui-automation-control-patterns-for-clients.md)
- [Hinzufügen von Inhalt in einem Textfeld mithilfe von Benutzeroberflächenautomatisierung](add-content-to-a-text-box-using-ui-automation.md)
- [Suchen und Hervorheben von Text durch Benutzeroberflächenautomatisierung](find-and-highlight-text-using-ui-automation.md)
