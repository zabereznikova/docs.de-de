---
title: 'Exemplarische Vorgehensweise: Lokalisieren einer Hybridanwendung'
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: b98bf7b3f0aa4e7698a5c0ca7c8ae16051ce6300
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991781"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a>Exemplarische Vorgehensweise: Lokalisieren einer Hybridanwendung

In dieser exemplarischen Vorgehensweise wird veranschaulicht, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wie Elemente in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]einer-basierten Hybrid Anwendung lokalisiert werden.

In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:

- Das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Host Projekt wird erstellt.

- Lokalisierbaren Inhalt hinzufügen

- Lokalisierungsfunktionalität aktivieren

- Ressourcenbezeichner zuweisen

- Verwenden des LocBaml-Tools zum Erzeugen einer Satellitenassembly.

Eine komplette Code Auflistung der Aufgaben, die in dieser exemplarischen Vorgehensweise veranschaulicht werden, finden Sie unter Beispiel für das [Lokalisieren einer Hybrid Anwendung](https://go.microsoft.com/fwlink/?LinkID=160015).

Am Ende werden Sie eine lokalisierte Hybridanwendung haben.

## <a name="prerequisites"></a>Erforderliche Komponenten

Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:

- Visual Studio 2017

## <a name="creating-the-windows-forms-host-project"></a>Erstellen des Windows Forms-Hostprojekts

Der erste Schritt besteht darin, das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Anwendungsprojekt zu erstellen und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ein-Element mit Inhalt hinzuzufügen, das Sie lokalisieren werden.

### <a name="to-create-the-host-project"></a>So erstellen Sie das Hostprojekt

1. Erstellen Sie ein **WPF** -Anwendungs `LocalizingWpfInWf`Projekt mit dem Namen.  (**Datei** > **Neues** **Projekt, Visual C#**  oder Visual Basic**klassische Desktop-** WPF- > Anwendung). >  >  > 

2. Fügen Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dem Projekt `SimpleControl` ein <xref:System.Windows.Controls.UserControl> -Element mit dem Namen hinzu.

3. Verwenden Sie <xref:System.Windows.Forms.Integration.ElementHost> das-Steuerelement `SimpleControl` , um ein-Element im Formular zu platzieren. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Hosting eines zusammengesetzten 3D-WPF-Steuer](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)Elements in Windows Forms.

## <a name="adding-localizable-content"></a>Hinzufügen von lokalisierbarem Inhalt

Fügen Sie als nächstes ein [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Label-Steuerelement hinzu, und legen Sie den Inhalt des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elements auf eine lokalisierbare Zeichenfolge fest.

### <a name="to-add-localizable-content"></a>So fügen Sie lokalisierbaren Inhalt hinzu

1. Doppelklicken Sie in **Projektmappen-Explorer**auf **SimpleControl. XAML** , um [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]es im zu öffnen.

2. Legen Sie den Inhalt des <xref:System.Windows.Controls.Button> -Steuer Elements mithilfe des folgenden Codes fest.

     [!code-xaml[LocalizingWpfInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3. Doppelklicken Sie in **Projektmappen-Explorer**auf **Form1** , um es im Windows Forms-Designer zu öffnen.

4. Öffnen Sie die **Toolbox** , und doppelklicken Sie auf **Bezeichnung** , um dem Formular ein Label-Steuerelement hinzuzufügen. Legen Sie den Wert von dessen <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft auf `"Hello"` fest.

5. Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.

     Sowohl das `SimpleControl` -Element als auch das Label-Steuerelement zeigen den Text **"Hello"** an.

## <a name="enabling-localization"></a>Aktivieren der Lokalisierungsfunktionalität

Windows Forms-Designer bietet Einstellungen für das Aktivieren der Lokalisierungsfunktionalität in einer Satellitenassembly.

### <a name="to-enable-localization"></a>So aktivieren Sie die Lokalisierungsfunktionalität

1. Doppelklicken Sie in **Projektmappen-Explorer**auf **Form1.cs** , um es im Windows Forms-Designer zu öffnen.

2. Legen Sie im Fenster **Eigenschaften** den Wert der **Lokalisier** baren Eigenschaft des Formulars auf `true`fest.

3. Legen Sie im Fenster **Eigenschaften** den Wert der **Language** -Eigenschaft auf **Spanisch (Spanien)** fest.

4. Wählen Sie im Windows Forms-Designer das Steuerelement „Label”.

5. Legen Sie im Fenster **Eigenschaften** den Wert <xref:System.Windows.Forms.Control.Text%2A> der-Eigenschaft auf `"Hola"`fest.

     Dem Projekt wird eine neue Ressourcendatei mit dem Namen Form1.es-ES.resx hinzugefügt.

6. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **Form1.cs** , und klicken Sie auf **Code anzeigen** , um ihn im Code-Editor zu öffnen.

7. Kopieren Sie `Form1` `InitializeComponent`den folgenden Code in den-Konstruktor, der dem-Vorgang vorangestellt ist.

     [!code-csharp[LocalizingWpfInWf#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **LocalizingWpfInWf** , und klicken Sie dann auf **Projekt entladen**.

     Der Projektname hat die Bezeichnung **(nicht verfügbar)** .

9. Klicken Sie mit der rechten Maustaste auf **LocalizingWpfInWf**, und klicken Sie auf **LocalizingWpfInWf. csproj bearbeiten**.

     Die Projektdatei wird im Code-Editor angezeigt.

10. Kopieren Sie die folgende Zeile in die `PropertyGroup` erste in der Projektdatei.

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. Speichern Sie die Projektdatei und schließen Sie sie.

12. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **LocalizingWpfInWf** , und klicken Sie auf **Projekt erneut laden**.

## <a name="assigning-resource-identifiers"></a>Ressourcenbezeichner zuweisen

Sie können mithilfe von Ressourcenbezeichnern eine Zuordnung von lokalisierbarem Inhalt zu Ressourcenassemblys erstellen. Die Anwendung MSBuild. exe weist Ressourcen Bezeichner automatisch zu, wenn Sie `updateuid` die Option angeben.

### <a name="to-assign-resource-identifiers"></a>So weisen Sie Ressourcenbezeichner zu

1. Öffnen Sie im Startmenü die Developer-Eingabeaufforderung für Visual Studio.

2. Verwenden Sie den folgenden Befehl, um ihrem lokalisierbaren Inhalt Ressourcenbezeichner zuzuweisen.

    ```console
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3. Doppelklicken Sie in **Projektmappen-Explorer**auf **SimpleControl. XAML** , um die Datei im Code-Editor zu öffnen. Sie sehen, dass der `msbuild` Befehl allen Elementen das `Uid` -Attribut hinzugefügt hat. Dies erleichtert die Lokalisierung durch Zuweisung von Ressourcenbezeichnern.

     [!code-xaml[LocalizingWpfInWf#20](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4. Drücken Sie **F6** , um die Projekt Mappe zu erstellen.

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a>Verwenden des LocBaml-Tools zum Erzeugen einer Satellitenassembly

Der lokalisierte Inhalt wird in einer *Satellitenassembly*gespeichert. Verwenden Sie das Befehlszeilen Tool "LocBaml. exe", um eine lokalisierte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Assembly für Ihren Inhalt zu entwickeln.

### <a name="to-produce-a-satellite-assembly"></a>So erzeugen Sie eine Satellitenassembly

1. Kopieren Sie LocBaml.exe in den Projektordner obj\Debug. Weitere Informationen finden Sie unter [Lokalisieren einer Anwendung](how-to-localize-an-application.md).

2. Führen Sie im Eingabeaufforderungsfenster den folgenden Befehl aus, um Ressourcenzeichenfolgen in eine temporäre Datei zu extrahieren.

    ```console
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3. Öffnen Sie die Datei "Temp. csv" mit Visual Studio oder einem anderen Text-Editor. Ersetzen Sie die `"Hello"` Zeichenfolge durch die spanische `"Hola"`Übersetzung.

4. Speichern Sie die Datei „temp.csv”.

5. Verwenden Sie den folgenden Befehl, um die lokalisierte Ressourcendatei zu generieren.

    ```console
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES
    ```

     Die Datei „LocalizingWpfInWf.g.es-es.resources” wird im Ordner obj\Debug erstellt.

6. Verwenden Sie den folgenden Befehl, um die lokalisierte Satellitenassembly zu erstellen.

    ```console
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources
    ```

     Die Datei „LocalizingWpfInWf.resources.dll” wird im Ordner obj\Debug erstellt.

7. Kopieren Sie die Datei LocalizingWpfInWf.Resources.dll in den Projektordner nach \bin\Debug\es-ES. Ersetzen Sie die vorhandene Datei.

8. Führen Sie die Datei „LocalizingWpfInWf.exe” aus, die sich im Projektordner unter "\bin\Debug" befindet. Erstellen Sie die Anwendung nicht neu, da dies die Satellitenassembly überschreiben würde.

     Die Anwendung zeigt nun die lokalisierten Zeichenfolgen statt der englischen Zeichenfolgen.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Lokalisieren einer Anwendung](how-to-localize-an-application.md)
- [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
