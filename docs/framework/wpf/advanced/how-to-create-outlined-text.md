---
title: 'Gewusst wie: Erstellen von Text mit Kontur'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], linear gradient brush
- outlined text [WPF]
- gradient brush [WPF]
- linear gradient brush [WPF]
- typography [WPF], outline effects
ms.assetid: 4aa3cf6e-1953-4f26-8230-7c1409e5f28d
ms.openlocfilehash: 86bfa396a2aa44eb511c014687501d60e170a396
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2020
ms.locfileid: "81278924"
---
# <a name="how-to-create-outlined-text"></a><span data-ttu-id="8664b-102">Gewusst wie: Erstellen von umrissenem Text</span><span class="sxs-lookup"><span data-stu-id="8664b-102">How to: Create outlined text</span></span>

<span data-ttu-id="8664b-103">In den meisten Fällen verwenden Sie Text in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Form einer Sammlung diskreter Zeichen oder Glyphen, wenn Sie Textzeichenfolgen zu Textzeichenfolgen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8664b-103">In most cases, when you're adding ornamentation to text strings in your [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application, you are using text in terms of a collection of discrete characters, or glyphs.</span></span> <span data-ttu-id="8664b-104">Sie können z. B. einen linearen <xref:System.Windows.Controls.Control.Foreground%2A> Verlaufspinsel <xref:System.Windows.Controls.TextBox> erstellen und ihn auf die Eigenschaft eines Objekts anwenden.</span><span class="sxs-lookup"><span data-stu-id="8664b-104">For example, you could create a linear gradient brush and apply it to the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.TextBox> object.</span></span> <span data-ttu-id="8664b-105">Wenn Sie das Textfeld anzeigen oder bearbeiten, wird der lineare Farbverlaufspinsel automatisch auf den aktuellen Zeichensatz in der Textzeichenfolge angewendet.</span><span class="sxs-lookup"><span data-stu-id="8664b-105">When you display or edit the text box, the linear gradient brush is automatically applied to the current set of characters in the text string.</span></span>  
  
 ![Angezeigter Text mit einem linearen Farbverlaufspinsel](./media/how-to-create-outlined-text/text-linear-gradient.jpg)
  
 <span data-ttu-id="8664b-107">Sie können jedoch auch <xref:System.Windows.Media.Geometry> Text in Objekte konvertieren, sodass Sie andere Arten von visuell reichem Text erstellen können.</span><span class="sxs-lookup"><span data-stu-id="8664b-107">However, you can also convert text into <xref:System.Windows.Media.Geometry> objects, allowing you to create other types of visually rich text.</span></span> <span data-ttu-id="8664b-108">Sie können z. <xref:System.Windows.Media.Geometry> B. ein Objekt basierend auf der Gliederung einer Textzeichenfolge erstellen.</span><span class="sxs-lookup"><span data-stu-id="8664b-108">For example, you could create a <xref:System.Windows.Media.Geometry> object based on the outline of a text string.</span></span>  
  
 ![Textkontur mit einem linearen Farbverlaufspinsel](./media/how-to-create-outlined-text/text-outline-linear-gradient.jpg)  
  
 <span data-ttu-id="8664b-110">Wenn Text in <xref:System.Windows.Media.Geometry> ein Objekt konvertiert wird, handelt es sich nicht mehr um eine Sammlung von Zeichen – Sie können die Zeichen in der Textzeichenfolge nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="8664b-110">When text is converted to a <xref:System.Windows.Media.Geometry> object, it is no longer a collection of characters—you cannot modify the characters in the text string.</span></span> <span data-ttu-id="8664b-111">Sie können jedoch die Darstellung des konvertierten Texts durch Ändern der Strich- und Füllungseigenschaften ändern.</span><span class="sxs-lookup"><span data-stu-id="8664b-111">However, you can affect the appearance of the converted text by modifying its stroke and fill properties.</span></span> <span data-ttu-id="8664b-112">Der Strich bezieht sich auf die Kontur des konvertierten Texts und die Füllung auf den Bereich innerhalb der Kontur.</span><span class="sxs-lookup"><span data-stu-id="8664b-112">The stroke refers to the outline of the converted text; the fill refers to the area inside the outline of the converted text.</span></span>  
  
 <span data-ttu-id="8664b-113">Die folgenden Beispiele veranschaulichen verschiedene Möglichkeiten zum Erstellen visueller Effekte, indem Sie den Strich und die Füllung von konvertiertem Text ändern.</span><span class="sxs-lookup"><span data-stu-id="8664b-113">The following examples illustrate several ways of creating visual effects by modifying the stroke and fill of converted text.</span></span>  
  
 ![Text mit unterschiedlichen Farben für Füllung und Strich](./media/how-to-create-outlined-text/fill-stroke-text-effect.jpg)  
  
 ![Text mit auf Strich angewendeten Bildpinsel](./media/how-to-create-outlined-text/image-brush-application.jpg)
  
 <span data-ttu-id="8664b-116">Es ist auch möglich, das Begrenzungsrahmenrechteck des konvertierten Textes zu ändern oder hervorzuheben.</span><span class="sxs-lookup"><span data-stu-id="8664b-116">It is also possible to modify the bounding box rectangle, or highlight, of the converted text.</span></span> <span data-ttu-id="8664b-117">Das folgende Beispiel veranschaulicht eine Möglichkeit, visuelle Effekte zu erstellen, indem Sie den Strich und die Hervorhebung von konvertiertem Text ändern.</span><span class="sxs-lookup"><span data-stu-id="8664b-117">The following example illustrates a way to create visual effects by modifying the stroke and highlight of converted text.</span></span>  
  
 ![Text mit Bildpinsel, der auf Strich und Hervorhebung angewendet wird](./media/how-to-create-outlined-text/image-brush-text-application.jpg)

