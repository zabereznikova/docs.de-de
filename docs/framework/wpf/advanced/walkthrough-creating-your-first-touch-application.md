---
title: 'Exemplarische Vorgehensweise: Erstellen der ersten Fingereingabeanwendung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating a touch-sensitive application [WPF]
- touchscreen applications [WPF], creating
- touch-sensitive applications [WPF], creating
- creating a touchscreen application [WPF]
ms.assetid: d69e602e-9a25-4e24-950b-e89eaa2a906b
ms.openlocfilehash: 2ebf22775ab9308bc896829be0b4e8cc147a3b4c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374153"
---
# <a name="walkthrough-creating-your-first-touch-application"></a>Exemplarische Vorgehensweise: Erstellen der ersten Fingereingabeanwendung
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ermöglicht es Anwendungen, die auf berührungen reagieren. Angenommen, Sie können mit einer Anwendung interagieren, indem Sie eine oder mehrere Finger auf einem Gerät mit Berührungseingabe, z.B. ein Touchscreen, den in dieser exemplarischen Vorgehensweise eine Anwendung, die dem Benutzer ermöglicht erstellt, zu verschieben, Ändern der Größe oder drehen Sie ein einzelnes Objekt mithilfe von Touch.  
  
## <a name="prerequisites"></a>Vorraussetzungen  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   Visual Studio.  
  
-   Ein Gerät, das Fingereingabe, z. B. ein Touchscreen, der Windows Touch unterstützt akzeptiert.  
  
 Darüber hinaus müssen Sie ein grundlegendes Verständnis der Vorgehensweise: erstellen eine Anwendung in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], insbesondere zum Abonnieren und Behandeln eines Ereignisses. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## <a name="creating-the-application"></a>Erstellen der Anwendung  
  
#### <a name="to-create-the-application"></a>So erstellen Sie die Anwendung  
  
