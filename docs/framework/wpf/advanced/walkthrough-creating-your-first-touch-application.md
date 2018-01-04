---
title: 'Exemplarische Vorgehensweise: Erstellen der ersten Fingereingabeanwendung'
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
- creating a touch-sensitive application [WPF]
- touchscreen applications [WPF], creating
- touch-sensitive applications [WPF], creating
- creating a touchscreen application [WPF]
ms.assetid: d69e602e-9a25-4e24-950b-e89eaa2a906b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 502fb9ae0c488f5f3e438a3ae0a7087538183f1b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-your-first-touch-application"></a>Exemplarische Vorgehensweise: Erstellen der ersten Fingereingabeanwendung
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ermöglicht Anwendungen, um touch reagieren. Beispielsweise eine Anwendung interagieren, indem Sie eine oder mehrere Finger auf einem Gerät mit Touch unterschieden, z. B. einem Touchscreen dar, die in dieser exemplarischen Vorgehensweise eine Anwendung, die dem Benutzer ermöglicht erstellt, zu verschieben, Ändern der Größe oder drehen Sie ein einzelnes Objekt mit Touch.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_dev10_ext](../../../../includes/vs-dev10-ext-md.md)]  
  
-   Windows 7  
  
-   Ein Gerät, das akzeptiert Fingereingabe, z. B. einem Touchscreen dar, die Windows Touch-Unterstützung.  
  
 Darüber hinaus müssen Sie ein grundlegendes Verständnis der Vorgehensweise zum Erstellen einer Anwendung in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], insbesondere die Durchführung von abonnieren und Behandeln eines Ereignisses. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## <a name="creating-the-application"></a>Erstellen der Anwendung  
  
#### <a name="to-create-the-application"></a>So erstellen Sie die Anwendung  
  