## <a name="example"></a><span data-ttu-id="8664b-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8664b-119">Example</span></span>  
 <span data-ttu-id="8664b-120">Der Schlüssel zum Konvertieren <xref:System.Windows.Media.Geometry> von Text in <xref:System.Windows.Media.FormattedText> ein Objekt ist die Verwendung des Objekts.</span><span class="sxs-lookup"><span data-stu-id="8664b-120">The key to converting text to a <xref:System.Windows.Media.Geometry> object is to use the <xref:System.Windows.Media.FormattedText> object.</span></span> <span data-ttu-id="8664b-121">Nachdem Sie dieses Objekt erstellt haben, <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> können Sie die <xref:System.Windows.Media.Geometry> <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> und Methoden verwenden, um den Text in Objekte zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="8664b-121">Once you have created this object, you can use the <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> and <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> methods to convert the text to <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="8664b-122">Die erste Methode gibt die Geometrie des formatierten Textes zurück. Die zweite Methode gibt die Geometrie des Begrenzungsrahmens des formatierten Textes zurück.</span><span class="sxs-lookup"><span data-stu-id="8664b-122">The first method returns the geometry of the formatted text; the second method returns the geometry of the formatted text's bounding box.</span></span> <span data-ttu-id="8664b-123">Das folgende Codebeispiel zeigt, <xref:System.Windows.Media.FormattedText> wie ein Objekt erstellt und die Geometrien des formatierten Textes und seines Begrenzungsrahmens abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8664b-123">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and to retrieve the geometries of the formatted text and its bounding box.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 <span data-ttu-id="8664b-124">Um die abgerufenen <xref:System.Windows.Media.Geometry> Objekte anzuzeigen, müssen <xref:System.Windows.Media.DrawingContext> Sie auf das Objekt zugreifen, das den konvertierten Text anzeigt.</span><span class="sxs-lookup"><span data-stu-id="8664b-124">In order to display the retrieved the <xref:System.Windows.Media.Geometry> objects, you need to access the <xref:System.Windows.Media.DrawingContext> of the object that's displaying the converted text.</span></span> <span data-ttu-id="8664b-125">In diesen Codebeispielen wird dieser Zugriff durch Erstellen eines benutzerdefinierten Steuerelementobjekts erreicht, das von einer Klasse abgeleitet wird, die benutzerdefiniertes Rendern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8664b-125">In these code examples, this access is achieved by creating a custom control object that's derived from a class that supports user-defined rendering.</span></span>  
  
 <span data-ttu-id="8664b-126">Um <xref:System.Windows.Media.Geometry> Objekte im benutzerdefinierten Steuerelement anzuzeigen, <xref:System.Windows.UIElement.OnRender%2A> geben Sie eine Außerkraftsetzung für die Methode an.</span><span class="sxs-lookup"><span data-stu-id="8664b-126">To display <xref:System.Windows.Media.Geometry> objects in the custom control, provide an override for the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span> <span data-ttu-id="8664b-127">Die überschriebene Methode <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> sollte die <xref:System.Windows.Media.Geometry> Methode zum Zeichnen der Objekte verwenden.</span><span class="sxs-lookup"><span data-stu-id="8664b-127">Your overridden method should use the <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> method to draw the <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
  <span data-ttu-id="8664b-128">Informationen zur Quelle des benutzerdefinierten Benutzersteuerelementobjekts finden Sie unter [OutlineTextControl.cs für C-](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) und [OutlineTextControl.vb für Visual Basic](https://github.com/dotnet/docs/blob/master/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb).</span><span class="sxs-lookup"><span data-stu-id="8664b-128">For the source of the example custom user control object, see [OutlineTextControl.cs for C#](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) and [OutlineTextControl.vb for Visual Basic](https://github.com/dotnet/docs/blob/master/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8664b-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8664b-129">See also</span></span>

- [<span data-ttu-id="8664b-130">Zeichnen von formatiertem Text</span><span class="sxs-lookup"><span data-stu-id="8664b-130">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
