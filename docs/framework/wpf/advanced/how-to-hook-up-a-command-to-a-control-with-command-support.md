---
title: 'Vorgehensweise: Einbinden eines Befehls in ein Steuerelement mit Befehlsunterstützung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Control class [WPF], attaching a RoutedCommand
- classes [WPF], Control [WPF], attaching a RoutedCommand
- RoutedCommand class [WPF], attaching to a Control
- classes [WPF], RoutedCommand [WPF], attaching to a Control
ms.assetid: 8d8592ae-0c91-469e-a1cd-d179c4544548
ms.openlocfilehash: 981fecf33b60c76ecab760185db7dab4bbb254d7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757247"
---
# <a name="how-to-hook-up-a-command-to-a-control-with-command-support"></a>Vorgehensweise: Einbinden eines Befehls in ein Steuerelement mit Befehlsunterstützung
Im folgenden Beispiel wird veranschaulicht, wie Sie ein <xref:System.Windows.Input.RoutedCommand>-Objekt an ein <xref:System.Windows.Controls.Control>-Objekt binden, in das Unterstützung für den Befehl integriert ist.  Ein vollständiges Beispiel, das Befehle mit mehrere Quellen verknüpft, finden Sie im Beispiel unter [Create a Custom RoutedCommand Sample (Erstellen eines benutzerdefinierten „RoutedCommand“-Beispiels)](https://github.com/Microsoft/WPF-Samples/tree/master/Input%20and%20Commands/CustomRoutedCommand).  
  
## <a name="example"></a>Beispiel  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt eine Bibliothek mit allgemeinen Befehlen bereit, die Anwendungsprogrammierer häufig nutzen.  Die Befehlsbibliothek besteht aus den folgenden Klassen: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands> und <xref:System.Windows.Documents.EditingCommands>.  
  
 Die statischen <xref:System.Windows.Input.RoutedCommand>-Objekte, aus denen diese Klassen bestehen, bieten keine Befehlslogik.  Die Logik für den Befehl wird mit dem Befehl mit einem <xref:System.Windows.Input.CommandBinding> in Verbindung gebracht.  Einige Steuerelemente verfügen über integrierte CommandBindings für einige Befehle.  Dieser Mechanismus ermöglicht es, dass die Semantik eines Befehls unverändert bleibt, während sich die eigentliche Implementierung ändern kann.  Eine <xref:System.Windows.Controls.TextBox> verarbeitet z.B. den <xref:System.Windows.Input.ApplicationCommands.Paste%2A>-Befehl anders als ein Steuerelement, das entworfen wurde, um Images zu unterstützen. Die grundlegende Idee, was es bedeutet, etwas einzufügen, ist jedoch die gleiche.  Die Befehlslogik kann nicht vom Befehl bereitgestellt werden, muss jedoch vom Steuerelement oder der Anwendung bereitgestellt werden.  
  
 Viele Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verfügen über eine integrierte Unterstützung für einige Befehle der Befehlsbibliothek.  <xref:System.Windows.Controls.TextBox> unterstützt z.B. viele Befehle zum Bearbeiten von Anwendungen (z.B. <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A> und <xref:System.Windows.Input.ApplicationCommands.Undo%2A>).  Der Anwendungsentwickler muss gar nichts Besonderes tun, um diese Befehle zum Arbeiten mit diesen Steuerelementen zu erhalten.  Wenn das <xref:System.Windows.Controls.TextBox>-Objekt bei Ausführung des Befehls das Ziel ist, wird der Befehl mit dem <xref:System.Windows.Input.CommandBinding>-Objekt behandelt, das in das Steuerelement integriert ist.  
  
 Im folgenden Codeausschnitt wird veranschaulicht, wie Sie ein <xref:System.Windows.Controls.MenuItem>-Objekt als Befehlsquelle für den <xref:System.Windows.Input.ApplicationCommands.Paste%2A>-Befehl verwenden können, wobei <xref:System.Windows.Controls.TextBox> das Ziel des Befehls ist.  Die gesamte Logik, die definiert, wie <xref:System.Windows.Controls.TextBox> den Einfügungsvorgang durchführt, ist im Steuerelement <xref:System.Windows.Controls.TextBox> integriert.  
  
 Eine <xref:System.Windows.Controls.MenuItem>-Klasse wird generiert, und deren <xref:System.Windows.Controls.MenuItem.Command%2A>-Eigenschaft wird auf den Befehl<xref:System.Windows.Input.ApplicationCommands.Paste%2A> festgelegt.  Die <xref:System.Windows.Controls.MenuItem.CommandTarget%2A>-Eigenschaft wird nicht explizit auf das Objekt <xref:System.Windows.Controls.TextBox> festgelegt.  Wenn <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> nicht festgelegt wird, ist das Ziel für den Befehl das Element, das den Tastaturfokus besitzt.  Wenn das Element, das den Tastaturfokus besitzt, den Befehl <xref:System.Windows.Input.ApplicationCommands.Paste%2A> nicht unterstützt oder derzeit den Einfügungsbefehl nicht ausführen kann (die Zwischenablage ist beispielsweise leer), ist das <xref:System.Windows.Controls.MenuItem> ausgegraut.  
  
 [!code-xaml[MenuItemCommandTask_XAML#MenuItemCommanding](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandTask_XAML/CS/Window1.xaml#menuitemcommanding)]  
  
 [!code-csharp[MenuItemCommandTask#MenuItemCommandingCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandTask/CSharp/Window1.xaml.cs#menuitemcommandingcodebehind)]
 [!code-vb[MenuItemCommandTask#MenuItemCommandingCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandTask/VisualBasic/Window1.xaml.vb#menuitemcommandingcodebehind)]  
  
## <a name="see-also"></a>Siehe auch

- [Befehlsübersicht](commanding-overview.md)
- [Einbinden eines Befehls in ein Steuerelement ohne Befehlsunterstützung](how-to-hook-up-a-command-to-a-control-with-no-command-support.md)
