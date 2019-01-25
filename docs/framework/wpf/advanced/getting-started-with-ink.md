---
title: Erstellen Sie ein InkCanvas-Steuerelement in einer WPF-app in Visual Studio
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- XAML [WPF], procedural code in lieu of
- InkCanvas (WPF)
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
ms.openlocfilehash: eaaa8ad5273331941bc6915231460100e8ac24b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646239"
---
# <a name="get-started-with-ink-in-wpf"></a>Erste Schritte mit Freihandeingaben in WPF

Windows Presentation Foundation (WPF) ist ein Freihand-Feature, das es einfach macht, Freihandeingaben in Ihre app zu integrieren.

## <a name="prerequisites"></a>Vorraussetzungen

Verwenden Sie die folgenden Beispielen wird zuerst [installieren Sie Microsoft Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017). Außerdem können wissen, wie Sie einfache WPF-apps zu schreiben. Erste Schritte mit WPF Hilfe finden Sie [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).

## <a name="quick-start"></a>Schnellstart

In diesem Abschnitt können Sie eine einfache WPF-Anwendung zu schreiben, die Freihandeingaben erfasst.

### <a name="got-ink"></a>Erfasst Freihandeingabe?

Zum Erstellen einer WPF-app, die Freihandeingaben unterstützt:

1. Öffnen Sie Visual Studio.

2. Erstellen Sie ein neues **WPF-App**.

   In der **neues Projekt** Dialogfeld erweitern Sie die **installiert** > **Visual C#-** oder **Visual Basic**  >   **Windows-Desktop** Kategorie. Wählen Sie dann die **WPF-App ((.NET Framework)** -app-Vorlage. Geben Sie einen Namen ein, und wählen Sie dann **OK**.

   Visual Studio erstellt das Projekt, und *"MainWindow.xaml"* im Designer geöffnet.

3. Typ `<InkCanvas/>` zwischen der `<Grid>` Tags.

   ![XAML-Designer mit InkCanvas-Steuerelement-tag](media/getting-started-with-ink/inkcanvas-xaml.png)

4. Drücken Sie **F5** auf die Anwendung im Debugger zu starten.

5. Schreiben Sie mit einem Stift oder der Maus **Hallo Welt** im Fenster.

Sie haben die Freihand-Entsprechung einer "Hello World"-Anwendung mit nur 12 Tastatureingaben geschrieben.

### <a name="spice-up-your-app"></a>Darstellungsschichten interessanter zu gestalten Sie Ihre App

Lassen Sie uns einige Funktionen von WPF nutzen. Ersetzen Sie alles zwischen den öffnenden und schließenden \<Fenster >-Tags mit folgendem Markup:

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

Dieses XAML erstellt einen Farbverlaufspinsel-Hintergrund für die Freihandoberfläche.

![Verlaufsfarben auf Freihand-Oberfläche in WPF-app](media/getting-started-with-ink/gradient-colors.png)

### <a name="add-some-code-behind-the-xaml"></a>Hinzufügen von Code hinter der XAML

Während der XAML sehr Entwerfen der Benutzeroberfläche erleichtert, muss jeder reale Anwendung Code hinzufügen, um Ereignisse zu behandeln. Hier ist ein einfaches Beispiel, das auf die Freihandeingabe in Reaktion auf eine mit der rechten Maustaste in eine Maus vergrößert.

1. Legen Sie die `MouseRightButtonUp` Ereignishandler in Ihrem XAML:

   [!code-xaml[DigitalInkTopics#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]

1. In **Projektmappen-Explorer**, erweitern Sie "MainWindow.xaml", und öffnen Sie die CodeBehind-Datei ("MainWindow.Xaml.cs" oder "MainWindow.Xaml.vb"). Fügen Sie den folgenden Ereignishandlercode hinzu:

   [!code-csharp[DigitalInkTopics#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
   [!code-vb[DigitalInkTopics#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]

1. Führen Sie die Anwendung aus. Einige Freihandeingaben, und klicken Sie dann mit der rechten Maustaste, oder führen Sie ein Äquivalent drücken und halten mit einem Stift.

   Die Anzeige vergrößert jedes Mal, wenn Sie mit der rechten Maustaste klicken.

### <a name="use-procedural-code-instead-of-xaml"></a>Prozeduralen Code statt XAML verwenden

Sie können alle WPF-Funktionen aus prozeduralen Code zugreifen. Um eine "Hello Freihand-World"-Anwendung für WPF erstellen, die alle XAML überhaupt nicht verwendet, gehen Sie wie folgt vor.

1. Erstellen Sie ein neues Konsolenanwendungsprojekt in Visual Studio.

   In der **neues Projekt** Dialogfeld erweitern Sie die **installiert** > **Visual C#-** oder **Visual Basic**  >   **Windows-Desktop** Kategorie. Wählen Sie dann die **Konsolen-App ((.NET Framework)** -app-Vorlage. Geben Sie einen Namen ein, und wählen Sie dann **OK**.

1. Fügen Sie den folgenden Code in der Datei Program.cs oder Program.vb-Datei ein:

   [!code-csharp[InkCanvasConsoleApp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
   [!code-vb[InkCanvasConsoleApp#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]

1. Fügen Sie Verweise auf die Assemblys PresentationCore, PresentationFramework und WindowsBase hinzu, indem Sie mit der rechten Maustaste auf **Verweise** in **Projektmappen-Explorer** und **VerweisHinzufügen**.

   ![Verweis-Manager angezeigt wird, PresentationCore und PresentationFramework getrennt](media/getting-started-with-ink/references.png)

1. Erstellen Sie die Anwendung durch Drücken von **F5**.

## <a name="see-also"></a>Siehe auch

- [Freihandeingaben](../../../../docs/framework/wpf/advanced/digital-ink.md)
- [Erfassen von Freihandeingaben](../../../../docs/framework/wpf/advanced/collecting-ink.md)
- [Schrifterkennung](../../../../docs/framework/wpf/advanced/handwriting-recognition.md)
- [Speichern von Eingabehilfen](../../../../docs/framework/wpf/advanced/storing-ink.md)
