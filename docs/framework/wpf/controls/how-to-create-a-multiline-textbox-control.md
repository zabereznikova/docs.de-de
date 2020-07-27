---
title: 'Gewusst wie: Erstellen eines mehrzeiligen TextBox-Steuerelements'
description: Erfahren Sie, wie Sie mit XAML ein TextBox-Steuerelement definieren, das erweitert wird, um mehrere Textzeilen in einer Windows Presentation Foundation Anwendung zu unterstützen.
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
ms.openlocfilehash: 0a88d4d768884df135afddb491431650b9ba2d24
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166245"
---
# <a name="how-to-create-a-multiline-textbox-control"></a><span data-ttu-id="54ac4-103">Gewusst wie: Erstellen eines mehrzeiligen TextBox-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="54ac4-103">How to: Create a Multiline TextBox Control</span></span>
<span data-ttu-id="54ac4-104">In diesem Beispiel wird gezeigt, wie verwendet [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] wird, um ein Steuerelement zu definieren <xref:System.Windows.Controls.TextBox> , das automatisch erweitert wird, um mehrere Textzeilen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="54ac4-104">This example shows how to use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to define a <xref:System.Windows.Controls.TextBox> control that will automatically expand to accommodate multiple lines of text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54ac4-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="54ac4-105">Example</span></span>  
 <span data-ttu-id="54ac4-106">Wenn das- <xref:System.Windows.Controls.TextBox.TextWrapping%2A> Attribut auf **Wrap** festgelegt wird, wird der eingegebene Text in eine neue Zeile eingeschlossen, wenn der Rand des <xref:System.Windows.Controls.TextBox> Steuer Elements erreicht wird. das Steuerelement wird automatisch erweitert, sodass es bei Bedarf den <xref:System.Windows.Controls.TextBox> Raum für eine neue Zeile einschließt.</span><span class="sxs-lookup"><span data-stu-id="54ac4-106">Setting the <xref:System.Windows.Controls.TextBox.TextWrapping%2A> attribute to **Wrap** will cause entered text to wrap to a new line when the edge of the <xref:System.Windows.Controls.TextBox> control is reached, automatically expanding the <xref:System.Windows.Controls.TextBox> control to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="54ac4-107">Wenn das-Attribut auf "true" festgelegt <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> wird, wird eine neue Zeile eingefügt, wenn die Rückgabetaste gedrückt wird. wenn dies der **Fall** ist, wird das automatisch erweitert, <xref:System.Windows.Controls.TextBox> um Platz für eine neue Zeile einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="54ac4-107">Setting the <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> attribute to **true** causes a new line to be inserted when the RETURN key is pressed, once again automatically expanding the <xref:System.Windows.Controls.TextBox> to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="54ac4-108">Das- <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> Attribut fügt der eine Bild Lauf Leiste hinzu <xref:System.Windows.Controls.TextBox> , sodass der Inhalt des <xref:System.Windows.Controls.TextBox> durchlaufen werden kann, wenn die <xref:System.Windows.Controls.TextBox> über die Größe des Frame oder Fensters hinausgeht, in dem Sie eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="54ac4-108">The <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> attribute adds a scroll bar to the <xref:System.Windows.Controls.TextBox>, so that the contents of the <xref:System.Windows.Controls.TextBox> can be scrolled through if the <xref:System.Windows.Controls.TextBox> expands beyond the size of the frame or window that encloses it.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="54ac4-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="54ac4-109">See also</span></span>

- <xref:System.Windows.TextWrapping>
- [<span data-ttu-id="54ac4-110">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="54ac4-110">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="54ac4-111">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="54ac4-111">RichTextBox Overview</span></span>](richtextbox-overview.md)