1.  Erstellen Sie ein neues WPF-Anwendungsprojekt in Visual Basic oder Visual C# mit dem Namen `BasicManipulation`. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
2.  Ersetzen Sie den Inhalt der Datei "MainWindow.xaml" durch den folgenden XAML an.  
  
     Dieses Markup erstellt eine einfache Anwendung, das ein Rot enthält <xref:System.Windows.Shapes.Rectangle> auf eine <xref:System.Windows.Controls.Canvas>. Die <xref:System.Windows.UIElement.IsManipulationEnabled%2A> Eigenschaft der <xref:System.Windows.Shapes.Rectangle> nastaven NA hodnotu true festgelegt, sodass Bearbeitungsereignisse empfangen wird. Die Anwendung abonniert die <xref:System.Windows.UIElement.ManipulationStarting>, <xref:System.Windows.UIElement.ManipulationDelta>, und <xref:System.Windows.UIElement.ManipulationInertiaStarting> Ereignisse. Diese Ereignisse enthalten die Logik zum Verschieben der <xref:System.Windows.Shapes.Rectangle> Wenn der Benutzer es bearbeitet.  
  
     [!code-xaml[BasicManipulation#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml#ui)]  
  
3.  Ersetzen Sie bei Verwendung von Visual Basic in der ersten Zeile der Datei "MainWindow.xaml" `x:Class="BasicManipulation.MainWindow"` mit `x:Class="MainWindow"`.  
  
4.  In der `MainWindow` Klasse, fügen Sie die folgenden <xref:System.Windows.UIElement.ManipulationStarting> -Ereignishandler.  
  
     Die <xref:System.Windows.UIElement.ManipulationStarting> Ereignis tritt auf, wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erkennt, dass die Fingereingabe beginnt, ein Objekt zu bearbeiten. Der Code gibt an, dass die Position der Manipulation relativ zum sein sollte die <xref:System.Windows.Window> durch Festlegen der <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> Eigenschaft.  
  
     [!code-csharp[BasicManipulation#ManipulationStarting](~/samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationstarting)]
     [!code-vb[BasicManipulation#ManipulationStarting](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationstarting)]

5.  In der `MainWindow` Klasse, fügen Sie die folgenden <xref:System.Windows.Input.ManipulationDelta> -Ereignishandler.

     Die <xref:System.Windows.Input.ManipulationDelta> Ereignis tritt auf, wenn die Fingereingabe ändert die Position kann mehrere Male während eines Bearbeitungsvorgangs auftreten. Das Ereignis kann auch auftreten, nachdem ein Finger ausgelöst wurde. Wenn der Benutzer einen Finger über den Bildschirm, zieht z. B. die <xref:System.Windows.Input.ManipulationDelta> -Ereignis tritt mehrmals sich der Finger bewegt. Wenn ein Benutzer einen Finger vom Bildschirm, der <xref:System.Windows.Input.ManipulationDelta> behält eintretende Ereignis um Trägheit zu simulieren.

     Der Code gilt die <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> auf die <xref:System.Windows.UIElement.RenderTransform%2A> von der <xref:System.Windows.Shapes.Rectangle> Eingabe zu verschieben, wenn der Benutzer die Touch bewegt. Außerdem überprüft, ob die <xref:System.Windows.Shapes.Rectangle> außerhalb der Grenzen des ist der <xref:System.Windows.Window> Wenn das Ereignis tritt auf, während der Trägheit. Wenn dies der Fall ist, die Anwendung ruft die <xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=nameWithType> Methode, um die Bearbeitung zu beenden.

     [!code-csharp[BasicManipulation#ManipulationDelta](~/samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationdelta)]
     [!code-vb[BasicManipulation#ManipulationDelta](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationdelta)]

6.  In der `MainWindow` Klasse, fügen Sie die folgenden <xref:System.Windows.UIElement.ManipulationInertiaStarting> -Ereignishandler.

     Die <xref:System.Windows.UIElement.ManipulationInertiaStarting> Ereignis tritt auf, wenn der Benutzer alle Finger vom Bildschirm. Der Code legt die ursprüngliche Geschwindigkeit und die Verzögerung für die Bewegung, Erweiterung und Drehung des Rechtecks.

     [!code-csharp[BasicManipulation#ManipulationInertiaStarting](~/samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationinertiastarting)]
     [!code-vb[BasicManipulation#ManipulationInertiaStarting](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationinertiastarting)]

7.  Erstellen Sie das Projekt, und führen Sie es aus.

     Daraufhin sollte ein rotes Quadrat im Fenster angezeigt werden.

## <a name="testing-the-application"></a>Testen der Anwendung
 Um die Anwendung zu testen, testen Sie die folgenden Manipulationen aus. Beachten Sie, dass Sie mehr als eine der folgenden zur gleichen Zeit ausführen können.

-   Verschieben der <xref:System.Windows.Shapes.Rectangle>, legen Sie einen Finger auf die <xref:System.Windows.Shapes.Rectangle> und verschieben Sie den Finger über den Bildschirm.

-   Zum Ändern der Größe der <xref:System.Windows.Shapes.Rectangle>, legen Sie zwei Finger auf die <xref:System.Windows.Shapes.Rectangle> und bewegen Sie die Finger näher zusammen oder weiter auseinander.

-   Rotieren der <xref:System.Windows.Shapes.Rectangle>, legen Sie zwei Finger auf die <xref:System.Windows.Shapes.Rectangle> und drehen Sie einen Finger um den jeweils anderen.

 Um Trägheit zu verursachen, lösen Sie schnell die Finger vom Bildschirm, wie Sie die vorherigen Manipulationen ausführen. Die <xref:System.Windows.Shapes.Rectangle> weiterhin verschieben, ändern Sie die Größe oder drehen ein paar Sekunden, bevor er beendet wird.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.UIElement.ManipulationStarting?displayProperty=nameWithType>
- <xref:System.Windows.UIElement.ManipulationDelta?displayProperty=nameWithType>
- <xref:System.Windows.UIElement.ManipulationInertiaStarting?displayProperty=nameWithType>