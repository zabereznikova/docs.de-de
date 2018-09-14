---
title: Erfassen von Freihandeingaben in WPF-apps
ms.date: 08/15/2018
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
ms.openlocfilehash: 25f9c0141a97d8e52e0883b14fd3e1f4574a05ea
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45527723"
---
# <a name="collect-ink"></a>Erfassen von Freihandeingaben

Als einen ihrer zentralen Funktionsbestandteile erfasst die [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md)-Plattform Freihandeingaben. Dieses Thema beschreibt Methoden zum Erfassen von Freihandeingaben in Windows Presentation Foundation (WPF).

## <a name="prerequisites"></a>Erforderliche Komponenten

Um die folgenden Beispiele verwenden zu können, müssen Sie zunächst Visual Studio installieren und die [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]. Sie sollten auch Gewusst wie: Schreiben von Anwendungen für WPF kennen. Weitere Informationen zu den ersten Schritten mit WPF finden Sie unter [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).

## <a name="use-the-inkcanvas-element"></a>Verwenden des InkCanvas-Elements

Die <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> -Element stellt die einfachste Möglichkeit zum Erfassen von Freihandeingaben in WPF bereit. Verwenden einer <xref:System.Windows.Controls.InkCanvas> Element zu empfangen und Freihandeingaben anzuzeigen. Freihandeingaben erfolgen im Allgemeinen mithilfe eines Tablettstifts, der über ein Digitalisierungsgerät Freihandstriche erzeugt. Anstelle eines Tablettstifts kann auch eine Maus verwendet werden. Die erzeugten Striche werden als dargestellt <xref:System.Windows.Ink.Stroke> Objekte und, können sowohl programmgesteuert als auch durch Benutzereingaben geändert werden. Die <xref:System.Windows.Controls.InkCanvas> ermöglicht Benutzern das auswählen, ändern oder Löschen eines vorhandenen <xref:System.Windows.Ink.Stroke>.

Mit XAML, Sie können festlegen, Freihandeingaben so einfach wie das Hinzufügen einer **InkCanvas** -Elements zur Struktur. Im folgenden Beispiel wird ein <xref:System.Windows.Controls.InkCanvas> auf ein Standard-WPF-Projekt in Visual Studio erstellt wurden:

[!code-xaml[DigitalInkTopics#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]

Die **InkCanvas** Element kann auch untergeordnete Elemente enthalten, wodurch Anmerkungsfunktionen von Freihandeingaben auf nahezu jede Art von XAML-Element hinzufügen. Zum Beispiel um ein Textelement Freihandfunktionen hinzufügen, indem Sie es einfach ein untergeordnetes Element des ein <xref:System.Windows.Controls.InkCanvas>:

[!code-xaml[DigitalInkTopics#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]

Hinzufügen von Unterstützung zum Markieren eines Bilds per Freihandeingabe ist ebenso einfach:

[!code-xaml[DigitalInkTopics#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]

### <a name="inkcollection-modes"></a>InkCollection-Modi

Die <xref:System.Windows.Controls.InkCanvas> bietet Unterstützung für verschiedene Modi durch Eingabe der <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> Eigenschaft.

### <a name="manipulate-ink"></a>Bearbeitung von Freihandeingaben

Die <xref:System.Windows.Controls.InkCanvas> bietet Unterstützung für viele Freihandbearbeitungsvorgänge. Z. B. <xref:System.Windows.Controls.InkCanvas> unterstützt das Back-von-Stift löschen und kein zusätzlicher Code ist erforderlich, um die Funktionalität auf das Element hinzufügen.

#### <a name="selection"></a>Auswahl

Auswahlmodus ist so einfach wie das Festlegen der <xref:System.Windows.Controls.InkCanvasEditingMode> Eigenschaft **wählen**.

Im folgenden Code wird den Bearbeitungsmodus basierend auf den Wert des einem <xref:System.Windows.Forms.CheckBox>:

[!code-csharp[DigitalInkTopics#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
[!code-vb[DigitalInkTopics#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]

#### <a name="drawingattributes"></a>DrawingAttributes

Verwenden der <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> Eigenschaft, um die Darstellung von Freihandstrichen zu ändern. Z. B. die <xref:System.Windows.Ink.DrawingAttributes.Color%2A> Mitglied <xref:System.Windows.Ink.DrawingAttributes> legt die Farbe des gerenderten <xref:System.Windows.Ink.Stroke>.

Im folgende Beispiel ändert die Farbe der ausgewählten Striche in Rot angezeigt:

[!code-csharp[DigitalInkTopics#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
[!code-vb[DigitalInkTopics#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]

### <a name="defaultdrawingattributes"></a>DefaultDrawingAttributes

Die <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> Eigenschaft bietet Zugriff auf Eigenschaften, z. B. Höhe, Breite und Farbe der Striche zu erstellende ein <xref:System.Windows.Controls.InkCanvas>. Sobald Sie ändern die <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, alle zukünftigen Striche eingegeben haben, in der <xref:System.Windows.Controls.InkCanvas> werden mit den neuen Eigenschaftswerten gerendert.

Zusätzlich zum Ändern der <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> in der CodeBehind-Datei können Sie XAML-Syntax verwenden, für die Angabe <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> Eigenschaften.

Im nächste Beispiel veranschaulicht das Festlegen der <xref:System.Windows.Ink.DrawingAttributes.Color%2A> Eigenschaft. Um diesen Code zu verwenden, erstellen Sie ein neues WPF-Projekt, das Namen "HelloInkCanvas" in Visual Studio. Ersetzen Sie den Code in die *"MainWindow.xaml"* -Datei mit den folgenden Code:

[!code-xaml[HelloInkCanvas#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]

Fügen Sie die folgenden Ereignishandler der Schaltfläche auf der CodeBehind-Datei, in der MainWindow-Klasse:

[!code-csharp[HelloInkCanvas#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]

Drücken Sie nach dem Kopieren dieser Code **F5** in Visual Studio, um das Programm im Debugger auszuführen.

Beachten Sie, dass die <xref:System.Windows.Controls.StackPanel> platziert die Schaltflächen oben auf der <xref:System.Windows.Controls.InkCanvas>. Wenn Sie, Freihandeingaben oberhalb der Schaltflächen versuchen, die <xref:System.Windows.Controls.InkCanvas> erfasst und rendert Freihandeingaben hinter den Schaltflächen. Dies ist, da die Schaltflächen gleichgeordnete Elemente des sind die <xref:System.Windows.Controls.InkCanvas> und nicht untergeordnet. Außerdem sind die Schaltflächen in der Z-Reihenfolge weiter oben, weshalb die Freihandeingaben dahinter gerendert werden.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Ink.DrawingAttributes>
- <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>
- <xref:System.Windows.Ink>