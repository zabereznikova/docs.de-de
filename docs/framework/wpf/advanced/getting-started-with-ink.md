---
title: "Erste Schritte mit Freihandeingaben | Microsoft Docs"
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
  - "Animation, Farben des Farbverlaufspinsels"
  - "Pinsel, Animieren der Farben von"
  - "Farbverlaufspinsel, Animieren der Farben von"
  - "Prozeduraler Code statt XAML"
  - "XAML, Prozeduraler Code statt"
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Erste Schritte mit Freihandeingaben
Das Integrieren digitaler Freihandeingaben in eigene Anwendungen ist leichter als je zuvor.  Freihandeingaben wurden von einer Begleiterscheinung zu COM\- und Windows Forms\-Programmiermethoden weiterentwickelt, um eine vollständige Integration im [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu erreichen.  Die Installation separater SDKs oder Laufzeitbibliotheken ist nicht notwendig.  
  
## Vorbereitungsmaßnahmen  
 Um die folgenden Beispiele verwenden zu können, müssen Sie zunächst Microsoft Visual Studio 2005 und das [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)] installieren.  Sie sollten ebenfalls wissen, wie Anwendungen für den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] geschrieben werden.  Weitere Informationen zu den ersten Schritten mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finden Sie unter [Exemplarische Vorgehensweise: Erste Schritte mit WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## Schnellstart  
 Dieser Abschnitt unterstützt Sie beim Schreiben einer einfachen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung, die Freihandeingaben erfasst.  
  
 Installieren Sie zunächst Microsoft Visual Studio 2005 und das [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)], wenn Sie dies nicht bereits getan haben.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen müssen in der Regel zunächst kompiliert werden, um sie anzeigen zu können, selbst wenn sie ausschließlich aus [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] bestehen.  Das [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)] enthält jedoch eine Anwendung, XamlPad, die zur schnelleren Implementierung einer [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-basierten Benutzeroberfläche entwickelt wurde.  Mit dieser Anwendung können Sie die ersten paar Beispiele in diesem Dokument anzeigen und mit den Beispielen experimentieren.  Der Prozess zum Erstellen kompilierter Anwendungen aus [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] wird weiter unten in diesem Dokument behandelt.  
  
 Klicken Sie zum Starten von XAMLPad auf **Start**, zeigen Sie auf **Alle Programme**, **Microsoft Windows SDK**, **Tools**, und klicken Sie auf **XAMLPad**.  Im Renderingbereich wird der im Codebereich eingegebene XAML\-Code von XAMLPad gerendert.  Sie können den XAML\-Code bearbeiten, und die Änderungen werden sofort im Renderingbereich angezeigt.  
  
#### Freihandeingabe erfasst?  
 So erstellen Sie Ihre erste [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung, die Freihandeingaben unterstützt  
  
1.  Öffnen Sie Microsoft Visual Studio 2005.  
  
2.  Erstellen Sie eine neue **Windows\-Anwendung \(WPF\)**.  
  
3.  Geben Sie `<InkCanvas/>` zwischen den `<Grid>`\-Tags ein.  
  
4.  Drücken Sie **F5**, um die Anwendung im Debugger zu starten.  
  
5.  Schreiben Sie mit einem Tablettstift oder einer Maus Hello World in das Fenster.  
  
 Sie haben gerade die Freihandeingabenentsprechung einer "Hello World"\-Anwendung mit lediglich 12 Tastaturanschlägen geschrieben\!  
  
#### Aufwerten Ihrer Anwendung  
 Nutzen Sie einige Features des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Ersetzen Sie alles zwischen dem öffnenden \<Window\>\- und dem schließenden \<\/Window\>\-Tag mit dem folgenden Markup, um einen Farbverlaufhintergrund für die Freihandoberfläche zu erhalten.  
  
 [!code-xml[DigitalInkTopics#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1)]  
[!code-xml[DigitalInkTopics#1a](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1a)]  
  
#### Verwenden von Animation  
 Animieren Sie nur zum Spaß die Farben des Farbverlaufs.  Fügen Sie das folgende [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] nach dem schließenden `</InkCanvas>`\-Tag, aber vor dem schließenden `</Page>`\-Tag hinzu.  
  
 [!code-xml[DigitalInkTopics#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#2)]  
  
#### Hinzufügen von Code zum XAML  
 Obwohl XAML das Entwerfen der Benutzeroberfläche sehr einfach macht, benötigt jede praxisnahe Anwendung zusätzlichen Code zum Behandeln von Ereignissen.  Ein kleines Beispiel zum Durchführen eines Zooms der Freihandeingabe als Reaktion auf einen Klick mit der rechten Maustaste:  
  
 Legen Sie den `MouseRightButtonUp`\-Handler im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] fest:  
  
 [!code-xml[DigitalInkTopics#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]  
  
 Erweitern Sie Windows1.xaml im Projektmappen\-Explorer von Visual Studio, und öffnen Sie die Code\-Behind\-Datei Window1.xaml.cs bzw. Window1.xaml.vb, wenn Sie Visual Basic verwenden.  Fügen Sie den folgenden Ereignishandlercode hinzu:  
  
 [!code-csharp[DigitalInkTopics#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
 [!code-vb[DigitalInkTopics#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]  
  
 Führen Sie nun die Anwendung aus.  Erstellen Sie einige Freihandeingaben, und klicken Sie dann mit der rechten Maustaste bzw. halten Sie den Tablettstift gedrückt.  
  
#### Verwenden von prozeduralem Code statt XAML  
 Mit prozeduralem Code können Sie auf alle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Features zugreifen.  Hier ist eine "Hello Ink World"\-Anwendung für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], die keinerlei [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] verwendet.  Fügen Sie den folgenden Code in Visual Studio in eine leere Konsolenanwendung ein.  Fügen Sie Verweise auf die Assemblys PresentationCore, PresentationFramework und WindowsBase hinzu, und erstellen Sie die Anwendung durch Drücken von **F5**:  
  
 [!code-csharp[InkCanvasConsoleApp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
 [!code-vb[InkCanvasConsoleApp#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]  
  
## Siehe auch  
 [Freihandeingaben](../../../../docs/framework/wpf/advanced/digital-ink.md)   
 [Erfassen von Freihandeingaben](../../../../docs/framework/wpf/advanced/collecting-ink.md)   
 [Schrifterkennung](../../../../docs/framework/wpf/advanced/handwriting-recognition.md)   
 [Speichern von Freihandeingaben](../../../../docs/framework/wpf/advanced/storing-ink.md)