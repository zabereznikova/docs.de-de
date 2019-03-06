---
title: 'Vorgehensweise: Erstellen von Text mit einem Schatten'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
ms.openlocfilehash: 4d200aa980e8f2e6d22291669dfb07db54a5f0c0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370674"
---
# <a name="how-to-create-text-with-a-shadow"></a><span data-ttu-id="07509-102">Vorgehensweise: Erstellen von Text mit einem Schatten</span><span class="sxs-lookup"><span data-stu-id="07509-102">How to: Create Text with a Shadow</span></span>
<span data-ttu-id="07509-103">Die Beispiele in diesem Abschnitt erklären, wie Sie einen Schatteneffekt für angezeigten Text erstellen.</span><span class="sxs-lookup"><span data-stu-id="07509-103">The examples in this section show how to create a shadow effect for displayed text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07509-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07509-104">Example</span></span>  
 <span data-ttu-id="07509-105">Die <xref:System.Windows.Media.Effects.DropShadowEffect> Objekt ermöglicht Ihnen die Erstellung eine Vielzahl von Schlagschatteneffekten für [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Objekte.</span><span class="sxs-lookup"><span data-stu-id="07509-105">The <xref:System.Windows.Media.Effects.DropShadowEffect> object allows you to create a variety of drop shadow effects for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] objects.</span></span> <span data-ttu-id="07509-106">Das folgende Beispiel zeigt einen auf einen Text angewendeten Schlagschatteneffekt.</span><span class="sxs-lookup"><span data-stu-id="07509-106">The following example shows a drop shadow effect applied to text.</span></span> <span data-ttu-id="07509-107">In diesem Fall ist der Schatten ein weicher Schatten, d.h. die Schattenfarbe verwischt.</span><span class="sxs-lookup"><span data-stu-id="07509-107">In this case, the shadow is a soft shadow, which means the shadow color blurs.</span></span>  
  
 <span data-ttu-id="07509-108">![Textschatten mit Weichheit &#61; 0,25](./media/shadowtext01.jpg "ShadowText01")</span><span class="sxs-lookup"><span data-stu-id="07509-108">![Text shadow with Softness &#61; 0.25](./media/shadowtext01.jpg "ShadowText01")</span></span>  
<span data-ttu-id="07509-109">Beispiel für Text mit einem weichen Schatten</span><span class="sxs-lookup"><span data-stu-id="07509-109">Example of text with a soft shadow</span></span>  
  
 <span data-ttu-id="07509-110">Sie können die Breite eines Schattens durch Festlegen von steuern die <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="07509-110">You can control the width of a shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> property.</span></span> <span data-ttu-id="07509-111">Der Wert `4.0` gibt eine Schattenbreite von 4 Pixeln.</span><span class="sxs-lookup"><span data-stu-id="07509-111">A value of `4.0` indicates a shadow width of 4 pixels.</span></span> <span data-ttu-id="07509-112">Sie können steuern, die Weichheit oder das Weichzeichnen eines Schattens durch Ändern der <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="07509-112">You can control the softness, or blur, of a shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property.</span></span> <span data-ttu-id="07509-113">Der Wert `0.0` gibt an, keinen Weichzeichner.</span><span class="sxs-lookup"><span data-stu-id="07509-113">A value of `0.0` indicates no blurring.</span></span> <span data-ttu-id="07509-114">Im folgenden Codebeispiel wird gezeigt, wie ein weicher Schatten erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="07509-114">The following code example shows how to create a soft shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
>  <span data-ttu-id="07509-115">Diese Schatteneffekte navigieren nicht über die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Textrendering-Pipeline.</span><span class="sxs-lookup"><span data-stu-id="07509-115">These shadow effects do not go through the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] text rendering pipeline.</span></span> <span data-ttu-id="07509-116">Daher ist ClearType bei Verwendung dieser Effekte deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="07509-116">As a result, ClearType is disabled when using these effects.</span></span>  
  
 <span data-ttu-id="07509-117">Das folgende Beispiel zeigt einen auf einen Text angewendeten harten Schlagschatteneffekt.</span><span class="sxs-lookup"><span data-stu-id="07509-117">The following example shows a hard drop shadow effect applied to text.</span></span> <span data-ttu-id="07509-118">In diesem Fall wird der Schatten nicht verwischt.</span><span class="sxs-lookup"><span data-stu-id="07509-118">In this case, the shadow is not blurred.</span></span>  
  
 <span data-ttu-id="07509-119">![Textschatten mit Weichheit &#61; 0](./media/shadowtext02.jpg "ShadowText02")</span><span class="sxs-lookup"><span data-stu-id="07509-119">![Text shadow with Softness &#61; 0](./media/shadowtext02.jpg "ShadowText02")</span></span>  
<span data-ttu-id="07509-120">Beispiel für Text mit einem harten Schatten</span><span class="sxs-lookup"><span data-stu-id="07509-120">Example of text with a hard shadow</span></span>  
  
 <span data-ttu-id="07509-121">Sie können einen harten Schatten erstellen, durch Festlegen der <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> Eigenschaft `0.0`, was bedeutet, dass kein Weichzeichner verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="07509-121">You can create a hard shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property to `0.0`, which indicates that no blurring is used.</span></span> <span data-ttu-id="07509-122">Sie können die Richtung des Schattens durch Ändern von steuern die <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="07509-122">You can control the direction of the shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property.</span></span> <span data-ttu-id="07509-123">Legen Sie den direktionalen Wert dieser Eigenschaft auf einen Grad zwischen `0` und `360`.</span><span class="sxs-lookup"><span data-stu-id="07509-123">Set the directional value of this property to a degree between `0` and `360`.</span></span> <span data-ttu-id="07509-124">Die folgende Abbildung zeigt die direktionalen Werte der <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> Einstellung der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="07509-124">The following illustration shows the directional values of the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property setting.</span></span>  
  
 <span data-ttu-id="07509-125">![DropShadow-gradeinstellung für Schatten](./media/shadowtext08.png "ShadowText08")</span><span class="sxs-lookup"><span data-stu-id="07509-125">![DropShadow degree setting of shadow](./media/shadowtext08.png "ShadowText08")</span></span>  
<span data-ttu-id="07509-126">Diagramm für die DropShadow-Richtung</span><span class="sxs-lookup"><span data-stu-id="07509-126">DropShadow Direction diagram</span></span>  
  
 <span data-ttu-id="07509-127">Im folgenden Codebeispiel wird das Erstellen eines harten Schattens veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="07509-127">The following code example shows how to create a hard shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a><span data-ttu-id="07509-128">Verwenden eines Weichzeichnereffekts</span><span class="sxs-lookup"><span data-stu-id="07509-128">Using a Blur Effect</span></span>  
 <span data-ttu-id="07509-129">Ein <xref:System.Windows.Media.Effects.BlurBitmapEffect> können verwendet werden, um einen schattenähnlichen Effekt zu erstellen, die hinter einem Textobjekt platziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="07509-129">A <xref:System.Windows.Media.Effects.BlurBitmapEffect> can be used to create a shadow-like effect that can be placed behind a text object.</span></span> <span data-ttu-id="07509-130">Ein auf Text angewendeter Weichzeichner-Bitmapeffekt verwischt Text gleichmäßig in alle Richtungen.</span><span class="sxs-lookup"><span data-stu-id="07509-130">A blur bitmap effect applied to text blurs the text evenly in all directions.</span></span>  
  
 <span data-ttu-id="07509-131">Das folgende Beispiel zeigt einen auf einen Text angewendeten Weichzeichnereffekt.</span><span class="sxs-lookup"><span data-stu-id="07509-131">The following example shows a blur effect applied to text.</span></span>  
  
 <span data-ttu-id="07509-132">![Textschatten mit einem BlurBitmapEffect](./media/shadowtext06.jpg "ShadowText06")</span><span class="sxs-lookup"><span data-stu-id="07509-132">![Text shadow using a BlurBitmapEffect](./media/shadowtext06.jpg "ShadowText06")</span></span>  
<span data-ttu-id="07509-133">Beispiel eines Text mit einem Weichzeichnereffekt</span><span class="sxs-lookup"><span data-stu-id="07509-133">Example of text with a blur effect</span></span>  
  
 <span data-ttu-id="07509-134">Im folgenden Codebeispiel wird das Erstellen eines Weichzeichnereffekts veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="07509-134">The following code example shows how to create a blur effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a><span data-ttu-id="07509-135">Verwenden von TranslateTransform</span><span class="sxs-lookup"><span data-stu-id="07509-135">Using a Translate Transform</span></span>  
 <span data-ttu-id="07509-136">Ein <xref:System.Windows.Media.TranslateTransform> können verwendet werden, um einen schattenähnlichen Effekt zu erstellen, die hinter einem Textobjekt platziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="07509-136">A <xref:System.Windows.Media.TranslateTransform> can be used to create a shadow-like effect that can be placed behind a text object.</span></span>  
  
 <span data-ttu-id="07509-137">Im folgenden Codebeispiel wird eine <xref:System.Windows.Media.TranslateTransform> um Text zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="07509-137">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="07509-138">In diesem Beispiel erstellt eine geringfügig versetzte Kopie des Textes hinter dem primären Text einen Schatteneffekt.</span><span class="sxs-lookup"><span data-stu-id="07509-138">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 <span data-ttu-id="07509-139">![Textschatten mit TranslateTransform](./media/shadowtext07.jpg "ShadowText07")</span><span class="sxs-lookup"><span data-stu-id="07509-139">![Text shadow using a TranslateTransform](./media/shadowtext07.jpg "ShadowText07")</span></span>  
<span data-ttu-id="07509-140">Beispiel für Text mit einer Transformation für einen Schatteneffekt</span><span class="sxs-lookup"><span data-stu-id="07509-140">Example of text using a transform for a shadow effect</span></span>  
  
 <span data-ttu-id="07509-141">Im folgenden Codebeispiel wird das Erstellen einer Transformation für einen Schatteneffekt veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="07509-141">The following code example shows how to create a transform for a shadow effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
