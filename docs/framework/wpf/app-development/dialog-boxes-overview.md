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
ms.openlocfilehash: 8008feb91a72353a74a647cf79bcecbf7023f962
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410556"
---
# <a name="dialog-boxes-overview"></a>Übersicht über Dialogfelder
Eigenständige Anwendungen haben in der Regel ein Hauptfenster, dass sowohl die hauptsächlichen Daten über den die Anwendung ausgeführt wird, und macht die Funktionalität zum Verarbeiten dieser Daten über zeigt [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] -Mechanismen wie Menüleisten, Symbolleisten und Statusleisten. Eine nicht triviale Anwendung kann auch zusätzliche Fenster anzeigen, um Folgendes auszuführen:  
  
- Spezifische Informationen für Benutzer anzeigen.  
  
- Informationen von Benutzern erfassen.  
  
- Informationen sowohl anzeigen als auch erfassen.  
  
 Diese Fenstertypen werden als bezeichnet *Dialogfelder*, und es gibt zwei Arten: modale und nicht modale.  
  
 Ein *modale* Dialogfeld wird von einer Funktion angezeigt, wenn die Funktion zusätzliche Daten von einem Benutzer, um den Vorgang fortzusetzen. Da die Funktion beim Erfassen der Daten vom modalen Dialogfeld abhängig ist, verhindert das modale Dialogfeld auch, dass der Benutzer andere Fenster in der Anwendung aktiviert, während das Dialogfeld geöffnet bleibt. In den meisten Fällen kann ein modales Dialogfeld einen Benutzer aus, um zu signalisieren, wenn sie mit das modale Dialogfeld abgeschlossen haben, drücken Sie eine eine **OK** oder **Abbrechen** Schaltfläche. Drücken Sie die **OK** Schaltfläche gibt an, dass ein Benutzer Daten eingegeben hat und möchte, die Funktion zum Fortsetzen der Verarbeitung dieser Daten dass. Drücken Sie die **Abbrechen** Schaltfläche gibt an, dass ein Benutzer möchte auf die Funktion die Ausführung komplett abbricht. Die häufigsten Beispiele für modale Dialogfelder sind das Öffnen, Speichern und Drucken von Daten.  
  
 Ein *nicht modale* im Dialogfeld auf der anderen Seite verhindert nicht, dass einen Benutzer über andere Fenster aktiviert wird, während er geöffnet ist. Wenn ein Benutzer z. B. Vorkommen eines bestimmten Worts in einem Dokument finden möchte, wird in einem Hauptfenster oft ein Dialogfeld geöffnet, um den Benutzer zu fragen, nach welchem Wort er sucht. Da die Suche nach einem Wort einen Benutzer aber nicht an der Bearbeitung des Dokuments hindert, muss das Dialogfeld nicht unbedingt modal sein. Ein nicht modales Dialogfeld enthält mindestens ein **schließen** Schaltfläche, um das Dialogfeld zu schließen, und möglicherweise zusätzliche Schaltflächen, um bestimmte Funktionen auszuführen, z. B. eine **Weitersuchen** Schaltfläche, um die nächste Wort, das entspricht die Suchkriterien einer Wortsuche.  
  
 Windows Presentation Foundation (WPF) können Sie mehrere Typen von Dialogfeldern, einschließlich Meldungsfelder, Standarddialogfelder und benutzerdefinierte Dialogfelder erstellen. In diesem Thema wird erläutert, und die [Dialogfeldbeispiel](https://go.microsoft.com/fwlink/?LinkID=159984) stellt entsprechende Beispiele bereit.  

<a name="Message_Boxes"></a>   
## <a name="message-boxes"></a>Meldungsfelder  
 Ein *Meldungsfeld* ist ein Dialogfeld mit dem Textinformationen angezeigt und können Benutzer mithilfe von Schaltflächen Entscheidungen treffen werden kann. In der folgenden Abbildung ist ein Meldungsfeld dargestellt, in dem Textinformationen angezeigt werden, eine Frage gestellt wird und der Benutzer mithilfe von drei Schaltflächen die Frage beantworten kann.  
  
 ![Schließt ein Dialogfeld gefragt, ob die Änderungen auf das Dokument vor der Anwendung gespeichert werden soll.](./media/dialog-boxes-overview/word-processor-dialog.png)  
  
 Um ein Meldungsfeld zu erstellen, verwenden Sie die <xref:System.Windows.MessageBox> Klasse. <xref:System.Windows.MessageBox> können Sie Text in Meldungsfeldern, Titel, Symbol und Schaltflächen, die mithilfe von Code wie folgt zu konfigurieren.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxconfigurecodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxconfigurecodebehind)]  
  
 Um ein Meldungsfeld anzuzeigen, rufen Sie die `static` <xref:System.Windows.MessageBox.Show%2A> -Methode, wie im folgenden Code gezeigt.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowcodebehind)]  
  
 Wenn Code, der ein Meldungsfeld anzeigt, die Entscheidung des Benutzers (welche Schaltfläche angeklickt wurde) erkennen und verarbeiten muss, kann der Code das Ergebnis des Meldungsfelds überprüfen, wie im folgenden Code gezeigt.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowandresultcodebehind1)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowandresultcodebehind1)]  
  
 Weitere Informationen zur Verwendung von Meldungsfeldern finden Sie unter <xref:System.Windows.MessageBox>, [MessageBox-Beispiel](https://go.microsoft.com/fwlink/?LinkID=160023), und [Dialogfeldbeispiel](https://go.microsoft.com/fwlink/?LinkID=159984).  
  
 Obwohl <xref:System.Windows.MessageBox> kann eine einfaches Dialogfeld benutzererfahrung mit Dialogfeldern, bietet den Vorteil bieten <xref:System.Windows.MessageBox> ist, ist die einzige Art von Fenster, das von Anwendungen angezeigt werden kann, die in einer teilweise vertrauenswürdigen Sicherheits-Sandbox ausgeführt (finden Sie unter [Sicherheit](../security-wpf.md)), wie z. B. [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)].  
  
 In den meisten Dialogfeldern werden komplexere Daten angezeigt und gesammelt als im Ergebnis eines Meldungsfelds. Dazu zählen Text, Auswahlmöglichkeiten (Kontrollkästchen), sich gegenseitig ausschließende Auswahlmöglichkeiten (Optionsfelder) und Auswahlmöglichkeiten in einer Liste (Listenfelder, Kombinationsfelder, Dropdown-Listenfelder). Für diese Windows Presentation Foundation (WPF) bietet mehrere häufig verwendete Dialogfelder und ermöglicht Ihnen, eigene Dialogfelder zu erstellen, obwohl die Verwendung beider auf Anwendungen, die mit voller Vertrauenswürdigkeit ausgeführt wird.  
  
