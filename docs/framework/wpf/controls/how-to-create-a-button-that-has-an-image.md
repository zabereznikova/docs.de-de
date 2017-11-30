---
title: "Gewusst wie: Erstellen einer Schaltfläche mit einem Bild"
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
helpviewer_keywords: Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fa3aa5454629d53fd8864df6a4f204e22028208f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-button-that-has-an-image"></a>Gewusst wie: Erstellen einer Schaltfläche mit einem Bild
In diesem Beispiel wird gezeigt, wie auf ein Bild enthalten eine <xref:System.Windows.Controls.Button>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt zwei <xref:System.Windows.Controls.Button> Steuerelemente. Eine <xref:System.Windows.Controls.Button> Text enthält und das andere ein Bild. Das Bild wird in einen Ordner namens Daten, d. h. einen Unterordner des Ordners für die Beispiel-Projekt. Wenn ein Benutzer klickt auf die <xref:System.Windows.Controls.Button> , besitzt das Bild, Hintergrund und den Text der anderen <xref:System.Windows.Controls.Button> ändern.  
  
 In diesem Beispiel wird <xref:System.Windows.Controls.Button> steuert mithilfe von Markup, aber zum Schreiben von Code verwendet die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler.  
  
 [!code-xaml[BtnColor#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelemente](../../../../docs/framework/wpf/controls/index.md)  
 [Steuerelementbibliothek](../../../../docs/framework/wpf/controls/control-library.md)
