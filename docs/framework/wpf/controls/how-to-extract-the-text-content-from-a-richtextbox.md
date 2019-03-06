---
title: 'Vorgehensweise: Extrahieren von Textinhalten aus einer RichTextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], extracting
- RichTextBox control [WPF], extracting text content
- content [WPF], extracting
- extracting text content [WPF]
ms.assetid: f13c093f-1a05-45b3-ac8f-c9ea5e4a11c5
ms.openlocfilehash: 8c7fd54931fad060a5d78e4c47c2cfce2767025a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355245"
---
# <a name="how-to-extract-the-text-content-from-a-richtextbox"></a><span data-ttu-id="0eae0-102">Vorgehensweise: Extrahieren von Textinhalten aus einer RichTextBox</span><span class="sxs-lookup"><span data-stu-id="0eae0-102">How to: Extract the Text Content from a RichTextBox</span></span>
<span data-ttu-id="0eae0-103">Dieses Beispiel zeigt, wie Sie den Inhalt des Extrahieren einer <xref:System.Windows.Controls.RichTextBox> als nur-Text.</span><span class="sxs-lookup"><span data-stu-id="0eae0-103">This example shows how to extract the contents of a <xref:System.Windows.Controls.RichTextBox> as plain text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0eae0-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0eae0-104">Example</span></span>  
 <span data-ttu-id="0eae0-105">Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Code beschreibt ein benanntes <xref:System.Windows.Controls.RichTextBox> -Steuerelement mit einfachem Inhalt.</span><span class="sxs-lookup"><span data-stu-id="0eae0-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a named <xref:System.Windows.Controls.RichTextBox> control with simple content.</span></span>  
  
 [!code-xaml[RichTextBoxSnippets#_RTB_XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml#_rtb_xaml)]  
  
## <a name="example"></a><span data-ttu-id="0eae0-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0eae0-106">Example</span></span>  
 <span data-ttu-id="0eae0-107">Der folgende Code implementiert eine Methode, verwendet eine <xref:System.Windows.Controls.RichTextBox> als Argument und gibt eine Zeichenfolge mit der nur-Text-Inhalt, der die <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="0eae0-107">The following code implements a method that takes a <xref:System.Windows.Controls.RichTextBox> as an argument, and returns a string representing the plain text contents of the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="0eae0-108">Die Methode erstellt ein neues <xref:System.Windows.Documents.TextRange> aus dem Inhalt der <xref:System.Windows.Controls.RichTextBox>unter Verwendung der <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> und <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> an, dass der Bereich des Inhalts extrahiert.</span><span class="sxs-lookup"><span data-stu-id="0eae0-108">The method creates a new <xref:System.Windows.Documents.TextRange> from the contents of the <xref:System.Windows.Controls.RichTextBox>, using the <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> and <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> to indicate the range of the contents to extract.</span></span>  <span data-ttu-id="0eae0-109"><xref:System.Windows.Documents.FlowDocument.ContentStart%2A> und <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> Eigenschaften jedes Zurückgeben einer <xref:System.Windows.Documents.TextPointer>, auf das zugrunde liegende FlowDocument, die den Inhalt des darstellt und verfügbar sind die <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="0eae0-109"><xref:System.Windows.Documents.FlowDocument.ContentStart%2A> and <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> properties each return a <xref:System.Windows.Documents.TextPointer>, and are accessible on the underlying FlowDocument that represents the contents of the <xref:System.Windows.Controls.RichTextBox>.</span></span>  <span data-ttu-id="0eae0-110"><xref:System.Windows.Documents.TextRange> Stellt eine Text-Eigenschaft, die die Teile für nur-Text zurückgibt. die <xref:System.Windows.Documents.TextRange> als Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="0eae0-110"><xref:System.Windows.Documents.TextRange> provides a Text property, which returns the plain text portions of the <xref:System.Windows.Documents.TextRange> as a string.</span></span>  
  
 [!code-csharp[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml.cs#_rtb_stringfrom)]
 [!code-vb[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxSnippets/visualbasic/window1.xaml.vb#_rtb_stringfrom)]  
  
## <a name="see-also"></a><span data-ttu-id="0eae0-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0eae0-111">See also</span></span>
- [<span data-ttu-id="0eae0-112">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="0eae0-112">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="0eae0-113">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="0eae0-113">TextBox Overview</span></span>](textbox-overview.md)
