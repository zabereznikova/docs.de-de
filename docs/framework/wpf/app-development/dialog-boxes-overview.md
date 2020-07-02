---
title: Übersicht über Dialogfelder
description: Erfahren Sie mehr über die Arten von Dialogfeldern in Windows Foundation Presentation (WPF), die Sie zum Erfassen und Anzeigen von Informationen verwenden können.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- modeless dialog boxes [WPF]
- dialog boxes [WPF]
- message boxes [WPF]
- modal dialog boxes [WPF]
ms.assetid: 0d23d544-a393-4a02-a3aa-d8cd5d3d6511
ms.openlocfilehash: 822604dd694f2f6260496872fd7a1a8440a62535
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618141"
---
# <a name="dialog-boxes-overview"></a>Übersicht über Dialog Felder
Eigenständige Anwendungen verfügen in der Regel über ein Hauptfenster, in dem sowohl die Hauptdaten angezeigt werden, über die die Anwendung ausgeführt wird, als auch die Funktionalität zur Verarbeitung dieser Daten über [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Mechanismen wie Menüleisten, Symbolleisten und Status leisten. Eine nicht triviale Anwendung kann auch zusätzliche Fenster anzeigen, um Folgendes auszuführen:  
  
- Spezifische Informationen für Benutzer anzeigen.  
  
- Informationen von Benutzern erfassen.  
  
- Informationen sowohl anzeigen als auch erfassen.  
  
 Diese Windows-Typen werden als *Dialogfelder*bezeichnet, und es gibt zwei Typen: modale und nicht modale Typen.  
  
 Ein *modales* Dialogfeld wird von einer Funktion angezeigt, wenn die Funktion zusätzliche Daten von einem Benutzer benötigt, um den Vorgang fortzusetzen. Da die Funktion beim Erfassen der Daten vom modalen Dialogfeld abhängig ist, verhindert das modale Dialogfeld auch, dass der Benutzer andere Fenster in der Anwendung aktiviert, während das Dialogfeld geöffnet bleibt. In den meisten Fällen ermöglicht ein modales Dialogfeld einem Benutzer, zu signalisieren, wann er das modale Dialogfeld durch Drücken der Schaltfläche **OK** oder **Abbrechen** beendet hat. Wenn Sie auf die Schaltfläche **OK** klicken, wird angegeben, dass ein Benutzerdaten eingegeben hat und die Funktion die Verarbeitung mit diesen Daten fortsetzen soll. Durch Drücken der Schaltfläche **Abbrechen** wird angegeben, dass ein Benutzer die Ausführung der Funktion beenden möchte. Die häufigsten Beispiele für modale Dialogfelder sind das Öffnen, Speichern und Drucken von Daten.  
  
 Ein nicht modalem Dialogfeld verhindert hingegen nicht, *dass ein Benutzer* andere Fenster aktiviert, während er geöffnet ist. Wenn ein Benutzer z. B. Vorkommen eines bestimmten Worts in einem Dokument finden möchte, wird in einem Hauptfenster oft ein Dialogfeld geöffnet, um den Benutzer zu fragen, nach welchem Wort er sucht. Da die Suche nach einem Wort einen Benutzer aber nicht an der Bearbeitung des Dokuments hindert, muss das Dialogfeld nicht unbedingt modal sein. Bei einem nicht modalem Dialogfeld wird mindestens eine Schaltfläche zum **Schließen** des Dialog Felds bereitgestellt, und es können zusätzliche Schaltflächen zum Ausführen bestimmter Funktionen bereitgestellt werden, z. b. eine Schaltfläche " **weiter suchen** ", um das nächste Wort zu suchen, das den Suchkriterien einer Wort Suche entspricht.  
  
 Mit Windows Presentation Foundation (WPF) können Sie verschiedene Arten von Dialogfeldern erstellen, einschließlich Meldungs Feldern, allgemeiner Dialogfelder und benutzerdefinierte Dialogfelder. In diesem Thema werden die einzelnen Themen erläutert, und im [Dialog Feld Beispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox) finden Sie entsprechende Beispiele.  

<a name="Message_Boxes"></a>
## <a name="message-boxes"></a>Meldungs Felder  
 Ein Meldungs *Feld* ist ein Dialogfeld, das verwendet werden kann, um Textinformationen anzuzeigen und Benutzern das Treffen von Entscheidungen mit Schaltflächen zu ermöglichen. In der folgenden Abbildung ist ein Meldungsfeld dargestellt, in dem Textinformationen angezeigt werden, eine Frage gestellt wird und der Benutzer mithilfe von drei Schaltflächen die Frage beantworten kann.  
  
 ![Ein Textverarbeitungs Dialogfeld, in dem Sie gefragt werden, ob Sie die Änderungen am Dokument speichern möchten, bevor die Anwendung geschlossen wird.](./media/dialog-boxes-overview/word-processor-dialog.png)  
  
 Um ein Meldungs Feld zu erstellen, verwenden Sie die- <xref:System.Windows.MessageBox> Klasse. <xref:System.Windows.MessageBox>mithilfe von Code wie dem folgenden können Sie das Meldungs Feld Text, den Titel, das Symbol und die Schaltflächen konfigurieren.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxconfigurecodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxconfigurecodebehind)]  
  
 Um ein Meldungs Feld anzuzeigen, wird die- `static` <xref:System.Windows.MessageBox.Show%2A> Methode aufgerufen, wie im folgenden Code gezeigt.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowcodebehind)]  
  
 Wenn Code, der ein Meldungsfeld anzeigt, die Entscheidung des Benutzers (welche Schaltfläche angeklickt wurde) erkennen und verarbeiten muss, kann der Code das Ergebnis des Meldungsfelds überprüfen, wie im folgenden Code gezeigt.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowandresultcodebehind1)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowandresultcodebehind1)]  
  
 Weitere Informationen zum Verwenden von Meldungs Feldern finden Sie unter Beispiel für <xref:System.Windows.MessageBox> [MessageBox](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/MessageBox)und [Dialog Feld](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox).  
  
 Obwohl <xref:System.Windows.MessageBox> möglicherweise eine einfache Dialogfeld-Benutzerumgebung bietet, ist der Vorteil von, <xref:System.Windows.MessageBox> dass der einzige Typ von Fenstern ist, der von Anwendungen angezeigt werden kann, die in einer teilweise vertrauenswürdigen Sicherheits Sandbox (siehe Sicherheit) ausgeführt werden (siehe [Sicherheit](../security-wpf.md)), z. b. XAML-Browser Anwendungen (XBAPs).  
  
 In den meisten Dialogfeldern werden komplexere Daten angezeigt und gesammelt als im Ergebnis eines Meldungsfelds. Dazu zählen Text, Auswahlmöglichkeiten (Kontrollkästchen), sich gegenseitig ausschließende Auswahlmöglichkeiten (Optionsfelder) und Auswahlmöglichkeiten in einer Liste (Listenfelder, Kombinationsfelder, Dropdown-Listenfelder). Windows Presentation Foundation (WPF) bietet mehrere allgemeine Dialogfelder und ermöglicht Ihnen das Erstellen eigener Dialogfelder, obwohl die Verwendung von entweder auf Anwendungen beschränkt ist, die mit voller Vertrauenswürdigkeit ausgeführt werden.  
  
