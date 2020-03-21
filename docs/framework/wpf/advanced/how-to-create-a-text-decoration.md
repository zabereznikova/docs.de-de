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
ms.openlocfilehash: cf3b3c3bcb75153a0be4f7ced03b38134b79a930
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185922"
---
# <a name="how-to-create-a-text-decoration"></a>Gewusst wie: Erstellen einer Textdekoration
Ein <xref:System.Windows.TextDecoration> Objekt ist eine visuelle Verzierung, die Sie dem Text hinzufügen können. Es gibt vier Arten von Textdekorationen: Unterstreichung, Baseline, Durchstreichen und Überlinie. Das folgende Beispiel zeigt die Positionen der Textdekorationen relativ zum Text.  
  
 ![Diagramm der Textdekorationstypen](./media/how-to-create-a-text-decoration/text-decoration-types.gif)  
  
 Um Text eine Textdekoration hinzuzufügen, erstellen Sie ein <xref:System.Windows.TextDecoration> Objekt, und ändern Sie dessen Eigenschaften. Verwenden <xref:System.Windows.TextDecoration.Location%2A> Sie die Eigenschaft, um anzugeben, wo die Textdekoration angezeigt wird, z. B. unterstreichen. Verwenden <xref:System.Windows.TextDecoration.Pen%2A> Sie die Eigenschaft, um die Darstellung der Textdekoration anzugeben, z. B. eine Volumenkörperfüllung oder Farbverlaufsfarbe. Wenn Sie keinen Wert für <xref:System.Windows.TextDecoration.Pen%2A> die Eigenschaft angeben, werden die Dekorationen standardmäßig auf die gleiche Farbe wie der Text festgelegt. Nachdem Sie ein <xref:System.Windows.TextDecoration> Objekt definiert haben, fügen Sie es der <xref:System.Windows.TextDecorations> Auflistung des gewünschten Textobjekts hinzu.  
  
 Das folgende Beispiel zeigt eine Textdekoration, die mit einem linearen Farbverlaufspinsel und einem gestrichelten Stift formatiert wurde.  
  
 ![Textergänzung mit linearer Farbverlaufsunterstreichung](./media/how-to-create-a-text-decoration/text-decoration-gradient.png)  
  
 Das <xref:System.Windows.Documents.Hyperlink> Objekt ist ein Flow-Inhaltselement auf Inlineebene, mit dem Sie Hyperlinks innerhalb des Flow-Inhalts hosten können. Verwendet standardmäßig <xref:System.Windows.Documents.Hyperlink> ein <xref:System.Windows.TextDecoration> Objekt, um eine Unterstreichung anzuzeigen. <xref:System.Windows.TextDecoration>Objekte können leistungsintensiv zu instanziieren sein, <xref:System.Windows.Documents.Hyperlink> insbesondere wenn Sie viele Objekte haben. Wenn Sie <xref:System.Windows.Documents.Hyperlink> Elemente ausgiebig verwenden, sollten Sie nur beim Auslösen eines Ereignisses, <xref:System.Windows.ContentElement.MouseEnter> z. B. des Ereignisses, eine Unterstreichung anzeigen.  
  
 Im folgenden Beispiel ist die Unterstreichung für die Verknüpfung "Mein MSN" dynamisch – sie wird nur angezeigt, wenn das <xref:System.Windows.ContentElement.MouseEnter> Ereignis ausgelöst wird.  
  
 ![Links mit TextDecorations](./media/how-to-create-a-text-decoration/text-decorations-hyperlinks.png)  

 Weitere Informationen finden Sie unter [Specify Whether a Hyperlink is Underlined (Angeben, ob ein Link unterstrichen wird)](how-to-specify-whether-a-hyperlink-is-underlined.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel verwendet eine Unterstreichungstextdekoration den Standardschriftwert.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 Im folgenden Codebeispiel wird eine Unterstreichungstextdekoration mit einem einfarbigen Pinsel für den Stift erstellt.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 Im folgenden Codebeispiel wird eine Unterstreichungstextdekoration mit einem linearen Farbverlaufspinsel für den gestrichelten Stift erstellt.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [Angeben, ob ein Hyperlink unterstrichen wird](how-to-specify-whether-a-hyperlink-is-underlined.md)
