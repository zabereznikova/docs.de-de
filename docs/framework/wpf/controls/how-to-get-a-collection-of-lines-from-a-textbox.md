---
title: 'Vorgehensweise: Abrufen einer Auflistung der Zeilen aus einem TextBox-Objekt'
ms.date: 03/30/2017
helpviewer_keywords:
- lines [WPF], getting collection of
- TextBox control [WPF], getting collection of lines
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
ms.openlocfilehash: b7b2f1c2e071388635fb50b1e3573fd7f44334dd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59224636"
---
# <a name="how-to-get-a-collection-of-lines-from-a-textbox"></a><span data-ttu-id="6f5ee-102">Vorgehensweise: Abrufen einer Auflistung der Zeilen aus einem TextBox-Objekt</span><span class="sxs-lookup"><span data-stu-id="6f5ee-102">How to: Get a Collection of Lines from a TextBox</span></span>
<span data-ttu-id="6f5ee-103">In diesem Beispiel wird gezeigt, wie zum Abrufen einer Auflistung von Textzeilen aus einer <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="6f5ee-103">This example shows how to get a collection of lines of text from a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f5ee-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6f5ee-104">Example</span></span>  
 <span data-ttu-id="6f5ee-105">Das folgende Beispiel zeigt eine einfache Methode, die eine <xref:System.Windows.Controls.TextBox> als Argument und gibt eine <xref:System.Collections.Specialized.StringCollection> , enthält die Textzeilen in der **Textfeld**.</span><span class="sxs-lookup"><span data-stu-id="6f5ee-105">The following example shows a simple method that takes a <xref:System.Windows.Controls.TextBox> as the argument, and returns a <xref:System.Collections.Specialized.StringCollection> containing the lines of text in the **TextBox**.</span></span>  <span data-ttu-id="6f5ee-106">Die <xref:System.Windows.Controls.TextBox.LineCount%2A> Eigenschaft wird verwendet, um zu bestimmen, wie viele Zeilen zurzeit sind die **Textfeld**, und die <xref:System.Windows.Controls.TextBox.GetLineText%2A> -Methode wird anschließend verwendet, können Sie jede Zeile zu extrahieren und auf die Auflistung von Zeilen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6f5ee-106">The <xref:System.Windows.Controls.TextBox.LineCount%2A> property is used to determine how many lines are currently in the **TextBox**, and the <xref:System.Windows.Controls.TextBox.GetLineText%2A> method is then used to extract each line and add it to the collection of lines.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## <a name="see-also"></a><span data-ttu-id="6f5ee-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f5ee-107">See also</span></span>

- [<span data-ttu-id="6f5ee-108">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="6f5ee-108">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="6f5ee-109">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="6f5ee-109">RichTextBox Overview</span></span>](richtextbox-overview.md)
