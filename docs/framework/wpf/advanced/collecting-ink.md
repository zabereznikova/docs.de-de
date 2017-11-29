---
title: Erfassen von Freihandeingaben
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
- ink [WPF], collecting
- InkCanvas element [WPF]
- properties [WPF], DrawingAttributes
- collecting digital ink [WPF]
- digital ink [WPF], collecting
- properties [WPF], DefaultDrawingAttributes
- DefaultDrawingAttributes property [WPF]
ms.assetid: 66a3129d-9577-43eb-acbd-56c147282016
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 81ed657de0c0e4d07fcb10b099cbf5e5c80a71fc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="collecting-ink"></a>Erfassen von Freihandeingaben
Als einen ihrer zentralen Funktionsbestandteile erfasst die [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md)-Plattform Freihandeingaben. Dieses Thema beschreibt die Methoden zur Erfassung von Freihandeingaben in [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Für die folgenden Beispiele installieren Sie zunächst [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] und anschließend [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]. Sie sollten außerdem mit dem Schreiben von Anwendungen für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vertraut sein. Weitere Informationen zu den ersten Schritten mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], finden Sie unter [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## <a name="using-the-inkcanvas-element"></a>Verwenden des InkCanvas-Elements  
 Die <xref:System.Windows.Controls.InkCanvas> -Element bietet die einfachste Möglichkeit zum Erfassen von Freihandeingaben in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Die <xref:System.Windows.Controls.InkCanvas> -Element ähnelt dem [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/microsoft.ink.inkoverlay\(v=vs.90\).aspx) -Objekt aus der [!INCLUDE[TLA2#tla_tpclssdk](../../../../includes/tla2sharptla-tpclssdk-md.md)] und früheren Versionen.  
  
 Verwenden einer <xref:System.Windows.Controls.InkCanvas> Element empfangen und Freihandeingaben angezeigt. Freihandeingaben erfolgen im Allgemeinen mithilfe eines Tablettstifts, der über ein Digitalisierungsgerät Freihandstriche erzeugt. Anstelle eines Tablettstifts kann auch eine Maus verwendet werden. Die erstellten Striche werden als dargestellt <xref:System.Windows.Ink.Stroke> Objekte, und sie Benutzereingaben bearbeitet werden können sowohl programmgesteuert als auch durch Benutzer. Die <xref:System.Windows.Controls.InkCanvas> ermöglicht es Benutzern, auszuwählen, ändern oder Löschen eines vorhandenen <xref:System.Windows.Ink.Stroke>.  
  
 Mit XAML gestaltet sich das Erfassen von Freihandeingaben genauso einfach wie das Hinzufügen eines `InkCanvas`-Elements zur Struktur. Im folgenden Beispiel wird ein <xref:System.Windows.Controls.InkCanvas> an einen Standard [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in erstellten Projekt [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)].  
  
 [!code-xaml[DigitalInkTopics#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]  
  
 Das `InkCanvas`-Element kann auch untergeordnete Elemente enthalten, wodurch Sie Funktionen zur Freihandanmerkung nahezu jeder Art von XAML-Element hinzufügen können. Z. B. um ein Textelement Freihand-Funktionen hinzuzufügen, schlicht es ein untergeordnetes Element von einem <xref:System.Windows.Controls.InkCanvas>.  
  
 [!code-xaml[DigitalInkTopics#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]  
  
 Ebenso einfach ist es, Unterstützung zum Markieren eines Bilds per Freihandeingabe hinzuzufügen.  
  
 [!code-xaml[DigitalInkTopics#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]  
  
### <a name="inkcollection-modes"></a>InkCollection-Modi  
 Die <xref:System.Windows.Controls.InkCanvas> bietet Unterstützung für verschiedene Modi durch Eingabe der <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> Eigenschaft.  
  
### <a name="manipulating-ink"></a>Bearbeiten von Freihandeingaben  
 Die <xref:System.Windows.Controls.InkCanvas> bietet Unterstützung für viele Bearbeitungsvorgänge Freihand. Beispielsweise <xref:System.Windows.Controls.InkCanvas> unterstützt Back-des-Stift löschen, ohne zusätzlichen Code erforderlich, um die Funktionen auf das Element hinzugefügt.  
  
#### <a name="selection"></a>Auswahl  
 Auswahlmodus Einstellung ist so einfach wie das Festlegen der <xref:System.Windows.Controls.InkCanvasEditingMode> Eigenschaft **wählen**. Im folgenden Code wird den Bearbeitungsmodus basierend auf dem Wert von einem <xref:System.Windows.Forms.CheckBox>:  
  
 [!code-csharp[DigitalInkTopics#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
 [!code-vb[DigitalInkTopics#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]  
  
#### <a name="drawingattributes"></a>DrawingAttributes  
 Verwenden der <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> Eigenschaft, um die Darstellung von Strichen geändert. Für die Instanz, die <xref:System.Windows.Ink.DrawingAttributes.Color%2A> Mitglied <xref:System.Windows.Ink.DrawingAttributes> legt die Farbe des gerenderten <xref:System.Windows.Ink.Stroke>. Im folgenden Beispiel wird die Farbe der ausgewählten Striche in Rot geändert.  
  
 [!code-csharp[DigitalInkTopics#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
 [!code-vb[DigitalInkTopics#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]  
  
### <a name="defaultdrawingattributes"></a>DefaultDrawingAttributes  
 Die <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> Eigenschaft ermöglicht den Zugriff auf Eigenschaften, z. B. Höhe, Breite und Farbe der Striche zu erstellende ein <xref:System.Windows.Controls.InkCanvas>. Sobald Sie ändern die <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, alle zukünftigen Striche eingegeben werden, in der <xref:System.Windows.Controls.InkCanvas> werden mit neuen Eigenschaftenwerten gerendert.  
  
 Zusätzlich zum Ändern der <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> in der CodeBehind-Datei können Sie XAML-Syntax zum Angeben von <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> Eigenschaften. Der folgende XAML-Code veranschaulicht das Festlegen der <xref:System.Windows.Ink.DrawingAttributes.Color%2A> Eigenschaft. Zum Verwenden dieses Codes erstellen Sie in Visual Studio 2005 ein neues [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Projekt mit dem Namen „HelloInkCanvas“. Ersetzen Sie den Code in der Window1.xaml-Datei durch den folgenden Code:  
  
 [!code-xaml[HelloInkCanvas#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]  
  
 Fügen Sie anschließend der CodeBehind-Datei die folgenden Ereignishandler für Schaltflächen innerhalb der Window1-Klasse hinzu.  
  
 [!code-csharp[HelloInkCanvas#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]  
  
 Nachdem Sie diesen Code kopiert haben, drücken Sie in Microsoft Visual Studio 2005 **F5**, um das Programm im Debugger auszuführen.  
  
 Beachten Sie, dass der <xref:System.Windows.Controls.StackPanel> platziert die Schaltflächen auf der Basis von der <xref:System.Windows.Controls.InkCanvas>. Wenn Sie, Freihandeingaben über die Schaltflächen oben versuchen die <xref:System.Windows.Controls.InkCanvas> erfasst und rendert Sie hinter der Schaltflächen. Dies ist, da die Schaltflächen der gleichgeordneten Elemente sind die <xref:System.Windows.Controls.InkCanvas> im Gegensatz zu untergeordneten Elementen. Außerdem sind die Schaltflächen in der Z-Reihenfolge weiter oben, weshalb die Freihandeingaben dahinter gerendert werden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Ink.DrawingAttributes>  
 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>  
 <xref:System.Windows.Ink>
