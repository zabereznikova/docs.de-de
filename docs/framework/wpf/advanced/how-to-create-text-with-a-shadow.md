---
title: 'Vorgehensweise: Erstellen von Text mit einem Schatten'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
ms.openlocfilehash: 0fe64e4e9e7aadbd30a38743647251f9fa49ba95
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960446"
---
# <a name="how-to-create-text-with-a-shadow"></a><span data-ttu-id="43b0c-102">Vorgehensweise: Erstellen von Text mit einem Schatten</span><span class="sxs-lookup"><span data-stu-id="43b0c-102">How to: Create Text with a Shadow</span></span>
<span data-ttu-id="43b0c-103">Die Beispiele in diesem Abschnitt erklären, wie Sie einen Schatteneffekt für angezeigten Text erstellen.</span><span class="sxs-lookup"><span data-stu-id="43b0c-103">The examples in this section show how to create a shadow effect for displayed text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43b0c-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="43b0c-104">Example</span></span>  
 <span data-ttu-id="43b0c-105">Mit <xref:System.Windows.Media.Effects.DropShadowEffect> dem-Objekt können Sie eine Vielzahl von Drop Shadow-Effekten [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] für-Objekte erstellen.</span><span class="sxs-lookup"><span data-stu-id="43b0c-105">The <xref:System.Windows.Media.Effects.DropShadowEffect> object allows you to create a variety of drop shadow effects for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] objects.</span></span> <span data-ttu-id="43b0c-106">Das folgende Beispiel zeigt einen auf einen Text angewendeten Schlagschatteneffekt.</span><span class="sxs-lookup"><span data-stu-id="43b0c-106">The following example shows a drop shadow effect applied to text.</span></span> <span data-ttu-id="43b0c-107">In diesem Fall ist der Schatten ein weicher Schatten, d.h. die Schattenfarbe verwischt.</span><span class="sxs-lookup"><span data-stu-id="43b0c-107">In this case, the shadow is a soft shadow, which means the shadow color blurs.</span></span>  
  
 ![Text Schatten mit Weichheit &#61; 0,25](./media/how-to-create-text-with-a-shadow/drop-shadow-text-effect.jpg) 
  
 <span data-ttu-id="43b0c-109">Sie können die Breite eines Schattens steuern, indem <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> Sie die-Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="43b0c-109">You can control the width of a shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> property.</span></span> <span data-ttu-id="43b0c-110">Der `4.0` Wert gibt eine Schatten Breite von 4 Pixeln an.</span><span class="sxs-lookup"><span data-stu-id="43b0c-110">A value of `4.0` indicates a shadow width of 4 pixels.</span></span> <span data-ttu-id="43b0c-111">Durch Ändern der <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> -Eigenschaft können Sie die Weichheit oder den weichungs Bereich eines Schattens steuern.</span><span class="sxs-lookup"><span data-stu-id="43b0c-111">You can control the softness, or blur, of a shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property.</span></span> <span data-ttu-id="43b0c-112">Der Wert gibt `0.0` an, dass kein blurring besteht.</span><span class="sxs-lookup"><span data-stu-id="43b0c-112">A value of `0.0` indicates no blurring.</span></span> <span data-ttu-id="43b0c-113">Im folgenden Codebeispiel wird gezeigt, wie ein weicher Schatten erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="43b0c-113">The following code example shows how to create a soft shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
> <span data-ttu-id="43b0c-114">Diese Schatteneffekte durchlaufen nicht die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Text Rendering-Pipeline.</span><span class="sxs-lookup"><span data-stu-id="43b0c-114">These shadow effects do not go through the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] text rendering pipeline.</span></span> <span data-ttu-id="43b0c-115">Daher ist ClearType bei Verwendung dieser Effekte deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="43b0c-115">As a result, ClearType is disabled when using these effects.</span></span>  
  
 <span data-ttu-id="43b0c-116">Das folgende Beispiel zeigt einen auf einen Text angewendeten harten Schlagschatteneffekt.</span><span class="sxs-lookup"><span data-stu-id="43b0c-116">The following example shows a hard drop shadow effect applied to text.</span></span> <span data-ttu-id="43b0c-117">In diesem Fall wird der Schatten nicht verwischt.</span><span class="sxs-lookup"><span data-stu-id="43b0c-117">In this case, the shadow is not blurred.</span></span>  
  
 ![Text Schatten mit Weichheit &#61; 0](./media/how-to-create-text-with-a-shadow/text-shadow-softness.jpg) 
  
 <span data-ttu-id="43b0c-119">Sie können einen harten Schatten erstellen, indem Sie <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> die- `0.0`Eigenschaft auf festlegen. Dies bedeutet, dass kein Weichzeichner verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="43b0c-119">You can create a hard shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property to `0.0`, which indicates that no blurring is used.</span></span> <span data-ttu-id="43b0c-120">Sie können die Richtung des Schattens steuern, indem <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> Sie die-Eigenschaft ändern.</span><span class="sxs-lookup"><span data-stu-id="43b0c-120">You can control the direction of the shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property.</span></span> <span data-ttu-id="43b0c-121">Legen Sie den direktionalen Wert dieser Eigenschaft auf einen `0` Grad `360`zwischen und fest.</span><span class="sxs-lookup"><span data-stu-id="43b0c-121">Set the directional value of this property to a degree between `0` and `360`.</span></span> <span data-ttu-id="43b0c-122">Die folgende Abbildung zeigt die direktionalen Werte <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> der-Eigenschaften Einstellung.</span><span class="sxs-lookup"><span data-stu-id="43b0c-122">The following illustration shows the directional values of the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property setting.</span></span>  
  
 ![DropShadow-Gradeinstellung für Schatten](./media/how-to-create-text-with-a-shadow/drop-shadow-degree-setting.png)
  
 <span data-ttu-id="43b0c-124">Im folgenden Codebeispiel wird das Erstellen eines harten Schattens veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="43b0c-124">The following code example shows how to create a hard shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a><span data-ttu-id="43b0c-125">Verwenden eines Weichzeichnereffekts</span><span class="sxs-lookup"><span data-stu-id="43b0c-125">Using a Blur Effect</span></span>  
 <span data-ttu-id="43b0c-126">Ein <xref:System.Windows.Media.Effects.BlurBitmapEffect> kann verwendet werden, um einen Schatten ähnlichen Effekt zu erstellen, der hinter einem Textobjekt platziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="43b0c-126">A <xref:System.Windows.Media.Effects.BlurBitmapEffect> can be used to create a shadow-like effect that can be placed behind a text object.</span></span> <span data-ttu-id="43b0c-127">Ein auf Text angewendeter Weichzeichner-Bitmapeffekt verwischt Text gleichmäßig in alle Richtungen.</span><span class="sxs-lookup"><span data-stu-id="43b0c-127">A blur bitmap effect applied to text blurs the text evenly in all directions.</span></span>  
  
 <span data-ttu-id="43b0c-128">Das folgende Beispiel zeigt einen auf einen Text angewendeten Weichzeichnereffekt.</span><span class="sxs-lookup"><span data-stu-id="43b0c-128">The following example shows a blur effect applied to text.</span></span>  
  
 ![Textschatten mit einem BlurBitmapEffect](./media/how-to-create-text-with-a-shadow/text-shadow-blur-effect.jpg)  
  
 <span data-ttu-id="43b0c-130">Im folgenden Codebeispiel wird das Erstellen eines Weichzeichnereffekts veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="43b0c-130">The following code example shows how to create a blur effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a><span data-ttu-id="43b0c-131">Verwenden von TranslateTransform</span><span class="sxs-lookup"><span data-stu-id="43b0c-131">Using a Translate Transform</span></span>  
 <span data-ttu-id="43b0c-132">Ein <xref:System.Windows.Media.TranslateTransform> kann verwendet werden, um einen Schatten ähnlichen Effekt zu erstellen, der hinter einem Textobjekt platziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="43b0c-132">A <xref:System.Windows.Media.TranslateTransform> can be used to create a shadow-like effect that can be placed behind a text object.</span></span>  
  
 <span data-ttu-id="43b0c-133">Im folgenden Codebeispiel wird ein <xref:System.Windows.Media.TranslateTransform> zum Offset von Text verwendet.</span><span class="sxs-lookup"><span data-stu-id="43b0c-133">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="43b0c-134">In diesem Beispiel erstellt eine geringfügig versetzte Kopie des Textes hinter dem primären Text einen Schatteneffekt.</span><span class="sxs-lookup"><span data-stu-id="43b0c-134">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 ![Textschatten mit einem TranslateTransform](./media/how-to-create-text-with-a-shadow/text-transform-shadow-effect.jpg)    
  
 <span data-ttu-id="43b0c-136">Im folgenden Codebeispiel wird das Erstellen einer Transformation für einen Schatteneffekt veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="43b0c-136">The following code example shows how to create a transform for a shadow effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
