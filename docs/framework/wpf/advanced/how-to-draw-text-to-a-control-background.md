---
title: 'Vorgehensweise: Zeichnen von Text im Hintergrund eines Steuerelements'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 091be80e055279685c9dba33dd6b6635e64eaff0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-text-to-a-control39s-background"></a>Vorgehensweise: Zeichnen von Text im Hintergrund eines Steuerelements
Sie können Text direkt im Hintergrund Zeichnen eines Steuerelements durch eine Zeichenfolge zu konvertieren einer <xref:System.Windows.Media.FormattedText> Objekt, und klicken Sie dann auf des Steuerelements Zeichnen des Objekts <xref:System.Windows.Media.DrawingContext>. Sie können dieses Verfahren auch verwenden, für die Zeichnung im Hintergrund von Objekten abgeleitet <xref:System.Windows.Controls.Panel>, wie z. B. <xref:System.Windows.Controls.Canvas> und <xref:System.Windows.Controls.StackPanel>.  
  
 ![Steuert das Anzeigen von Text als Hintergrund](../../../../docs/framework/wpf/advanced/media/drawtext2background01.png "DrawText2Background01")  
Beispiel für Steuerelemente mit benutzerdefinierten Texthintergründen  
  
## <a name="example"></a>Beispiel  
 Um dem Hintergrund eines Steuerelements zu zeichnen, erstellen Sie ein neues <xref:System.Windows.Media.DrawingBrush> Objekt, und zeichnen Sie den konvertierten Text mit des Objekts <xref:System.Windows.Media.DrawingContext>. Weisen Sie anschließend auf die neue <xref:System.Windows.Media.DrawingBrush> Hintergrund-Eigenschaft des Steuerelements.  
  
 Das folgende Codebeispiel veranschaulicht das Erstellen einer <xref:System.Windows.Media.FormattedText> Objekt, und zeichnen Sie in den Hintergrund des eine <xref:System.Windows.Controls.Label> und <xref:System.Windows.Controls.Button> Objekt.  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.FormattedText>  
 [Zeichnen von formatiertem Text](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
