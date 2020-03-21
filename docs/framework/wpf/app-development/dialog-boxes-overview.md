---
title: Übersicht über Dialogfelder
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
ms.openlocfilehash: c98d6a45d151d4b683a21e48eaeb5f4a19eaadb1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187456"
---
# <a name="dialog-boxes-overview"></a>Dialogfelder im Überblick
Eigenständige Anwendungen verfügen in der Regel über ein Hauptfenster, das sowohl die Hauptdaten [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] anzeigt, über die die Anwendung arbeitet, als auch die Funktionalität für die Verarbeitung dieser Daten über Mechanismen wie Menüleisten, Symbolleisten und Statusleisten verfügbar macht. Eine nicht triviale Anwendung kann auch zusätzliche Fenster anzeigen, um Folgendes auszuführen:  
  
- Spezifische Informationen für Benutzer anzeigen.  
  
- Informationen von Benutzern erfassen.  
  
- Informationen sowohl anzeigen als auch erfassen.  
  
 Diese Fenstertypen werden als *Dialogfelder*bezeichnet, und es gibt zwei Typen: modal und modeless.  
  
 Ein *modales* Dialogfeld wird von einer Funktion angezeigt, wenn die Funktion zusätzliche Daten von einem Benutzer benötigt, um fortzufahren. Da die Funktion beim Erfassen der Daten vom modalen Dialogfeld abhängig ist, verhindert das modale Dialogfeld auch, dass der Benutzer andere Fenster in der Anwendung aktiviert, während das Dialogfeld geöffnet bleibt. In den meisten Fällen ermöglicht ein modales Dialogfeld einem Benutzer, zu signalisieren, wenn er mit dem modalen Dialogfeld fertig ist, indem er entweder eine **SCHALTFLÄCHE OK** oder **Abbrechen** drückt. Durch Drücken der **Schaltfläche OK** wird angezeigt, dass ein Benutzer Daten eingegeben hat und möchte, dass die Funktion mit diesen Daten weiterverarbeitet wird. Durch Drücken der **Schaltfläche Abbrechen** wird angezeigt, dass ein Benutzer die Ausführung der Funktion ganz beenden möchte. Die häufigsten Beispiele für modale Dialogfelder sind das Öffnen, Speichern und Drucken von Daten.  
  
 Ein *modusloses* Dialogfeld hindert einen Benutzer hingegen nicht daran, andere Fenster zu aktivieren, während es geöffnet ist. Wenn ein Benutzer z. B. Vorkommen eines bestimmten Worts in einem Dokument finden möchte, wird in einem Hauptfenster oft ein Dialogfeld geöffnet, um den Benutzer zu fragen, nach welchem Wort er sucht. Da die Suche nach einem Wort einen Benutzer aber nicht an der Bearbeitung des Dokuments hindert, muss das Dialogfeld nicht unbedingt modal sein. Ein modusloses Dialogfeld stellt zumindest eine Schaltfläche **Schließen** bereit, um das Dialogfeld zu schließen, und kann zusätzliche Schaltflächen zum Ausführen bestimmter Funktionen bereitstellen, z. B. eine Schaltfläche **Weiter suchen,** um das nächste Wort zu finden, das den Suchkriterien einer Wortsuche entspricht.  
  
 Mit Windows Presentation Foundation (WPF) können Sie verschiedene Arten von Dialogfeldern erstellen, z. B. Meldungsfelder, allgemeine Dialogfelder und benutzerdefinierte Dialogfelder. In diesem Thema werden die einzelnen Themen erläutert, und das [Dialogfeldbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox) enthält passende Beispiele.  

