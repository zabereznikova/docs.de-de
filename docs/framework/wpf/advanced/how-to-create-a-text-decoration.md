---
title: 'Gewusst wie: Erstellen einer Textdekoration'
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
ms.openlocfilehash: c16073dd2413c1258f4875ac4118e0656d29b171
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545408"
---
# <a name="how-to-create-a-text-decoration"></a>Gewusst wie: Erstellen einer Textdekoration
Ein <xref:System.Windows.TextDecoration> Objekt ist eine visuelle Verzierung können Sie Text hinzufügen. Es gibt vier Arten von Textdekorationen: "Unterstreichen", die Baseline, durchgestrichen und Überstrichen. Das folgende Beispiel zeigt die Speicherorte der Textdekorationen relativ zu dem Text.  
  
 ![Diagramm der Textergänzungsstellen](../../../../docs/framework/wpf/advanced/media/textdecoration01.gif "TextDecoration01")  
Beispiel für die Text-Decoration-Typen  
  
 Ein Text-Decoration Text hinzufügen, erstellen Sie ein <xref:System.Windows.TextDecoration> -Objekt und dessen Eigenschaften ändern. Verwenden der <xref:System.Windows.TextDecoration.Location%2A> Eigenschaft, um anzugeben, wo die Textdekoration angezeigt wird, z. B. "Unterstreichen". Verwenden der <xref:System.Windows.TextDecoration.Pen%2A> Eigenschaft, um die Darstellung der Textdekoration, z. B. einer einfarbigen Füllung oder Verlaufsfarbe anzugeben. Wenn Sie einen Wert für nicht angeben der <xref:System.Windows.TextDecoration.Pen%2A> -Eigenschaft, die standardmäßig Ergänzungen, die die gleiche Farbe wie der Text. Sobald Sie definiert haben, eine <xref:System.Windows.TextDecoration> Objekt, fügen Sie diese der <xref:System.Windows.TextDecorations> Auflistung des gewünschten Text-Objekts.  
  
 Das folgende Beispiel zeigt einen Text-Decoration, die mit einem linearen Farbverlaufspinsel und einem gestrichelten Stift formatiert wurde.  
  
 ![Textergänzung mit linearer farbverlaufsunterstreichung](../../../../docs/framework/wpf/advanced/media/textdecoration02.png "TextDecoration02")  
Beispiel einer Unterstreichung formatiert mit einem linearen Farbverlauf Pinsel und gestrichelt  
  
 Die <xref:System.Windows.Documents.Hyperlink> Objekt ist ein Inhaltselement Inlineebene, der Ihnen das Hosten von links im fortlaufenden Inhalt ermöglicht. Standardmäßig <xref:System.Windows.Documents.Hyperlink> verwendet ein <xref:System.Windows.TextDecoration> Objekt, das eine Unterstreichung anzuzeigen. <xref:System.Windows.TextDecoration> Objekte können ressourcenintensiv sein zu instanziieren, insbesondere, wenn Sie viele haben <xref:System.Windows.Documents.Hyperlink> Objekte. Wenn Sie eine umfangreiche nutzen <xref:System.Windows.Documents.Hyperlink> Elemente, Sie sollten in Betracht ziehen einen Unterstrich nur, wenn ein Ereignis auslösen, z. B. Anzeigen der <xref:System.Windows.ContentElement.MouseEnter> Ereignis.  
  
 Im folgenden Beispiel wird die Unterstreichung für den Link "My MSN" dynamische – es wird nur angezeigt, wenn die <xref:System.Windows.ContentElement.MouseEnter> Ereignis wird ausgelöst.  
  
 ![Links mit TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")  
Links mit TextDecorations definiert  
  
 Weitere Informationen finden Sie unter [Specify Whether a Hyperlink is Underlined (Angeben, ob ein Link unterstrichen wird)](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird ein "Unterstreichen" Text-Decoration den Standardwert für die Schriftart verwendet.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 Im folgenden Codebeispiel wird ein "Unterstreichen" Text-Decoration mit einem Pinsel mit Volltonfarbe für den Stift erstellt.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 Im folgenden Codebeispiel wird ein "Unterstreichen" Text-Decoration mit einem linearen Farbverlaufspinsel für die gestrichelt erstellt.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.TextDecoration>  
 <xref:System.Windows.Documents.Hyperlink>  
 [Angeben, ob ein Hyperlink unterstrichen wird](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md)
