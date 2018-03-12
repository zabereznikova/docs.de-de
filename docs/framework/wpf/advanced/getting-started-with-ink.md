---
title: Erste Schritte mit Freihandeingaben
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- gradient brush [WPF], animating colors of
- XAML [WPF], procedural code in lieu of
- animation [WPF], gradient brush colors
- brushes [WPF], animating colors of
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 74227ebe815e971087569ff39ac0a3479c1b0d14
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2018
---
# <a name="getting-started-with-ink"></a>Erste Schritte mit Freihandeingaben
Freihandeingaben in Ihre Anwendungen integrieren ist einfacher als je zuvor. Freihandeingaben wurden von wird eine begleitende COM und Windows Forms-Methode der Programmierung zum Erzielen einer vollständige Integration in die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Sie müssen keine separaten SDKs oder Laufzeitbibliotheken installieren.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Um die folgenden Beispiele verwenden zu können, müssen Sie zuerst Microsoft Visual Studio 2005 installieren und die [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]. Sie sollten außerdem mit dem Schreiben von Anwendungen für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vertraut sein. Weitere Informationen zu den ersten Schritten mit der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], finden Sie unter [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## <a name="quick-start"></a>Schnellstart  
 Dieser Abschnitt hilft Ihnen das Schreiben einer einfachen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung, die Freihandeingaben erfasst.  
  
 Wenn Sie dies nicht bereits getan haben, installieren Sie Microsoft Visual Studio 2005 und den [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)]. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen in der Regel müssen kompiliert werden, bevor Sie sie anzeigen können, selbst wenn sie vollständig aus bestehen aus [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Allerdings die [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)] enthält Anwendung XamlPad, entwickelt, um den Prozess der Implementierung zu beschleunigen eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-basierte Benutzeroberfläche. Sie können diese Anwendung verwenden, anzeigen und Experimentieren mit der ersten einige Beispiele in diesem Dokument. Der Prozess der Erstellung kompiliert Anwendungen aus [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] wird weiter unten in diesem Dokument behandelt.  
  
 Um XAMLPad zu starten, klicken Sie auf die **starten** Sie im Menü **Programme**, zeigen Sie auf **Microsoft Windows SDK**, zeigen Sie auf **Tools**, und klicken Sie auf **XAMLPad**. Klicken Sie im Bereich "Wiedergabe" rendert XAMLPad den XAML-Code im Codebereich geschrieben. Sie können den XAML-Code bearbeiten und die Änderungen sofort angezeigt werden, klicken Sie im Bereich "Wiedergabe".  
  
#### <a name="got-ink"></a>Erfasst Freihandeingabe?  
 Starten Sie Ihre erste [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung, die Freihandeingaben unterstützt:  
  
1.  Open Microsoft Visual Studio 2005  
  
2.  Erstellen Sie ein neues **Windows-Anwendung (WPF)**  
  
3.  Typ `<InkCanvas/>` zwischen den `<Grid>` Tags  
  
4.  Drücken Sie **F5** um Ihre Anwendung im Debugger zu starten.  
  
5.  Schreiben Sie mit einem Stift oder die Maus **Hello World** im Fenster  
  
 Sie haben die Freihand-Entsprechung einer Anwendung "Hello World" mit nur 12 Tastatureingaben geschrieben.  
  
#### <a name="spice-up-your-application"></a>Interessanter gestalten Sie Ihre Anwendung  
 Nehmen wir einige Funktionen von der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Ersetzen Sie alles zwischen das öffnende \<Fenster > und Schließen von \</Window > RFID-Transponder durch Folgendes Markup einen Hintergrund eines Farbverlaufspinsels auf die Oberfläche des Freihand abgerufen.  
  
 [!code-xaml[DigitalInkTopics#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1)]  
[!code-xaml[DigitalInkTopics#1a](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1a)]  
  
#### <a name="using-animation"></a>Verwenden von Animationen  
 Animieren Sie für unterhaltsamer wir die Farben des Farbverlaufs. Fügen Sie die folgenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] nach dem schließenden `</InkCanvas>` Tag, aber vor der schließenden `</Page>` Tag.  
  
 [!code-xaml[DigitalInkTopics#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#2)]  
  
#### <a name="adding-some-code-behind-the-xaml"></a>Hinzufügen von Code hinter der XAML-Code  
 Während XAML sehr Entwerfen der Benutzeroberfläche erleichtert, muss jede praktische Anwendung Code hinzufügen, um Ereignisse zu behandeln. Hier ist ein einfaches Beispiel, das die Freihandeingabe Reaktion auf einen Rechtsklick aus einer Maus vergrößert ein:  
  
 Legen Sie die `MouseRightButtonUp` Ereignishandler in Ihrem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:  
  
 [!code-xaml[DigitalInkTopics#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]  
  
 Klicken Sie im Projektmappen-Explorer von Visual Studio erweitern Sie Windows1.XAML im, und öffnen Sie die Code-Behind-Datei Window1.xaml.cs oder Window1.xaml.vb bei Verwendung von Visual Basic. Fügen Sie den folgenden Ereignishandlercode hinzu:  
  
 [!code-csharp[DigitalInkTopics#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
 [!code-vb[DigitalInkTopics#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]  
  
 Führen Sie nun Ihre Anwendung ein. Einige Freihandeingaben und mit der rechten Maustaste, oder eine Entsprechung von drücken und halten Sie mit einen Tablettstift ausführen.  
  
#### <a name="using-procedural-code-instead-of-xaml"></a>Unter Verwendung prozeduralen Codes anstelle von XAML  
 Sie können Zugriff auf alle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Funktionen von prozeduralem Code. Hier ist eine "Hello Freihand-World"-Anwendung für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet, die keine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] überhaupt. Fügen Sie den folgenden Code in eine leere-Konsolenanwendung in Visual Studio aus. Fügen Sie Verweise auf die Assemblys PresentationCore, PresentationFramework und WindowsBase hinzu, und erstellen Sie die Anwendung durch Drücken von **F5**:  
  
 [!code-csharp[InkCanvasConsoleApp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
 [!code-vb[InkCanvasConsoleApp#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 [Freihandeingaben](../../../../docs/framework/wpf/advanced/digital-ink.md)  
 [Erfassen von Freihandeingaben](../../../../docs/framework/wpf/advanced/collecting-ink.md)  
 [Schrifterkennung](../../../../docs/framework/wpf/advanced/handwriting-recognition.md)  
 [Speichern von Eingabehilfen](../../../../docs/framework/wpf/advanced/storing-ink.md)
