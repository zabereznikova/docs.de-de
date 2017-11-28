---
title: "Gewusst wie: Erkennen, wenn die EINGABETASTE gedrückt wird"
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
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8311083b4b82d4ab4827e8d0a2cf958c67347014
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a>Gewusst wie: Erkennen, wenn die EINGABETASTE gedrückt wird
Dieses Beispiel zeigt, wie Sie feststellen, ob die <xref:System.Windows.Input.Key.Enter> Taste auf der Tastatur gedrückt wird.  
  
 In diesem Beispiel besteht aus einem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und eine Code-Behind-Datei.  
  
## <a name="example"></a>Beispiel  
 Wenn der Benutzer drückt die <xref:System.Windows.Input.Key.Enter> -Schlüssel in der <xref:System.Windows.Controls.TextBox>, die Eingabe in das Textfeld angezeigt wird, in eine andere Stelle der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
 Die folgenden [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] erstellt die Benutzeroberfläche, die sich aus einer <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.TextBlock>, und ein <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xaml[keydown#KeyDownUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 Der folgende Code-behind erstellt die <xref:System.Windows.UIElement.KeyDown> -Ereignishandler.  Wenn der Schlüssel, die gedrückt wird, ist die <xref:System.Windows.Input.Key.Enter> drücken, wird eine Meldung angezeigt, der <xref:System.Windows.Controls.TextBlock>.  
  
 [!code-csharp[keydown#KeyDownSample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