<a name="Common_Dialogs"></a>   
## <a name="common-dialog-boxes"></a>Häufig verwendete Dialogfelder  
 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] implementiert eine Reihe von wiederverwendbaren Dialogfeldern, die für alle Anwendungen gleich sind. Dazu zählen Dialogfelder zum Öffnen und Speichern von Dateien und zum Drucken. Da diese Dialogfelder durch das Betriebssystem implementiert werden, können sie von allen Anwendungen, die unter dem Betriebssystem ausgeführt werden, genutzt werden. Dies trägt zu einer konsistenten Benutzererfahrung bei: Wenn Benutzer mit der Verwendung eines durch das Betriebssystem bereitgestellten Dialogfelds in einer Anwendung vertraut sind, müssen Sie nicht lernen, wie sie dieses Dialogfeld in anderen Anwendungen verwenden. Da diese Dialogfelder allen Anwendungen zur Verfügung stehen, und sie bieten eine konsistente benutzererfahrung zu bieten, werden sie als bezeichnet *Standarddialogfelder*.  
  
 Windows Presentation Foundation (WPF) kapselt die geöffnete Datei, speichern Sie die Datei, und Drucken der häufig verwendete Dialogfelder und macht sie als verwaltete Klassen für die Verwendung in eigenständigen Anwendungen verwenden. Dieses Thema enthält eine kurze Übersicht über die einzelnen Dialogfelder.  
  
