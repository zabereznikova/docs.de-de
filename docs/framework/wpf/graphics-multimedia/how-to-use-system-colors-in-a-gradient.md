---
title: 'Vorgehensweise: Verwenden von Systemfarben in einem Farbverlauf'
ms.date: 03/30/2017
helpviewer_keywords:
- gradients [WPF], system colors in
- system colors in gradients [WPF]
ms.assetid: 11942e7e-6300-4b50-8ed1-f50e8d20e7d2
ms.openlocfilehash: 3148a5901ccf64194717e26664ab8b9cbd57db2a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365957"
---
# <a name="how-to-use-system-colors-in-a-gradient"></a>Vorgehensweise: Verwenden von Systemfarben in einem Farbverlauf
Um Systemfarben in einem Farbverlauf zu verwenden, verwenden Sie die  *\<SystemColor >* Farbe und  *\<SystemColor >* ColorKey statischen Eigenschaften der der <xref:System.Windows.SystemColors> Klasse zum Abrufen einer Verweis auf die Farbe, in denen  *\<SystemColor >* ist der Name der gewünschten Systemfarbe. Verwenden der  *\<SystemColor >* ColorKey-Eigenschaften, wenn Sie einen dynamischen Verweis erstellen, die automatisch die Systemdesigns aktualisiert werden sollen. Verwenden Sie andernfalls die  *\<SystemColor >* Color-Eigenschaften.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Farbverlauf mithilfe dynamischer Systemfarbressourcen erstellt.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemColorExample.xaml#graphicsmmdynamicsystemcolorgradientexamplewholepage)]  
  
 Im nächsten Beispiel wird ein Farbverlauf mithilfe statischer Systemfarbressourcen erstellt.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemColorExample.xaml#graphicsmmstaticsystemcolorgradientexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.SystemColors>
- [Zeichnen eines Bereichs mit einem Systempinsel](how-to-paint-an-area-with-a-system-brush.md)
- [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md)
