---
title: 'Vorgehensweise: Erstellen eines mehrzeiligen TextBox-Steuerelements'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
ms.openlocfilehash: 29fb4c9498fe163c36e71680242d3ef8cf98c089
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62001272"
---
# <a name="how-to-create-a-multiline-textbox-control"></a>Vorgehensweise: Erstellen eines mehrzeiligen TextBox-Steuerelements
Dieses Beispiel zeigt, wie Sie mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] zum Definieren einer <xref:System.Windows.Controls.TextBox> -Steuerelement, das automatisch erweitert wird, um mehrere Textzeilen aufzunehmen.  
  
## <a name="example"></a>Beispiel  
 Festlegen der <xref:System.Windows.Controls.TextBox.TextWrapping%2A> -Attribut auf **umschließen** bewirkt, dass eingegebenen Text in ein neues umbrochen werden, bei Zeile am Rand des der <xref:System.Windows.Controls.TextBox> Steuerelement erreicht ist, wird automatisch zu erweitern die <xref:System.Windows.Controls.TextBox> Steuerelement auf einer neuen Zeile aufzunehmen erforderlich.  
  
 Festlegen der <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> Attribut **"true"** bewirkt, dass eine neue Zeile eingefügt werden soll, wenn die RETURN-Taste gedrückt wird, automatisch angepasst wird, die <xref:System.Windows.Controls.TextBox> eine neue Zeile, ggf. aufzunehmen.  
  
 Die <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> -Attribut fügt eine Bildlaufleiste angezeigt, die <xref:System.Windows.Controls.TextBox>, sodass den Inhalt des der <xref:System.Windows.Controls.TextBox> Bildlauf durchgeführt werden können, wenn die <xref:System.Windows.Controls.TextBox> die Größe des Frames oder Fensters überschreitet.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.TextWrapping>
- [Übersicht über TextBox](textbox-overview.md)
- [Übersicht über RichTextBox](richtextbox-overview.md)
