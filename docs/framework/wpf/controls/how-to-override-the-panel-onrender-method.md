---
title: "Gewusst wie: Überschreiben der Panel.OnRender-Methode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 958595cdfa521b372270d6283c7134ef0ba0ef79
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-override-the-panel-onrender-method"></a>Gewusst wie: Überschreiben der Panel.OnRender-Methode
Dieses Beispiel veranschaulicht das Überschreiben der <xref:System.Windows.Controls.Panel.OnRender%2A> Methode <xref:System.Windows.Controls.Panel> damit benutzerdefinierte grafische Effekte Layoutelement hinzufügen.  
  
## <a name="example"></a>Beispiel  
 Verwenden der <xref:System.Windows.Controls.Panel.OnRender%2A> Methode, um grafische Effekte auf ein Bereichselement gerenderten hinzuzufügen. Diese Methode können Sie z. B. benutzerdefinierte Rahmen oder Hintergrundeffekte hinzufügen. Ein <xref:System.Windows.Media.DrawingContext> Objekt als Argument, das Methoden zum Zeichnen von Formen, Text, Bilder oder Videos von Ereignissen übergeben. Diese Methode eignet sich daher, für die Anpassung eines Objekts Bereich.  
  
 [!code-csharp[LightWeightCustomPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Panel>  
 [Übersicht über Panel-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Benutzerdefinierte radiale Bereichsbeispiel](http://go.microsoft.com/fwlink/?LinkID=159982)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/panel-how-to-topics.md)