1.  Erstellen Sie ein neues WPF-Anwendungsprojekt in Visual Basic oder Visual C# mit dem Namen `BasicManipulation`. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines neuen WPF-Anwendungsprojekts](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
2.  Ersetzen Sie den Inhalt von "MainWindow.xaml", durch Folgendes XAML.  
  
     Dieses Markup erstellt eine einfache Anwendung, die einen roten enthält <xref:System.Windows.Shapes.Rectangle> auf eine <xref:System.Windows.Controls.Canvas>. Die <xref:System.Windows.UIElement.IsManipulationEnabled%2A> Eigenschaft von der <xref:System.Windows.Shapes.Rectangle> festgelegt ist, auf "true", damit Manipulationsereignisse empfangen wird. Die Anwendung abonniert die <xref:System.Windows.UIElement.ManipulationStarting>, <xref:System.Windows.UIElement.ManipulationDelta>, und <xref:System.Windows.UIElement.ManipulationInertiaStarting> Ereignisse. Diese Ereignisse enthalten die Logik zum Verschieben der <xref:System.Windows.Shapes.Rectangle> Wenn der Benutzer es bearbeitet.  
  
     [!code-xaml[BasicManipulation#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml#ui)]  
  
3.  Ersetzen Sie bei Verwendung von Visual Basic, in der ersten Zeile von "MainWindow.xaml" `x:Class="BasicManipulation.MainWindow"` mit `x:Class="MainWindow"`.  
  
4.  In der `MainWindow` Klasse, fügen Sie die folgenden <xref:System.Windows.UIElement.ManipulationStarting> -Ereignishandler.  
  
     Die <xref:System.Windows.UIElement.ManipulationStarting> Ereignis tritt auf, wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erkennt, dass die Fingereingabe beginnt, ein Objekt zu bearbeiten. Der Code gibt an, dass die Position der Manipulation relativ zum sollte die <xref:System.Windows.Window> durch Festlegen der <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> Eigenschaft.  
  
     [!code-csharp[BasicManipulation#ManipulationStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationstarting)]
     [!code-vb[BasicManipulation#ManipulationStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationstarting)]  
  
5.  In der `MainWindow` Klasse, fügen Sie die folgenden <xref:System.Windows.Input.ManipulationDelta> -Ereignishandler.  
  
     Die <xref:System.Windows.Input.ManipulationDelta> Ereignis tritt auf, wenn die Fingereingabe ändert die Position kann mehrere Male während eines Bearbeitungsvorgangs auftreten. Das Ereignis kann auch auftreten, nachdem ein Finger angehoben wird. Angenommen, einen Finger über einen Bildschirm bewegt die <xref:System.Windows.Input.ManipulationDelta> Ereignis tritt auf, mehrere Male sich der Finger bewegt. Wenn der Benutzer einen Finger vom Bildschirm, löst die <xref:System.Windows.Input.ManipulationDelta> behält-Ereignis auftritt, um Trägheit zu simulieren.  
  
     Der Code gilt die <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> auf die <xref:System.Windows.UIElement.RenderTransform%2A> von der <xref:System.Windows.Shapes.Rectangle> Eingabe für das Verschieben Sie sie an, wenn der Benutzer die Touch bewegt. Außerdem überprüft, ob die <xref:System.Windows.Shapes.Rectangle> liegt außerhalb des Bereichs der der <xref:System.Windows.Window> Wenn das Ereignis tritt auf, während der Trägheit. Wenn dies der Fall ist, die Anwendung ruft die <xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=nameWithType> Methode, um die Bearbeitung zu beenden.  
  
     [!code-csharp[BasicManipulation#ManipulationDelta](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationdelta)]
     [!code-vb[BasicManipulation#ManipulationDelta](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationdelta)]  
  
6.  In der `MainWindow` Klasse, fügen Sie die folgenden <xref:System.Windows.UIElement.ManipulationInertiaStarting> -Ereignishandler.  
  
     Die <xref:System.Windows.UIElement.ManipulationInertiaStarting> Ereignis tritt auf, wenn der Benutzer alle Finger vom Bildschirm auslöst. Der Code legt der ursprünglichen Geschwindigkeit und die Verzögerung für die Verschiebung, Erweiterung und Drehung des Rechtecks.  
  
     [!code-csharp[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationinertiastarting)]
     [!code-vb[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationinertiastarting)]  
  
7.  Erstellen Sie das Projekt, und führen Sie es aus.  
  
     Daraufhin sollte ein rotes Quadrat im Fenster angezeigt werden.  
  
## <a name="testing-the-application"></a>Testen der Anwendung  
 Wiederholen Sie zum Testen der Anwendung die folgenden Manipulationen aus. Beachten Sie, dass Sie mehr als eine der folgenden gleichzeitig ausführen können.  
  
-   So verschieben Sie die <xref:System.Windows.Shapes.Rectangle>, stellen einen Finger auf die <xref:System.Windows.Shapes.Rectangle> und bewegen die Finger auf dem Bildschirm.  
  
-   Um die Größe der <xref:System.Windows.Shapes.Rectangle>, legen Sie zwei Finger auf dem <xref:System.Windows.Shapes.Rectangle> und bewegen die Finger aufeinander nahe zusammen oder getrennt weiter.  
  
-   Drehen der <xref:System.Windows.Shapes.Rectangle>, legen Sie zwei Finger auf dem <xref:System.Windows.Shapes.Rectangle> und drehen Sie den Finger um den jeweils anderen.  
  
 Um Trägheit zu verursachen, lösen Sie schnell Ihre Finger vom Bildschirm, wie Sie die vorherigen Manipulationen ausführen. Die <xref:System.Windows.Shapes.Rectangle> weiterhin verschieben, ändern Sie die Größe oder drehen Sie ein paar Sekunden, bevor er beendet.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.UIElement.ManipulationStarting?displayProperty=nameWithType>  
 <xref:System.Windows.UIElement.ManipulationDelta?displayProperty=nameWithType>  
 <xref:System.Windows.UIElement.ManipulationInertiaStarting?displayProperty=nameWithType>