<a name="Open_File_Dialog"></a>   
### <a name="open-file-dialog"></a>Dialogfeld "Datei öffnen"  
 Das Dialogfeld „Datei öffnen“, das in der folgenden Abbildung gezeigt wird, wird von Funktionen zum Öffnen von Dateien verwendet, um den Namen einer zu öffnenden Datei abzurufen.  
  
 ![Ein Dialogfeld geöffnet, das die Position zum Abrufen der Datei.](./media/dialog-boxes-overview/open-file-dialog-box.png)  
  
 Das Standarddialogfeld Datei öffnen, wird als implementiert die <xref:Microsoft.Win32.OpenFileDialog> Klasse und befindet sich in der <xref:Microsoft.Win32> Namespace. Im folgenden Code wird gezeigt, wie ein solches Dialogfeld erstellt, konfiguriert und angezeigt und wie das Ergebnis verarbeitet wird.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#openfiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#openfiledialogboxcodebehind)]  
  
 Weitere Informationen zu den im Dialogfeld Datei öffnen, finden Sie unter <xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>.  
  
> [!NOTE]
>  <xref:Microsoft.Win32.OpenFileDialog> dienen zum sicher abrufen, die Namen von Anwendungen, die mit teilweiser Vertrauenswürdigkeit ausgeführt (finden Sie unter [Sicherheit](../security-wpf.md)).  
  
<a name="Save_File_Dialog"></a>   
### <a name="save-file-dialog-box"></a>Datei speichern (Dialogfeld)  
 Das Dialogfeld „Datei speichern“, das in der folgenden Abbildung gezeigt wird, wird von Funktionen zum Speichern von Dateien verwendet, um den Namen einer zu speichernden Datei abzurufen.  
  
 ![Ein Dialogfeld Speichern unter, die den Standort zum Speichern der Datei.](./media/dialog-boxes-overview/save-file-dialog-box.png)  
  
 Das Standarddialogfeld speichern Datei wird als implementiert die <xref:Microsoft.Win32.SaveFileDialog> Klasse, und befindet sich in der <xref:Microsoft.Win32> Namespace. Im folgenden Code wird gezeigt, wie ein solches Dialogfeld erstellt, konfiguriert und angezeigt und wie das Ergebnis verarbeitet wird.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#savefiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#savefiledialogboxcodebehind)]  
  
 Weitere Informationen zu speichern (Dialogfeld), finden Sie unter <xref:Microsoft.Win32.SaveFileDialog?displayProperty=nameWithType>.  
  
<a name="Print_Dialog"></a>   
### <a name="print-dialog-box"></a>Dialogfeld Drucken

Das Dialogfeld „Drucken“, das in der folgenden Abbildung gezeigt wird, wird von Funktionen zum Drucken verwendet, um den Drucker auszuwählen und zu konfigurieren, auf dem der Benutzer Daten ausgeben möchte.  
  
![Screenshot, ein Druckdialogfeld zeigt.](./media/dialog-boxes-overview/print-data-dialog-box.png)  
  
Das Standarddialogfeld Drucken wird implementiert, als die <xref:System.Windows.Controls.PrintDialog> Klasse, und befindet sich in der <xref:System.Windows.Controls> Namespace. Im folgenden Code wird gezeigt, wie ein solches Dialogfeld erstellt, konfiguriert und angezeigt wird.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#printdialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#printdialogboxcodebehind)]  
  
 Klicken Sie im Dialogfeld "Drucken" auf Weitere Informationen finden Sie unter <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>. Ausführliche Informationen über das Drucken in WPF, finden Sie unter [Übersicht über das Drucken](../advanced/printing-overview.md).  
  
<a name="Custom_Dialog_Boxes"></a>   
## <a name="custom-dialog-boxes"></a>Benutzerdefinierte Dialogfelder

Obwohl Standarddialogfelder hilfreich sind und nach Möglichkeit verwendet werden sollten, unterstützen sie nicht die Anforderungen von domänenspezifischen Dialogfeldern. In diesen Fällen müssen Sie eigene Dialogfelder erstellen. Wie später ersichtlich wird, ist ein Dialogfeld ein Fenster mit besonderen Verhaltensweisen. <xref:System.Windows.Window> implementiert jene Verhaltensweisen und infolgedessen verwenden Sie das <xref:System.Windows.Window> um benutzerdefinierte modale und nicht modale Dialogfelder zu erstellen.  
  
<a name="Creating_a_Modal_Custom_Dialog_Box"></a>   
### <a name="creating-a-modal-custom-dialog-box"></a>Erstellen einen modalen benutzerdefinierten Dialogfelds

