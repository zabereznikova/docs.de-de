---
title: 'Vorgehensweise: Erstellen eines mehrzeiligen TextBox-Steuerelements'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
ms.openlocfilehash: 29fb4c9498fe163c36e71680242d3ef8cf98c089
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181167"
---
# <a name="how-to-create-a-multiline-textbox-control"></a><span data-ttu-id="8bf58-102">Vorgehensweise: Erstellen eines mehrzeiligen TextBox-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="8bf58-102">How to: Create a Multiline TextBox Control</span></span>
<span data-ttu-id="8bf58-103">Dieses Beispiel zeigt, wie Sie mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] zum Definieren einer <xref:System.Windows.Controls.TextBox> -Steuerelement, das automatisch erweitert wird, um mehrere Textzeilen aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="8bf58-103">This example shows how to use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to define a <xref:System.Windows.Controls.TextBox> control that will automatically expand to accommodate multiple lines of text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8bf58-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8bf58-104">Example</span></span>  
 <span data-ttu-id="8bf58-105">Festlegen der <xref:System.Windows.Controls.TextBox.TextWrapping%2A> -Attribut auf **umschließen** bewirkt, dass eingegebenen Text in ein neues umbrochen werden, bei Zeile am Rand des der <xref:System.Windows.Controls.TextBox> Steuerelement erreicht ist, wird automatisch zu erweitern die <xref:System.Windows.Controls.TextBox> Steuerelement auf einer neuen Zeile aufzunehmen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8bf58-105">Setting the <xref:System.Windows.Controls.TextBox.TextWrapping%2A> attribute to **Wrap** will cause entered text to wrap to a new line when the edge of the <xref:System.Windows.Controls.TextBox> control is reached, automatically expanding the <xref:System.Windows.Controls.TextBox> control to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="8bf58-106">Festlegen der <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> Attribut **"true"** bewirkt, dass eine neue Zeile eingefügt werden soll, wenn die RETURN-Taste gedrückt wird, automatisch angepasst wird, die <xref:System.Windows.Controls.TextBox> eine neue Zeile, ggf. aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="8bf58-106">Setting the <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> attribute to **true** causes a new line to be inserted when the RETURN key is pressed, once again automatically expanding the <xref:System.Windows.Controls.TextBox> to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="8bf58-107">Die <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> -Attribut fügt eine Bildlaufleiste angezeigt, die <xref:System.Windows.Controls.TextBox>, sodass den Inhalt des der <xref:System.Windows.Controls.TextBox> Bildlauf durchgeführt werden können, wenn die <xref:System.Windows.Controls.TextBox> die Größe des Frames oder Fensters überschreitet.</span><span class="sxs-lookup"><span data-stu-id="8bf58-107">The <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> attribute adds a scroll bar to the <xref:System.Windows.Controls.TextBox>, so that the contents of the <xref:System.Windows.Controls.TextBox> can be scrolled through if the <xref:System.Windows.Controls.TextBox> expands beyond the size of the frame or window that encloses it.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="8bf58-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8bf58-108">See also</span></span>

- <xref:System.Windows.TextWrapping>
- [<span data-ttu-id="8bf58-109">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="8bf58-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="8bf58-110">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="8bf58-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
