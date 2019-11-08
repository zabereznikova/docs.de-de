---
title: Sammeln von frei Hand Eingaben in WPF-apps
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
ms.openlocfilehash: 8109e0d6a746d6ca23c25643c510014c1a1e656c
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740870"
---
# <a name="collect-ink"></a>Frei Hand Eingaben erfassen

Als einen ihrer zentralen Funktionsbestandteile erfasst die [Windows Presentation Foundation](../index.md)-Plattform Freihandeingaben. In diesem Thema werden die Methoden für die Sammlung von frei Hand Eingaben in Windows Presentation Foundation (WPF) erläutert.

## <a name="prerequisites"></a>Erforderliche Voraussetzungen

Um die folgenden Beispiele verwenden zu können, müssen Sie zuerst Visual Studio und den Windows SDK installieren. Außerdem sollten Sie wissen, wie Anwendungen für das WPF geschrieben werden. Weitere Informationen zu den ersten Schritten mit WPF finden Sie unter Exemplarische Vorgehensweise [: meine erste WPF-Desktop Anwendung](../getting-started/walkthrough-my-first-wpf-desktop-application.md).

## <a name="use-the-inkcanvas-element"></a>Verwenden des InkCanvas-Elements

Das <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName>-Element bietet die einfachste Möglichkeit, frei Hand Eingaben in WPF zu erfassen. Verwenden Sie ein <xref:System.Windows.Controls.InkCanvas>-Element, um frei Hand Eingaben zu empfangen und anzuzeigen. Freihandeingaben erfolgen im Allgemeinen mithilfe eines Tablettstifts, der über ein Digitalisierungsgerät Freihandstriche erzeugt. Anstelle eines Tablettstifts kann auch eine Maus verwendet werden. Die erstellten Striche werden als <xref:System.Windows.Ink.Stroke> Objekte dargestellt und können sowohl Programm gesteuert als auch durch Benutzereingaben bearbeitet werden. Der <xref:System.Windows.Controls.InkCanvas> ermöglicht Benutzern das auswählen, ändern oder Löschen eines vorhandenen <xref:System.Windows.Ink.Stroke>.

Mithilfe von XAML können Sie die frei Hand Auflistung so einfach einrichten, wie Sie der Struktur ein **InkCanvas** -Element hinzufügen. Im folgenden Beispiel wird einem WPF-Standard Projekt, das in Visual Studio erstellt wurde, ein <xref:System.Windows.Controls.InkCanvas> hinzugefügt:

[!code-xaml[DigitalInkTopics#6](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]

Das **InkCanvas** -Element kann auch untergeordnete Elemente enthalten, sodass Sie nahezu allen Typen von XAML-Elementen frei Hand Anmerkung-Funktionen hinzufügen können. Wenn Sie z. b. einem Textelement Bindungsfunktionen hinzufügen möchten, machen Sie es einfach als untergeordnetes Element eines <xref:System.Windows.Controls.InkCanvas>:

[!code-xaml[DigitalInkTopics#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]

Das Hinzufügen von Unterstützung für das Markieren eines Bilds mit frei Hand Eingaben ist ebenso einfach:

[!code-xaml[DigitalInkTopics#7](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]

### <a name="inkcollection-modes"></a>InkCollection-Modi

Der <xref:System.Windows.Controls.InkCanvas> bietet Unterstützung für verschiedene Eingabemodi über seine <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>-Eigenschaft.

### <a name="manipulate-ink"></a>Freihand bearbeiten

Der <xref:System.Windows.Controls.InkCanvas> bietet Unterstützung für viele Handschrift Bearbeitungsvorgänge. <xref:System.Windows.Controls.InkCanvas> unterstützt z. b. das Löschen von abblicken, und es ist kein zusätzlicher Code erforderlich, um dem-Element die Funktionalität hinzuzufügen.

#### <a name="selection"></a>Auswahl

Das Festlegen des Auswahlmodus ist so einfach wie das Festlegen der <xref:System.Windows.Controls.InkCanvasEditingMode>-Eigenschaft auf **Select**.

Mit dem folgenden Code wird der Bearbeitungsmodus basierend auf dem Wert eines <xref:System.Windows.Forms.CheckBox>festgelegt:

[!code-csharp[DigitalInkTopics#8](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
[!code-vb[DigitalInkTopics#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]

#### <a name="drawingattributes"></a>DrawingAttributes

Verwenden Sie die <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A>-Eigenschaft, um die Darstellung von frei Hand Strichen zu ändern. Beispielsweise legt der <xref:System.Windows.Ink.DrawingAttributes.Color%2A> Member von <xref:System.Windows.Ink.DrawingAttributes> die Farbe der gerenderten <xref:System.Windows.Ink.Stroke>fest.

Im folgenden Beispiel wird die Farbe der ausgewählten Striche in rot geändert:

[!code-csharp[DigitalInkTopics#9](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
[!code-vb[DigitalInkTopics#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]

### <a name="defaultdrawingattributes"></a>DefaultDrawingAttributes

Die <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>-Eigenschaft ermöglicht den Zugriff auf Eigenschaften, z. b. Höhe, Breite und Farbe der Striche, die in einem <xref:System.Windows.Controls.InkCanvas>erstellt werden sollen. Nachdem Sie die <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>geändert haben, werden alle zukünftigen Eingaben, die in die <xref:System.Windows.Controls.InkCanvas> eingegeben werden, mit den neuen Eigenschafts Werten gerendert.

Zusätzlich zum Ändern der <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> in der Code Behind-Datei können Sie die XAML-Syntax zum Angeben von <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> Eigenschaften verwenden.

Im nächsten Beispiel wird veranschaulicht, wie die <xref:System.Windows.Ink.DrawingAttributes.Color%2A>-Eigenschaft festgelegt wird. Um diesen Code zu verwenden, erstellen Sie in Visual Studio ein neues WPF-Projekt mit dem Namen "HelloInkCanvas". Ersetzen Sie den Code in der Datei " *MainWindow. XAML* " durch den folgenden Code:

[!code-xaml[HelloInkCanvas#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]

Fügen Sie als nächstes die folgenden Ereignishandler für die Schaltfläche der Code-Behind-Datei innerhalb der MainWindow-Klasse hinzu:

[!code-csharp[HelloInkCanvas#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]

Nachdem Sie diesen Code kopiert haben, drücken Sie in Visual Studio **F5** , um das Programm im Debugger auszuführen.

Beachten Sie, wie die <xref:System.Windows.Controls.StackPanel> die Schaltflächen oben auf der <xref:System.Windows.Controls.InkCanvas>platziert. Wenn Sie versuchen, über den oberen Rand der Schaltflächen zu übergeben, sammelt und rendert der <xref:System.Windows.Controls.InkCanvas> die frei Hand Eingaben hinter den Schaltflächen. Dies liegt daran, dass die Schaltflächen gleich geordnete Elemente der <xref:System.Windows.Controls.InkCanvas> im Gegensatz zu untergeordneten Elementen sind. Außerdem sind die Schaltflächen in der Z-Reihenfolge weiter oben, weshalb die Freihandeingaben dahinter gerendert werden.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Ink.DrawingAttributes>
- <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>
- <xref:System.Windows.Ink>
