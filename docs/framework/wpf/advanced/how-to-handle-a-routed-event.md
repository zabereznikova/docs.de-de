---
title: 'Vorgehensweise: Behandeln eines Routingereignisses'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], handling
- bubbling events [WPF]
ms.assetid: 157787b4-f469-4047-8777-5b034145f32e
ms.openlocfilehash: 42f5f247e775fbf0bd323fc693a74d6149c87bb3
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368193"
---
# <a name="how-to-handle-a-routed-event"></a>Vorgehensweise: Behandeln eines Routingereignisses
Dieses Beispiel zeigt, wie Bubbling-Ereignisse funktionieren, und wie Sie einen Handler schreiben, der die Routingereignisdaten verarbeiten kann.  
  
## <a name="example"></a>Beispiel  
 In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] werden Elemente in einer Elementstruktur angeordnet. Bei der Verarbeitung von Ereignissen, die ursprünglich von untergeordneten Elementen in der Elementstruktur ausgelöst werden, kann das übergeordnete Element teilnehmen. Dies ist durch das Ereignisrouting möglich.  
  
 Routingereignisse verfolgen normalerweise eine der folgenden Routingstrategien: Bubbling oder Tunneln. Dieses Beispiel konzentriert sich auf das bubbling-Ereignis und verwendet die <xref:System.Windows.Controls.Primitives.ButtonBase.Click?displayProperty=nameWithType> Ereignis, um das routing zu verdeutlichen.  
  
 Das folgende Beispiel erstellt zwei <xref:System.Windows.Controls.Button> steuert und verwendet [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Attributsyntax, um ein Ereignishandler einem gemeinsamen übergeordneten Element anzufügen, die in diesem Beispiel wird <xref:System.Windows.Controls.StackPanel>. Anstatt einzelne Ereignishandler für die einzelnen <xref:System.Windows.Controls.Button> untergeordnetes Element im Beispiel verwendet, um den Ereignishandler zum Anfügen der <xref:System.Windows.Controls.StackPanel> übergeordnetes Element. Dieses Muster für die Ereignisbehandlung veranschaulicht, wie das Ereignisrouting als Verfahren zum Reduzieren der Anzahl der Elemente verwendet wird, bei denen ein Handler angefügt ist. Alle bubbling-Ereignisse für die einzelnen <xref:System.Windows.Controls.Button> Route über das übergeordnete Element.  
  
 Beachten Sie, dass auf dem übergeordneten Element <xref:System.Windows.Controls.StackPanel> -Element, das <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignisnamen angegeben, wie das Attribut teilweise durch benennen qualifiziert wird die <xref:System.Windows.Controls.Button> Klasse. Die <xref:System.Windows.Controls.Button> -Klasse ist eine <xref:System.Windows.Controls.Primitives.ButtonBase> abgeleitete Klasse, die die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis in der Elementauflistung. Diese partiellen Qualifikation-Technik für das Anhängen eines ereignishandlers ist erforderlich, wenn das Ereignis behandelt wird, das nicht, in die Elemente vorhanden ist des Elements, an der Routingereignishandler angefügt, auflisten.  
  
 [!code-xaml[RoutedEventHandle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml#xaml)]  
  
 Das folgende Beispiel verarbeitet die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis.  Im Beispiel wird gemeldet, welches Element das Ereignis behandelt und welches Element das Ereignis auslöst. Der Ereignishandler wird ausgeführt, wenn der Benutzer auf eine Schaltfläche klickt.  
  
 [!code-csharp[RoutedEventHandle#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventHandle#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventHandle/VisualBasic/MainWindow.xaml.vb#handler)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.RoutedEvent>
- [Übersicht über die Eingabe](input-overview.md)
- [Übersicht über Routingereignisse](routed-events-overview.md)
- [Themen zu Vorgehensweisen](events-how-to-topics.md)
- [Ausführliche Erläuterung der XAML-Syntax](xaml-syntax-in-detail.md)