In diesem Thema wird gezeigt, wie Sie mit <xref:System.Windows.Window> eine typische modale dialogfeldimplementierung zu erstellen. mit der `Margins` Dialogfeld als Beispiel (finden Sie unter [Dialogfeldbeispiel](https://go.microsoft.com/fwlink/?LinkID=159984)). Die `Margins` Dialogfeld wird in der folgenden Abbildung dargestellt.  
  
 ![Ein Dialogfeld Ränder mit Feldern zum linken Rand, Oberer Rand, der rechte Rand und der untere Rand zu definieren.](./media/dialog-boxes-overview/margin-size-dialog-box.png)  
  
#### <a name="configuring-a-modal-dialog-box"></a>Konfigurieren eines modalen Dialogfelds

Die Benutzeroberfläche für ein normales Dialogfeld enthält Folgendes:  
  
- Die verschiedenen Steuerelemente, die zum Erfassen der gewünschten Daten erforderlich sind.  
  
- Ein **OK** Schaltfläche, durch die Benutzer klicken, um das Schließen des Dialogfelds, das an die Funktion zurück und setzt die Verarbeitung fort.  
  
- Ein **Abbrechen** Schaltfläche, die Benutzer klicken, um das Dialogfeld schließen und die Funktion die weitere Verarbeitung zu beenden.  
  
- Ein **schließen** Schaltfläche in der Titelleiste angezeigt.  
  
- Symbol  
  
- **Minimieren Sie**, **Maximieren**, und **wiederherstellen** Schaltflächen.  
  
- Ein **System** Menü zu minimieren, maximieren, wiederherstellen und das Dialogfeld zu schließen.  
  
- Eine Position nach oben und in der Mitte des Fensters, das das Dialogfeld geöffnet.  
  
- Die Fähigkeit, deren Größe geändert werden, wenn möglich, um zu verhindern, dass Sie das Dialogfeld zu klein ist, und klicken Sie auf dem Benutzer eine sinnvolle Standardgröße bereitzustellen. Dies erfordert, dass Sie sowohl die Standard-als auch einen minimalen Abmessungen festlegen.  
  
- Die ESC-Taste als Tastenkombination, die bewirkt, dass die **Abbrechen** Schaltfläche gedrückt wird. Diesem Zweck legen die <xref:System.Windows.Controls.Button.IsCancel%2A> Eigenschaft der **Abbrechen** Schaltfläche `true`.  
  
- Die EINGABETASTE (oder RÜCKGABE)-Taste als Tastenkombination, die bewirkt, dass die **OK** Schaltfläche gedrückt wird. Sie tun dies durch Festlegen der <xref:System.Windows.Controls.Button.IsDefault%2A> Eigenschaft der **OK** Schaltfläche `true`.  
  
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

Hier wird im Code Standardinformationen (die aktuellen Ränder), um das Dialogfeld. Außerdem wird die <xref:System.Windows.Window.Owner%2A?displayProperty=nameWithType> Eigenschaft mit einem Verweis auf das Fenster, das das Dialogfeld angezeigt wird. Im Allgemeinen sollten Sie immer den Besitzer für ein Dialogfeld, Fenster Status Verhalten bereitzustellen, die für alle Dialogfelder gelten festlegen (siehe [Übersicht über WPF-Windows](wpf-windows-overview.md) für Weitere Informationen).

> [!NOTE]
> Sie müssen einen Besitzer für die Unterstützung von Benutzer-Benutzeroberfläche (UI)-Automatisierung für Dialogfelder bereitstellen (siehe [UI Automation Overview](../../ui-automation/ui-automation-overview.md)).

Nachdem Sie das Dialogfeld konfiguriert ist, wird es modal angezeigt werden, durch den Aufruf der <xref:System.Windows.Window.ShowDialog%2A> Methode.  
  
#### <a name="validating-user-provided-data"></a>Überprüfen von vom Benutzer bereitgestellte Daten

Wenn ein Dialogfeld geöffnet wird und der Benutzer die benötigten Daten zur Verfügung stellt, ist ein Dialogfeld aus folgenden Gründen dafür verantwortlich, dass die bereitgestellten Daten gültig sind:  
  
- Aus Gründen der Datensicherheit sollten alle Eingaben überprüft werden.  
  
- Aus domänenspezifischer Sicht verhindert die Datenvalidierung, dass fehlerhafte Daten vom Code verarbeitet werden, was zum Auslösen von Ausnahmen führen kann.  
  
- Aus Gründen der Benutzererfahrung kann ein Dialogfeld dazu beitragen, Benutzern zu helfen, indem ihnen gezeigt wird, welche der von ihnen eingegebenen Daten ungültig sind.  
  
- Unter Leistungsaspekten betrachtet, kann die Datenvalidierung in einer Anwendung mit mehreren Ebenen die Anzahl von Roundtrips zwischen der Client- und der Anwendungsebene vermindern, insbesondere, wenn die Anwendung aus Webdiensten oder serverbasierten Datenbanken besteht.  

Um ein gebundenes Steuerelement in WPF zu überprüfen, müssen Sie eine Validierungsregel definieren und die Bindung zuordnen. Eine Validierungsregel ist eine benutzerdefinierte abgeleitete Klasse <xref:System.Windows.Controls.ValidationRule>. Das folgende Beispiel zeigt eine Validierungsregel `MarginValidationRule`, der überprüft werden, die ein gebundener Wert ist eine <xref:System.Double> und innerhalb eines bestimmten Bereichs ist.  

[!code-csharp[Margin validation rules](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginValidationRule.cs)]
[!code-vb[Margin validation rules](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginValidationRule.vb)]  

In diesem Code wird die Validierungslogik einer Validierungsregel durch Überschreiben implementiert die <xref:System.Windows.Controls.ValidationRule.Validate%2A> -Methode, die die Daten überprüft und gibt eine entsprechende <xref:System.Windows.Controls.ValidationResult>.  

Um die Validierungsregel dem gebundenen Steuerelement zuzuordnen, wird das folgende Markup verwendet.  
  
[!code-xaml[Associating a validation rule with a control](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml?range=1-16,57-68,111-112)]

Nachdem die Validierungsregel zugeordnet ist, wird dieses durch die WPF automatisch angewendet, wenn Daten in das gebundene Steuerelement eingegeben werden. Wenn ein Steuerelement ungültige Daten enthält, wird WPF einen roten Rahmen um das ungültige Steuerelement angezeigt, wie in der folgenden Abbildung dargestellt.  
  
![Ein Dialogfeld Ränder mit einem roten Rahmen um den Wert Ungültiger Linker Rand.](./media/dialog-boxes-overview/invalid-left-margin-dialog.png)  

WPF schränkt keinen Benutzer auf das ungültige Steuerelement, bis sie gültige Daten eingegeben haben. Das wird als gutes Verhalten für ein Dialogfeld verstanden: Benutzer sollten in einem Dialogfeld frei durch die Steuerelemente navigieren können, unabhängig davon, ob die Daten gültig sind. Dies bedeutet jedoch ein Benutzer eingeben kann ungültige Daten, und drücken Sie die **OK** Schaltfläche. Aus diesem Grund müssen vom Code auch zum Validieren aller Steuerelemente in einem Dialogfeld Feld, wenn die **OK** gedrückt wird durch Behandeln der <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis.  
  
[!code-csharp[Validating all controls in a dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,26-29,33-68)]
[!code-vb[Validating all controls in a dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27-29,33-62)]  

Dieser Code Listet alle Abhängigkeitsobjekte in einem Fenster und, falls ungültige (wie vom <xref:System.Windows.Controls.Validation.GetHasError%2A>, erhält das ungültige Steuerelement den Fokus erhält, die `IsValid` Methodenrückgabe `false`, und das Fenster wird als ungültig angesehen.  
  
Sobald ein Dialogfeld gültig ist, kann es sicher geschlossen und zurückgegeben werden. Als Teil des Rückgabevorgangs muss es ein Ergebnis an die aufrufende Funktion zurückgeben.  
  
#### <a name="setting-the-modal-dialog-result"></a>Festlegen des modalen Dialogergebnisses

Öffnen eines Dialogfelds mithilfe <xref:System.Windows.Window.ShowDialog%2A> entspricht im Wesentlichen dem Aufrufen einer Methode: der Code, der Öffnen des Dialogfelds mit <xref:System.Windows.Window.ShowDialog%2A> wartet, bis <xref:System.Windows.Window.ShowDialog%2A> zurückgibt. Wenn <xref:System.Windows.Window.ShowDialog%2A> gibt, wird der Code, die diese Anforderungen aufgerufen, zu entscheiden, ob die Verarbeitung fortgesetzt oder abgebrochen wird, basierend auf vom Benutzer gedrückten der **OK** Schaltfläche oder die **Abbrechen** Schaltfläche. Um diese Entscheidung zu erleichtern, muss das Dialogfeld die Auswahl des Benutzers als Zurückgeben einer <xref:System.Boolean> aus zurückgegebene Wert die <xref:System.Windows.Window.ShowDialog%2A> Methode.  

Wenn die **OK** Schaltfläche geklickt wird, <xref:System.Windows.Window.ShowDialog%2A> sollte zurückgeben `true`. Dies wird erreicht, indem die <xref:System.Windows.Window.DialogResult%2A> Eigenschaft im Dialogfeld im Feld, wenn die **OK** geklickt wird.  

[!code-csharp[Responding to the OK button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,25-27,32-33,67-68)]
[!code-vb[Responding to the OK button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27,31-33,61-62)]  

Beachten Sie diese Einstellung die <xref:System.Windows.Window.DialogResult%2A> Eigenschaft bewirkt auch, dass das Fenster automatisch geschlossen, die die explizit nicht aufgerufen werden muss <xref:System.Windows.Window.Close%2A>.  
  
Wenn die **Abbrechen** Schaltfläche geklickt wird, <xref:System.Windows.Window.ShowDialog%2A> sollte zurückgeben `false`, erfordert ebenfalls die Einstellung der <xref:System.Windows.Window.DialogResult%2A> Eigenschaft.  
  
[!code-csharp[Responding to the Cancel button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,19-24,67-68)]
[!code-vb[Responding to the Cancel button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,22-25,61-62)]  

Beim Klicken auf einer Schaltfläche des <xref:System.Windows.Controls.Button.IsCancel%2A> -Eigenschaftensatz auf `true` und der Benutzer drückt die **Abbrechen** Schaltfläche oder die ESC-Taste, <xref:System.Windows.Window.DialogResult%2A> wird automatisch festgelegt, um `false`. Das folgende Markup hat dieselbe Wirkung wie der vorhergehende Code, ohne die Notwendigkeit, behandeln die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis.  
  
[!code-xaml[Markup instead of handling the Click event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#L109-L109)]  

Ein Dialogfeld gibt automatisch zurück `false` Wenn ein Benutzer drückt die **schließen** Schaltfläche in der Titelleiste an oder wählt die **schließen** Menüelement der **System** Menü.  

#### <a name="processing-data-returned-from-a-modal-dialog-box"></a>Verarbeiten von Daten, die von einem modalen Dialogfeld zurückgegeben werden.  

Wenn <xref:System.Windows.Window.DialogResult%2A> festgelegt ist von einem Dialogfeld kann die Funktion, die es geöffnet das Dialogfeldergebnis abrufen, indem Sie überprüfen die <xref:System.Windows.Window.DialogResult%2A> Eigenschaft beim <xref:System.Windows.Window.ShowDialog%2A> zurückgibt.  
  
[!code-csharp[Processing data returned from the modal dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,77-79,89-96,194-195)]
[!code-vb[Processing data returned from the modal dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,58,69-73,131-132)]

Wenn das Dialogergebnis `true`, die Funktion verwendet, die als Hinweis zum Abrufen und verarbeiten, die vom Benutzer bereitgestellten Daten.  
  
> [!NOTE]
> Nach dem <xref:System.Windows.Window.ShowDialog%2A> zurückgegeben wurde, wird ein Dialogfeld kann nicht erneut geöffnet werden. Stattdessen müssen Sie eine neue Instanz erstellen.

Wenn das Dialogergebnis `false`, sollte die Funktion die Verarbeitung entsprechend beenden.  
  
<a name="Creating_a_Modeless_Custom_Dialog_Box"></a>   
### <a name="creating-a-modeless-custom-dialog-box"></a>Erstellen eines nicht modalen benutzerdefinierten Dialogfelds

Ein nicht modales Dialogfeld, z. B. das in der folgenden Abbildung dargestellte Dialogfeld „Suchen“, besitzt dasselbe grundlegende Aussehen wie das modale Dialogfeld.  

![Screenshot mit einem Dialogfeld Suchen.](./media/dialog-boxes-overview/find-modeless-dialog-box.png)  

Allerdings ist das Verhalten etwas anders, wie in den folgenden Abschnitten beschrieben wird.  
  
#### <a name="opening-a-modeless-dialog-box"></a>Ein nicht modales Dialogfeld Öffnen

Ein nicht modales Dialogfeld geöffnet wird, durch den Aufruf der <xref:System.Windows.Window.Show%2A> Methode.  

[!code-xaml[XAML to define a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#L21-L22)]  
 
[!code-csharp[Opening a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,65-76,194-195)]
[!code-vb[Openng a modeless dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,18-23,131,132)]  

Im Gegensatz zu <xref:System.Windows.Window.ShowDialog%2A>, <xref:System.Windows.Window.Show%2A> kehrt sofort zurück. Dementsprechend kann das aufrufende Fenster nicht erkennen, wann das nicht modale Dialogfeld geschlossen wird, und weiß deshalb auch nicht, wann es ein Dialogfeldergebnis überprüfen oder Daten vom Dialogfeld zur weiteren Verarbeitung abrufen soll. Stattdessen muss vom Dialogfeld eine andere Möglichkeit erstellt werden, um Daten an das aufrufende Fenster zur Verarbeitung zurückzugeben.  
  
#### <a name="processing-data-returned-from-a-modeless-dialog-box"></a>Verarbeiten von Daten, die von einem nicht modalen Dialogfeld zurückgegeben werden.  

In diesem Beispiel die `FindDialogBox` kann eine oder mehrere Suchergebnisse an das Hauptfenster, je nach dem Suchtext ohne besondere Häufigkeit zurückgeben kann. Wie ein modales Dialogfeld kann auch ein nicht modales Dialogfeld Ergebnisse mithilfe von Eigenschaften zurückgeben. Das Fenster, das Besitzer des Dialogfelds ist, muss jedoch wissen, wann es diese Eigenschaften überprüfen soll. Diese Funktionalität kann z. B. dadurch aktiviert werden, dass das Dialogfeld ein Ereignis implementiert, das jedes Mal ausgelöst wird, wenn Text gefunden wird. `FindDialogBox` implementiert die `TextFoundEvent` zu diesem Zweck der zuerst ein Delegat erforderlich ist.  

[!code-csharp[The TextFoundEventHandler delegate](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/TextFoundEventHandler.cs)]
[!code-vb[The TextFoundEventHandler delegate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/TextFoundEventHandler.vb)]  

Mithilfe der `TextFoundEventHandler` zu delegieren, `FindDialogBox` implementiert die `TextFoundEvent`.
  
[!code-csharp[The TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-17,125-126)]
[!code-vb[The TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-15,102-103)]

Folglich `Find` können Auslösen des Ereignisses, wenn ein Suchergebnis gefunden wird.  
  
[!code-csharp[Raising the TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,50-52,91-94,124-127)]
[!code-vb[Raising the TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,15,60-64,102-103)]  

Das Besitzerfenster muss anschließend bei diesem Ereignis registriert werden und es behandeln.

[!code-csharp[Registering and handling the event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,184-195)]
[!code-vb[Registering and handling the event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,126-132)]  

#### <a name="closing-a-modeless-dialog-box"></a>Ein nicht modales Dialogfeld schließen

Da <xref:System.Windows.Window.DialogResult%2A> muss nicht festgelegt werden kann, ein nicht modales Dialogfeld kann geschlossen werden, mithilfe von System bieten Mechanismen, einschließlich der folgenden:  
  
- Klicken auf die **schließen** Schaltfläche in der Titelleiste angezeigt.  
  
- Drücken von ALT+F4.  
  
- Auswahl **schließen** aus der **System** Menü.  
  
Sie können auch Ihren Code Aufrufen <xref:System.Windows.Window.Close%2A> bei der **schließen** geklickt wird.  

[!code-csharp[Calling the Close method](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,119-126)]
[!code-vb[Calling the Close method](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,99-103)]  

## <a name="see-also"></a>Siehe auch

- [Übersicht über Popups](../controls/popup-overview.md)
- [Beispiel für ein Dialogfeld](https://go.microsoft.com/fwlink/?LinkID=159984)