<a name="Message_Boxes"></a>
## <a name="message-boxes"></a>Meldungsfelder  
 Ein *Meldungsfeld* ist ein Dialogfeld, das verwendet werden kann, um Textinformationen anzuzeigen und Benutzern zu ermöglichen, Entscheidungen mit Schaltflächen zu treffen. In der folgenden Abbildung ist ein Meldungsfeld dargestellt, in dem Textinformationen angezeigt werden, eine Frage gestellt wird und der Benutzer mithilfe von drei Schaltflächen die Frage beantworten kann.  
  
 ![In einem Dialogfeld für Wordprocessor wird gefragt, ob Sie die Änderungen am Dokument speichern möchten, bevor die Anwendung geschlossen wird.](./media/dialog-boxes-overview/word-processor-dialog.png)  
  
 Um ein Meldungsfeld zu <xref:System.Windows.MessageBox> erstellen, verwenden Sie die Klasse. <xref:System.Windows.MessageBox>können Sie den Meldungsfeldtext, Titel, Symbol und Schaltflächen mithilfe von Code wie dem folgenden konfigurieren.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxconfigurecodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxconfigurecodebehind)]  
  
 Um ein Meldungsfeld anzuzeigen, rufen Sie die `static` <xref:System.Windows.MessageBox.Show%2A> Methode auf, wie im folgenden Code gezeigt.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowcodebehind)]  
  
 Wenn Code, der ein Meldungsfeld anzeigt, die Entscheidung des Benutzers (welche Schaltfläche angeklickt wurde) erkennen und verarbeiten muss, kann der Code das Ergebnis des Meldungsfelds überprüfen, wie im folgenden Code gezeigt.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowandresultcodebehind1)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowandresultcodebehind1)]  
  
 Weitere Informationen zur Verwendung von <xref:System.Windows.MessageBox>Meldungsfeldern finden Sie unter , [MessageBox Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/MessageBox)und [Dialog Box Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox).  
  
 Obwohl <xref:System.Windows.MessageBox> eine einfache Benutzererfahrung im Dialogfeld <xref:System.Windows.MessageBox> möglich ist, ist der Vorteil der Verwendung der einzige Fenstertyp, der von Anwendungen angezeigt werden kann, die in einer teilweise vertrauenswürdigen Sicherheitssandbox ausgeführt werden (siehe [Sicherheit](../security-wpf.md)), z. B. XAML-Browseranwendungen (XBAPs).  
  
 In den meisten Dialogfeldern werden komplexere Daten angezeigt und gesammelt als im Ergebnis eines Meldungsfelds. Dazu zählen Text, Auswahlmöglichkeiten (Kontrollkästchen), sich gegenseitig ausschließende Auswahlmöglichkeiten (Optionsfelder) und Auswahlmöglichkeiten in einer Liste (Listenfelder, Kombinationsfelder, Dropdown-Listenfelder). Für diese bietet Windows Presentation Foundation (WPF) mehrere allgemeine Dialogfelder und ermöglicht es Ihnen, eigene Dialogfelder zu erstellen, obwohl die Verwendung von beiden auf Anwendungen beschränkt ist, die mit voller Vertrauenswürdigkeit ausgeführt werden.  
  
<a name="Common_Dialogs"></a>
## <a name="common-dialog-boxes"></a>Gemeinsame Dialogfelder  
 Windows implementiert eine Vielzahl wiederverwendbarer Dialogfelder, die allen Anwendungen gemeinsam sind, einschließlich Dialogfeldern zum Öffnen von Dateien, Speichern von Dateien und Drucken. Da diese Dialogfelder durch das Betriebssystem implementiert werden, können sie von allen Anwendungen, die unter dem Betriebssystem ausgeführt werden, genutzt werden. Dies trägt zu einer konsistenten Benutzererfahrung bei: Wenn Benutzer mit der Verwendung eines durch das Betriebssystem bereitgestellten Dialogfelds in einer Anwendung vertraut sind, müssen Sie nicht lernen, wie sie dieses Dialogfeld in anderen Anwendungen verwenden. Da diese Dialogfelder für alle Anwendungen verfügbar sind und eine konsistente Benutzererfahrung bieten, werden sie als *allgemeine Dialogfelder*bezeichnet.  
  
 Windows Presentation Foundation (WPF) kapselt die geöffnete Datei, speichert Die Datei und druckt allgemeine Dialogfelder und macht sie als verwaltete Klassen verfügbar, die Sie in eigenständigen Anwendungen verwenden können. Dieses Thema enthält eine kurze Übersicht über die einzelnen Dialogfelder.  
  
