---
title: 'Vorgehensweise: Erstellen von Text mit einem Schatten'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
ms.openlocfilehash: a2225e297dbc0b5f9d49799cb34eb5539746e62e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776819"
---
# <a name="how-to-create-text-with-a-shadow"></a><span data-ttu-id="cd762-102">Vorgehensweise: Erstellen von Text mit einem Schatten</span><span class="sxs-lookup"><span data-stu-id="cd762-102">How to: Create Text with a Shadow</span></span>
<span data-ttu-id="cd762-103">Die Beispiele in diesem Abschnitt erklären, wie Sie einen Schatteneffekt für angezeigten Text erstellen.</span><span class="sxs-lookup"><span data-stu-id="cd762-103">The examples in this section show how to create a shadow effect for displayed text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd762-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cd762-104">Example</span></span>  
 <span data-ttu-id="cd762-105">Die <xref:System.Windows.Media.Effects.DropShadowEffect> Objekt ermöglicht Ihnen die Erstellung eine Vielzahl von Schlagschatteneffekten für [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Objekte.</span><span class="sxs-lookup"><span data-stu-id="cd762-105">The <xref:System.Windows.Media.Effects.DropShadowEffect> object allows you to create a variety of drop shadow effects for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] objects.</span></span> <span data-ttu-id="cd762-106">Das folgende Beispiel zeigt einen auf einen Text angewendeten Schlagschatteneffekt.</span><span class="sxs-lookup"><span data-stu-id="cd762-106">The following example shows a drop shadow effect applied to text.</span></span> <span data-ttu-id="cd762-107">In diesem Fall ist der Schatten ein weicher Schatten, d.h. die Schattenfarbe verwischt.</span><span class="sxs-lookup"><span data-stu-id="cd762-107">In this case, the shadow is a soft shadow, which means the shadow color blurs.</span></span>  
  
 ![Textschatten mit Weichheit &#61; 0,25](./media/how-to-create-text-with-a-shadow/drop-shadow-text-effect.jpg) 
  
 <span data-ttu-id="cd762-109">Sie können die Breite eines Schattens durch Festlegen von steuern die <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="cd762-109">You can control the width of a shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> property.</span></span> <span data-ttu-id="cd762-110">Der Wert `4.0` gibt eine Schattenbreite von 4 Pixeln.</span><span class="sxs-lookup"><span data-stu-id="cd762-110">A value of `4.0` indicates a shadow width of 4 pixels.</span></span> <span data-ttu-id="cd762-111">Sie können steuern, die Weichheit oder das Weichzeichnen eines Schattens durch Ändern der <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="cd762-111">You can control the softness, or blur, of a shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property.</span></span> <span data-ttu-id="cd762-112">Der Wert `0.0` gibt an, keinen Weichzeichner.</span><span class="sxs-lookup"><span data-stu-id="cd762-112">A value of `0.0` indicates no blurring.</span></span> <span data-ttu-id="cd762-113">Im folgenden Codebeispiel wird gezeigt, wie ein weicher Schatten erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="cd762-113">The following code example shows how to create a soft shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
>  <span data-ttu-id="cd762-114">Diese Schatteneffekte navigieren nicht über die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Textrendering-Pipeline.</span><span class="sxs-lookup"><span data-stu-id="cd762-114">These shadow effects do not go through the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] text rendering pipeline.</span></span> <span data-ttu-id="cd762-115">Daher ist ClearType bei Verwendung dieser Effekte deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="cd762-115">As a result, ClearType is disabled when using these effects.</span></span>  
  
 <span data-ttu-id="cd762-116">Das folgende Beispiel zeigt einen auf einen Text angewendeten harten Schlagschatteneffekt.</span><span class="sxs-lookup"><span data-stu-id="cd762-116">The following example shows a hard drop shadow effect applied to text.</span></span> <span data-ttu-id="cd762-117">In diesem Fall wird der Schatten nicht verwischt.</span><span class="sxs-lookup"><span data-stu-id="cd762-117">In this case, the shadow is not blurred.</span></span>  
  
 ![Textschatten mit Weichheit &#61; 0](./media/how-to-create-text-with-a-shadow/text-shadow-softness.jpg) 
  
 <span data-ttu-id="cd762-119">Sie können einen harten Schatten erstellen, durch Festlegen der <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> Eigenschaft `0.0`, was bedeutet, dass kein Weichzeichner verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cd762-119">You can create a hard shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property to `0.0`, which indicates that no blurring is used.</span></span> <span data-ttu-id="cd762-120">Sie können die Richtung des Schattens durch Ändern von steuern die <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="cd762-120">You can control the direction of the shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property.</span></span> <span data-ttu-id="cd762-121">Legen Sie den direktionalen Wert dieser Eigenschaft auf einen Grad zwischen `0` und `360`.</span><span class="sxs-lookup"><span data-stu-id="cd762-121">Set the directional value of this property to a degree between `0` and `360`.</span></span> <span data-ttu-id="cd762-122">Die folgende Abbildung zeigt die direktionalen Werte der <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> Einstellung der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="cd762-122">The following illustration shows the directional values of the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property setting.</span></span>  
  
 ![DropShadow-Gradeinstellung für Schatten](./media/how-to-create-text-with-a-shadow/drop-shadow-degree-setting.png)
  
 <span data-ttu-id="cd762-124">Im folgenden Codebeispiel wird das Erstellen eines harten Schattens veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="cd762-124">The following code example shows how to create a hard shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a><span data-ttu-id="cd762-125">Verwenden eines Weichzeichnereffekts</span><span class="sxs-lookup"><span data-stu-id="cd762-125">Using a Blur Effect</span></span>  
 <span data-ttu-id="cd762-126">Ein <xref:System.Windows.Media.Effects.BlurBitmapEffect> können verwendet werden, um einen schattenähnlichen Effekt zu erstellen, die hinter einem Textobjekt platziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="cd762-126">A <xref:System.Windows.Media.Effects.BlurBitmapEffect> can be used to create a shadow-like effect that can be placed behind a text object.</span></span> <span data-ttu-id="cd762-127">Ein auf Text angewendeter Weichzeichner-Bitmapeffekt verwischt Text gleichmäßig in alle Richtungen.</span><span class="sxs-lookup"><span data-stu-id="cd762-127">A blur bitmap effect applied to text blurs the text evenly in all directions.</span></span>  
  
 <span data-ttu-id="cd762-128">Das folgende Beispiel zeigt einen auf einen Text angewendeten Weichzeichnereffekt.</span><span class="sxs-lookup"><span data-stu-id="cd762-128">The following example shows a blur effect applied to text.</span></span>  
  
 ![Textschatten mit einem BlurBitmapEffect](./media/how-to-create-text-with-a-shadow/text-shadow-blur-effect.jpg)  
  
 <span data-ttu-id="cd762-130">Im folgenden Codebeispiel wird das Erstellen eines Weichzeichnereffekts veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="cd762-130">The following code example shows how to create a blur effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a><span data-ttu-id="cd762-131">Verwenden von TranslateTransform</span><span class="sxs-lookup"><span data-stu-id="cd762-131">Using a Translate Transform</span></span>  
 <span data-ttu-id="cd762-132">Ein <xref:System.Windows.Media.TranslateTransform> können verwendet werden, um einen schattenähnlichen Effekt zu erstellen, die hinter einem Textobjekt platziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="cd762-132">A <xref:System.Windows.Media.TranslateTransform> can be used to create a shadow-like effect that can be placed behind a text object.</span></span>  
  
 <span data-ttu-id="cd762-133">Im folgenden Codebeispiel wird eine <xref:System.Windows.Media.TranslateTransform> um Text zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="cd762-133">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="cd762-134">In diesem Beispiel erstellt eine geringfügig versetzte Kopie des Textes hinter dem primären Text einen Schatteneffekt.</span><span class="sxs-lookup"><span data-stu-id="cd762-134">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 ![Textschatten mit einem TranslateTransform](./media/how-to-create-text-with-a-shadow/text-transform-shadow-effect.jpg)    
  
 <span data-ttu-id="cd762-136">Im folgenden Codebeispiel wird das Erstellen einer Transformation für einen Schatteneffekt veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="cd762-136">The following code example shows how to create a transform for a shadow effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
