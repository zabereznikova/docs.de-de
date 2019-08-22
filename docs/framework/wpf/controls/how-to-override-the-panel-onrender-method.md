---
title: 'Vorgehensweise: Überschreiben der Panel.OnRender-Methode'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- overriding OnRender method
- Panel control, overriding OnRender method
- OnRender method
- controls, Panel, overriding OnRender method
helpviewer_keywords:
- overriding OnRender method of Panel control [WPF]
- OnRender method [WPF], overriding
- Panel control [WPF], overriding OnRender method
ms.assetid: 57397834-a085-4e36-90ab-416fad98f341
ms.openlocfilehash: 23c3353e130585ed83726816a467ca73f6aa9152
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666715"
---
# <a name="how-to-override-the-panel-onrender-method"></a>Vorgehensweise: Überschreiben der Panel.OnRender-Methode
In diesem Beispiel wird gezeigt, wie <xref:System.Windows.Controls.Panel.OnRender%2A> die- <xref:System.Windows.Controls.Panel> Methode von überschrieben wird, um einem Layout-Element benutzerdefinierte grafische Effekte hinzuzufügen.  
  
## <a name="example"></a>Beispiel  
 Verwenden Sie <xref:System.Windows.Controls.Panel.OnRender%2A> die-Methode, um einem gerenderten Panel-Element grafische Effekte hinzuzufügen. Beispielsweise können Sie mit dieser Methode benutzerdefinierte Rahmen-oder Hintergrundeffekte hinzufügen. Ein <xref:System.Windows.Media.DrawingContext> -Objekt wird als Argument übermittelt, das Methoden zum Zeichnen von Formen, Text, Bildern oder Videos bereitstellt. Folglich ist diese Methode nützlich für die Anpassung eines Panel-Objekts.  
  
 [!code-csharp[LightWeightCustomPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.Panel>
- [Übersicht über Panel-Elemente](panels-overview.md)
- [Themen zu Vorgehensweisen](panel-how-to-topics.md)