<a name="Common_Dialogs"></a>
## <a name="common-dialog-boxes"></a>Allgemeine Dialogfelder  
 Windows implementiert eine Reihe von wiederverwendbaren Dialogfeldern, die allen Anwendungen gemeinsam sind, einschließlich Dialogfeldern zum Öffnen von Dateien, Speichern von Dateien und drucken. Da diese Dialogfelder durch das Betriebssystem implementiert werden, können sie von allen Anwendungen, die unter dem Betriebssystem ausgeführt werden, genutzt werden. Dies trägt zu einer konsistenten Benutzererfahrung bei: Wenn Benutzer mit der Verwendung eines durch das Betriebssystem bereitgestellten Dialogfelds in einer Anwendung vertraut sind, müssen Sie nicht lernen, wie sie dieses Dialogfeld in anderen Anwendungen verwenden. Da diese Dialogfelder für alle Anwendungen verfügbar sind und Sie bei der Bereitstellung eines konsistenten Benutzer Erlebnisses helfen, werden Sie als *Allgemeine Dialogfelder*bezeichnet.  
  
 Windows Presentation Foundation (WPF) kapselt die Dialogfelder "Datei öffnen", "Datei speichern" und "Drucken" ein und macht Sie als verwaltete Klassen verfügbar, die Sie in eigenständigen Anwendungen verwenden können. Dieses Thema enthält eine kurze Übersicht über die einzelnen Dialogfelder.  
  
