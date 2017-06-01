---
title: "Exemplarische Vorgehensweise: Erstellen der ersten Fingereingabeanwendung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Erstellen einer Touchscreenanwendung [WPF]"
  - "Erstellen einer Anwendung mit Berührungseingabe [WPF]"
  - "Touchscreenanwendungen [WPF], Erstellen"
  - "Anwendungen mit Berührungseingabe [WPF], Erstellen"
ms.assetid: d69e602e-9a25-4e24-950b-e89eaa2a906b
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Exemplarische Vorgehensweise: Erstellen der ersten Fingereingabeanwendung
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ermöglicht es Anwendungen, auf Fingereingabe zu reagieren.  Sie können z. B. mit einer Anwendung über einen oder mehrere Finger auf einem Gerät mit Berührungseingabe, z. B. einem Touchscreen, interagieren. In dieser  exemplarischen Vorgehensweise wird eine Anwendung erstellt, die es dem Benutzer ermöglicht, ein Objekt per Fingereingabe zu verschieben, seine Größe zu ändern oder es zu drehen.  
  
## Vorbereitungsmaßnahmen  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_dev10_ext](../../../../includes/vs-dev10-ext-md.md)].  
  
-   Windows 7.  
  
-   Ein Gerät, das Fingereingabe akzeptiert, z. B. ein Touchscreen mit Windows Touch\-Unterstützung.  
  
 Darüber hinaus sollten Sie über Grundkenntnisse zum Erstellen einer Anwendung in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verfügen, insbesondere zum Abonnieren und Verarbeiten eines Ereignisses.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erste Schritte mit WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## Erstellen der Anwendung  
  
#### So erstellen Sie die Anwendung  
  
