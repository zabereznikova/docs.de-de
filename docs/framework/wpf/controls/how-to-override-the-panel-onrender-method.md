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
ms.openlocfilehash: c4539847368c1a5789e99ec92106d17077ed5943
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59102530"
---
# <a name="how-to-override-the-panel-onrender-method"></a>Vorgehensweise: Überschreiben der Panel.OnRender-Methode
Dieses Beispiel veranschaulicht das Überschreiben der <xref:System.Windows.Controls.Panel.OnRender%2A> -Methode der <xref:System.Windows.Controls.Panel> damit benutzerdefinierte grafische Effekte ein Layoutelement hinzufügen.  
  
## <a name="example"></a>Beispiel  
 Verwenden der <xref:System.Windows.Controls.Panel.OnRender%2A> Methode, um einen gerenderten Bereichselements grafische Effekte hinzuzufügen. Diese Methode können Sie z. B. benutzerdefinierten Rahmen oder Hintergrundeffekte hinzuzufügen. Ein <xref:System.Windows.Media.DrawingContext> Objekt als Argument, das Methoden zum Zeichnen von Formen, Text, Bilder oder Videos enthält übergeben wird. Diese Methode eignet sich daher für die Anpassung von ein-Objekt.  
  
 [!code-csharp[LightWeightCustomPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.Panel>
- [Übersicht über Panel-Elemente](panels-overview.md)
- [Benutzerdefinierte Radial Panel Sample](https://go.microsoft.com/fwlink/?LinkID=159982)
- [Gewusst wie-Themen](panel-how-to-topics.md)
