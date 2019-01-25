---
title: 'Vorgehensweise: Erstellen einer Textdekoration'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [WPF], baseline
- text [WPF], decorations
- fonts [WPF], underline
- fonts [WPF], overline
- strikethrough type [WPF]
- fonts [WPF], strikethrough
- overline type [WPF]
- underline type [WPF]
- typography [WPF], text decorations
- baseline type [WPF]
ms.assetid: cf3cb4e7-782a-4be7-b2d4-e0935e21e4e0
ms.openlocfilehash: b85bbaed13d9406f85c62a9a5bc5ca220d90b0b2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607945"
---
# <a name="how-to-create-a-text-decoration"></a>Vorgehensweise: Erstellen einer Textdekoration
Ein <xref:System.Windows.TextDecoration> Objekt ist eine visuelle Verzierung, können Sie Text hinzufügen. Es gibt vier Arten von Textdekorationen: Unterstreichung, Baseline, durchgestrichen und Überstrichen. Das folgende Beispiel zeigt die Speicherorte der Textdekorationen relativ zum Text.  
  
 ![Diagramm der Textergänzungsstellen](../../../../docs/framework/wpf/advanced/media/textdecoration01.gif "TextDecoration01")  
Beispiel für Text-Decoration-Typen  
  
 Erstellen Sie zum Hinzufügen einer Textdekorations Text eine <xref:System.Windows.TextDecoration> Objekt, und ändern Sie seine Eigenschaften. Verwenden der <xref:System.Windows.TextDecoration.Location%2A> Eigenschaft, um anzugeben, wo die Textdekoration angezeigt wird, z. B. unterstrichen. Verwenden der <xref:System.Windows.TextDecoration.Pen%2A> Eigenschaft, um die Darstellung der Textdekoration, z. B. eine durchgehende Füllung oder den Farbverlauf anzugeben. Wenn Sie einen Wert für nicht angeben der <xref:System.Windows.TextDecoration.Pen%2A> die Dekorationen standardmäßig die gleiche Farbe wie der Text-Eigenschaft. Nachdem Sie definiert haben eine <xref:System.Windows.TextDecoration> Objekt, das Hinzufügen der <xref:System.Windows.TextDecorations> Auflistung mit den gewünschten Text-Objekt.  
  
 Das folgende Beispiel zeigt einen Text-Decoration, die mit einem linearen Farbverlaufspinsel und ein gestrichelten Stift formatiert wurde.  
  
 ![Textergänzung mit linearer farbverlaufsunterstreichung](../../../../docs/framework/wpf/advanced/media/textdecoration02.png "TextDecoration02")  
Beispiel für eine Unterstreichung formatiert mit einem linearen Farbverlauf Pinsel und gestrichelten Stift  
  
 Die <xref:System.Windows.Documents.Hyperlink> Objekt ist ein fortlaufendes Inhaltselement, das Ihnen das Hosten von links im fortlaufenden Inhalt ermöglicht. In der Standardeinstellung <xref:System.Windows.Documents.Hyperlink> verwendet eine <xref:System.Windows.TextDecoration> Objekt, das eine Unterstreichung anzuzeigen. <xref:System.Windows.TextDecoration> Objekte können ressourcenintensiv sein, zu instanziieren, insbesondere wenn Sie viele <xref:System.Windows.Documents.Hyperlink> Objekte. Wenn Sie umfassenden Gebrauch von machen <xref:System.Windows.Documents.Hyperlink> Elemente, Sie möchten könnten eine Unterstreichung nur, wenn ein Ereignis auslösen, z. B. die <xref:System.Windows.ContentElement.MouseEnter> Ereignis.  
  
 Im folgenden Beispiel wird die Unterstreichung für den Link "Meine MSN" dynamische – es nur angezeigt, wenn die <xref:System.Windows.ContentElement.MouseEnter> Ereignis wird ausgelöst.  
  
 ![Links mit TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")  
Links mit TextDecorations definiert  
  
 Weitere Informationen finden Sie unter [Specify Whether a Hyperlink is Underlined (Angeben, ob ein Link unterstrichen wird)](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel verwendet eine Textdekoration "Unterstreichen" den Standardwert für die Schriftart.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 Im folgenden Codebeispiel wird eine Unterstreichung Textdekoration mit Pinsel mit Volltonfarbe für den Stift erstellt.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 Das folgende Codebeispiel zeigt wird ein "Unterstreichen" Text-Decoration mit einem linearen Farbverlaufspinsel für den Stift gestrichelte erstellt.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [Angeben, ob ein Hyperlink unterstrichen wird](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md)
