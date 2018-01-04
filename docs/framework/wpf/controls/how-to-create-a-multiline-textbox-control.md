---
title: 'Gewusst wie: Erstellen eines mehrzeiligen TextBox-Steuerelements'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2a6885a594e5fcd747f85dedf1afbd39ec644717
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-multiline-textbox-control"></a><span data-ttu-id="f4a1a-102">Gewusst wie: Erstellen eines mehrzeiligen TextBox-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="f4a1a-102">How to: Create a Multiline TextBox Control</span></span>
<span data-ttu-id="f4a1a-103">Dieses Beispiel zeigt, wie [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] zum Definieren einer <xref:System.Windows.Controls.TextBox> Steuerelement, das automatisch erweitert wird, um mehrere Textzeilen aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="f4a1a-103">This example shows how to use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to define a <xref:System.Windows.Controls.TextBox> control that will automatically expand to accommodate multiple lines of text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4a1a-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f4a1a-104">Example</span></span>  
 <span data-ttu-id="f4a1a-105">Festlegen der <xref:System.Windows.Controls.TextBox.TextWrapping%2A> -Attribut auf **umschließen** führt dazu, dass eingegebenen Text umbrochen, um eine neue Zeile am Rand des der <xref:System.Windows.Controls.TextBox> Steuerelement erreicht ist die <xref:System.Windows.Controls.TextBox> Steuerelement für eine neue Zeile aufzunehmen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f4a1a-105">Setting the <xref:System.Windows.Controls.TextBox.TextWrapping%2A> attribute to **Wrap** will cause entered text to wrap to a new line when the edge of the <xref:System.Windows.Controls.TextBox> control is reached, automatically expanding the <xref:System.Windows.Controls.TextBox> control to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="f4a1a-106">Festlegen der <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> -Attribut auf **"true"** bewirkt, dass eine neue Zeile eingefügt, wenn die RETURN-Taste wieder automatisch zu erweitern gedrückt wird, die <xref:System.Windows.Controls.TextBox> Platz für eine neue Zeile bei Bedarf enthalten.</span><span class="sxs-lookup"><span data-stu-id="f4a1a-106">Setting the <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> attribute to **true** causes a new line to be inserted when the RETURN key is pressed, once again automatically expanding the <xref:System.Windows.Controls.TextBox> to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="f4a1a-107">Die <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> Attribut fügt eine Bildlaufleiste, um die <xref:System.Windows.Controls.TextBox>, sodass den Inhalt des der <xref:System.Windows.Controls.TextBox> Bildlauf durchgeführt werden kann, wenn die <xref:System.Windows.Controls.TextBox> erweitert die Größe des den Frame oder das Fenster, das es umschließt.</span><span class="sxs-lookup"><span data-stu-id="f4a1a-107">The <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> attribute adds a scroll bar to the <xref:System.Windows.Controls.TextBox>, so that the contents of the <xref:System.Windows.Controls.TextBox> can be scrolled through if the <xref:System.Windows.Controls.TextBox> expands beyond the size of the frame or window that encloses it.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="f4a1a-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4a1a-108">See Also</span></span>  
 <xref:System.Windows.TextWrapping>  
 [<span data-ttu-id="f4a1a-109">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="f4a1a-109">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="f4a1a-110">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="f4a1a-110">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