<a name="Open_File_Dialog"></a>
### <a name="open-file-dialog"></a>Dialogfeld Öffnen  
 Das Dialogfeld „Datei öffnen“, das in der folgenden Abbildung gezeigt wird, wird von Funktionen zum Öffnen von Dateien verwendet, um den Namen einer zu öffnenden Datei abzurufen.  
  
 ![Ein Dialogfeld öffnen, in dem der Speicherort zum Abrufen der Datei angezeigt wird.](./media/dialog-boxes-overview/open-file-dialog-box.png)  
  
 Das allgemeine Dialogfeld Datei öffnen wird als <xref:Microsoft.Win32.OpenFileDialog> -Klasse implementiert und befindet sich im- <xref:Microsoft.Win32> Namespace. Im folgenden Code wird gezeigt, wie ein solches Dialogfeld erstellt, konfiguriert und angezeigt und wie das Ergebnis verarbeitet wird.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#openfiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#openfiledialogboxcodebehind)]  
  
 Weitere Informationen zum Dialogfeld Datei öffnen finden Sie unter <xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType> .  
  
> [!NOTE]
> <xref:Microsoft.Win32.OpenFileDialog>kann verwendet werden, um Dateinamen von Anwendungen, die mit teilweiser Vertrauenswürdigkeit ausgeführt werden (siehe [Sicherheit](../security-wpf.md)), sicher abzurufen.  
  
<a name="Save_File_Dialog"></a>
### <a name="save-file-dialog-box"></a>Datei speichern (Dialogfeld)  
 Das Dialogfeld „Datei speichern“, das in der folgenden Abbildung gezeigt wird, wird von Funktionen zum Speichern von Dateien verwendet, um den Namen einer zu speichernden Datei abzurufen.  
  
 ![Das Dialogfeld Speichern unter zeigt den Speicherort zum Speichern der Datei an.](./media/dialog-boxes-overview/save-file-dialog-box.png)  
  
 Das Dialogfeld Datei speichern wird als <xref:Microsoft.Win32.SaveFileDialog> -Klasse implementiert und befindet sich im- <xref:Microsoft.Win32> Namespace. Im folgenden Code wird gezeigt, wie ein solches Dialogfeld erstellt, konfiguriert und angezeigt und wie das Ergebnis verarbeitet wird.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#savefiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#savefiledialogboxcodebehind)]  
  
 Weitere Informationen zum Dialogfeld Datei speichern finden Sie unter <xref:Microsoft.Win32.SaveFileDialog?displayProperty=nameWithType> .  
  
<a name="Print_Dialog"></a>
### <a name="print-dialog-box"></a>Dialogfeld Drucken

Das Dialogfeld „Drucken“, das in der folgenden Abbildung gezeigt wird, wird von Funktionen zum Drucken verwendet, um den Drucker auszuwählen und zu konfigurieren, auf dem der Benutzer Daten ausgeben möchte.  
  
![Screenshot, der das Dialogfeld "Drucken" anzeigt.](./media/dialog-boxes-overview/print-data-dialog-box.png)  
  
Das Dialogfeld allgemeiner Druck wird als <xref:System.Windows.Controls.PrintDialog> -Klasse implementiert und befindet sich im- <xref:System.Windows.Controls> Namespace. Im folgenden Code wird gezeigt, wie ein solches Dialogfeld erstellt, konfiguriert und angezeigt wird.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#printdialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#printdialogboxcodebehind)]  
  
 Weitere Informationen zum Dialogfeld Drucken finden Sie unter <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> . Ausführliche Erläuterungen zum Drucken in WPF finden Sie unter [Übersicht über das Drucken](../advanced/printing-overview.md).  
  
