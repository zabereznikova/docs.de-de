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
# <a name="how-to-create-text-with-a-shadow"></a>Vorgehensweise: Erstellen von Text mit einem Schatten
Die Beispiele in diesem Abschnitt erklären, wie Sie einen Schatteneffekt für angezeigten Text erstellen.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.Media.Effects.DropShadowEffect> Objekt ermöglicht Ihnen die Erstellung eine Vielzahl von Schlagschatteneffekten für [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Objekte. Das folgende Beispiel zeigt einen auf einen Text angewendeten Schlagschatteneffekt. In diesem Fall ist der Schatten ein weicher Schatten, d.h. die Schattenfarbe verwischt.  
  
 ![Textschatten mit Weichheit &#61; 0,25](./media/shadowtext01.jpg "ShadowText01")  
Beispiel für Text mit einem weichen Schatten  
  
 Sie können die Breite eines Schattens durch Festlegen von steuern die <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> Eigenschaft. Der Wert `4.0` gibt eine Schattenbreite von 4 Pixeln. Sie können steuern, die Weichheit oder das Weichzeichnen eines Schattens durch Ändern der <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> Eigenschaft. Der Wert `0.0` gibt an, keinen Weichzeichner. Im folgenden Codebeispiel wird gezeigt, wie ein weicher Schatten erstellt wird.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
>  Diese Schatteneffekte navigieren nicht über die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Textrendering-Pipeline. Daher ist ClearType bei Verwendung dieser Effekte deaktiviert.  
  
 Das folgende Beispiel zeigt einen auf einen Text angewendeten harten Schlagschatteneffekt. In diesem Fall wird der Schatten nicht verwischt.  
  
 ![Textschatten mit Weichheit &#61; 0](./media/shadowtext02.jpg "ShadowText02")  
Beispiel für Text mit einem harten Schatten  
  
 Sie können einen harten Schatten erstellen, durch Festlegen der <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> Eigenschaft `0.0`, was bedeutet, dass kein Weichzeichner verwendet wird. Sie können die Richtung des Schattens durch Ändern von steuern die <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> Eigenschaft. Legen Sie den direktionalen Wert dieser Eigenschaft auf einen Grad zwischen `0` und `360`. Die folgende Abbildung zeigt die direktionalen Werte der <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> Einstellung der Eigenschaft.  
  
 ![DropShadow-gradeinstellung für Schatten](./media/shadowtext08.png "ShadowText08")  
Diagramm für die DropShadow-Richtung  
  
 Im folgenden Codebeispiel wird das Erstellen eines harten Schattens veranschaulicht.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a>Verwenden eines Weichzeichnereffekts  
 Ein <xref:System.Windows.Media.Effects.BlurBitmapEffect> können verwendet werden, um einen schattenähnlichen Effekt zu erstellen, die hinter einem Textobjekt platziert werden kann. Ein auf Text angewendeter Weichzeichner-Bitmapeffekt verwischt Text gleichmäßig in alle Richtungen.  
  
 Das folgende Beispiel zeigt einen auf einen Text angewendeten Weichzeichnereffekt.  
  
 ![Textschatten mit einem BlurBitmapEffect](./media/shadowtext06.jpg "ShadowText06")  
Beispiel eines Text mit einem Weichzeichnereffekt  
  
 Im folgenden Codebeispiel wird das Erstellen eines Weichzeichnereffekts veranschaulicht.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a>Verwenden von TranslateTransform  
 Ein <xref:System.Windows.Media.TranslateTransform> können verwendet werden, um einen schattenähnlichen Effekt zu erstellen, die hinter einem Textobjekt platziert werden kann.  
  
 Im folgenden Codebeispiel wird eine <xref:System.Windows.Media.TranslateTransform> um Text zu versetzen. In diesem Beispiel erstellt eine geringfügig versetzte Kopie des Textes hinter dem primären Text einen Schatteneffekt.  
  
 ![Textschatten mit TranslateTransform](./media/shadowtext07.jpg "ShadowText07")  
Beispiel für Text mit einer Transformation für einen Schatteneffekt  
  
 Im folgenden Codebeispiel wird das Erstellen einer Transformation für einen Schatteneffekt veranschaulicht.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
