---
title: 'Gewusst wie: Erstellen von Text mit einem Schatten'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31bbc3da54c10304e52f93d38365a8d9ed005505
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-text-with-a-shadow"></a><span data-ttu-id="b6bd0-102">Gewusst wie: Erstellen von Text mit einem Schatten</span><span class="sxs-lookup"><span data-stu-id="b6bd0-102">How to: Create Text with a Shadow</span></span>
<span data-ttu-id="b6bd0-103">Die Beispiele in diesem Abschnitt erklären, wie Sie einen Schatteneffekt für angezeigten Text erstellen.</span><span class="sxs-lookup"><span data-stu-id="b6bd0-103">The examples in this section show how to create a shadow effect for displayed text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6bd0-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b6bd0-104">Example</span></span>  
 <span data-ttu-id="b6bd0-105">Die <xref:System.Windows.Media.Effects.DropShadowEffect> Objekt können Sie eine Vielzahl von Schatteneffekten für erstellen [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Objekte.</span><span class="sxs-lookup"><span data-stu-id="b6bd0-105">The <xref:System.Windows.Media.Effects.DropShadowEffect> object allows you to create a variety of drop shadow effects for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] objects.</span></span> <span data-ttu-id="b6bd0-106">Das folgende Beispiel zeigt einen auf einen Text angewendeten Schlagschatteneffekt.</span><span class="sxs-lookup"><span data-stu-id="b6bd0-106">The following example shows a drop shadow effect applied to text.</span></span> <span data-ttu-id="b6bd0-107">In diesem Fall ist der Schatten ein weicher Schatten, d.h. die Schattenfarbe verwischt.</span><span class="sxs-lookup"><span data-stu-id="b6bd0-107">In this case, the shadow is a soft shadow, which means the shadow color blurs.</span></span>  
  
 <span data-ttu-id="b6bd0-108">![Textschatten mit Weichheit &#61; 0,25](../../../../docs/framework/wpf/advanced/media/shadowtext01.jpg "ShadowText01")</span><span class="sxs-lookup"><span data-stu-id="b6bd0-108">![Text shadow with Softness &#61; 0.25](../../../../docs/framework/wpf/advanced/media/shadowtext01.jpg "ShadowText01")</span></span>  
<span data-ttu-id="b6bd0-109">Beispiel für Text mit einem weichen Schatten</span><span class="sxs-lookup"><span data-stu-id="b6bd0-109">Example of text with a soft shadow</span></span>  
  
 <span data-ttu-id="b6bd0-110">Sie können die Breite des Schattens steuern, indem die <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b6bd0-110">You can control the width of a shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> property.</span></span> <span data-ttu-id="b6bd0-111">Ein Wert von `4.0` eine Schattenkopie Breite von 4 Pixeln angibt.</span><span class="sxs-lookup"><span data-stu-id="b6bd0-111">A value of `4.0` indicates a shadow width of 4 pixels.</span></span> <span data-ttu-id="b6bd0-112">Sie können die Weichheit steuern oder Blur, der einen Schatten durch Ändern der <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b6bd0-112">You can control the softness, or blur, of a shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property.</span></span> <span data-ttu-id="b6bd0-113">Ein Wert von `0.0` keine Weichzeichnen angibt.</span><span class="sxs-lookup"><span data-stu-id="b6bd0-113">A value of `0.0` indicates no blurring.</span></span> <span data-ttu-id="b6bd0-114">Im folgenden Codebeispiel wird gezeigt, wie ein weicher Schatten erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="b6bd0-114">The following code example shows how to create a soft shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
>  <span data-ttu-id="b6bd0-115">Diese Schatteneffekte gehen Sie nicht über die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Text-Rendering-Pipeline.</span><span class="sxs-lookup"><span data-stu-id="b6bd0-115">These shadow effects do not go through the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] text rendering pipeline.</span></span> <span data-ttu-id="b6bd0-116">Daher ist ClearType bei Verwendung dieser Effekte deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b6bd0-116">As a result, ClearType is disabled when using these effects.</span></span>  
  
 <span data-ttu-id="b6bd0-117">Das folgende Beispiel zeigt einen auf einen Text angewendeten harten Schlagschatteneffekt.</span><span class="sxs-lookup"><span data-stu-id="b6bd0-117">The following example shows a hard drop shadow effect applied to text.</span></span> <span data-ttu-id="b6bd0-118">In diesem Fall wird der Schatten nicht verwischt.</span><span class="sxs-lookup"><span data-stu-id="b6bd0-118">In this case, the shadow is not blurred.</span></span>  
  
 <span data-ttu-id="b6bd0-119">![Textschatten mit Weichheit &#61; 0](../../../../docs/framework/wpf/advanced/media/shadowtext02.jpg "ShadowText02")</span><span class="sxs-lookup"><span data-stu-id="b6bd0-119">![Text shadow with Softness &#61; 0](../../../../docs/framework/wpf/advanced/media/shadowtext02.jpg "ShadowText02")</span></span>  
<span data-ttu-id="b6bd0-120">Beispiel für Text mit einem harten Schatten</span><span class="sxs-lookup"><span data-stu-id="b6bd0-120">Example of text with a hard shadow</span></span>  
  
 <span data-ttu-id="b6bd0-121">Sie können einen festen Schatten erstellen, durch Festlegen der <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> Eigenschaft `0.0`, gibt an, dass keine Weichzeichnen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b6bd0-121">You can create a hard shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property to `0.0`, which indicates that no blurring is used.</span></span> <span data-ttu-id="b6bd0-122">Sie können die Richtung des Schattens steuern, indem Sie ändern die <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b6bd0-122">You can control the direction of the shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property.</span></span> <span data-ttu-id="b6bd0-123">Legen Sie den direktionalen Wert dieser Eigenschaft zu einem gewissen Grad zwischen `0` und `360`.</span><span class="sxs-lookup"><span data-stu-id="b6bd0-123">Set the directional value of this property to a degree between `0` and `360`.</span></span> <span data-ttu-id="b6bd0-124">Die folgende Abbildung zeigt die direktionale Werte von der <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> Einstellung der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b6bd0-124">The following illustration shows the directional values of the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property setting.</span></span>  
  
 <span data-ttu-id="b6bd0-125">![DropShadow-gradeinstellung Schatten](../../../../docs/framework/wpf/advanced/media/shadowtext08.png "ShadowText08")</span><span class="sxs-lookup"><span data-stu-id="b6bd0-125">![DropShadow degree setting of shadow](../../../../docs/framework/wpf/advanced/media/shadowtext08.png "ShadowText08")</span></span>  
<span data-ttu-id="b6bd0-126">Diagramm für die DropShadow-Richtung</span><span class="sxs-lookup"><span data-stu-id="b6bd0-126">DropShadow Direction diagram</span></span>  
  
 <span data-ttu-id="b6bd0-127">Im folgenden Codebeispiel wird das Erstellen eines harten Schattens veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b6bd0-127">The following code example shows how to create a hard shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a><span data-ttu-id="b6bd0-128">Verwenden eines Weichzeichnereffekts</span><span class="sxs-lookup"><span data-stu-id="b6bd0-128">Using a Blur Effect</span></span>  
 <span data-ttu-id="b6bd0-129">Ein <xref:System.Windows.Media.Effects.BlurBitmapEffect> kann verwendet werden, um einen Schatten-ähnlichen Effekt zu erstellen, die hinter einem Textobjekt platziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b6bd0-129">A <xref:System.Windows.Media.Effects.BlurBitmapEffect> can be used to create a shadow-like effect that can be placed behind a text object.</span></span> <span data-ttu-id="b6bd0-130">Ein auf Text angewendeter Weichzeichner-Bitmapeffekt verwischt Text gleichmäßig in alle Richtungen.</span><span class="sxs-lookup"><span data-stu-id="b6bd0-130">A blur bitmap effect applied to text blurs the text evenly in all directions.</span></span>  
  
 <span data-ttu-id="b6bd0-131">Das folgende Beispiel zeigt einen auf einen Text angewendeten Weichzeichnereffekt.</span><span class="sxs-lookup"><span data-stu-id="b6bd0-131">The following example shows a blur effect applied to text.</span></span>  
  
 <span data-ttu-id="b6bd0-132">![Textschatten mit einem BlurBitmapEffect](../../../../docs/framework/wpf/advanced/media/shadowtext06.jpg "ShadowText06")</span><span class="sxs-lookup"><span data-stu-id="b6bd0-132">![Text shadow using a BlurBitmapEffect](../../../../docs/framework/wpf/advanced/media/shadowtext06.jpg "ShadowText06")</span></span>  
<span data-ttu-id="b6bd0-133">Beispiel eines Text mit einem Weichzeichnereffekt</span><span class="sxs-lookup"><span data-stu-id="b6bd0-133">Example of text with a blur effect</span></span>  
  
 <span data-ttu-id="b6bd0-134">Im folgenden Codebeispiel wird das Erstellen eines Weichzeichnereffekts veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b6bd0-134">The following code example shows how to create a blur effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a><span data-ttu-id="b6bd0-135">Verwenden von TranslateTransform</span><span class="sxs-lookup"><span data-stu-id="b6bd0-135">Using a Translate Transform</span></span>  
 <span data-ttu-id="b6bd0-136">Ein <xref:System.Windows.Media.TranslateTransform> kann verwendet werden, um einen Schatten-ähnlichen Effekt zu erstellen, die hinter einem Textobjekt platziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b6bd0-136">A <xref:System.Windows.Media.TranslateTransform> can be used to create a shadow-like effect that can be placed behind a text object.</span></span>  
  
 <span data-ttu-id="b6bd0-137">Im folgenden Codebeispiel wird mit einem <xref:System.Windows.Media.TranslateTransform> um Text zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="b6bd0-137">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="b6bd0-138">In diesem Beispiel erstellt eine geringfügig versetzte Kopie des Textes hinter dem primären Text einen Schatteneffekt.</span><span class="sxs-lookup"><span data-stu-id="b6bd0-138">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 <span data-ttu-id="b6bd0-139">![Textschatten mit einem TranslateTransform](../../../../docs/framework/wpf/advanced/media/shadowtext07.jpg "ShadowText07")</span><span class="sxs-lookup"><span data-stu-id="b6bd0-139">![Text shadow using a TranslateTransform](../../../../docs/framework/wpf/advanced/media/shadowtext07.jpg "ShadowText07")</span></span>  
<span data-ttu-id="b6bd0-140">Beispiel für Text mit einer Transformation für einen Schatteneffekt</span><span class="sxs-lookup"><span data-stu-id="b6bd0-140">Example of text using a transform for a shadow effect</span></span>  
  
 <span data-ttu-id="b6bd0-141">Im folgenden Codebeispiel wird das Erstellen einer Transformation für einen Schatteneffekt veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b6bd0-141">The following code example shows how to create a transform for a shadow effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