1.  Erstellen Sie ein neues WPF\-Anwendungsprojekt in Visual Basic oder Visual C\# mit dem Namen `BasicManipulation`.  Weitere Informationen finden Sie unter [Gewusst wie: Erstellen eines neuen WPF\-Anwendungsprojekts](http://msdn.microsoft.com/de-de/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
2.  Ersetzen Sie den Inhalt der Datei MainWindow.xaml durch folgende XAML.  
  
     Dieses Markup erstellt eine einfache Anwendung, die auf einem <xref:System.Windows.Controls.Canvas> ein rotes <xref:System.Windows.Shapes.Rectangle> enthält.  Die <xref:System.Windows.UIElement.IsManipulationEnabled%2A>\-Eigenschaft des <xref:System.Windows.Shapes.Rectangle> wird auf true festgelegt, sodass es Manipulationsereignisse empfängt.  Die Anwendung abonniert die Ereignisse <xref:System.Windows.UIElement.ManipulationStarting>, <xref:System.Windows.UIElement.ManipulationDelta> und <xref:System.Windows.UIElement.ManipulationInertiaStarting>.  Diese Ereignisse enthalten die Logik, um das <xref:System.Windows.Shapes.Rectangle> zu verschieben, wenn der Benutzer es bearbeitet.  
  
     [!code-xml[BasicManipulation#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml#ui)]  
  
3.  Ersetzen Sie bei Verwendung von Visual Basic in der ersten Zeile von "MainWindow.xaml" den Code `x:Class="BasicManipulation.MainWindow"` durch `x:Class="MainWindow"`.  
  
4.  Fügen Sie in der `MainWindow`\-Klasse den folgenden <xref:System.Windows.UIElement.ManipulationStarting>\-Ereignishandler hinzu.  
  
     Das <xref:System.Windows.UIElement.ManipulationStarting>\-Ereignis tritt ein, wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erkennt, dass die Fingereingabe beginnt, ein Objekt zu bearbeiten.  Der Code gibt an, dass die Position der Manipulation relativ zum <xref:System.Windows.Window> sein sollte, indem er die <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A>\-Eigenschaft festlegt.  
  
     [!code-csharp[BasicManipulation#ManipulationStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationstarting)]
     [!code-vb[BasicManipulation#ManipulationStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationstarting)]  
  
5.  Fügen Sie in der `MainWindow`\-Klasse den folgenden <xref:System.Windows.Input.ManipulationDelta>\-Ereignishandler hinzu.  
  
     Das <xref:System.Windows.Input.ManipulationDelta>\-Ereignis tritt ein, wenn die Fingereingabe die Position ändert. Es kann mehrmals während einer Manipulation auftreten.  Das Ereignis kann auch eintreten, nachdem ein Finger angehoben wurde.  Wenn der Benutzer z. B. einen Finger über einen Bildschirm zieht, tritt das <xref:System.Windows.Input.ManipulationDelta>\-Ereignis mehrmals ein, wenn sich der Finger bewegt.  Wenn der Benutzer einen Finger vom Bildschirm hebt, tritt das <xref:System.Windows.Input.ManipulationDelta>\-Ereignis weiterhin ein, um Trägheit zu simulieren.  
  
     Der Code wendet die <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> auf die  <xref:System.Windows.UIElement.RenderTransform%2A> des <xref:System.Windows.Shapes.Rectangle> an, um es zu verschieben, wenn der Benutzer die Fingereingabe verschiebt.  Er überprüft auch, ob sich das <xref:System.Windows.Shapes.Rectangle> außerhalb der Grenzen des <xref:System.Windows.Window> befindet, wenn das Ereignis während der Trägheit auftritt.  In diesem Fall ruft die Anwendung die <xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=fullName>\-Methode auf, um die Manipulation zu beenden.  
  
     [!code-csharp[BasicManipulation#ManipulationDelta](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationdelta)]
     [!code-vb[BasicManipulation#ManipulationDelta](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationdelta)]  
  
6.  Fügen Sie in der `MainWindow`\-Klasse den folgenden <xref:System.Windows.UIElement.ManipulationInertiaStarting>\-Ereignishandler hinzu.  
  
     Das <xref:System.Windows.UIElement.ManipulationInertiaStarting>\-Ereignis tritt ein, wenn der Benutzer alle Finger vom Bildschirm hebt.  Der Code legt die anfängliche Geschwindigkeit und die Verzögerung für Bewegung, Erweiterung und Drehung des Rechtecks fest.  
  
     [!code-csharp[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationinertiastarting)]
     [!code-vb[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationinertiastarting)]  
  
7.  Erstellen Sie das Projekt, und führen Sie es aus.  
  
     Sie sollten sehen, dass ein rotes Quadrat im Fenster angezeigt wird.  
  
## Testen der Anwendung  
 Probieren Sie zum Testen der Anwendung die folgenden Manipulationen aus.  Beachten Sie, dass Sie mehrere der folgenden Schritte gleichzeitig ausführen können.  
  
-   Um das <xref:System.Windows.Shapes.Rectangle> zu verschieben, legen Sie einen Finger auf das <xref:System.Windows.Shapes.Rectangle>, und bewegen Sie den Finger über den Bildschirm.  
  
-   Um die Größe des <xref:System.Windows.Shapes.Rectangle> zu ändern, legen Sie zwei Finger auf das <xref:System.Windows.Shapes.Rectangle>, und bewegen Sie die Finger näher zusammen oder weiter auseinander.  
  
-   Um das <xref:System.Windows.Shapes.Rectangle> zu drehen, legen Sie zwei Finger auf das <xref:System.Windows.Shapes.Rectangle>, und drehen Sie die Finger um den jeweils anderen Finger.  
  
 Um Trägheit zu verursachen, lösen Sie die Finger schnell vom Bildschirm, während Sie die vorherigen Manipulationen ausführen.  Das <xref:System.Windows.Shapes.Rectangle> wird für einige Sekunden weiter verschoben, in der Größe verändert oder gedreht.  
  
## Siehe auch  
 <xref:System.Windows.UIElement.ManipulationStarting?displayProperty=fullName>   
 <xref:System.Windows.UIElement.ManipulationDelta?displayProperty=fullName>   
 <xref:System.Windows.UIElement.ManipulationInertiaStarting?displayProperty=fullName>