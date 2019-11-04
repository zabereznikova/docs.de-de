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
ms.openlocfilehash: 9ec6716fefdc8de75d7e523c56ae0b3a02c8cf02
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424645"
---
# <a name="dialog-boxes-overview"></a>Übersicht über Dialog Felder
Eigenständige Anwendungen verfügen in der Regel über ein Hauptfenster, in dem die Hauptdaten angezeigt werden, über die die Anwendung ausgeführt wird, und die Funktionalität zur Verarbeitung dieser Daten über [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Mechanismen wie Menüleisten, Symbolleisten und Status leisten verfügbar macht. Eine nicht triviale Anwendung kann auch zusätzliche Fenster anzeigen, um Folgendes auszuführen:  
  
- Spezifische Informationen für Benutzer anzeigen.  
  
- Informationen von Benutzern erfassen.  
  
- Informationen sowohl anzeigen als auch erfassen.  
  
 Diese Windows-Typen werden als *Dialogfelder*bezeichnet, und es gibt zwei Typen: modale und nicht modale Typen.  
  
 Ein *modales* Dialogfeld wird von einer Funktion angezeigt, wenn die Funktion zusätzliche Daten von einem Benutzer benötigt, um den Vorgang fortzusetzen. Da die Funktion beim Erfassen der Daten vom modalen Dialogfeld abhängig ist, verhindert das modale Dialogfeld auch, dass der Benutzer andere Fenster in der Anwendung aktiviert, während das Dialogfeld geöffnet bleibt. In den meisten Fällen ermöglicht ein modales Dialogfeld einem Benutzer, zu signalisieren, wann er das modale Dialogfeld durch Drücken der Schaltfläche **OK** oder **Abbrechen** beendet hat. Wenn Sie auf die Schaltfläche **OK** klicken, wird angegeben, dass ein Benutzerdaten eingegeben hat und die Funktion die Verarbeitung mit diesen Daten fortsetzen soll. Durch Drücken der Schaltfläche **Abbrechen** wird angegeben, dass ein Benutzer die Ausführung der Funktion beenden möchte. Die häufigsten Beispiele für modale Dialogfelder sind das Öffnen, Speichern und Drucken von Daten.  
  
 Ein nicht modalem Dialogfeld verhindert hingegen nicht, *dass ein Benutzer* andere Fenster aktiviert, während er geöffnet ist. Wenn ein Benutzer z. B. Vorkommen eines bestimmten Worts in einem Dokument finden möchte, wird in einem Hauptfenster oft ein Dialogfeld geöffnet, um den Benutzer zu fragen, nach welchem Wort er sucht. Da die Suche nach einem Wort einen Benutzer aber nicht an der Bearbeitung des Dokuments hindert, muss das Dialogfeld nicht unbedingt modal sein. Bei einem nicht modalem Dialogfeld wird mindestens eine Schaltfläche zum **Schließen** des Dialog Felds bereitgestellt, und es können zusätzliche Schaltflächen zum Ausführen bestimmter Funktionen bereitgestellt werden, z. b. eine Schaltfläche " **weiter suchen** ", um das nächste Wort zu suchen, das den Suchkriterien einer Wort Suche entspricht.  
  
 Mit Windows Presentation Foundation (WPF) können Sie verschiedene Arten von Dialogfeldern erstellen, einschließlich Meldungs Feldern, allgemeiner Dialogfelder und benutzerdefinierte Dialogfelder. In diesem Thema werden die einzelnen Themen erläutert, und im [Dialog Feld Beispiel](https://go.microsoft.com/fwlink/?LinkID=159984) finden Sie entsprechende Beispiele.  

<a name="Message_Boxes"></a>   
## <a name="message-boxes"></a>Meldungs Felder  
 Ein Meldungs *Feld* ist ein Dialogfeld, das verwendet werden kann, um Textinformationen anzuzeigen und Benutzern das Treffen von Entscheidungen mit Schaltflächen zu ermöglichen. In der folgenden Abbildung ist ein Meldungsfeld dargestellt, in dem Textinformationen angezeigt werden, eine Frage gestellt wird und der Benutzer mithilfe von drei Schaltflächen die Frage beantworten kann.  
  
 ![Ein Textverarbeitungs Dialogfeld, in dem Sie gefragt werden, ob Sie die Änderungen am Dokument speichern möchten, bevor die Anwendung geschlossen wird.](./media/dialog-boxes-overview/word-processor-dialog.png)  
  
 Um ein Meldungs Feld zu erstellen, verwenden Sie die <xref:System.Windows.MessageBox>-Klasse. mit <xref:System.Windows.MessageBox> können Sie den Text, den Titel, das Symbol und die Schaltflächen der Nachricht mithilfe von Code wie dem folgenden konfigurieren.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxconfigurecodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxconfigurecodebehind)]  
  
 Um ein Meldungs Feld anzuzeigen, nennen Sie den `static`<xref:System.Windows.MessageBox.Show%2A>-Methode, wie im folgenden Code gezeigt.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowcodebehind)]  
  
 Wenn Code, der ein Meldungsfeld anzeigt, die Entscheidung des Benutzers (welche Schaltfläche angeklickt wurde) erkennen und verarbeiten muss, kann der Code das Ergebnis des Meldungsfelds überprüfen, wie im folgenden Code gezeigt.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowandresultcodebehind1)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowandresultcodebehind1)]  
  
 Weitere Informationen zum Verwenden von Meldungs Feldern finden Sie unter <xref:System.Windows.MessageBox>, [MessageBox Sample](https://go.microsoft.com/fwlink/?LinkID=160023)und [Dialog Feld Sample](https://go.microsoft.com/fwlink/?LinkID=159984).  
  
 Obwohl <xref:System.Windows.MessageBox> eine einfache Dialogfeld Benutzerumgebung anbieten können, ist der Vorteil der Verwendung von <xref:System.Windows.MessageBox>, dass die einzige Art von Fenster ist, die von Anwendungen angezeigt werden kann, die in einer teilweise vertrauenswürdigen Sicherheits Sandbox ausgeführt werden (siehe [Sicherheit](../security-wpf.md)), wie z. b. XAML-Browser. Anwendungen (XBAPs).  
  
 In den meisten Dialogfeldern werden komplexere Daten angezeigt und gesammelt als im Ergebnis eines Meldungsfelds. Dazu zählen Text, Auswahlmöglichkeiten (Kontrollkästchen), sich gegenseitig ausschließende Auswahlmöglichkeiten (Optionsfelder) und Auswahlmöglichkeiten in einer Liste (Listenfelder, Kombinationsfelder, Dropdown-Listenfelder). Windows Presentation Foundation (WPF) bietet mehrere allgemeine Dialogfelder und ermöglicht Ihnen das Erstellen eigener Dialogfelder, obwohl die Verwendung von entweder auf Anwendungen beschränkt ist, die mit voller Vertrauenswürdigkeit ausgeführt werden.  
  
<a name="Common_Dialogs"></a>   
## <a name="common-dialog-boxes"></a>Allgemeine Dialogfelder  
 Windows implementiert eine Reihe von wiederverwendbaren Dialogfeldern, die allen Anwendungen gemeinsam sind, einschließlich Dialogfeldern zum Öffnen von Dateien, Speichern von Dateien und drucken. Da diese Dialogfelder durch das Betriebssystem implementiert werden, können sie von allen Anwendungen, die unter dem Betriebssystem ausgeführt werden, genutzt werden. Dies trägt zu einer konsistenten Benutzererfahrung bei: Wenn Benutzer mit der Verwendung eines durch das Betriebssystem bereitgestellten Dialogfelds in einer Anwendung vertraut sind, müssen Sie nicht lernen, wie sie dieses Dialogfeld in anderen Anwendungen verwenden. Da diese Dialogfelder für alle Anwendungen verfügbar sind und Sie bei der Bereitstellung eines konsistenten Benutzer Erlebnisses helfen, werden Sie als *Allgemeine Dialogfelder*bezeichnet.  
  
 Windows Presentation Foundation (WPF) kapselt die Dialogfelder "Datei öffnen", "Datei speichern" und "Drucken" ein und macht Sie als verwaltete Klassen verfügbar, die Sie in eigenständigen Anwendungen verwenden können. Dieses Thema enthält eine kurze Übersicht über die einzelnen Dialogfelder.  
  
<a name="Open_File_Dialog"></a>   
### <a name="open-file-dialog"></a>Dialogfeld Öffnen  
 Das Dialogfeld „Datei öffnen“, das in der folgenden Abbildung gezeigt wird, wird von Funktionen zum Öffnen von Dateien verwendet, um den Namen einer zu öffnenden Datei abzurufen.  
  
 ![Ein Dialogfeld öffnen, in dem der Speicherort zum Abrufen der Datei angezeigt wird.](./media/dialog-boxes-overview/open-file-dialog-box.png)  
  
 Das allgemeine Dialogfeld Datei öffnen wird als <xref:Microsoft.Win32.OpenFileDialog>-Klasse implementiert und befindet sich im <xref:Microsoft.Win32>-Namespace. Im folgenden Code wird gezeigt, wie ein solches Dialogfeld erstellt, konfiguriert und angezeigt und wie das Ergebnis verarbeitet wird.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#openfiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#openfiledialogboxcodebehind)]  
  
 Weitere Informationen zum Dialogfeld Datei öffnen finden Sie unter <xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>.  
  
> [!NOTE]
> <xref:Microsoft.Win32.OpenFileDialog> können verwendet werden, um Dateinamen von Anwendungen, die mit teilweiser Vertrauenswürdigkeit ausgeführt werden, sicher abzurufen (siehe [Sicherheit](../security-wpf.md)).  
  
<a name="Save_File_Dialog"></a>   
### <a name="save-file-dialog-box"></a>Datei speichern (Dialogfeld)  
 Das Dialogfeld „Datei speichern“, das in der folgenden Abbildung gezeigt wird, wird von Funktionen zum Speichern von Dateien verwendet, um den Namen einer zu speichernden Datei abzurufen.  
  
 ![Das Dialogfeld Speichern unter zeigt den Speicherort zum Speichern der Datei an.](./media/dialog-boxes-overview/save-file-dialog-box.png)  
  
 Das Dialogfeld Datei speichern wird als <xref:Microsoft.Win32.SaveFileDialog>-Klasse implementiert und befindet sich im <xref:Microsoft.Win32>-Namespace. Im folgenden Code wird gezeigt, wie ein solches Dialogfeld erstellt, konfiguriert und angezeigt und wie das Ergebnis verarbeitet wird.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#savefiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#savefiledialogboxcodebehind)]  
  
 Weitere Informationen zum Dialogfeld Datei speichern finden Sie unter <xref:Microsoft.Win32.SaveFileDialog?displayProperty=nameWithType>.  
  
<a name="Print_Dialog"></a>   
### <a name="print-dialog-box"></a>Dialogfeld Drucken

Das Dialogfeld „Drucken“, das in der folgenden Abbildung gezeigt wird, wird von Funktionen zum Drucken verwendet, um den Drucker auszuwählen und zu konfigurieren, auf dem der Benutzer Daten ausgeben möchte.  
  
![Screenshot, der das Dialogfeld "Drucken" anzeigt.](./media/dialog-boxes-overview/print-data-dialog-box.png)  
  
Das Dialogfeld allgemeiner Druck wird als <xref:System.Windows.Controls.PrintDialog>-Klasse implementiert und befindet sich im <xref:System.Windows.Controls>-Namespace. Im folgenden Code wird gezeigt, wie ein solches Dialogfeld erstellt, konfiguriert und angezeigt wird.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#printdialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#printdialogboxcodebehind)]  
  
 Weitere Informationen zum Dialogfeld Drucken finden Sie unter <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>. Ausführliche Erläuterungen zum Drucken in WPF finden Sie unter [Übersicht über das Drucken](../advanced/printing-overview.md).  
  
<a name="Custom_Dialog_Boxes"></a>   
## <a name="custom-dialog-boxes"></a>Benutzerdefinierte Dialogfelder

Obwohl Standarddialogfelder hilfreich sind und nach Möglichkeit verwendet werden sollten, unterstützen sie nicht die Anforderungen von domänenspezifischen Dialogfeldern. In diesen Fällen müssen Sie eigene Dialogfelder erstellen. Wie später ersichtlich wird, ist ein Dialogfeld ein Fenster mit besonderen Verhaltensweisen. <xref:System.Windows.Window> implementiert diese Verhaltensweisen und folglich verwenden Sie <xref:System.Windows.Window>, um benutzerdefinierte modale und nicht modale Dialogfelder zu erstellen.  
  
<a name="Creating_a_Modal_Custom_Dialog_Box"></a>   
### <a name="creating-a-modal-custom-dialog-box"></a>Erstellen eines modalen benutzerdefinierten Dialog Felds

In diesem Thema wird gezeigt, wie <xref:System.Windows.Window> verwendet wird, um eine typische modale Dialogfeld Implementierung zu erstellen, indem das Dialogfeld `Margins` als Beispiel verwendet wird (siehe Beispiel für ein [Dialogfeld](https://go.microsoft.com/fwlink/?LinkID=159984)). Das Dialogfeld `Margins` ist in der folgenden Abbildung dargestellt.  
  
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
  
- ESC-Taste als Tastenkombination, die bewirkt, dass die Schaltfläche **Abbrechen** gedrückt wird. Hierzu legen Sie die <xref:System.Windows.Controls.Button.IsCancel%2A>-Eigenschaft der Schaltfläche **Abbrechen** auf `true`fest.  
  
- Die EINGABETASTE (oder Rückgabetaste) als Tastenkombination, die bewirkt, dass die Schaltfläche **OK** gedrückt wird. Hierzu legen Sie die <xref:System.Windows.Controls.Button.IsDefault%2A>-Eigenschaft der Schaltfläche **OK** `true`fest.  
  
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

Hier übergibt der Code Standardinformationen (die aktuellen Ränder) an das Dialogfeld. Außerdem wird die <xref:System.Windows.Window.Owner%2A?displayProperty=nameWithType>-Eigenschaft mit einem Verweis auf das Fenster, das das Dialogfeld anzeigt, festgelegt. Im Allgemeinen sollten Sie immer den Besitzer für ein Dialogfeld festlegen, um Verhalten im Zusammenhang mit dem Fenster Zustand bereitzustellen, die für alle Dialogfelder gelten (Weitere Informationen finden Sie unter [Übersicht über WPF-Fenster](wpf-windows-overview.md) ).

> [!NOTE]
> Sie müssen einen Besitzer angeben, um die Automatisierung der Benutzeroberfläche (UI) für Dialogfelder zu unterstützen (siehe [Übersicht über](../../ui-automation/ui-automation-overview.md)die Benutzeroberflächen Automatisierung).

Nachdem das Dialogfeld konfiguriert wurde, wird es modal durch Aufrufen der <xref:System.Windows.Window.ShowDialog%2A>-Methode angezeigt.  
  
#### <a name="validating-user-provided-data"></a>Überprüfen der vom Benutzer bereitgestellten Daten

Wenn ein Dialogfeld geöffnet wird und der Benutzer die benötigten Daten zur Verfügung stellt, ist ein Dialogfeld aus folgenden Gründen dafür verantwortlich, dass die bereitgestellten Daten gültig sind:  
  
- Aus Gründen der Datensicherheit sollten alle Eingaben überprüft werden.  
  
- Aus domänenspezifischer Sicht verhindert die Datenvalidierung, dass fehlerhafte Daten vom Code verarbeitet werden, was zum Auslösen von Ausnahmen führen kann.  
  
- Aus Gründen der Benutzererfahrung kann ein Dialogfeld dazu beitragen, Benutzern zu helfen, indem ihnen gezeigt wird, welche der von ihnen eingegebenen Daten ungültig sind.  
  
- Unter Leistungsaspekten betrachtet, kann die Datenvalidierung in einer Anwendung mit mehreren Ebenen die Anzahl von Roundtrips zwischen der Client- und der Anwendungsebene vermindern, insbesondere, wenn die Anwendung aus Webdiensten oder serverbasierten Datenbanken besteht.  

Um ein gebundenes Steuerelement in WPF zu validieren, müssen Sie eine Validierungs Regel definieren und der Bindung zuordnen. Eine Validierungs Regel ist eine benutzerdefinierte Klasse, die von <xref:System.Windows.Controls.ValidationRule>abgeleitet ist. Das folgende Beispiel zeigt eine Validierungs Regel, `MarginValidationRule`, die überprüft, ob es sich bei einem gebundenen Wert um einen <xref:System.Double> handelt und innerhalb eines angegebenen Bereichs liegt.  

[!code-csharp[Margin validation rules](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginValidationRule.cs)]
[!code-vb[Margin validation rules](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginValidationRule.vb)]  

In diesem Code wird die Validierungs Logik einer Validierungs Regel durch Überschreiben der <xref:System.Windows.Controls.ValidationRule.Validate%2A>-Methode implementiert, die die Daten überprüft und eine entsprechende <xref:System.Windows.Controls.ValidationResult>zurückgibt.  

Um die Validierungsregel dem gebundenen Steuerelement zuzuordnen, wird das folgende Markup verwendet.  
  
[!code-xaml[Associating a validation rule with a control](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml?range=1-16,57-68,111-112)]

Nachdem die Validierungs Regel zugeordnet wurde, wird Sie von WPF automatisch angewendet, wenn Daten in das gebundene Steuerelement eingegeben werden. Wenn ein Steuerelement ungültige Daten enthält, zeigt WPF einen roten Rahmen um das ungültige Steuerelement an, wie in der folgenden Abbildung dargestellt.  
  
![Ein Seitenränder-Dialogfeld mit einem roten Rahmen um den ungültigen Wert für den linken Rand.](./media/dialog-boxes-overview/invalid-left-margin-dialog.png)  

WPF schränkt einen Benutzer nicht auf das ungültige Steuerelement ein, bis Sie gültige Daten eingegeben haben. Das wird als gutes Verhalten für ein Dialogfeld verstanden: Benutzer sollten in einem Dialogfeld frei durch die Steuerelemente navigieren können, unabhängig davon, ob die Daten gültig sind. Dies bedeutet jedoch, dass ein Benutzer ungültige Daten eingeben und auf die Schaltfläche " **OK** " klicken kann. Aus diesem Grund muss der Code auch alle Steuerelemente in einem Dialogfeld validieren, wenn die Schaltfläche " **OK** " gedrückt wird, indem das <xref:System.Windows.Controls.Primitives.ButtonBase.Click>-Ereignis verarbeitet wird.  
  
[!code-csharp[Validating all controls in a dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,26-29,33-68)]
[!code-vb[Validating all controls in a dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27-29,33-62)]  

Dieser Code listet alle Abhängigkeits Objekte in einem Fenster auf. Wenn eine solche ungültig ist (wie von <xref:System.Windows.Controls.Validation.GetHasError%2A>zurückgegeben, erhält das ungültige Steuerelement den Fokus, die `IsValid` Methode gibt `false`zurück, und das Fenster wird als ungültig betrachtet.  
  
Sobald ein Dialogfeld gültig ist, kann es sicher geschlossen und zurückgegeben werden. Als Teil des Rückgabevorgangs muss es ein Ergebnis an die aufrufende Funktion zurückgeben.  
  
#### <a name="setting-the-modal-dialog-result"></a>Festlegen des modalen Dialog Ergebnisses

Das Öffnen eines Dialog Felds mit <xref:System.Windows.Window.ShowDialog%2A> ist im Grunde das Aufrufen einer Methode: der Code, der das Dialogfeld mithilfe <xref:System.Windows.Window.ShowDialog%2A> geöffnet hat, wartet, bis <xref:System.Windows.Window.ShowDialog%2A> zurückgibt. Wenn <xref:System.Windows.Window.ShowDialog%2A> zurückgibt, muss der Code, der Sie aufgerufen hat, entscheiden, ob die Verarbeitung fortgesetzt oder die Verarbeitung beendet werden soll, je nachdem, ob der Benutzer auf die Schaltfläche **OK** oder auf die Schaltfläche **Abbrechen** Um diese Entscheidung zu vereinfachen, muss das Dialogfeld die Auswahl des Benutzers als <xref:System.Boolean> Wert zurückgeben, der von der <xref:System.Windows.Window.ShowDialog%2A>-Methode zurückgegeben wird.  

Wenn auf die Schaltfläche " **OK** " geklickt wird, sollte <xref:System.Windows.Window.ShowDialog%2A> `true`zurückgeben. Dies wird erreicht, indem die <xref:System.Windows.Window.DialogResult%2A>-Eigenschaft des Dialog Felds festgelegt wird, wenn auf die Schaltfläche **OK** geklickt wird.  

[!code-csharp[Responding to the OK button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,25-27,32-33,67-68)]
[!code-vb[Responding to the OK button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27,31-33,61-62)]  

Beachten Sie, dass das Festlegen der <xref:System.Windows.Window.DialogResult%2A>-Eigenschaft auch bewirkt, dass das Fenster automatisch geschlossen wird, wodurch die Notwendigkeit verringert wird, <xref:System.Windows.Window.Close%2A>explizit aufzurufen.  
  
Wenn Sie auf die Schaltfläche **Abbrechen** klicken, sollten <xref:System.Windows.Window.ShowDialog%2A> `false`zurückgeben. Dies erfordert auch das Festlegen der <xref:System.Windows.Window.DialogResult%2A>-Eigenschaft.  
  
[!code-csharp[Responding to the Cancel button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,19-24,67-68)]
[!code-vb[Responding to the Cancel button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,22-25,61-62)]  

Wenn die <xref:System.Windows.Controls.Button.IsCancel%2A>-Eigenschaft einer Schaltfläche auf `true` festgelegt ist und der Benutzer entweder die Schaltfläche **Abbrechen** oder die ESC-Taste drückt, wird <xref:System.Windows.Window.DialogResult%2A> automatisch auf `false`festgelegt. Das folgende Markup hat denselben Effekt wie der vorangehende Code, ohne dass das <xref:System.Windows.Controls.Primitives.ButtonBase.Click>-Ereignis behandelt werden muss.  
  
[!code-xaml[Markup instead of handling the Click event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#L109-L109)]  

Ein Dialogfeld gibt automatisch `false` zurück, wenn ein Benutzer die Schaltfläche **Schließen** in der Titelleiste drückt oder das Menü Element **Schließen** im Menü **System** auswählt.  

#### <a name="processing-data-returned-from-a-modal-dialog-box"></a>Verarbeiten der von einem modalen Dialogfeld zurückgegebenen Daten  

Wenn <xref:System.Windows.Window.DialogResult%2A> von einem Dialogfeld festgelegt wird, kann die Funktion, die es geöffnet hat, das Ergebnis des Dialog Felds erhalten, indem die <xref:System.Windows.Window.DialogResult%2A>-Eigenschaft überprüft wird, wenn <xref:System.Windows.Window.ShowDialog%2A> zurückgibt.  
  
[!code-csharp[Processing data returned from the modal dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,77-79,89-96,194-195)]
[!code-vb[Processing data returned from the modal dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,58,69-73,131-132)]

Wenn das Dialog Ergebnis `true`ist, verwendet die Funktion dies als Hinweis, um die vom Benutzer bereitgestellten Daten abzurufen und zu verarbeiten.  
  
> [!NOTE]
> Nachdem <xref:System.Windows.Window.ShowDialog%2A> zurückgegeben wurde, kann ein Dialogfeld nicht erneut geöffnet werden. Stattdessen müssen Sie eine neue Instanz erstellen.

Wenn das Dialog Ergebnis `false`ist, sollte die Funktion die Verarbeitung entsprechend beenden.  
  
<a name="Creating_a_Modeless_Custom_Dialog_Box"></a>   
### <a name="creating-a-modeless-custom-dialog-box"></a>Erstellen eines nicht modalem benutzerdefinierten Dialog Felds

Ein nicht modales Dialogfeld, z. B. das in der folgenden Abbildung dargestellte Dialogfeld „Suchen“, besitzt dasselbe grundlegende Aussehen wie das modale Dialogfeld.  

![Screenshot, der das Dialogfeld Suchen anzeigt](./media/dialog-boxes-overview/find-modeless-dialog-box.png)  

Allerdings ist das Verhalten etwas anders, wie in den folgenden Abschnitten beschrieben wird.  
  
#### <a name="opening-a-modeless-dialog-box"></a>Öffnen eines nicht modalem Dialog Felds

Wenn Sie die <xref:System.Windows.Window.Show%2A>-Methode aufrufen, wird ein nicht modalem Dialogfeld geöffnet.  

[!code-xaml[XAML to define a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#L21-L22)]  
 
[!code-csharp[Opening a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,65-76,194-195)]
[!code-vb[Openng a modeless dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,18-23,131,132)]  

Im Gegensatz zu <xref:System.Windows.Window.ShowDialog%2A>wird <xref:System.Windows.Window.Show%2A> sofort zurückgegeben. Dementsprechend kann das aufrufende Fenster nicht erkennen, wann das nicht modale Dialogfeld geschlossen wird, und weiß deshalb auch nicht, wann es ein Dialogfeldergebnis überprüfen oder Daten vom Dialogfeld zur weiteren Verarbeitung abrufen soll. Stattdessen muss vom Dialogfeld eine andere Möglichkeit erstellt werden, um Daten an das aufrufende Fenster zur Verarbeitung zurückzugeben.  
  
#### <a name="processing-data-returned-from-a-modeless-dialog-box"></a>Verarbeiten der von einem nicht modalem Dialogfeld zurückgegebenen Daten  

In diesem Beispiel gibt der `FindDialogBox` möglicherweise ein oder mehrere Suchergebnisse an das Hauptfenster zurück, abhängig vom gesuchten Text ohne bestimmte Häufigkeit. Wie ein modales Dialogfeld kann auch ein nicht modales Dialogfeld Ergebnisse mithilfe von Eigenschaften zurückgeben. Das Fenster, das Besitzer des Dialogfelds ist, muss jedoch wissen, wann es diese Eigenschaften überprüfen soll. Diese Funktionalität kann z. B. dadurch aktiviert werden, dass das Dialogfeld ein Ereignis implementiert, das jedes Mal ausgelöst wird, wenn Text gefunden wird. `FindDialogBox` implementiert den `TextFoundEvent` zu diesem Zweck, der zuerst einen Delegaten erfordert.  

[!code-csharp[The TextFoundEventHandler delegate](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/TextFoundEventHandler.cs)]
[!code-vb[The TextFoundEventHandler delegate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/TextFoundEventHandler.vb)]  

Mithilfe des-`TextFoundEventHandler` Delegaten implementiert `FindDialogBox` den `TextFoundEvent`.
  
[!code-csharp[The TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-17,125-126)]
[!code-vb[The TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-15,102-103)]

Folglich kann `Find` das-Ereignis nach dem auffallen finden, wenn ein Suchergebnis gefunden wird.  
  
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
  
Alternativ kann der Code <xref:System.Windows.Window.Close%2A> aufzurufen, wenn auf die Schaltfläche **Schließen** geklickt wird.  

[!code-csharp[Calling the Close method](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,119-126)]
[!code-vb[Calling the Close method](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,99-103)]  

## <a name="see-also"></a>Siehe auch

- [Übersicht über Popups](../controls/popup-overview.md)
- [Dialog Feld Beispiel](https://go.microsoft.com/fwlink/?LinkID=159984)