<a name="Open_File_Dialog"></a>
### <a name="open-file-dialog"></a>Dialogmittum "Datei öffnen"  
 Das Dialogfeld „Datei öffnen“, das in der folgenden Abbildung gezeigt wird, wird von Funktionen zum Öffnen von Dateien verwendet, um den Namen einer zu öffnenden Datei abzurufen.  
  
 ![Ein Dialogfeld Öffnen, in dem der Speicherort zum Abrufen der Datei angezeigt wird.](./media/dialog-boxes-overview/open-file-dialog-box.png)  
  
 Das allgemeine Dialogfeld für offene <xref:Microsoft.Win32.OpenFileDialog> Dateien wird als <xref:Microsoft.Win32> Klasse implementiert und befindet sich im Namespace. Im folgenden Code wird gezeigt, wie ein solches Dialogfeld erstellt, konfiguriert und angezeigt und wie das Ergebnis verarbeitet wird.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#openfiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#openfiledialogboxcodebehind)]  
  
 Weitere Informationen zum Dialogfeld "Offene <xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>Datei" finden Sie unter .  
  
> [!NOTE]
> <xref:Microsoft.Win32.OpenFileDialog>kann verwendet werden, um Dateinamen sicher von Anwendungen abzurufen, die mit teilweiser Vertrauenswürdigkeit ausgeführt werden (siehe [Sicherheit](../security-wpf.md)).  
  
<a name="Save_File_Dialog"></a>
### <a name="save-file-dialog-box"></a>Datei speichern (Dialogfeld)  
 Das Dialogfeld „Datei speichern“, das in der folgenden Abbildung gezeigt wird, wird von Funktionen zum Speichern von Dateien verwendet, um den Namen einer zu speichernden Datei abzurufen.  
  
 ![Ein Dialogfeld Speichern unter, in dem der Speicherort für die Datei angezeigt wird.](./media/dialog-boxes-overview/save-file-dialog-box.png)  
  
 Das allgemeine Dialogfeld Datei speichern <xref:Microsoft.Win32.SaveFileDialog> wird als Klasse <xref:Microsoft.Win32> implementiert und befindet sich im Namespace. Im folgenden Code wird gezeigt, wie ein solches Dialogfeld erstellt, konfiguriert und angezeigt und wie das Ergebnis verarbeitet wird.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#savefiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#savefiledialogboxcodebehind)]  
  
 Weitere Informationen zum Dialogfeld Datei <xref:Microsoft.Win32.SaveFileDialog?displayProperty=nameWithType>speichern finden Sie unter .  
  
<a name="Print_Dialog"></a>
### <a name="print-dialog-box"></a>Dialogfeld Drucken

Das Dialogfeld „Drucken“, das in der folgenden Abbildung gezeigt wird, wird von Funktionen zum Drucken verwendet, um den Drucker auszuwählen und zu konfigurieren, auf dem der Benutzer Daten ausgeben möchte.  
  
![Screenshot, der ein Dialogfeld Drucken anzeigt.](./media/dialog-boxes-overview/print-data-dialog-box.png)  
  
Das allgemeine Druckdialogfeld wird <xref:System.Windows.Controls.PrintDialog> als Klasse implementiert <xref:System.Windows.Controls> und befindet sich im Namespace. Im folgenden Code wird gezeigt, wie ein solches Dialogfeld erstellt, konfiguriert und angezeigt wird.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#printdialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#printdialogboxcodebehind)]  
  
 Weitere Informationen zum Druckdialogfeld <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>finden Sie unter . Ausführliche Informationen zum Drucken in WPF finden Sie unter [Druckübersicht](../advanced/printing-overview.md).  
  
<a name="Custom_Dialog_Boxes"></a>
## <a name="custom-dialog-boxes"></a>Benutzerdefinierte Dialogfelder

