---
title: 'Vorgehensweise: Einbinden eines Befehls in ein Steuerelement ohne Befehlsunterstützung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Control class [WPF], attaching a RoutedCommand
- classes [WPF], Control [WPF], attaching a RoutedCommand
- RoutedCommand class [WPF], attaching to a Control
- classes [WPF], RoutedCommand [WPF], attaching to a Control
ms.assetid: dad08f64-700b-46fb-ad3f-fbfee95f0dfe
ms.openlocfilehash: 66b371f4d67c1102ddf341dd4b70aac66aa41605
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352671"
---
# <a name="how-to-hook-up-a-command-to-a-control-with-no-command-support"></a>Vorgehensweise: Einbinden eines Befehls in ein Steuerelement ohne Befehlsunterstützung
Im folgenden Beispiel wird veranschaulicht, wie Sie ein <xref:System.Windows.Input.RoutedCommand>-Objekt an ein <xref:System.Windows.Controls.Control>-Objekt binden, in das keine Unterstützung für den Befehl integriert ist.  Ein vollständiges Beispiel, das Befehle mit mehrere Quellen verknüpft, finden Sie im Beispiel unter [Create a Custom RoutedCommand Sample (Erstellen eines benutzerdefinierten „RoutedCommand“-Beispiels)](https://github.com/Microsoft/WPF-Samples/tree/master/Input%20and%20Commands/CustomRoutedCommand).  
  
## <a name="example"></a>Beispiel  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt eine Bibliothek mit allgemeinen Befehlen bereit, die Anwendungsprogrammierer häufig nutzen.  Die Befehlsbibliothek besteht aus den folgenden Klassen: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands> und <xref:System.Windows.Documents.EditingCommands>.  
  
 Die statischen <xref:System.Windows.Input.RoutedCommand>-Objekte, aus denen diese Klassen bestehen, bieten keine Befehlslogik.  Die Logik für den Befehl wird mit dem Befehl mit einem <xref:System.Windows.Input.CommandBinding> in Verbindung gebracht.  Viele Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verfügen über eine integrierte Unterstützung für einige Befehle der Befehlsbibliothek.  <xref:System.Windows.Controls.TextBox> unterstützt z.B. viele Befehle zum Bearbeiten von Anwendungen (z.B. <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A> und <xref:System.Windows.Input.ApplicationCommands.Undo%2A>).  Der Anwendungsentwickler muss gar nichts Besonderes tun, um diese Befehle zum Arbeiten mit diesen Steuerelementen zu erhalten.  Wenn das <xref:System.Windows.Controls.TextBox>-Objekt bei Ausführung des Befehls das Ziel ist, wird der Befehl mit dem <xref:System.Windows.Input.CommandBinding>-Objekt behandelt, das in das Steuerelement integriert ist.  
  
 Im folgenden Codeausschnitt wird veranschaulicht, wie Sie ein <xref:System.Windows.Controls.Button>-Objekt als Befehlsquelle für den <xref:System.Windows.Input.ApplicationCommands.Open%2A>-Befehl verwenden können.  Es wird ein <xref:System.Windows.Input.CommandBinding>-Objekt erstellt, das die angegebenen <xref:System.Windows.Input.CanExecuteRoutedEventHandler>- und <xref:System.Windows.Input.CanExecuteRoutedEventHandler>-Objekte mit dem <xref:System.Windows.Input.RoutedCommand>-Objekt verknüpft.  
  
 Zunächst wird die Befehlsquelle erstellt.  Ein <xref:System.Windows.Controls.Button>-Objekt wird als Befehlsquelle verwendet.  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandSource](~/samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandsource)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerButtonCommandSource](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbuttoncommandsource)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerButtonCommandSource](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbuttoncommandsource)]  
  
 Als Nächstes werden die <xref:System.Windows.Input.ExecutedRoutedEventHandler>- und <xref:System.Windows.Input.CanExecuteRoutedEventHandler>-Objekte erstellt.  Der <xref:System.Windows.Input.ExecutedRoutedEventHandler> öffnet einfach ein <xref:System.Windows.MessageBox>-Objekt, um anzugeben, dass der Befehl ausgeführt wurde.  Der <xref:System.Windows.Input.CanExecuteRoutedEventHandler> legt die <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A>-Eigenschaft auf `true` fest.  Normalerweise führt der CanExecute-Handler stabilere Prüfungen durch, um festzustellen, ob der Befehl mit dem aktuellen Befehlsziel erfolgreich ausgeführt werden kann.  
  
 [!code-csharp[commandWithHandler#CommandHandlerBothHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerbothhandlers)]
 [!code-vb[commandWithHandler#CommandHandlerBothHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerbothhandlers)]  
  
 Zum Schluss wird ein <xref:System.Windows.Input.CommandBinding>-Objekt am <xref:System.Windows.Window>-Stammobjekt der Anwendung erstellt, das den Routingereignishandler mit dem <xref:System.Windows.Input.ApplicationCommands.Open%2A>-Befehl verknüpft.  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
## <a name="see-also"></a>Siehe auch
- [Befehlsübersicht](commanding-overview.md)
- [Einbinden eines Befehls in ein Steuerelement mit Befehlsunterstützung](how-to-hook-up-a-command-to-a-control-with-command-support.md)
