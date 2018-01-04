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
ms.workload: dotnet
ms.openlocfilehash: b031b0dce8e1fd06399ded0b6d612a23323ae837
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-text-with-a-shadow"></a>Gewusst wie: Erstellen von Text mit einem Schatten
Die Beispiele in diesem Abschnitt erklären, wie Sie einen Schatteneffekt für angezeigten Text erstellen.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.Media.Effects.DropShadowEffect> Objekt können Sie eine Vielzahl von Schatteneffekten für erstellen [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Objekte. Das folgende Beispiel zeigt einen auf einen Text angewendeten Schlagschatteneffekt. In diesem Fall ist der Schatten ein weicher Schatten, d.h. die Schattenfarbe verwischt.  
  
 ![Textschatten mit Weichheit &#61; 0,25](../../../../docs/framework/wpf/advanced/media/shadowtext01.jpg "ShadowText01")  
Beispiel für Text mit einem weichen Schatten  
  
 Sie können die Breite des Schattens steuern, indem die <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> Eigenschaft. Ein Wert von `4.0` eine Schattenkopie Breite von 4 Pixeln angibt. Sie können die Weichheit steuern oder Blur, der einen Schatten durch Ändern der <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> Eigenschaft. Ein Wert von `0.0` keine Weichzeichnen angibt. Im folgenden Codebeispiel wird gezeigt, wie ein weicher Schatten erstellt wird.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
>  Diese Schatteneffekte gehen Sie nicht über die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Text-Rendering-Pipeline. Daher ist ClearType bei Verwendung dieser Effekte deaktiviert.  
  
 Das folgende Beispiel zeigt einen auf einen Text angewendeten harten Schlagschatteneffekt. In diesem Fall wird der Schatten nicht verwischt.  
  
 ![Textschatten mit Weichheit &#61; 0](../../../../docs/framework/wpf/advanced/media/shadowtext02.jpg "ShadowText02")  
Beispiel für Text mit einem harten Schatten  
  
 Sie können einen festen Schatten erstellen, durch Festlegen der <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> Eigenschaft `0.0`, gibt an, dass keine Weichzeichnen verwendet wird. Sie können die Richtung des Schattens steuern, indem Sie ändern die <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> Eigenschaft. Legen Sie den direktionalen Wert dieser Eigenschaft zu einem gewissen Grad zwischen `0` und `360`. Die folgende Abbildung zeigt die direktionale Werte von der <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> Einstellung der Eigenschaft.  
  
 ![DropShadow-gradeinstellung Schatten](../../../../docs/framework/wpf/advanced/media/shadowtext08.png "ShadowText08")  
Diagramm für die DropShadow-Richtung  
  
 Im folgenden Codebeispiel wird das Erstellen eines harten Schattens veranschaulicht.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a>Verwenden eines Weichzeichnereffekts  
 Ein <xref:System.Windows.Media.Effects.BlurBitmapEffect> kann verwendet werden, um einen Schatten-ähnlichen Effekt zu erstellen, die hinter einem Textobjekt platziert werden kann. Ein auf Text angewendeter Weichzeichner-Bitmapeffekt verwischt Text gleichmäßig in alle Richtungen.  
  
 Das folgende Beispiel zeigt einen auf einen Text angewendeten Weichzeichnereffekt.  
  
 ![Textschatten mit einem BlurBitmapEffect](../../../../docs/framework/wpf/advanced/media/shadowtext06.jpg "ShadowText06")  
Beispiel eines Text mit einem Weichzeichnereffekt  
  
 Im folgenden Codebeispiel wird das Erstellen eines Weichzeichnereffekts veranschaulicht.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a>Verwenden von TranslateTransform  
 Ein <xref:System.Windows.Media.TranslateTransform> kann verwendet werden, um einen Schatten-ähnlichen Effekt zu erstellen, die hinter einem Textobjekt platziert werden kann.  
  
 Im folgenden Codebeispiel wird mit einem <xref:System.Windows.Media.TranslateTransform> um Text zu versetzen. In diesem Beispiel erstellt eine geringfügig versetzte Kopie des Textes hinter dem primären Text einen Schatteneffekt.  
  
 ![Textschatten mit einem TranslateTransform](../../../../docs/framework/wpf/advanced/media/shadowtext07.jpg "ShadowText07")  
Beispiel für Text mit einer Transformation für einen Schatteneffekt  
  
 Im folgenden Codebeispiel wird das Erstellen einer Transformation für einen Schatteneffekt veranschaulicht.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