<a name="Custom_Dialog_Boxes"></a>
## <a name="custom-dialog-boxes"></a>Benutzerdefinierte Dialogfelder

Obwohl Standarddialogfelder hilfreich sind und nach Möglichkeit verwendet werden sollten, unterstützen sie nicht die Anforderungen von domänenspezifischen Dialogfeldern. In diesen Fällen müssen Sie eigene Dialogfelder erstellen. Wie später ersichtlich wird, ist ein Dialogfeld ein Fenster mit besonderen Verhaltensweisen. <xref:System.Windows.Window>implementiert diese Verhaltensweisen. Folglich verwenden Sie, <xref:System.Windows.Window> um benutzerdefinierte modale und nicht modale Dialogfelder zu erstellen.  
  
<a name="Creating_a_Modal_Custom_Dialog_Box"></a>
### <a name="creating-a-modal-custom-dialog-box"></a>Erstellen eines modalen benutzerdefinierten Dialog Felds

In diesem Thema <xref:System.Windows.Window> wird gezeigt, wie mithilfe von eine typische modale Dialogfeld Implementierung mithilfe des `Margins` Dialog Felds als Beispiel erstellt wird (siehe Beispiel für ein [Dialogfeld](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)). Das `Margins` Dialogfeld wird in der folgenden Abbildung dargestellt.  
  
 ![Ein Seitenränder-Dialogfeld mit Feldern zum Definieren des linken und oberen Rands, des rechten Rands und des unteren Rands.](./media/dialog-boxes-overview/margin-size-dialog-box.png)  
  
#### <a name="configuring-a-modal-dialog-box"></a>Konfigurieren eines modalen Dialog Felds

Die Benutzeroberfläche für ein normales Dialogfeld enthält Folgendes:  
  
- Die verschiedenen Steuerelemente, die zum Erfassen der gewünschten Daten erforderlich sind.  
  
- Eine Schaltfläche " **OK** ", auf die Benutzer klicken, um das Dialogfeld zu schließen, zur Funktion zurückzukehren und die Verarbeitung fortzusetzen.  
  
- Eine Schaltfläche **Abbrechen** , auf die Benutzer klicken, um das Dialogfeld zu schließen und die Funktion aus der weiteren Verarbeitung zu beenden.  
  
- Die Schaltfläche **Schließen** in der Titelleiste.  
  
- Symbol  
  
- Schaltflächen zum **minimieren**, **maximieren**und **Wiederherstellen** .  
  
- Ein **System** Menü zum minimieren, maximieren, wiederherstellen und Schließen des Dialog Felds.  
  
- Eine Position oberhalb und in der Mitte des Fensters, das das Dialogfeld geöffnet hat.  
  
- Die Möglichkeit, nach Möglichkeit die Größe der Größe zu ändern, um zu verhindern, dass das Dialogfeld zu klein ist, und dem Benutzer eine nützliche Standardgröße bereitzustellen. Hierfür müssen Sie sowohl die Standard-als auch die minimal-Dimension festlegen.  
  
- ESC-Taste als Tastenkombination, die bewirkt, dass die Schaltfläche **Abbrechen** gedrückt wird. Dies erreichen Sie, indem Sie die- <xref:System.Windows.Controls.Button.IsCancel%2A> Eigenschaft der Schaltfläche **Abbrechen** auf festlegen `true` .  
  
- Die EINGABETASTE (oder Rückgabetaste) als Tastenkombination, die bewirkt, dass die Schaltfläche **OK** gedrückt wird. Hierzu legen Sie die- <xref:System.Windows.Controls.Button.IsDefault%2A> Eigenschaft der Schaltfläche **OK** fest `true` .  
  
Im folgenden Code wird diese Konfiguration veranschaulicht.  
  
[!code-xaml[MarginsDialogBox XAML file](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml?range=1-16,106-112)]  

