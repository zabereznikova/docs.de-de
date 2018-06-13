---
title: 'Gewusst wie: Behandeln eines Routingereignisses'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], handling
- bubbling events [WPF]
ms.assetid: 157787b4-f469-4047-8777-5b034145f32e
ms.openlocfilehash: 80b3be439498c0dc448322d1e7daf30202a470dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544316"
---
# <a name="how-to-handle-a-routed-event"></a>Gewusst wie: Behandeln eines Routingereignisses
Dieses Beispiel zeigt, wie Bubbling-Ereignisse funktionieren, und wie Sie einen Handler schreiben, der die Routingereignisdaten verarbeiten kann.  
  
## <a name="example"></a>Beispiel  
 In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] werden Elemente in einer Elementstruktur angeordnet. Bei der Verarbeitung von Ereignissen, die ursprünglich von untergeordneten Elementen in der Elementstruktur ausgelöst werden, kann das übergeordnete Element teilnehmen. Dies ist durch das Ereignisrouting möglich.  
  
 Routingereignisse verfolgen normalerweise eine der folgenden Routingstrategien: Bubbling oder Tunneln. In diesem Beispiel konzentriert sich auf das bubbling-Ereignis und verwendet die <xref:System.Windows.Controls.Primitives.ButtonBase.Click?displayProperty=nameWithType> Ereignis, um die Funktionsweise des Routings angezeigt.  
  
 Das folgende Beispiel erstellt zwei <xref:System.Windows.Controls.Button> steuert und verwendet [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -Attribut Syntax, um einen Ereignishandler zu einem gemeinsamen übergeordneten Element anfügen, die in diesem Beispiel wird <xref:System.Windows.Controls.StackPanel>. Anstatt durch Anfügen von einzelnen Ereignishandler für die einzelnen <xref:System.Windows.Controls.Button> untergeordnetes Element im Beispiel wird den Ereignishandler angefügt Attributsyntax verwendet die <xref:System.Windows.Controls.StackPanel> übergeordneten Elements. Dieses Muster für die Ereignisbehandlung veranschaulicht, wie das Ereignisrouting als Verfahren zum Reduzieren der Anzahl der Elemente verwendet wird, bei denen ein Handler angefügt ist. Alle bubbling-Ereignisse für die einzelnen <xref:System.Windows.Controls.Button> über das übergeordnete Element weiterleiten.  
  
 Beachten Sie, dass für die übergeordnete <xref:System.Windows.Controls.StackPanel> Element, das <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignisname angegeben, wie das Attribut teilweise von Benennung qualifiziert wird die <xref:System.Windows.Controls.Button> Klasse. Die <xref:System.Windows.Controls.Button> Klasse ist eine <xref:System.Windows.Controls.Primitives.ButtonBase> abgeleitete Klasse, verfügt die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis in ihre Member auflisten. Diese Technik partielle Qualifizierung für einen Ereignishandler anfügen ist erforderlich, wenn das Ereignis behandelt wird, das in die Elemente nicht vorhanden ist eine Liste der das Element, an der Routingereignishandler angefügt ist.  
  
 [!code-xaml[RoutedEventHandle#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml#xaml)]  
  
 Das folgende Beispiel verarbeitet die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis.  Im Beispiel wird gemeldet, welches Element das Ereignis behandelt und welches Element das Ereignis auslöst. Der Ereignishandler wird ausgeführt, wenn der Benutzer auf eine Schaltfläche klickt.  
  
 [!code-csharp[RoutedEventHandle#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventHandle#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventHandle/VisualBasic/MainWindow.xaml.vb#handler)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.RoutedEvent>  
 [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)  
 [Ausführliche Erläuterung der XAML-Syntax](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)
