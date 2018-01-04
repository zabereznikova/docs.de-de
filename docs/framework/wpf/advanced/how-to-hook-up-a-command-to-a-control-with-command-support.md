---
title: "Gewusst wie: Einbinden eines Befehls in ein Steuerelement mit Befehlsunterstützung"
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
- Control class [WPF], attaching a RoutedCommand
- classes [WPF], Control [WPF], attaching a RoutedCommand
- RoutedCommand class [WPF], attaching to a Control
- classes [WPF], RoutedCommand [WPF], attaching to a Control
ms.assetid: 8d8592ae-0c91-469e-a1cd-d179c4544548
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8b190868b8718442966a22d7be14d976ec47f53b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-hook-up-a-command-to-a-control-with-command-support"></a>Gewusst wie: Einbinden eines Befehls in ein Steuerelement mit Befehlsunterstützung
Im folgende Beispiel wird gezeigt, wie zum Einbinden einer <xref:System.Windows.Input.RoutedCommand> auf eine <xref:System.Windows.Controls.Control> die verfügt über integrierte Unterstützung für den Befehl.  Ein vollständiges Beispiel, das Befehle mit mehrere Quellen verknüpft, finden Sie im Beispiel unter [Create a Custom RoutedCommand Sample (Erstellen eines benutzerdefinierten „RoutedCommand“-Beispiels)](http://go.microsoft.com/fwlink/?LinkID=159980).  
  
## <a name="example"></a>Beispiel  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt eine Bibliothek mit allgemeinen Befehlen bereit, die Anwendungsprogrammierer häufig nutzen.  Die Klassen, die Befehlsbibliothek sind: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, und <xref:System.Windows.Documents.EditingCommands>.  
  
 Die statische <xref:System.Windows.Input.RoutedCommand> Geben Sie Objekte, die diese Klassen bilden keine Logik.  Die Logik für den Befehl bezieht sich auf den Befehl mit einem <xref:System.Windows.Input.CommandBinding>.  Einige Steuerelemente verfügen über integrierte CommandBindings für einige Befehle.  Dieser Mechanismus ermöglicht es, dass die Semantik eines Befehls unverändert bleibt, während sich die eigentliche Implementierung ändern kann.  Ein <xref:System.Windows.Controls.TextBox>, z. B. behandelt die <xref:System.Windows.Input.ApplicationCommands.Paste%2A> Befehl anders als ein Steuerelement Bilder unterstützen soll, aber das Grundkonzept von Bedeutung Einfügens unverändert bleibt.  Die Befehlslogik kann nicht vom Befehl bereitgestellt werden, muss jedoch vom Steuerelement oder der Anwendung bereitgestellt werden.  
  
 Viele Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verfügen über eine integrierte Unterstützung für einige Befehle der Befehlsbibliothek.  <xref:System.Windows.Controls.TextBox>, z. B. unterstützt viele der Anwendung Bearbeitungsbefehle wie z. B. <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A>, und <xref:System.Windows.Input.ApplicationCommands.Undo%2A>.  Der Anwendungsentwickler muss gar nichts Besonderes tun, um diese Befehle zum Arbeiten mit diesen Steuerelementen zu erhalten.  Wenn die <xref:System.Windows.Controls.TextBox> ist das Befehlsziel, wenn der Befehl ausgeführt wird, wird er behandeln, den Befehl mithilfe der <xref:System.Windows.Input.CommandBinding> , die in das Steuerelement erstellt wird.  
  
 Im folgenden wird gezeigt, wie eine <xref:System.Windows.Controls.MenuItem> als Befehlsquelle für die <xref:System.Windows.Input.ApplicationCommands.Paste%2A> Befehl, in dem eine <xref:System.Windows.Controls.TextBox> ist das Ziel des Befehls.  Die gesamte Logik, die definiert, wie die <xref:System.Windows.Controls.TextBox> führt einfügen integriert die <xref:System.Windows.Controls.TextBox> Steuerelement.  
  
 Ein <xref:System.Windows.Controls.MenuItem> wird erstellt, und es ist <xref:System.Windows.Controls.MenuItem.Command%2A> -Eigenschaftensatz auf die <xref:System.Windows.Input.ApplicationCommands.Paste%2A> Befehl.  Die <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> nicht ausdrücklich festgelegt ist die <xref:System.Windows.Controls.TextBox> Objekt.  Wenn die <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> nicht festgelegt ist, das Ziel für der Befehl das Element ist, über den Tastaturfokus verfügt.  Wenn das Element, das über den Tastaturfokus verfügt, nicht unterstützt die <xref:System.Windows.Input.ApplicationCommands.Paste%2A> Befehls oder einer momentan nicht den Paste-Befehl (z. B. ist die Zwischenablage leer) ausführen und dann die <xref:System.Windows.Controls.MenuItem> abgeblendet.  
  
 [!code-xaml[MenuItemCommandTask_XAML#MenuItemCommanding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandTask_XAML/CS/Window1.xaml#menuitemcommanding)]  
  
 [!code-csharp[MenuItemCommandTask#MenuItemCommandingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandTask/CSharp/Window1.xaml.cs#menuitemcommandingcodebehind)]
 [!code-vb[MenuItemCommandTask#MenuItemCommandingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandTask/VisualBasic/Window1.xaml.vb#menuitemcommandingcodebehind)]  
  
## <a name="see-also"></a>Siehe auch  
 [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md)  
 [Einbinden eines Befehls in ein Steuerelement ohne Befehlsunterstützung](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-no-command-support.md)