[!code-csharp[MarginsDialogBox C# code-behind](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-12,67-68)]
[!code-vb[MarginsDialogBox VB code-behind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-11,61-62)]  
  
Die Benutzererfahrung eines Dialogfelds setzt sich auch in der Menüleiste des Fensters fort, das das Dialogfeld öffnet. Wenn ein Menüelement eine Funktion ausführt, die eine Benutzerinteraktion über ein Dialogfeld benötigt, bevor die Funktion fortfahren kann, weist das Menüelement für die Funktion Auslassungszeichen im Header auf, wie nachfolgend gezeigt.  
  
[!code-xaml[Menu bar of MainWindow.Xaml file](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#L26-L27)]  
  
Wenn ein Menüelement eine Funktion ausführt, die ein Dialogfeld anzeigt, das ohne Benutzerinteraktion auskommt, z. B. das Dialogfeld „Info“, werden die Auslassungszeichen nicht benötigt.  
  
#### <a name="opening-a-modal-dialog-box"></a>Öffnen eines modalen Dialog Felds

Ein Dialogfeld wird üblicherweise als Ergebnis des Vorgangs angezeigt, bei dem ein Benutzer ein Menüelement auswählt, um eine domänenspezifische Funktion auszuführen, z. B. das Festlegen der Ränder eines Dokuments in einem Textverarbeitungsprogramm. Das Anzeigen eines Fensters als Dialogfeld ähnelt dem Anzeigen eines normalen Fensters, benötigt jedoch eine zusätzliche dialogfeldspezifische Konfiguration. Der vollständige Vorgang des Instanziierens, Konfigurierens und Öffnens eines Dialogfelds wird im folgenden Code gezeigt.  
  
[!code-csharp[Opening a modal dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-11,78-88,193-195)]
[!code-vb[Opening a modal dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,58-67,130-132)]  

Hier übergibt der Code Standardinformationen (die aktuellen Ränder) an das Dialogfeld. Außerdem wird die- <xref:System.Windows.Window.Owner%2A?displayProperty=nameWithType> Eigenschaft mit einem Verweis auf das Fenster, das das Dialogfeld anzeigt, festgelegt. Im Allgemeinen sollten Sie immer den Besitzer für ein Dialogfeld festlegen, um Verhalten im Zusammenhang mit dem Fenster Zustand bereitzustellen, die für alle Dialogfelder gelten (Weitere Informationen finden Sie unter [Übersicht über WPF-Fenster](wpf-windows-overview.md) ).

> [!NOTE]
> Sie müssen einen Besitzer angeben, um die Automatisierung der Benutzeroberfläche (UI) für Dialogfelder zu unterstützen (siehe [Übersicht über](../../ui-automation/ui-automation-overview.md)die Benutzeroberflächen Automatisierung).

Nachdem das Dialogfeld konfiguriert wurde, wird es modal durch Aufrufen der- <xref:System.Windows.Window.ShowDialog%2A> Methode angezeigt.  
  
#### <a name="validating-user-provided-data"></a>Überprüfen der vom Benutzer bereitgestellten Daten

Wenn ein Dialogfeld geöffnet wird und der Benutzer die benötigten Daten zur Verfügung stellt, ist ein Dialogfeld aus folgenden Gründen dafür verantwortlich, dass die bereitgestellten Daten gültig sind:  
  
- Aus Gründen der Datensicherheit sollten alle Eingaben überprüft werden.  
  
- Aus domänenspezifischer Sicht verhindert die Datenvalidierung, dass fehlerhafte Daten vom Code verarbeitet werden, was zum Auslösen von Ausnahmen führen kann.  
  
- Aus Gründen der Benutzererfahrung kann ein Dialogfeld dazu beitragen, Benutzern zu helfen, indem ihnen gezeigt wird, welche der von ihnen eingegebenen Daten ungültig sind.  
  
- Unter Leistungsaspekten betrachtet, kann die Datenvalidierung in einer Anwendung mit mehreren Ebenen die Anzahl von Roundtrips zwischen der Client- und der Anwendungsebene vermindern, insbesondere, wenn die Anwendung aus Webdiensten oder serverbasierten Datenbanken besteht.  

Um ein gebundenes Steuerelement in WPF zu validieren, müssen Sie eine Validierungs Regel definieren und der Bindung zuordnen. Eine Validierungs Regel ist eine benutzerdefinierte Klasse, die von abgeleitet wird <xref:System.Windows.Controls.ValidationRule> . Das folgende Beispiel zeigt eine Validierungs Regel, `MarginValidationRule` die überprüft, ob ein gebundener Wert eine ist <xref:System.Double> und innerhalb eines angegebenen Bereichs liegt.  

[!code-csharp[Margin validation rules](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginValidationRule.cs)]
[!code-vb[Margin validation rules](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginValidationRule.vb)]  

In diesem Code wird die Validierungs Logik einer Validierungs Regel durch Überschreiben der- <xref:System.Windows.Controls.ValidationRule.Validate%2A> Methode implementiert, die die Daten überprüft und ein entsprechendes-Element zurückgibt <xref:System.Windows.Controls.ValidationResult> .  

Um die Validierungsregel dem gebundenen Steuerelement zuzuordnen, wird das folgende Markup verwendet.  
  
[!code-xaml[Associating a validation rule with a control](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml?range=1-16,57-68,111-112)]

Nachdem die Validierungs Regel zugeordnet wurde, wird Sie von WPF automatisch angewendet, wenn Daten in das gebundene Steuerelement eingegeben werden. Wenn ein Steuerelement ungültige Daten enthält, zeigt WPF einen roten Rahmen um das ungültige Steuerelement an, wie in der folgenden Abbildung dargestellt.  
  
![Ein Seitenränder-Dialogfeld mit einem roten Rahmen um den ungültigen Wert für den linken Rand.](./media/dialog-boxes-overview/invalid-left-margin-dialog.png)  

WPF schränkt einen Benutzer nicht auf das ungültige Steuerelement ein, bis Sie gültige Daten eingegeben haben. Das wird als gutes Verhalten für ein Dialogfeld verstanden: Benutzer sollten in einem Dialogfeld frei durch die Steuerelemente navigieren können, unabhängig davon, ob die Daten gültig sind. Dies bedeutet jedoch, dass ein Benutzer ungültige Daten eingeben und auf die Schaltfläche " **OK** " klicken kann. Aus diesem Grund muss der Code auch alle Steuerelemente in einem Dialogfeld validieren, wenn die Schaltfläche " **OK** " durch die Behandlung des-Ereignisses gedrückt wird <xref:System.Windows.Controls.Primitives.ButtonBase.Click> .  
  
[!code-csharp[Validating all controls in a dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,26-29,33-68)]
[!code-vb[Validating all controls in a dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27-29,33-62)]  

Dieser Code listet alle Abhängigkeits Objekte in einem Fenster auf und, wenn eine ungültig ist (wie von zurückgegeben), <xref:System.Windows.Controls.Validation.GetHasError%2A> erhält das ungültige Steuerelement den Fokus, die `IsValid` Methode gibt zurück `false` , und das Fenster wird als ungültig betrachtet.  
  
Sobald ein Dialogfeld gültig ist, kann es sicher geschlossen und zurückgegeben werden. Als Teil des Rückgabevorgangs muss es ein Ergebnis an die aufrufende Funktion zurückgeben.  
  
#### <a name="setting-the-modal-dialog-result"></a>Festlegen des modalen Dialog Ergebnisses

Das Öffnen eines Dialog Felds mit <xref:System.Windows.Window.ShowDialog%2A> ist im Grunde das Aufrufen einer Methode: der Code, der das Dialogfeld mithilfe von warte Vorgängen geöffnet hat, wird <xref:System.Windows.Window.ShowDialog%2A> zurückgegeben <xref:System.Windows.Window.ShowDialog%2A> . Wenn <xref:System.Windows.Window.ShowDialog%2A> zurückgibt, muss der Code, der ihn aufgerufen hat, entscheiden, ob die Verarbeitung fortgesetzt oder die Verarbeitung beendet werden soll, je nachdem, ob der Benutzer die Schaltfläche **OK** oder die Schaltfläche **Abbrechen** gedrückt hat Um diese Entscheidung zu vereinfachen, muss das Dialogfeld die Auswahl des Benutzers als Wert zurückgeben, der <xref:System.Boolean> von der-Methode zurückgegeben wird <xref:System.Windows.Window.ShowDialog%2A> .  

Wenn auf die Schaltfläche " **OK** " geklickt wird, <xref:System.Windows.Window.ShowDialog%2A> sollte zurückgeben `true` . Dies wird erreicht, indem die- <xref:System.Windows.Window.DialogResult%2A> Eigenschaft des Dialog Felds festgelegt wird, wenn auf die Schaltfläche **OK** geklickt wird.  

[!code-csharp[Responding to the OK button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,25-27,32-33,67-68)]
[!code-vb[Responding to the OK button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27,31-33,61-62)]  

Beachten Sie, dass das Festlegen der- <xref:System.Windows.Window.DialogResult%2A> Eigenschaft auch bewirkt, dass das Fenster automatisch geschlossen wird, wodurch die Notwendigkeit verringert wird, explizit aufzurufen <xref:System.Windows.Window.Close%2A> .  
  
Wenn auf die Schaltfläche **Abbrechen** geklickt wird, <xref:System.Windows.Window.ShowDialog%2A> sollte zurückgeben `false` . Dies erfordert auch das Festlegen der- <xref:System.Windows.Window.DialogResult%2A> Eigenschaft.  
  
[!code-csharp[Responding to the Cancel button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,19-24,67-68)]
[!code-vb[Responding to the Cancel button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,22-25,61-62)]  

Wenn die-Eigenschaft einer Schaltfläche <xref:System.Windows.Controls.Button.IsCancel%2A> auf festgelegt ist `true` und der Benutzer entweder die Schaltfläche **Abbrechen** oder die ESC-Taste drückt, <xref:System.Windows.Window.DialogResult%2A> wird automatisch auf festgelegt `false` . Das folgende Markup hat denselben Effekt wie der vorangehende Code, ohne dass das-Ereignis behandelt werden muss <xref:System.Windows.Controls.Primitives.ButtonBase.Click> .  
  
[!code-xaml[Markup instead of handling the Click event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#L109-L109)]  

Ein Dialogfeld wird automatisch zurückgegeben, `false` Wenn ein Benutzer die Schaltfläche **Schließen** in der Titelleiste drückt oder das Menü Element **Schließen** im Menü **System** auswählt.  

#### <a name="processing-data-returned-from-a-modal-dialog-box"></a>Verarbeiten der von einem modalen Dialogfeld zurückgegebenen Daten  

Wenn <xref:System.Windows.Window.DialogResult%2A> von einem Dialogfeld festgelegt wird, kann die Funktion, die es geöffnet hat, das Ergebnis des Dialog Felds erhalten, indem die-Eigenschaft überprüft wird, <xref:System.Windows.Window.DialogResult%2A> Wenn <xref:System.Windows.Window.ShowDialog%2A> zurückgibt.  
  
[!code-csharp[Processing data returned from the modal dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,77-79,89-96,194-195)]
[!code-vb[Processing data returned from the modal dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,58,69-73,131-132)]

Wenn das Dialog Ergebnis ist `true` , verwendet die Funktion dies als Hinweis, um die vom Benutzer bereitgestellten Daten abzurufen und zu verarbeiten.  
  
> [!NOTE]
> Nachdem <xref:System.Windows.Window.ShowDialog%2A> zurückgegeben wurde, kann ein Dialogfeld nicht erneut geöffnet werden. Stattdessen müssen Sie eine neue Instanz erstellen.

Wenn das Dialog Ergebnis ist `false` , sollte die Funktion die Verarbeitung entsprechend beenden.  
  
<a name="Creating_a_Modeless_Custom_Dialog_Box"></a>
### <a name="creating-a-modeless-custom-dialog-box"></a>Erstellen eines nicht modalem benutzerdefinierten Dialog Felds

Ein nicht modales Dialogfeld, z. B. das in der folgenden Abbildung dargestellte Dialogfeld „Suchen“, besitzt dasselbe grundlegende Aussehen wie das modale Dialogfeld.  

![Screenshot, der das Dialogfeld Suchen anzeigt](./media/dialog-boxes-overview/find-modeless-dialog-box.png)  

Allerdings ist das Verhalten etwas anders, wie in den folgenden Abschnitten beschrieben wird.  
  
#### <a name="opening-a-modeless-dialog-box"></a>Öffnen eines nicht modalem Dialog Felds

Ein nicht modalem Dialogfeld wird durch Aufrufen der- <xref:System.Windows.Window.Show%2A> Methode geöffnet.  

[!code-xaml[XAML to define a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#L21-L22)]  

[!code-csharp[Opening a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,65-76,194-195)]
[!code-vb[Openng a modeless dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,18-23,131,132)]  

Im Gegensatz zu <xref:System.Windows.Window.ShowDialog%2A> wird <xref:System.Windows.Window.Show%2A> sofort zurückgegeben. Dementsprechend kann das aufrufende Fenster nicht erkennen, wann das nicht modale Dialogfeld geschlossen wird, und weiß deshalb auch nicht, wann es ein Dialogfeldergebnis überprüfen oder Daten vom Dialogfeld zur weiteren Verarbeitung abrufen soll. Stattdessen muss vom Dialogfeld eine andere Möglichkeit erstellt werden, um Daten an das aufrufende Fenster zur Verarbeitung zurückzugeben.  
  
#### <a name="processing-data-returned-from-a-modeless-dialog-box"></a>Verarbeiten der von einem nicht modalem Dialogfeld zurückgegebenen Daten  

In diesem Beispiel `FindDialogBox` gibt möglicherweise ein oder mehrere Suchergebnisse an das Hauptfenster zurück, abhängig vom gesuchten Text ohne bestimmte Häufigkeit. Wie ein modales Dialogfeld kann auch ein nicht modales Dialogfeld Ergebnisse mithilfe von Eigenschaften zurückgeben. Das Fenster, das Besitzer des Dialogfelds ist, muss jedoch wissen, wann es diese Eigenschaften überprüfen soll. Diese Funktionalität kann z. B. dadurch aktiviert werden, dass das Dialogfeld ein Ereignis implementiert, das jedes Mal ausgelöst wird, wenn Text gefunden wird. `FindDialogBox`implementiert `TextFoundEvent` zu diesem Zweck, der zuerst einen Delegaten erfordert.  

[!code-csharp[The TextFoundEventHandler delegate](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/TextFoundEventHandler.cs)]
[!code-vb[The TextFoundEventHandler delegate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/TextFoundEventHandler.vb)]  

Mithilfe des-Delegaten `TextFoundEventHandler` `FindDialogBox` implementiert `TextFoundEvent` .
  
[!code-csharp[The TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-17,125-126)]
[!code-vb[The TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-15,102-103)]

Folglich `Find` kann das-Ereignis durch das Auftreten eines Suchergebnisses erhöhen.  
  
[!code-csharp[Raising the TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,50-52,91-94,124-127)]
[!code-vb[Raising the TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,15,60-64,102-103)]  

Das Besitzerfenster muss anschließend bei diesem Ereignis registriert werden und es behandeln.

[!code-csharp[Registering and handling the event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,184-195)]
[!code-vb[Registering and handling the event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,126-132)]  

#### <a name="closing-a-modeless-dialog-box"></a>Schließen eines nicht modalem Dialog Felds

Da <xref:System.Windows.Window.DialogResult%2A> nicht festgelegt werden muss, kann ein nicht modalem Dialogfeld mithilfe von System Bereitstellungs Mechanismen geschlossen werden, einschließlich der folgenden:  
  
- Klicken Sie in der Titelleiste auf die Schaltfläche **Schließen** .  
  
- Drücken von ALT+F4.  
  
- Wählen Sie im Menü **System** die Option **Schließen** aus.  
  
Der Code kann auch aufgerufen werden, <xref:System.Windows.Window.Close%2A> Wenn auf die Schaltfläche **Schließen** geklickt wird.  

[!code-csharp[Calling the Close method](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,119-126)]
[!code-vb[Calling the Close method](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,99-103)]  

## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Popups](../controls/popup-overview.md)
- [Beispiel für ein Dialogfeld](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)