Obwohl Standarddialogfelder hilfreich sind und nach Möglichkeit verwendet werden sollten, unterstützen sie nicht die Anforderungen von domänenspezifischen Dialogfeldern. In diesen Fällen müssen Sie eigene Dialogfelder erstellen. Wie später ersichtlich wird, ist ein Dialogfeld ein Fenster mit besonderen Verhaltensweisen. <xref:System.Windows.Window>implementiert diese Verhaltensweisen und wird daher <xref:System.Windows.Window> verwendet, um benutzerdefinierte modale und moduslose Dialogfelder zu erstellen.  
  
<a name="Creating_a_Modal_Custom_Dialog_Box"></a>
### <a name="creating-a-modal-custom-dialog-box"></a>Erstellen eines benutzerdefinierten modalen Dialogfelds

In diesem Thema <xref:System.Windows.Window> wird gezeigt, wie Sie eine `Margins` typische modale Dialogfeldimplementierung erstellen, indem Sie das Dialogfeld als Beispiel verwenden (siehe [Dialogfeldbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)). Das `Margins` Dialogfeld wird in der folgenden Abbildung angezeigt.  
  
 ![Ein Dialogfeld Ränder mit Feldern zum Definieren des linken Rands, des oberen Rands, des rechten Rands und des unteren Rands.](./media/dialog-boxes-overview/margin-size-dialog-box.png)  
  
#### <a name="configuring-a-modal-dialog-box"></a>Konfigurieren eines modalen Dialogfelds

Die Benutzeroberfläche für ein normales Dialogfeld enthält Folgendes:  
  
- Die verschiedenen Steuerelemente, die zum Erfassen der gewünschten Daten erforderlich sind.  
  
- Eine **Schaltfläche OK,** auf die Benutzer klicken, um das Dialogfeld zu schließen, zur Funktion zurückzukehren und die Verarbeitung fortzusetzen.  
  
- Eine **Schaltfläche Abbrechen,** auf die Benutzer klicken, um das Dialogfeld zu schließen und die Funktion von der weiteren Verarbeitung zu beenden.  
  
- Eine **Schaltfläche Schließen** in der Titelleiste.  
  
- Symbol  
  
- **Minimieren**, **Maximieren**und **Wiederherstellen** von Schaltflächen.  
  
- Ein **Systemmenü** zum Minimieren, Maximieren, Wiederherstellen und Schließen des Dialogfelds.  
  
- Eine Position über und in der Mitte des Fensters, das das Dialogfeld geöffnet hat.  
  
- Die Möglichkeit, die Größe nach Möglichkeit zu ändern, um zu verhindern, dass das Dialogfeld zu klein ist, und dem Benutzer eine nützliche Standardgröße zu geben. Dies erfordert, dass Sie sowohl die Standard- als auch die Mindestbemaßung festlegen.  
  
- Die ESC-Taste als Tastenkombination, die bewirkt, dass die **Schaltfläche Abbrechen** gedrückt wird. Dazu legen Sie <xref:System.Windows.Controls.Button.IsCancel%2A> die Eigenschaft der `true`Schaltfläche **Abbrechen** auf fest.  
  
- Die ENTER-Taste (oder RETURN) als Tastenkombination, mit der die **OK-Taste** gedrückt wird. Dazu legen Sie <xref:System.Windows.Controls.Button.IsDefault%2A> die Eigenschaft der `true`Schaltfläche OK **fest.**  
  
Im folgenden Code wird diese Konfiguration veranschaulicht.  
  
[!code-xaml[MarginsDialogBox XAML file](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml?range=1-16,106-112)]  

