---
title: 'Exemplarische Vorgehensweise: Lokalisieren einer Hybridanwendung'
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: 69aa5ae145ffe378b7a4547e5a33826965bf7894
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111113"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a>Exemplarische Vorgehensweise: Lokalisieren einer Hybridanwendung

In dieser exemplarischen Vorgehensweise [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erfahren Sie, wie Sie Elemente in einer Windows Forms-basierten Hybridanwendung lokalisieren.

In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:

- Erstellen des Windows Forms-Hostprojekts.

- Lokalisierbaren Inhalt hinzufügen

- Lokalisierungsfunktionalität aktivieren

- Ressourcenbezeichner zuweisen

- Verwenden des LocBaml-Tools zum Erzeugen einer Satellitenassembly.

Eine vollständige Codeliste der in dieser exemplarischen Vorgehensweise dargestellten Aufgaben finden Sie unter [Lokalisieren eines Hybridanwendungsbeispiels](https://go.microsoft.com/fwlink/?LinkID=160015).

Am Ende werden Sie eine lokalisierte Hybridanwendung haben.

## <a name="prerequisites"></a>Voraussetzungen

Zum Abschließen dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:

- Visual Studio 2017

## <a name="creating-the-windows-forms-host-project"></a>Erstellen des Windows Forms-Hostprojekts

Der erste Schritt besteht darin, das Windows [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Forms-Anwendungsprojekt zu erstellen und ein Element mit Inhalt hinzuzufügen, das Sie lokalisieren möchten.

### <a name="to-create-the-host-project"></a>So erstellen Sie das Hostprojekt

1. Erstellen Sie ein **WPF-App-Projekt** mit dem Namen `LocalizingWpfInWf`.  (**Datei** > **Neues** > **Project** > Visual**C-** oder Visual **Basic** > Classic**Desktop** > **WPF-Anwendung**).

2. Fügen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> Sie `SimpleControl` ein Element hinzu, das dem Projekt aufgerufen wird.

3. Verwenden <xref:System.Windows.Forms.Integration.ElementHost> Sie das `SimpleControl` Steuerelement, um ein Element im Formular zu platzieren. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Hosten eines 3D WPF Composite Control in Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).

## <a name="adding-localizable-content"></a>Hinzufügen von lokalisierbarem Inhalt

Als Nächstes fügen Sie ein Windows Forms-Beschriftungssteuerelement hinzu und legen den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt des Elements auf eine lokalisierbare Zeichenfolge fest.

### <a name="to-add-localizable-content"></a>So fügen Sie lokalisierbaren Inhalt hinzu

1. Doppelklicken Sie im **Projektmappen-Explorer**auf **SimpleControl.xaml,** um es im WPF-Designer zu öffnen.

2. Legen Sie den <xref:System.Windows.Controls.Button> Inhalt des Steuerelements mithilfe des folgenden Codes fest.

     [!code-xaml[LocalizingWpfInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3. Doppelklicken Sie im **Projektmappen-Explorer**auf **Form1,** um es im Windows Forms Designer zu öffnen.

4. Öffnen Sie die **Toolbox,** und doppelklicken Sie auf **Beschriftung,** um dem Formular ein Beschriftungssteuerelement hinzuzufügen. Legen Sie den Wert von dessen <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft auf `"Hello"` fest.

5. Drücken Sie **F5,** um die Anwendung zu erstellen und auszuführen.

     Sowohl `SimpleControl` das Element als auch das Beschriftungssteuerelement zeigen den Text **"Hello"** an.

## <a name="enabling-localization"></a>Aktivieren der Lokalisierungsfunktionalität

Windows Forms-Designer bietet Einstellungen für das Aktivieren der Lokalisierungsfunktionalität in einer Satellitenassembly.

### <a name="to-enable-localization"></a>So aktivieren Sie die Lokalisierungsfunktionalität

1. Doppelklicken Sie im **Projektmappen-Explorer**auf **Form1.cs,** um sie im Windows Forms Designer zu öffnen.

2. Legen Sie im **Fenster Eigenschaften** den Wert der **Localizable-Eigenschaft** des Formulars auf `true`fest.

3. Legen Sie im Fenster **Eigenschaften** den Wert der **Language-Eigenschaft** auf **Spanisch (Spanien)** fest.

4. Wählen Sie im Windows Forms-Designer das Steuerelement „Label”.

5. Legen Sie im **Fenster Eigenschaften** <xref:System.Windows.Forms.Control.Text%2A> den `"Hola"`Wert der Eigenschaft auf fest.

     Dem Projekt wird eine neue Ressourcendatei mit dem Namen Form1.es-ES.resx hinzugefügt.

6. Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf **Form1.cs** und klicken Sie auf **Code anzeigen,** um ihn im Code-Editor zu öffnen.

7. Kopieren Sie den `Form1` folgenden Code in den `InitializeComponent`Konstruktor, der dem Aufruf von vorangestellt wird.

     [!code-csharp[LocalizingWpfInWf#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8. Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf **LocalizingWpfInWf,** und klicken Sie auf **Projekt entladen**.

     Der Projektname ist mit **(nicht verfügbar)** beschriftet.

9. Klicken Sie mit der rechten Maustaste auf **LocalizingWpfInWf**, und klicken Sie auf **Lokalisieren bearbeitenWpfInWf.csproj**.

     Die Projektdatei wird im Code-Editor angezeigt.

10. Kopieren Sie die folgende `PropertyGroup` Zeile in die erste Zeile in der Projektdatei.

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. Speichern Sie die Projektdatei und schließen Sie sie.

12. Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf **LocalizingWpfInWf,** und klicken Sie auf **Projekt neu laden**.

## <a name="assigning-resource-identifiers"></a>Ressourcenbezeichner zuweisen

Sie können mithilfe von Ressourcenbezeichnern eine Zuordnung von lokalisierbarem Inhalt zu Ressourcenassemblys erstellen. Die MsBuild.exe-Anwendung weist automatisch Ressourcenbezeichner zu, wenn Sie die `updateuid` Option angeben.

### <a name="to-assign-resource-identifiers"></a>So weisen Sie Ressourcenbezeichner zu

1. Öffnen Sie im Startmenü die Eingabeaufforderung für Entwickler für Visual Studio.

2. Verwenden Sie den folgenden Befehl, um ihrem lokalisierbaren Inhalt Ressourcenbezeichner zuzuweisen.

    ```console
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3. Doppelklicken Sie im **Projektmappen-Explorer**auf **SimpleControl.xaml,** um sie im Code-Editor zu öffnen. Sie werden sehen, dass `msbuild` `Uid` der Befehl das Attribut allen Elementen hinzugefügt hat. Dies erleichtert die Lokalisierung durch Zuweisung von Ressourcenbezeichnern.

     [!code-xaml[LocalizingWpfInWf#20](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4. Drücken Sie **F6**, um die Projektmappe zu erstellen.

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a>Verwenden des LocBaml-Tools zum Erzeugen einer Satellitenassembly

Ihr lokalisierter Inhalt wird in einer *reinen Ressourcensatellitenassembly*gespeichert. Verwenden Sie das Befehlszeilentool LocBaml.exe, um [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine lokalisierte Assembly für Ihren Inhalt zu erstellen.

### <a name="to-produce-a-satellite-assembly"></a>So erzeugen Sie eine Satellitenassembly

1. Kopieren Sie LocBaml.exe in den Projektordner obj\Debug. Weitere Informationen finden Sie unter [Lokalisieren einer Anwendung](how-to-localize-an-application.md).

2. Führen Sie im Eingabeaufforderungsfenster den folgenden Befehl aus, um Ressourcenzeichenfolgen in eine temporäre Datei zu extrahieren.

    ```console
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3. Öffnen Sie die Datei temp.csv mit Visual Studio oder einem anderen Texteditor. Ersetzen Sie `"Hello"` die Zeichenfolge `"Hola"`durch ihre spanische Übersetzung .

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

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Lokalisieren einer Anwendung](how-to-localize-an-application.md)
- [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
