---
title: Erstellen von InkCanvas in Visual Studio
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- XAML [WPF], procedural code in lieu of
- InkCanvas (WPF)
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
ms.openlocfilehash: b8087d6db04f7024b9ee48f28002bee04045a14b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737890"
---
# <a name="get-started-with-ink-in-wpf"></a>Ersten Einstieg in WPF

Windows Presentation Foundation (WPF) verfügt über eine Ink-Funktion, die das Integrieren von digitalem frei Hand Eingaben in Ihre APP erleichtert.

## <a name="prerequisites"></a>Voraussetzungen

Wenn Sie die folgenden Beispiele verwenden möchten, installieren Sie zunächst [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019). Außerdem ist es hilfreich zu wissen, wie Sie grundlegende WPF-apps schreiben können. Hilfe zu den ersten Schritten mit WPF finden Sie unter Exemplarische Vorgehensweise [: meine erste WPF-Desktop Anwendung](../getting-started/walkthrough-my-first-wpf-desktop-application.md).

## <a name="quick-start"></a>Schnellstart

Dieser Abschnitt unterstützt Sie beim Schreiben einer einfachen WPF-Anwendung, die frei Hand Eingaben sammelt.

### <a name="got-ink"></a>Sie haben Freihand?

So erstellen Sie eine WPF-App, die frei Hand Eingaben unterstützt

1. Öffnen Sie Visual Studio.

2. Erstellen Sie eine neue **WPF-App**.

   Erweitern Sie im Dialogfeld **Neues Projekt** die Kategorie **installierter** >  **C# Visual** oder **Visual Basic** > **Windows-Desktop** . Wählen Sie dann die APP-Vorlage **WPF-App (.NET Framework)** aus. Geben Sie einen Namen ein, und klicken Sie dann auf **OK**.

   Visual Studio erstellt das Projekt, und *MainWindow. XAML* wird im Designer geöffnet.

3. Geben Sie `<InkCanvas/>` zwischen den `<Grid>`-Tags ein.

   ![XAML-Designer mit InkCanvas-Tag](./media/getting-started-with-ink/inkcanvas-xaml.png)

4. Drücken Sie **F5** , um die Anwendung im Debugger zu starten.

5. Schreiben Sie mit einem **Tablettstift** oder einer Maus im Fenster "Hello World".

Sie haben die Ink-Entsprechung einer "Hello World"-Anwendung mit nur 12 Keystrokes geschrieben!

### <a name="spice-up-your-app"></a>Hochskalieren der APP

Wir nutzen einige Features von WPF. Ersetzen Sie alles zwischen dem öffnenden und dem schließenden \<Fenster > Tags durch das folgende Markup:

```xaml
<Page>
  <InkCanvas Name="myInkCanvas" MouseRightButtonUp="RightMouseUpHandler">
    <InkCanvas.Background>
      <LinearGradientBrush>
        <GradientStop Color="Yellow" Offset="0.0" />
          <GradientStop Color="Blue" Offset="0.5" />
            <GradientStop Color="HotPink" Offset="1.0" />
              </LinearGradientBrush>
    </InkCanvas.Background>
  </InkCanvas>
</Page>
```

Dieser XAML-Code erstellt einen Hintergrund für den Farbverlaufs Pinsel auf der Eingangs Oberfläche.

![Farbverlaufs Farben auf der Erstellungs Oberfläche in der WPF-App](./media/getting-started-with-ink/gradient-colors.png)

### <a name="add-some-code-behind-the-xaml"></a>Code hinter dem XAML hinzufügen

Obwohl XAML das Entwerfen der Benutzeroberfläche vereinfacht, muss jede reale Anwendung Code zum Behandeln von Ereignissen hinzufügen. Im folgenden finden Sie ein einfaches Beispiel, das als Reaktion auf einen Rechtsklick mit der Maus auf die frei Hand Eingabe zoomt.

1. Legen Sie den `MouseRightButtonUp` Handler in Ihrem XAML-Code fest:

   [!code-xaml[DigitalInkTopics#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]

1. Erweitern Sie in **Projektmappen-Explorer**den Eintrag MainWindow. XAML, und öffnen Sie die Code Behind-Datei (MainWindow.XAML.cs oder MainWindow. XAML. vb). Fügen Sie den folgenden Ereignishandlercode hinzu:

   [!code-csharp[DigitalInkTopics#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
   [!code-vb[DigitalInkTopics#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]

1. Führen Sie die Anwendung aus. Fügen Sie frei Hand Eingaben hinzu, klicken Sie dann mit der rechten Maustaste auf die Maus, oder führen Sie eine Press-and-Hold-Entsprechung mit einem Tablettstift

   Wenn Sie mit der rechten Maustaste klicken, wird die Anzeige vergrößert.

### <a name="use-procedural-code-instead-of-xaml"></a>Verwenden von prozeduralem Code anstelle von XAML

Sie können auf alle WPF-Funktionen über prozeduralen Code zugreifen. Führen Sie die folgenden Schritte aus, um eine "Hello Ink World"-Anwendung für WPF zu erstellen, die überhaupt kein XAML verwendet.

1. Erstellen Sie in Visual Studio ein neues Konsolen Anwendungsprojekt.

   Erweitern Sie im Dialogfeld **Neues Projekt** die Kategorie **installierter** >  **C# Visual** oder **Visual Basic** > **Windows-Desktop** . Wählen Sie dann die APP-Vorlage für **Konsolen-app (.NET Framework)** aus. Geben Sie einen Namen ein, und klicken Sie dann auf **OK**.

1. Fügen Sie den folgenden Code in die Datei Program.cs oder Program. vb ein:

   [!code-csharp[InkCanvasConsoleApp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
   [!code-vb[InkCanvasConsoleApp#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]

1. Fügen Sie Verweise auf die Assemblys PresentationCore, presentationframework und WindowsBase hinzu, indem Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf **Verweise** klicken und **Verweis hinzufügen**auswählen.

   ![Verweis-Manager mit "PresentationCore" und "PresentationFramework"](./media/getting-started-with-ink/reference-manager-presentationcore-presentationframework.png)

1. Erstellen Sie die Anwendung, indem Sie **F5**drücken.

## <a name="see-also"></a>Weitere Informationen

- [Freihandeingaben](digital-ink.md)
- [Erfassen von Freihandeingaben](collecting-ink.md)
- [Schrifterkennung](handwriting-recognition.md)
- [Speichern von Eingabehilfen](storing-ink.md)