[!code-csharp[MarginsDialogBox C# code-behind](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-12,67-68)]
[!code-vb[MarginsDialogBox VB code-behind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-11,61-62)]  
  
Die Benutzererfahrung eines Dialogfelds setzt sich auch in der Menüleiste des Fensters fort, das das Dialogfeld öffnet. Wenn ein Menüelement eine Funktion ausführt, die eine Benutzerinteraktion über ein Dialogfeld benötigt, bevor die Funktion fortfahren kann, weist das Menüelement für die Funktion Auslassungszeichen im Header auf, wie nachfolgend gezeigt.  
  
[!code-xaml[Menu bar of MainWindow.Xaml file](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#L26-L27)]  
  
Wenn ein Menüelement eine Funktion ausführt, die ein Dialogfeld anzeigt, das ohne Benutzerinteraktion auskommt, z. B. das Dialogfeld „Info“, werden die Auslassungszeichen nicht benötigt.  
  
#### <a name="opening-a-modal-dialog-box"></a>Öffnen eines modalen Dialogfelds

Ein Dialogfeld wird üblicherweise als Ergebnis des Vorgangs angezeigt, bei dem ein Benutzer ein Menüelement auswählt, um eine domänenspezifische Funktion auszuführen, z. B. das Festlegen der Ränder eines Dokuments in einem Textverarbeitungsprogramm. Das Anzeigen eines Fensters als Dialogfeld ähnelt dem Anzeigen eines normalen Fensters, benötigt jedoch eine zusätzliche dialogfeldspezifische Konfiguration. Der vollständige Vorgang des Instanziierens, Konfigurierens und Öffnens eines Dialogfelds wird im folgenden Code gezeigt.  
  
[!code-csharp[Opening a modal dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-11,78-88,193-195)]
[!code-vb[Opening a modal dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,58-67,130-132)]  

Hier übergibt der Code Standardinformationen (die aktuellen Ränder) an das Dialogfeld. Außerdem wird <xref:System.Windows.Window.Owner%2A?displayProperty=nameWithType> die Eigenschaft mit einem Verweis auf das Fenster festgelegt, das das Dialogfeld anzeigt. Im Allgemeinen sollten Sie den Besitzer immer für ein Dialogfeld festlegen, um fensterzustandsbezogene Verhaltensweisen bereitzustellen, die allen Dialogfeldern gemeinsam sind (weitere Informationen finden Sie unter [WPF Windows Overview).](wpf-windows-overview.md)

> [!NOTE]
> Sie müssen einen Besitzer bereitstellen, um die Automatisierung der Benutzeroberfläche für Dialogfelder zu unterstützen (siehe [UI Automation Overview](../../ui-automation/ui-automation-overview.md)).

Nachdem das Dialogfeld konfiguriert wurde, wird es <xref:System.Windows.Window.ShowDialog%2A> modal durch Aufrufen der Methode angezeigt.  
  
#### <a name="validating-user-provided-data"></a>Validieren von vom Benutzer bereitgestellten Daten

Wenn ein Dialogfeld geöffnet wird und der Benutzer die benötigten Daten zur Verfügung stellt, ist ein Dialogfeld aus folgenden Gründen dafür verantwortlich, dass die bereitgestellten Daten gültig sind:  
  
- Aus Gründen der Datensicherheit sollten alle Eingaben überprüft werden.  
  
- Aus domänenspezifischer Sicht verhindert die Datenvalidierung, dass fehlerhafte Daten vom Code verarbeitet werden, was zum Auslösen von Ausnahmen führen kann.  
  
- Aus Gründen der Benutzererfahrung kann ein Dialogfeld dazu beitragen, Benutzern zu helfen, indem ihnen gezeigt wird, welche der von ihnen eingegebenen Daten ungültig sind.  
  
- Unter Leistungsaspekten betrachtet, kann die Datenvalidierung in einer Anwendung mit mehreren Ebenen die Anzahl von Roundtrips zwischen der Client- und der Anwendungsebene vermindern, insbesondere, wenn die Anwendung aus Webdiensten oder serverbasierten Datenbanken besteht.  

Um ein gebundenes Steuerelement in WPF zu überprüfen, müssen Sie eine Validierungsregel definieren und der Bindung zuordnen. Eine Validierungsregel ist eine benutzerdefinierte <xref:System.Windows.Controls.ValidationRule>Klasse, die von ableitet. Das folgende Beispiel zeigt `MarginValidationRule`eine Validierungsregel, , <xref:System.Double> die überprüft, ob ein gebundener Wert a ist und sich innerhalb eines angegebenen Bereichs befindet.  

[!code-csharp[Margin validation rules](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginValidationRule.cs)]
[!code-vb[Margin validation rules](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginValidationRule.vb)]  

In diesem Code wird die Validierungslogik einer Validierungsregel durch Überschreiben der <xref:System.Windows.Controls.ValidationRule.Validate%2A> Methode <xref:System.Windows.Controls.ValidationResult>implementiert, die die Daten überprüft und eine entsprechende zurückgibt.  

Um die Validierungsregel dem gebundenen Steuerelement zuzuordnen, wird das folgende Markup verwendet.  
  
[!code-xaml[Associating a validation rule with a control](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml?range=1-16,57-68,111-112)]

Sobald die Validierungsregel zugeordnet ist, wendet WPF sie automatisch an, wenn Daten in das gebundene Steuerelement eingegeben werden. Wenn ein Steuerelement ungültige Daten enthält, zeigt WPF einen roten Rahmen um das ungültige Steuerelement an, wie in der folgenden Abbildung dargestellt.  
  
![Ein Dialogfeld Ränder mit einem roten Rahmen um den ungültigen linken Randwert.](./media/dialog-boxes-overview/invalid-left-margin-dialog.png)  

WPF beschränkt einen Benutzer erst auf das ungültige Steuerelement, wenn er gültige Daten eingegeben hat. Das wird als gutes Verhalten für ein Dialogfeld verstanden: Benutzer sollten in einem Dialogfeld frei durch die Steuerelemente navigieren können, unabhängig davon, ob die Daten gültig sind. Dies bedeutet jedoch, dass ein Benutzer ungültige Daten eingeben und die **Schaltfläche OK** drücken kann. Aus diesem Grund muss Ihr Code auch alle Steuerelemente in einem Dialogfeld <xref:System.Windows.Controls.Primitives.ButtonBase.Click> überprüfen, wenn die Schaltfläche **OK** gedrückt wird, indem das Ereignis behandelt wird.  
  
[!code-csharp[Validating all controls in a dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,26-29,33-68)]
[!code-vb[Validating all controls in a dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27-29,33-62)]  

Dieser Code zählt alle Abhängigkeitsobjekte in einem Fenster auf, und <xref:System.Windows.Controls.Validation.GetHasError%2A>falls alle ungültig sind (wie `IsValid` von `false`zurückgegeben, erhält das ungültige Steuerelement den Fokus, die Methode gibt zurück, und das Fenster wird als ungültig betrachtet.  
  
Sobald ein Dialogfeld gültig ist, kann es sicher geschlossen und zurückgegeben werden. Als Teil des Rückgabevorgangs muss es ein Ergebnis an die aufrufende Funktion zurückgeben.  
  
#### <a name="setting-the-modal-dialog-result"></a>Festlegen des modalen Dialogergebnisses

Das Öffnen eines <xref:System.Windows.Window.ShowDialog%2A> Dialogfelds ist grundsätzlich wie das Aufrufen <xref:System.Windows.Window.ShowDialog%2A> einer Methode: der Code, der das Dialogfeld mit Wartezeiten geöffnet hat, bis <xref:System.Windows.Window.ShowDialog%2A> er zurückkehrt. Bei <xref:System.Windows.Window.ShowDialog%2A> der Rückgabe muss der Code, der ihn aufgerufen hat, entscheiden, ob die Verarbeitung fortgesetzt oder die Verarbeitung beendet werden soll, je nachdem, ob der Benutzer die **Schaltfläche OK** oder die **Schaltfläche Abbrechen** gedrückt hat. Um diese Entscheidung zu erleichtern, muss das Dialogfeld <xref:System.Boolean> die Auswahl des <xref:System.Windows.Window.ShowDialog%2A> Benutzers als Wert zurückgeben, der von der Methode zurückgegeben wird.  

Wenn auf **OK** geklickt wird, <xref:System.Windows.Window.ShowDialog%2A> sollten Sie zurückkehren. `true` Dies wird erreicht, indem die <xref:System.Windows.Window.DialogResult%2A> Eigenschaft des Dialogfelds gesetzt wird, wenn auf ok geklickt wird. **OK**  

[!code-csharp[Responding to the OK button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,25-27,32-33,67-68)]
[!code-vb[Responding to the OK button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27,31-33,61-62)]  

Beachten Sie, <xref:System.Windows.Window.DialogResult%2A> dass das Festlegen der Eigenschaft auch dazu führt, <xref:System.Windows.Window.Close%2A>dass das Fenster automatisch geschlossen wird, was die Notwendigkeit des expliziten Aufrufs verringert.  
  
Wenn **Cancel** auf die Schaltfläche <xref:System.Windows.Window.ShowDialog%2A> Abbrechen `false`geklickt wird, <xref:System.Windows.Window.DialogResult%2A> sollte die Schaltfläche "Zurück" zurückgegeben werden, wodurch auch die Eigenschaft gesetzt werden muss.  
  
[!code-csharp[Responding to the Cancel button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,19-24,67-68)]
[!code-vb[Responding to the Cancel button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,22-25,61-62)]  

Wenn die <xref:System.Windows.Controls.Button.IsCancel%2A> Eigenschaft einer Schaltfläche `true` auf gesetzt ist und der Benutzer entweder <xref:System.Windows.Window.DialogResult%2A> die Schaltfläche `false` **Abbrechen** oder die ESC-Taste drückt, wird automatisch auf . Das folgende Markup hat den gleichen Effekt wie der <xref:System.Windows.Controls.Primitives.ButtonBase.Click> vorherige Code, ohne dass das Ereignis behandelt werden muss.  
  
[!code-xaml[Markup instead of handling the Click event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#L109-L109)]  

Ein Dialogfeld `false` wird automatisch zurückgegeben, wenn ein Benutzer die Schaltfläche **Schließen** in der Titelleiste drückt oder das Menüelement **Schließen** aus dem **MenüSystem** auswählt.  

#### <a name="processing-data-returned-from-a-modal-dialog-box"></a>Verarbeiten von Daten, die aus einem modalen Dialogfeld zurückgegeben werden  

Wenn <xref:System.Windows.Window.DialogResult%2A> durch ein Dialogfeld festgelegt wird, kann die Funktion, die <xref:System.Windows.Window.DialogResult%2A> sie <xref:System.Windows.Window.ShowDialog%2A> geöffnet hat, das Dialogfeldergebnis abrufen, indem sie die Eigenschaft bei der Rückgabe überprüft.  
  
[!code-csharp[Processing data returned from the modal dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,77-79,89-96,194-195)]
[!code-vb[Processing data returned from the modal dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,58,69-73,131-132)]

Wenn das Dialogergebnis ist `true`, verwendet die Funktion dies als Hinweis, um die vom Benutzer bereitgestellten Daten abzurufen und zu verarbeiten.  
  
> [!NOTE]
> Nach <xref:System.Windows.Window.ShowDialog%2A> der Rückgabe kann ein Dialogfeld nicht erneut geöffnet werden. Stattdessen müssen Sie eine neue Instanz erstellen.

Wenn das Dialogergebnis lautet, `false`sollte die Funktion die Verarbeitung entsprechend beenden.  
  
<a name="Creating_a_Modeless_Custom_Dialog_Box"></a>
### <a name="creating-a-modeless-custom-dialog-box"></a>Erstellen eines moduslosen benutzerdefinierten Dialogfelds

Ein nicht modales Dialogfeld, z. B. das in der folgenden Abbildung dargestellte Dialogfeld „Suchen“, besitzt dasselbe grundlegende Aussehen wie das modale Dialogfeld.  

![Screenshot, der ein Dialogfeld Suchen anzeigt.](./media/dialog-boxes-overview/find-modeless-dialog-box.png)  

Allerdings ist das Verhalten etwas anders, wie in den folgenden Abschnitten beschrieben wird.  
  
#### <a name="opening-a-modeless-dialog-box"></a>Öffnen eines moduslosen Dialogfelds

Ein modusloses Dialogfeld wird <xref:System.Windows.Window.Show%2A> durch Aufrufen der Methode geöffnet.  

[!code-xaml[XAML to define a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#L21-L22)]  

[!code-csharp[Opening a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,65-76,194-195)]
[!code-vb[Openng a modeless dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,18-23,131,132)]  

Im <xref:System.Windows.Window.ShowDialog%2A> <xref:System.Windows.Window.Show%2A> Gegensatz zu kehrt sofort zurück. Dementsprechend kann das aufrufende Fenster nicht erkennen, wann das nicht modale Dialogfeld geschlossen wird, und weiß deshalb auch nicht, wann es ein Dialogfeldergebnis überprüfen oder Daten vom Dialogfeld zur weiteren Verarbeitung abrufen soll. Stattdessen muss vom Dialogfeld eine andere Möglichkeit erstellt werden, um Daten an das aufrufende Fenster zur Verarbeitung zurückzugeben.  
  
#### <a name="processing-data-returned-from-a-modeless-dialog-box"></a>Verarbeiten von Daten, die aus einem moduslosen Dialogfeld zurückgegeben werden  

In diesem Beispiel `FindDialogBox` kann der ein oder mehrere Suchergebnisse an das Hauptfenster zurückgeben, je nachdem, nach dem Text gesucht wird, nach dem ohne bestimmte Häufigkeit gesucht wird. Wie ein modales Dialogfeld kann auch ein nicht modales Dialogfeld Ergebnisse mithilfe von Eigenschaften zurückgeben. Das Fenster, das Besitzer des Dialogfelds ist, muss jedoch wissen, wann es diese Eigenschaften überprüfen soll. Diese Funktionalität kann z. B. dadurch aktiviert werden, dass das Dialogfeld ein Ereignis implementiert, das jedes Mal ausgelöst wird, wenn Text gefunden wird. `FindDialogBox`implementiert die `TextFoundEvent` zu diesem Zweck, für die zunächst ein Delegierter erforderlich ist.  

[!code-csharp[The TextFoundEventHandler delegate](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/TextFoundEventHandler.cs)]
[!code-vb[The TextFoundEventHandler delegate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/TextFoundEventHandler.vb)]  

Implementiert `TextFoundEventHandler` die `FindDialogBox` mithilfe des `TextFoundEvent`Delegaten .
  
[!code-csharp[The TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-17,125-126)]
[!code-vb[The TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-15,102-103)]

Daher `Find` kann das Ereignis angezeigt werden, wenn ein Suchergebnis gefunden wird.  
  
[!code-csharp[Raising the TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,50-52,91-94,124-127)]
[!code-vb[Raising the TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,15,60-64,102-103)]  

Das Besitzerfenster muss anschließend bei diesem Ereignis registriert werden und es behandeln.

[!code-csharp[Registering and handling the event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,184-195)]
[!code-vb[Registering and handling the event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,126-132)]  

#### <a name="closing-a-modeless-dialog-box"></a>Schließen eines moduslosen Dialogfelds

Da <xref:System.Windows.Window.DialogResult%2A> kein Moduslos-Dialog eingestellt werden muss, kann ein modusloses Dialogfeld mithilfe von Systembereitstellungsmechanismen geschlossen werden, einschließlich der folgenden:  
  
- Klicken Sie auf die Schaltfläche **Schließen** in der Titelleiste.  
  
- Drücken von ALT+F4.  
  
- Wählen Sie **Schließen** aus dem **Menü System.**  
  
Alternativ kann Ihr Code <xref:System.Windows.Window.Close%2A> aufrufen, wenn auf die Schaltfläche **Schließen** geklickt wird.  

[!code-csharp[Calling the Close method](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,119-126)]
[!code-vb[Calling the Close method](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,99-103)]  

## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Popups](../controls/popup-overview.md)
- [Beispiel für ein Dialogfeld](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)
