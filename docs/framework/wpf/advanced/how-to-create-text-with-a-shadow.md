---
title: 'Gewusst wie: Erstellen von Text mit einem Schatten'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
ms.openlocfilehash: c3e8135372ce4a092552c812cd971cb70bc49bf3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186848"
---
# <a name="how-to-create-text-with-a-shadow"></a><span data-ttu-id="58538-102">Gewusst wie: Erstellen von Text mit einem Schatten</span><span class="sxs-lookup"><span data-stu-id="58538-102">How to: Create Text with a Shadow</span></span>
<span data-ttu-id="58538-103">Die Beispiele in diesem Abschnitt erklären, wie Sie einen Schatteneffekt für angezeigten Text erstellen.</span><span class="sxs-lookup"><span data-stu-id="58538-103">The examples in this section show how to create a shadow effect for displayed text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58538-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="58538-104">Example</span></span>  
 <span data-ttu-id="58538-105">Mit <xref:System.Windows.Media.Effects.DropShadowEffect> dem Objekt können Sie eine Vielzahl [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] von Schlagschatteneffekten für Objekte erstellen.</span><span class="sxs-lookup"><span data-stu-id="58538-105">The <xref:System.Windows.Media.Effects.DropShadowEffect> object allows you to create a variety of drop shadow effects for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] objects.</span></span> <span data-ttu-id="58538-106">Das folgende Beispiel zeigt einen auf einen Text angewendeten Schlagschatteneffekt.</span><span class="sxs-lookup"><span data-stu-id="58538-106">The following example shows a drop shadow effect applied to text.</span></span> <span data-ttu-id="58538-107">In diesem Fall ist der Schatten ein weicher Schatten, d.h. die Schattenfarbe verwischt.</span><span class="sxs-lookup"><span data-stu-id="58538-107">In this case, the shadow is a soft shadow, which means the shadow color blurs.</span></span>  
  
 ![Textschatten mit Weichheit &#61; 0,25](./media/how-to-create-text-with-a-shadow/drop-shadow-text-effect.jpg)
  
 <span data-ttu-id="58538-109">Sie können die Breite eines Schattens steuern, indem Sie die <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="58538-109">You can control the width of a shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> property.</span></span> <span data-ttu-id="58538-110">Der Wert `4.0` von gibt eine Schattenbreite von 4 Pixel an.</span><span class="sxs-lookup"><span data-stu-id="58538-110">A value of `4.0` indicates a shadow width of 4 pixels.</span></span> <span data-ttu-id="58538-111">Sie können die Weichheit oder Unschärfe eines <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> Schattens steuern, indem Sie die Eigenschaft ändern.</span><span class="sxs-lookup"><span data-stu-id="58538-111">You can control the softness, or blur, of a shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property.</span></span> <span data-ttu-id="58538-112">Der Wert `0.0` von gibt keine Unschärfe an.</span><span class="sxs-lookup"><span data-stu-id="58538-112">A value of `0.0` indicates no blurring.</span></span> <span data-ttu-id="58538-113">Im folgenden Codebeispiel wird gezeigt, wie ein weicher Schatten erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="58538-113">The following code example shows how to create a soft shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
> <span data-ttu-id="58538-114">Diese Schatteneffekte durchlaufen nicht [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] die Textrenderingpipeline.</span><span class="sxs-lookup"><span data-stu-id="58538-114">These shadow effects do not go through the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] text rendering pipeline.</span></span> <span data-ttu-id="58538-115">Daher ist ClearType bei Verwendung dieser Effekte deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="58538-115">As a result, ClearType is disabled when using these effects.</span></span>  
  
 <span data-ttu-id="58538-116">Das folgende Beispiel zeigt einen auf einen Text angewendeten harten Schlagschatteneffekt.</span><span class="sxs-lookup"><span data-stu-id="58538-116">The following example shows a hard drop shadow effect applied to text.</span></span> <span data-ttu-id="58538-117">In diesem Fall wird der Schatten nicht verwischt.</span><span class="sxs-lookup"><span data-stu-id="58538-117">In this case, the shadow is not blurred.</span></span>  
  
 ![Textschatten mit Weichheit &#61; 0](./media/how-to-create-text-with-a-shadow/text-shadow-softness.jpg)
  
 <span data-ttu-id="58538-119">Sie können einen harten Schatten <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> erstellen, indem Sie die Eigenschaft auf `0.0`festlegen, was darauf hinweist, dass keine Unschärfe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="58538-119">You can create a hard shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property to `0.0`, which indicates that no blurring is used.</span></span> <span data-ttu-id="58538-120">Sie können die Richtung des Schattens <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> steuern, indem Sie die Eigenschaft ändern.</span><span class="sxs-lookup"><span data-stu-id="58538-120">You can control the direction of the shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property.</span></span> <span data-ttu-id="58538-121">Legen Sie den Richtungswert dieser `0` Eigenschaft `360`auf einen Grad zwischen und fest.</span><span class="sxs-lookup"><span data-stu-id="58538-121">Set the directional value of this property to a degree between `0` and `360`.</span></span> <span data-ttu-id="58538-122">Die folgende Abbildung zeigt die <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> Richtungswerte der Eigenschaftseinstellung.</span><span class="sxs-lookup"><span data-stu-id="58538-122">The following illustration shows the directional values of the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property setting.</span></span>  
  
 ![DropShadow-Gradeinstellung für Schatten](./media/how-to-create-text-with-a-shadow/drop-shadow-degree-setting.png)
  
 <span data-ttu-id="58538-124">Im folgenden Codebeispiel wird das Erstellen eines harten Schattens veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="58538-124">The following code example shows how to create a hard shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a><span data-ttu-id="58538-125">Verwenden eines Weichzeichnereffekts</span><span class="sxs-lookup"><span data-stu-id="58538-125">Using a Blur Effect</span></span>  
 <span data-ttu-id="58538-126">A <xref:System.Windows.Media.Effects.BlurBitmapEffect> kann verwendet werden, um einen schattenähnlichen Effekt zu erzeugen, der hinter einem Textobjekt platziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="58538-126">A <xref:System.Windows.Media.Effects.BlurBitmapEffect> can be used to create a shadow-like effect that can be placed behind a text object.</span></span> <span data-ttu-id="58538-127">Ein auf Text angewendeter Weichzeichner-Bitmapeffekt verwischt Text gleichmäßig in alle Richtungen.</span><span class="sxs-lookup"><span data-stu-id="58538-127">A blur bitmap effect applied to text blurs the text evenly in all directions.</span></span>  
  
 <span data-ttu-id="58538-128">Das folgende Beispiel zeigt einen Text mit Weichzeichnereffekt.</span><span class="sxs-lookup"><span data-stu-id="58538-128">The following example shows a blur effect applied to text.</span></span>  
  
 ![Textschatten mit einem BlurBitmapEffect](./media/how-to-create-text-with-a-shadow/text-shadow-blur-effect.jpg)  
  
 <span data-ttu-id="58538-130">Im folgenden Codebeispiel wird das Erstellen eines Weichzeichnereffekts veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="58538-130">The following code example shows how to create a blur effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a><span data-ttu-id="58538-131">Verwenden von TranslateTransform</span><span class="sxs-lookup"><span data-stu-id="58538-131">Using a Translate Transform</span></span>  
 <span data-ttu-id="58538-132">A <xref:System.Windows.Media.TranslateTransform> kann verwendet werden, um einen schattenähnlichen Effekt zu erzeugen, der hinter einem Textobjekt platziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="58538-132">A <xref:System.Windows.Media.TranslateTransform> can be used to create a shadow-like effect that can be placed behind a text object.</span></span>  
  
 <span data-ttu-id="58538-133">Im folgenden Codebeispiel <xref:System.Windows.Media.TranslateTransform> wird ein zum Versetzen von Text verwendet.</span><span class="sxs-lookup"><span data-stu-id="58538-133">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="58538-134">In diesem Beispiel erstellt eine geringfügig versetzte Kopie des Textes hinter dem primären Text einen Schatteneffekt.</span><span class="sxs-lookup"><span data-stu-id="58538-134">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 ![Textschatten mit einem TranslateTransform](./media/how-to-create-text-with-a-shadow/text-transform-shadow-effect.jpg)
  
 <span data-ttu-id="58538-136">Im folgenden Codebeispiel wird das Erstellen einer Transformation für einen Schatteneffekt veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="58538-136">The following code example shows how to create a transform for a shadow effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
