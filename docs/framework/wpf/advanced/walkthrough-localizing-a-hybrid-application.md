---
title: 'Exemplarische Vorgehensweise: Lokalisieren einer Hybridanwendung'
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: 86779197004f2a8e84d44aaeff2df2dacb05fb01
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64621212"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a>Exemplarische Vorgehensweise: Lokalisieren einer Hybridanwendung

In dieser exemplarischen Vorgehensweise erfahren Sie, wie zum Lokalisieren von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elemente in einem [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]--basierten hybridanwendung.

In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:

- Erstellen der [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Hostprojekt.

- Lokalisierbaren Inhalt hinzufügen

- Lokalisierungsfunktionalität aktivieren

- Ressourcenbezeichner zuweisen

- Verwenden des LocBaml-Tools zum Erzeugen einer Satellitenassembly.

Eine vollständige codeauflistung der Aufgaben in dieser exemplarischen Vorgehensweise veranschaulicht, finden Sie unter [Lokalisieren einer Anwendung Hybridbeispiel](https://go.microsoft.com/fwlink/?LinkID=160015).

Am Ende werden Sie eine lokalisierte Hybridanwendung haben.

## <a name="prerequisites"></a>Vorraussetzungen

Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:

- Visual Studio 2017

## <a name="creating-the-windows-forms-host-project"></a>Erstellen des Windows Forms-Hostprojekts

Der erste Schritt ist die Erstellung der [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Anwendung Projekt, und fügen eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Element mit dem Inhalt, die Sie lokalisieren werden.

### <a name="to-create-the-host-project"></a>So erstellen Sie das Hostprojekt

1. Erstellen Sie eine **WPF-App** Projekt mit dem Namen `LocalizingWpfInWf`.  (**Datei** > **neue** > **Projekt** > **Visual C#-** oder **Visual Basic**   >  **Klassischer Desktop** > **WPF-Anwendung**).

2. Hinzufügen einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> Element namens `SimpleControl` zum Projekt.

3. Verwenden der <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement platzieren einer `SimpleControl` Element auf dem Formular. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten 3D-WPF-Steuerelements in Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).

## <a name="adding-localizable-content"></a>Hinzufügen von lokalisierbarem Inhalt

Als Nächstes fügen Sie eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] beschriftungs-Steuerelement, und legen Sie die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt des Elements auf eine lokalisierbare Zeichenfolge.

### <a name="to-add-localizable-content"></a>So fügen Sie lokalisierbaren Inhalt hinzu

1. In **Projektmappen-Explorer**, doppelklicken Sie auf **SimpleControl.xaml** zum Öffnen der [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].

2. Legen Sie den Inhalt von der <xref:System.Windows.Controls.Button> mithilfe des folgenden Codes zu steuern.

     [!code-xaml[LocalizingWpfInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3. In **Projektmappen-Explorer**, doppelklicken Sie auf **Form1** um es im Windows Forms-Designer zu öffnen.

4. Öffnen der **Toolbox** und doppelklicken Sie auf **Bezeichnung** auf dem Formular ein Label-Steuerelement hinzuzufügen. Legen Sie den Wert von dessen <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft auf `"Hello"` fest.

5. Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.

     Sowohl die `SimpleControl` Element und das Label-Steuerelement zeigt den Text **"Hello"**.

## <a name="enabling-localization"></a>Aktivieren der Lokalisierungsfunktionalität

Windows Forms-Designer bietet Einstellungen für das Aktivieren der Lokalisierungsfunktionalität in einer Satellitenassembly.

### <a name="to-enable-localization"></a>So aktivieren Sie die Lokalisierungsfunktionalität

1. In **Projektmappen-Explorer**, doppelklicken Sie auf **"Form1.cs"** um es im Windows Forms-Designer zu öffnen.

2. In der **Eigenschaften** legen den Wert des Formulars **Localizable** Eigenschaft `true`.

3. In der **Eigenschaften** legen den Wert des der **Sprache** Eigenschaft **Spanisch (Spanien)**.

4. Wählen Sie im Windows Forms-Designer das Steuerelement „Label”.

5. In der **Eigenschaften** legen den Wert des der <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft `"Hola"`.

     Dem Projekt wird eine neue Ressourcendatei mit dem Namen Form1.es-ES.resx hinzugefügt.

6. In **Projektmappen-Explorer**, mit der rechten Maustaste **"Form1.cs"** , und klicken Sie auf **Ansichtscode** um ihn im Code-Editor zu öffnen.

7. Kopieren Sie den folgenden Code der `Form1` Konstruktor vor dem Aufruf von `InitializeComponent`.

     [!code-csharp[LocalizingWpfInWf#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8. In **Projektmappen-Explorer**, mit der rechten Maustaste **LocalizingWpfInWf** , und klicken Sie auf **Projekt entladen**.

     Der Projektname ist mit der Bezeichnung **(nicht verfügbar)**.

9. Mit der rechten Maustaste **LocalizingWpfInWf**, und klicken Sie auf **bearbeiten LocalizingWpfInWf.csproj**.

     Die Projektdatei wird im Code-Editor angezeigt.

10. Kopieren Sie die folgende Zeile in der ersten `PropertyGroup` in der Projektdatei.

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. Speichern Sie die Projektdatei und schließen Sie sie.

12. In **Projektmappen-Explorer**, mit der rechten Maustaste **LocalizingWpfInWf** , und klicken Sie auf **Projekt erneut laden**.

## <a name="assigning-resource-identifiers"></a>Ressourcenbezeichner zuweisen

Sie können mithilfe von Ressourcenbezeichnern eine Zuordnung von lokalisierbarem Inhalt zu Ressourcenassemblys erstellen. Die MsBuild.exe-Anwendung weist automatisch Ressourcenbezeichner, bei der Angabe der `updateuid` Option.

### <a name="to-assign-resource-identifiers"></a>So weisen Sie Ressourcenbezeichner zu

1. Öffnen Sie die Developer-Eingabeaufforderung für Visual Studio, über das Startmenü.

2. Verwenden Sie den folgenden Befehl, um ihrem lokalisierbaren Inhalt Ressourcenbezeichner zuzuweisen.

    ```
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3. In **Projektmappen-Explorer**, doppelklicken Sie auf **SimpleControl.xaml** um ihn im Code-Editor zu öffnen. Sie sehen, dass die `msbuild` Befehl wurde hinzugefügt, die `Uid` Attribut auf alle Elemente. Dies erleichtert die Lokalisierung durch Zuweisung von Ressourcenbezeichnern.

     [!code-xaml[LocalizingWpfInWf#20](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4. Drücken Sie **F6** zum Erstellen der Projektmappe.

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a>Verwenden des LocBaml-Tools zum Erzeugen einer Satellitenassembly

Ihr lokalisierte Inhalt befindet sich in einer reinen Ressourcen- *Satellitenassembly*. Verwenden Sie das Befehlszeilentool LocBaml.exe, erstellen Sie eine lokalisierte Assembly für Ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt.

### <a name="to-produce-a-satellite-assembly"></a>So erzeugen Sie eine Satellitenassembly

1. Kopieren Sie LocBaml.exe in den Projektordner obj\Debug. Weitere Informationen finden Sie unter [Lokalisieren einer Anwendung](how-to-localize-an-application.md).

2. Führen Sie im Eingabeaufforderungsfenster den folgenden Befehl aus, um Ressourcenzeichenfolgen in eine temporäre Datei zu extrahieren.

    ```
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3. Öffnen Sie die Datei "temp.csv" mit Visual Studio oder einem anderen Texteditor ein. Ersetzen Sie die Zeichenfolge `"Hello"` mit entsprechende spanische Übersetzung `"Hola"`.

4. Speichern Sie die Datei „temp.csv”.

5. Verwenden Sie den folgenden Befehl, um die lokalisierte Ressourcendatei zu generieren.

    ```
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES
    ```

     Die Datei „LocalizingWpfInWf.g.es-es.resources” wird im Ordner obj\Debug erstellt.

6. Verwenden Sie den folgenden Befehl, um die lokalisierte Satellitenassembly zu erstellen.

    ```
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
