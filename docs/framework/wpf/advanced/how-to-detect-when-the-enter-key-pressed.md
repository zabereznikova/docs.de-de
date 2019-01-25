---
title: 'Vorgehensweise: Erkennen, wenn die EINGABETASTE gedrückt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: fbb9b1b9cbb56a49aba018f122a7e903bd4f677d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54592246"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a>Vorgehensweise: Erkennen, wenn die EINGABETASTE gedrückt
Dieses Beispiel zeigt, wie Sie feststellen, ob die <xref:System.Windows.Input.Key.Enter> Taste auf der Tastatur gedrückt wird.  
  
 In diesem Beispiel besteht aus einem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und eine CodeBehind-Datei.  
  
## <a name="example"></a>Beispiel  
 Wenn der Benutzer drückt die <xref:System.Windows.Input.Key.Enter> -Schlüssel in der <xref:System.Windows.Controls.TextBox>, die Eingabe in das Textfeld angezeigt wird, in einem anderen Bereich von der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
 Die folgenden [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] erstellt die Benutzeroberfläche besteht aus einem <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.TextBlock>, und ein <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xaml[keydown#KeyDownUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 Der folgende Code hinter erstellt die <xref:System.Windows.UIElement.KeyDown> -Ereignishandler.  Wenn der Schlüssel, die gedrückt wird, wird die <xref:System.Windows.Input.Key.Enter> drücken, wird eine Meldung angezeigt, der <xref:System.Windows.Controls.TextBlock>.  
  
 [!code-csharp[keydown#KeyDownSample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md)
- [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
