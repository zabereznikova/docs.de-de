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
# <a name="how-to-create-text-with-a-shadow"></a>Gewusst wie: Erstellen von Text mit einem Schatten
Die Beispiele in diesem Abschnitt erklären, wie Sie einen Schatteneffekt für angezeigten Text erstellen.  
  
## <a name="example"></a>Beispiel  
 Mit <xref:System.Windows.Media.Effects.DropShadowEffect> dem Objekt können Sie eine Vielzahl [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] von Schlagschatteneffekten für Objekte erstellen. Das folgende Beispiel zeigt einen auf einen Text angewendeten Schlagschatteneffekt. In diesem Fall ist der Schatten ein weicher Schatten, d.h. die Schattenfarbe verwischt.  
  
 ![Textschatten mit Weichheit &#61; 0,25](./media/how-to-create-text-with-a-shadow/drop-shadow-text-effect.jpg)
  
 Sie können die Breite eines Schattens steuern, indem Sie die <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> Eigenschaft festlegen. Der Wert `4.0` von gibt eine Schattenbreite von 4 Pixel an. Sie können die Weichheit oder Unschärfe eines <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> Schattens steuern, indem Sie die Eigenschaft ändern. Der Wert `0.0` von gibt keine Unschärfe an. Im folgenden Codebeispiel wird gezeigt, wie ein weicher Schatten erstellt wird.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
> Diese Schatteneffekte durchlaufen nicht [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] die Textrenderingpipeline. Daher ist ClearType bei Verwendung dieser Effekte deaktiviert.  
  
 Das folgende Beispiel zeigt einen auf einen Text angewendeten harten Schlagschatteneffekt. In diesem Fall wird der Schatten nicht verwischt.  
  
 ![Textschatten mit Weichheit &#61; 0](./media/how-to-create-text-with-a-shadow/text-shadow-softness.jpg)
  
 Sie können einen harten Schatten <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> erstellen, indem Sie die Eigenschaft auf `0.0`festlegen, was darauf hinweist, dass keine Unschärfe verwendet wird. Sie können die Richtung des Schattens <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> steuern, indem Sie die Eigenschaft ändern. Legen Sie den Richtungswert dieser `0` Eigenschaft `360`auf einen Grad zwischen und fest. Die folgende Abbildung zeigt die <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> Richtungswerte der Eigenschaftseinstellung.  
  
 ![DropShadow-Gradeinstellung für Schatten](./media/how-to-create-text-with-a-shadow/drop-shadow-degree-setting.png)
  
 Im folgenden Codebeispiel wird das Erstellen eines harten Schattens veranschaulicht.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a>Verwenden eines Weichzeichnereffekts  
 A <xref:System.Windows.Media.Effects.BlurBitmapEffect> kann verwendet werden, um einen schattenähnlichen Effekt zu erzeugen, der hinter einem Textobjekt platziert werden kann. Ein auf Text angewendeter Weichzeichner-Bitmapeffekt verwischt Text gleichmäßig in alle Richtungen.  
  
 Das folgende Beispiel zeigt einen Text mit Weichzeichnereffekt.  
  
 ![Textschatten mit einem BlurBitmapEffect](./media/how-to-create-text-with-a-shadow/text-shadow-blur-effect.jpg)  
  
 Im folgenden Codebeispiel wird das Erstellen eines Weichzeichnereffekts veranschaulicht.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a>Verwenden von TranslateTransform  
 A <xref:System.Windows.Media.TranslateTransform> kann verwendet werden, um einen schattenähnlichen Effekt zu erzeugen, der hinter einem Textobjekt platziert werden kann.  
  
 Im folgenden Codebeispiel <xref:System.Windows.Media.TranslateTransform> wird ein zum Versetzen von Text verwendet. In diesem Beispiel erstellt eine geringfügig versetzte Kopie des Textes hinter dem primären Text einen Schatteneffekt.  
  
 ![Textschatten mit einem TranslateTransform](./media/how-to-create-text-with-a-shadow/text-transform-shadow-effect.jpg)
  
 Im folgenden Codebeispiel wird das Erstellen einer Transformation für einen Schatteneffekt veranschaulicht.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
