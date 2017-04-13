---
title: "&#220;bersicht &#252;ber Dialogfelder | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Nicht modale Dialogfelder"
  - "Dialogfelder"
  - "Meldungsfelder"
  - "Modale Dialogfelder"
ms.assetid: 0d23d544-a393-4a02-a3aa-d8cd5d3d6511
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# &#220;bersicht &#252;ber Dialogfelder
Eigenständige Anwendungen haben in der Regel ein Hauptfenster, dass sowohl anzeigt, dass die Daten über die die Anwendung ausgeführt wird, und macht die Funktionalität zum Bearbeiten der Daten über [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Mechanismen wie Menüleisten, Symbolleisten und Statusleisten. Eine wichtige Anwendung kann auch zusätzliche Windows Folgendes anzeigen:  
  
-   Spezifische Informationen für Benutzer angezeigt.  
  
-   Sammeln Sie Informationen von Benutzern.  
  
-   Anzeigen und Erfassen von Informationen.  
  
 Diese Typen von Fenstern werden als bezeichnet *Dialogfelder*, und es gibt zwei Arten: modale und nicht modale.  
  
 Ein *modale* Dialogfeld wird angezeigt, eine Funktion, wenn die Funktion zusätzliche Daten von einem Benutzer, um den Vorgang fortzusetzen. Da die Funktion das modale Dialogfeld zum Sammeln von Daten abhängig ist, verhindert das modale Dialogfeld auch Benutzer andere Fenster in der Anwendung aktiviert wird, während er geöffnet bleibt. In den meisten Fällen ein modales Dialogfeld ermöglicht einem Benutzer zu signalisieren, wenn sie das modale Dialogfeld abgeschlossen haben, drücken Sie entweder eine **OK** oder **Abbrechen** Schaltfläche. Drücken Sie die **OK** Schaltfläche gibt an, dass ein Benutzer Daten eingegeben hat und möchte, die Funktion zum Fortsetzen der Verarbeitung dieser Daten dass. Drücken Sie die **Abbrechen** Schaltfläche gibt an, dass ein Benutzer die Funktion die möchte Ausführung komplett abbricht. Die häufigsten Beispiele für modale Dialogfelder werden angezeigt, öffnen, speichern und Drucken von Daten.  
  
 Ein *nicht modalen* klicken Sie im Dialogfeld auf der anderen Seite verhindert nicht, dass einen Benutzer andere Fenster aktiviert wird, während es geöffnet ist. Z. B. wenn ein Benutzer Vorkommen eines bestimmten Worts in einem Dokument gefunden möchte, wird ein Hauptfenster oft öffnen Sie das Dialogfeld welche Word Benutzerinformationen gesucht werden. Da die Suche nach ein Wort nicht verhindern, dass einen Benutzer das Dokument bearbeiten, jedoch nicht das Dialogfeld gebunden sein muss. Mindestens ein nicht modales Dialogfeld enthält einen **schließen** Schaltfläche, um das Dialogfeld zu schließen, und möglicherweise weitere Schaltflächen, um bestimmte Funktionen auszuführen, wie z. B. ein **Weitersuchen** Schaltfläche, um das nächste Wort zu suchen, die den Suchkriterien einer Wortsuche entspricht.  
  
 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]können Sie mehrere Typen von Dialogfeldern, einschließlich Meldungsfelder, häufig verwendete Dialogfelder und benutzerdefinierte Dialogfelder erstellen. In diesem Thema wird erläutert, und die [Dialog Box Sample](http://go.microsoft.com/fwlink/?LinkID=159984) enthält entsprechende Beispiele.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Message_Boxes"></a>   
## <a name="message-boxes"></a>Meldungsfelder  
 Ein *Meldungsfeld* ist ein Dialogfeld, das zum Anzeigen von Textinformationen und ermöglichen es Benutzern mit Schaltflächen Entscheidungen verwendet werden kann. Die folgende Abbildung zeigt ein Meldungsfeld an, die Textinformationen angezeigt und stellt eine Frage ermöglicht dem Benutzer drei Schaltflächen, um die Frage zu beantworten.  
  
 ![Dialogfeld Textverarbeitung](../../../../docs/framework/wpf/app-development/media/dialogboxesoverviewfigure1.png "DialogBoxesOverviewFigure1")  
  
 Um ein Meldungsfeld zu erstellen, verwenden Sie die <xref:System.Windows.MessageBox> Klasse.                  <xref:System.Windows.MessageBox> können Sie den Text in Meldungsfeldern, Titel, Symbol und Schaltflächen, verwenden Sie Code wie den folgenden zu konfigurieren.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxconfigurecodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxconfigurecodebehind)]  
  
 Um ein Meldungsfeld anzuzeigen, rufen Sie die `static` <xref:System.Windows.MessageBox.Show%2A> -Methode, wie im folgenden Code gezeigt.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowcodebehind)]  
  
 Wenn Code, der ein Meldungsfeld zeigt muss erkennen und verarbeiten die Entscheidung des Benutzers (welche Schaltfläche geklickt wurde), kann das Ergebnis des Meldungsfelds, den Code überprüfen, wie im folgenden Code gezeigt.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowandresultcodebehind1)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowandresultcodebehind1)]  
  
 Weitere Informationen zum Verwenden von Meldungsfeldern finden Sie unter <xref:System.Windows.MessageBox>, [MessageBox Sample](http://go.microsoft.com/fwlink/?LinkID=160023), und [Dialog Box Sample](http://go.microsoft.com/fwlink/?LinkID=159984).  
  
 Obwohl <xref:System.Windows.MessageBox> kann ein einfaches Dialogfeld Feld-Benutzerfunktionalität, bietet den Vorteil bieten <xref:System.Windows.MessageBox> ist das ist die einzige Art von Fenster, das von Clientanwendungen angezeigt werden kann, die in einer teilweise vertrauenswürdigen Sicherheits-Sandbox ausgeführt (finden Sie unter [Sicherheit](../../../../docs/framework/wpf/security-wpf.md)), wie z. B. [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)].  
  
 Die meisten Dialogfelder angezeigt und komplexere Daten als das Ergebnis eines Meldungsfelds, einschließlich Text, Auswahl (Kontrollkästchen), sich gegenseitig ausschließende Auswahl (Optionsfelder) sammeln und Liste Auswahl (Listenfeldern, Kombinationsfeldern, Dropdown Listen). Für diese [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] stellt mehrere allgemeine Dialogfelder bereit und ermöglicht es Ihnen, Ihre eigenen Dialogfelder erstellen, zwar die Verwendung von entweder nur mit voller Vertrauenswürdigkeit ausgeführt.  
  
<a name="Common_Dialogs"></a>   
## <a name="common-dialog-boxes"></a>Häufig verwendete Dialogfelder  
 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]implementiert eine Vielzahl von wieder verwendbaren Dialogfelder, die für alle Anwendungen, einschließlich der Dialogfelder zum Öffnen von Dateien, Dateien speichern und drucken. Da diese Dialogfelder vom Betriebssystem implementiert sind, können sie für alle Anwendungen freigegeben werden, die auf dem Betriebssystem ausgeführt werden dem Benutzer die Konsistenz können; Wenn Benutzer mit der ein Betriebssystem bereitgestellte Dialogfeld in einer Anwendung vertraut sind, müssen sie Informationen zur Verwendung dieses Dialogfelds in einer anderen Anwendung. Da diese Dialogfelder für alle Programme verfügbar sind und weil sie dabei helfen, ein konsistentes Benutzererlebnis bieten, werden sie als bezeichnet *häufig verwendete Dialogfelder*.  
  
 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]Kapselt die geöffnete Datei, speichern Sie Datei- und Druckserver häufig verwendete Dialogfelder und macht sie als verwaltete Klassen in einer eigenständigen Anwendung zu verwenden. Dieses Thema enthält eine kurze Übersicht über die einzelnen.  
  
<a name="Open_File_Dialog"></a>   
### <a name="open-file-dialog"></a>Dialogfeld "Datei öffnen"  
 Das Dialogfeld Datei öffnen, in der folgenden Abbildung gezeigt wird von Datei öffnen zum Abrufen des Namens einer Datei zu öffnen.  
  
 ![Das Dialogfeld Öffnen](../../../../docs/framework/wpf/app-development/media/dialogboxesoverviewfigure2.png "DialogBoxesOverviewFigure2")  
  
 Das Standarddialogfeld Datei öffnen wird als implementiert die <xref:Microsoft.Win32.OpenFileDialog> Klasse und befindet sich in der <xref:Microsoft.Win32> Namespace. Der folgende Code zeigt, wie erstellen, konfigurieren und Anzeigen eines und wie das Ergebnis verarbeitet.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#openfiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#openfiledialogboxcodebehind)]  
  
 Weitere Informationen zu den im Dialogfeld Datei öffnen, finden Sie unter <xref:Microsoft.Win32.OpenFileDialog?displayProperty=fullName>.  
  
> [!NOTE]
>  <xref:Microsoft.Win32.OpenFileDialog> dienen zum Dateinamen sicher Abrufen von Clientanwendungen, die mit teilweiser Vertrauenswürdigkeit ausgeführt wird (siehe [Security](../../../../docs/framework/wpf/security-wpf.md)).  
  
<a name="Save_File_Dialog"></a>   
### <a name="save-file-dialog-box"></a>Im Dialogfeld Datei speichern  
 Das Speichern in der folgenden Abbildung dargestellte Dateidialogfeld wird zum Abrufen des Namens einer Datei zum Speichern von Funktionen zum Speichern von Dateien verwendet.  
  
 ![Im Dialogfeld Speichern unter](../../../../docs/framework/wpf/app-development/media/dialogboxesoverviewfigure3.png "DialogBoxesOverviewFigure3")  
  
 Das Standarddialogfeld Datei speichern wird als implementiert die <xref:Microsoft.Win32.SaveFileDialog> Klasse, und befindet sich in der <xref:Microsoft.Win32> Namespace. Der folgende Code zeigt, wie erstellen, konfigurieren und Anzeigen eines und wie das Ergebnis verarbeitet.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#savefiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#savefiledialogboxcodebehind)]  
  
 Weitere Informationen zum Speichern (Dialogfeld), finden Sie unter <xref:Microsoft.Win32.SaveFileDialog?displayProperty=fullName>.  
  
<a name="Print_Dialog"></a>   
### <a name="print-dialog-box"></a>Drucken (Dialogfeld)  
 Das Dialogfeld Drucken, in der folgenden Abbildung dargestellt werden Druckfunktionen auswählen und konfigurieren den Drucker, dem ein Benutzer Daten ausgeben möchten.  
  
 ![Dialogfeld Drucken](../../../../docs/framework/wpf/app-development/media/dialogboxesoverviewfigure4.png "DialogBoxesOverviewFigure4")  
  
 Das Standarddialogfeld Drucken wird als implementiert die <xref:System.Windows.Controls.PrintDialog> Klasse, und befindet sich in der <xref:System.Windows.Controls> Namespace. Der folgende Code veranschaulicht das Erstellen, konfigurieren und Anzeigen eines.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#printdialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#printdialogboxcodebehind)]  
  
 Weitere Informationen über das Dialogfeld Drucken finden Sie unter <xref:System.Windows.Controls.PrintDialog?displayProperty=fullName>. Ausführliche Informationen für das Drucken in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], finden Sie unter [Printing Overview](../../../../docs/framework/wpf/advanced/printing-overview.md).  
  
<a name="Custom_Dialog_Boxes"></a>   
## <a name="custom-dialog-boxes"></a>Benutzerdefinierte Dialogfelder  
 Zwar häufig verwendete Dialogfelder nützlich sind und sollte verwendet werden, wenn möglich, unterstützen sie nicht die Anforderungen der domänenspezifischen Dialogfelder. In diesen Fällen müssen Sie eigene Dialogfelder erstellen. Wir sehen, ist ein Dialogfeld ein Fenster mit besonderen Verhaltensweisen.                  <xref:System.Windows.Window> implementiert jene Verhaltensweisen und infolgedessen verwenden Sie <xref:System.Windows.Window> benutzerdefinierte modale und nicht modale Dialogfelder zu erstellen.  
  
<a name="Creating_a_Modal_Custom_Dialog_Box"></a>   
### <a name="creating-a-modal-custom-dialog-box"></a>Erstellen eines modalen benutzerdefinierten Dialogfelds  
 In diesem Thema veranschaulicht, wie <xref:System.Windows.Window> zum Erstellen einer normalen modales Dialogfeld Feld-Implementierung, mit der `Margins` Dialogfeld als Beispiel (finden Sie unter [Dialog Box Sample](http://go.microsoft.com/fwlink/?LinkID=159984)). Die `Margins` Dialogfeld wird in der folgenden Abbildung gezeigt.  
  
 ![Dialogfeld Ränder](../../../../docs/framework/wpf/app-development/media/dialogboxesoverviewfigure5.png "DialogBoxesOverviewFigure5")  
  
#### <a name="configuring-a-modal-dialog-box"></a>Konfigurieren ein modales Dialogfeld  
 Die Benutzeroberfläche für ein normales Dialogfeld enthält Folgendes:  
  
-   Die verschiedenen Steuerelemente, die erforderlich sind, um die gewünschten Daten zu sammeln.  
  
-   Zeigt eine **OK** Schaltfläche, auf die Benutzer klicken, um das Dialogfeld zurück an die Funktion zu schließen und die Verarbeitung fortsetzen.  
  
-   Zeigt eine **Abbrechen** Schaltfläche, die Benutzer klicken, um das Dialogfeld zu schließen, und beenden die Funktion die weitere Verarbeitung.  
  
-   Zeigt eine **schließen** Schaltfläche in der Titelleiste angezeigt.  
  
-   Ein Symbol.  
  
-   Showing                                          **Minimize**,                                          **Maximize**, and                                          **Restore** buttons.  
  
-   Zeigt eine **System** Menü zu minimieren, maximieren, wiederherstellen und das Dialogfeld zu schließen.  
  
-   Öffnen über und in der Mitte des Fensters, das das Dialogfeld geöffnet.  
  
-   Dialogfelder sollten geändert werden, kann sich nach Möglichkeit, um zu verhindern, dass das Dialogfeld zu klein und dem Benutzer eine nützliche Standardgröße bereitzustellen, Sie sowohl Standard-als auch mindestens festlegen müssen lassen.  
  
-   Drücken die ESC-Taste sollte als Tastenkombination, die bewirkt, dass konfiguriert werden die **Abbrechen** Schaltfläche gedrückt. Dies wird erreicht, indem die <xref:System.Windows.Controls.Button.IsCancel%2A> Eigenschaft der **Abbrechen** -Schaltfläche, um `true`.  
  
-   Drücken der Taste eingeben (oder RETURN) sollten konfiguriert werden, als Tastenkombination, die bewirkt, dass die **OK** Schaltfläche gedrückt. Dies wird erreicht, indem die <xref:System.Windows.Controls.Button.IsDefault%2A> Eigenschaft der **OK** Schaltfläche `true`.  
  
 Der folgende Code veranschaulicht diese Konfiguration.  
  
 [!code-xml[DialogBoxSample#MarginsDialogBoxMainBitsMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsdialogboxmainbitsmarkup1)]  
[!code-xml[DialogBoxSample#MarginsDialogBoxMainBitsMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsdialogboxmainbitsmarkup2)]  
  
 [!code-csharp[DialogBoxSample#MarginsDialogBoxMainBitsCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxmainbitscodebehind1)]
 [!code-vb[DialogBoxSample#MarginsDialogBoxMainBitsCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxmainbitscodebehind1)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxMainBitsCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxmainbitscodebehind2)]
[!code-vb[DialogBoxSample#MarginsDialogBoxMainBitsCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxmainbitscodebehind2)]  
  
 Die Benutzeroberfläche für ein Dialogfeld Erweitert außerdem in der Menüleiste des Fensters, das das Dialogfeld wird geöffnet. Wenn ein Menüelement eine Funktion, die eine Benutzerinteraktion über ein Dialogfeld erfordert ausführt, bevor die Funktion fortgesetzt werden kann, müssen das Menüelement für die Funktion Auslassungszeichen im Header, wie hier gezeigt.  
  
 [!code-xml[DialogBoxSample#MainWindowMarginsDialogBoxMenuItemMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#mainwindowmarginsdialogboxmenuitemmarkup1)]  
[!code-xml[DialogBoxSample#MainWindowMarginsDialogBoxMenuItemMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#mainwindowmarginsdialogboxmenuitemmarkup2)]  
  
 Eine Ellipse ist nicht erforderlich, wenn ein Menüelement eine Funktion ausführt, die ein Dialogfeld angezeigt, die keinen Benutzereingriff, z. B. das Dialogfeld Info, benötigt.  
  
#### <a name="opening-a-modal-dialog-box"></a>Ein modales Dialogfeld Öffnen  
 Ein Dialogfeld wird in der Regel durch das Auswählen eines Menüelements angezeigt, zum Ausführen einer domänenspezifischen-Funktion, z. B. das Festlegen der Ränder eines Dokuments in einem Textverarbeitungsprogramm. Das Anzeigen eines Fensters als Dialogfeld ähnelt dem Anzeigen eines normalen Fensters, es ist jedoch zusätzliche Feld-spezifische Konfiguration erforderlich. Der gesamte Prozess zu instanziieren, wird im folgenden Code konfigurieren und ein Dialogfeld Öffnen angezeigt werden.  
  
 [!code-csharp[DialogBoxSample#OpenMarginsDialogCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogcodebehind1)]
 [!code-vb[DialogBoxSample#OpenMarginsDialogCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogcodebehind1)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogcodebehind2)]
[!code-vb[DialogBoxSample#OpenMarginsDialogCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogcodebehind2)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogcodebehind3)]
[!code-vb[DialogBoxSample#OpenMarginsDialogCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogcodebehind3)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogCODEBEHIND4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogcodebehind4)]
[!code-vb[DialogBoxSample#OpenMarginsDialogCODEBEHIND4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogcodebehind4)]  
  
 Hier wird der Code Standardinformationen (die aktuellen Ränder) an das Dialogfeld geleitet. Es ist auch eine Einstellung der <xref:System.Windows.Window.Owner%2A?displayProperty=fullName> Eigenschaft mit einem Verweis auf das Fenster, das das Dialogfeld angezeigt wird. Im Allgemeinen sollten Sie immer den Besitzer für ein Dialogfeld Fensterverhalten zustandsbezogenen bereitstellen, die für alle Dialogfelder gelten festlegen (siehe [WPF Windows Overview](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md) für Weitere Informationen).  
  
> [!NOTE]
>  Geben Sie einen Besitzer unterstützen [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Automatisierung für Dialogfelder (finden Sie unter [UI Automation Overview](../../../../docs/framework/ui-automation/ui-automation-overview.md)).  
  
 Nachdem das Dialogfeld konfiguriert ist, wird es modal angezeigt werden, durch Aufrufen der <xref:System.Windows.Window.ShowDialog%2A> Methode.  
  
#### <a name="validating-user-provided-data"></a>Überprüfen der vom Benutzer bereitgestellte Daten  
 Wenn ein Dialogfeld geöffnet wird, und der Benutzer die erforderlichen Daten enthält, wird ein Dialogfeld dafür verantwortlich, dass die bereitgestellten Daten ungültig, aus den folgenden Gründen sind:  
  
-   Aus Gründen der Sicherheit sollten alle Eingaben überprüft werden.  
  
-   Vom Standpunkt einer domänenspezifischen verhindert Validierung fehlerhafte Daten von der Verarbeitung durch den Code, der möglicherweise Ausnahmen auslösen können.  
  
-   Hinsichtlich der Funktionalität für Benutzer hilft ein Dialogfeld Benutzern zeigen sie die eingegebenen Daten ungültig sind.  
  
-   Hinsichtlich der Leistung kann Validierung in einer Anwendung mit mehreren Ebenen verringern die Anzahl der Roundtrips zwischen Client und Anwendungsebenen, insbesondere dann, wenn die Anwendung von Webdiensten oder Server-basierten Datenbanken besteht.  
  
 So überprüfen Sie ein gebundenes Steuerelement in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], müssen Sie eine Validierungsregel definieren und die Bindung zugeordnet wird. Eine Validierungsregel ist eine benutzerdefinierte Klasse, die von abgeleitet <xref:System.Windows.Controls.ValidationRule>. Das folgende Beispiel zeigt eine Validierungsregel `MarginValidationRule`, der überprüft werden, die ein gebundener Wert ist ein <xref:System.Double> und in einem angegebenen Bereich liegt.  
  
 [!code-csharp[DialogBoxSample#MarginValidationRuleCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginValidationRule.cs#marginvalidationrulecode)]
 [!code-vb[DialogBoxSample#MarginValidationRuleCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginValidationRule.vb#marginvalidationrulecode)]  
  
 In diesem Code wird die Validierungslogik einer Validierungsregel durch Überschreiben implementiert die <xref:System.Windows.Controls.ValidationRule.Validate%2A> -Methode, die die Daten überprüft und gibt eine entsprechende <xref:System.Windows.Controls.ValidationResult>.  
  
 Um die Validierungsregel dem gebundenen Steuerelement zuzuordnen, verwenden Sie das folgende Markup.  
  
 [!code-xml[DialogBoxSample#MarginsValidationMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsvalidationmarkup1)]  
[!code-xml[DialogBoxSample#MarginsValidationMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsvalidationmarkup2)]  
[!code-xml[DialogBoxSample#MarginsValidationMARKUP3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsvalidationmarkup3)]  
  
 Nachdem die Validierungsregel zugeordnet ist, wird [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] automatisch angewendet, wenn Daten in das gebundene Steuerelement eingegeben werden. Wenn ein Steuerelement ungültige Daten enthält [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] einen roten Rahmen um das ungültige Steuerelement wird angezeigt, wie in der folgenden Abbildung dargestellt.  
  
 ![Ungültiger Linker Rand](../../../../docs/framework/wpf/app-development/media/dialogboxesoverviewfigure7.png "DialogBoxesOverviewFigure7")  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]schränkt keinen Benutzer auf das ungültige Steuerelement, bis sie gültige Daten eingegeben haben. Dies ist eine gute Verhalten für ein Dialogfeld. ein Benutzer sollte die Steuerelemente in einem Dialogfeld frei zu navigieren, ob Daten gültig sind. Dies bedeutet jedoch ein Benutzer eingeben kann ungültige Daten, und drücken Sie die **OK** Schaltfläche. Aus diesem Grund müssen vom Code auch So überprüfen Sie alle Steuerelemente in einem Dialogfeld Feld, wenn die **OK** gedrückt wird durch das Behandeln der <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis.  
  
 [!code-csharp[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxvalidationcodebehind1)]
 [!code-vb[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxvalidationcodebehind1)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxvalidationcodebehind2)]
[!code-vb[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxvalidationcodebehind2)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxvalidationcodebehind3)]
[!code-vb[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxvalidationcodebehind3)]  
  
 Dieser Code Listet alle Abhängigkeitsobjekte in einem Fenster und, wenn eine ungültige (zurückgegeben <xref:System.Windows.Controls.Validation.GetHasError%2A>, das ungültige Steuerelement den Fokus erhält, ruft der `IsValid` -Methode gibt `false`, und das Fenster ist ungültig.  
  
 Sobald ein Dialogfeld gültig ist, kann es sicher geschlossen und wieder. Als Teil des Prozesses zurück muss er ein Ergebnis an die aufrufende Funktion zurückgeben.  
  
#### <a name="setting-the-modal-dialog-result"></a>Das modale Dialogfeld Ergebnis  
 Öffnen eines Dialogfelds mithilfe <xref:System.Windows.Window.ShowDialog%2A> entspricht im Wesentlichen dem Aufruf einer Methode: der Code, der das Dialogfeld mithilfe geöffnet <xref:System.Windows.Window.ShowDialog%2A> abwartet, bevor <xref:System.Windows.Window.ShowDialog%2A> zurückgibt. Wenn <xref:System.Windows.Window.ShowDialog%2A> gibt, den Code, der Aufruf muss entscheiden, ob die Verarbeitung fortgesetzt oder abgebrochen wird, ob basierend auf der Benutzer geklickt hat die **OK** Schaltfläche oder **Abbrechen** Schaltfläche. Um diese Entscheidung zu erleichtern, muss das Dialogfeld die Auswahl des Benutzers als Zurückgeben einer <xref:System.Boolean> von zurückgegebene Wert der <xref:System.Windows.Window.ShowDialog%2A> Methode.  
  
 Wenn die **OK** Schaltfläche geklickt wird, <xref:System.Windows.Window.ShowDialog%2A> sollte zurückgeben `true`. Dies wird erreicht, indem die <xref:System.Windows.Window.DialogResult%2A> Eigenschaft im Dialogfeld Feld, wenn die **OK** geklickt wird.  
  
 [!code-csharp[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxokresultsetcodebehind1)]
 [!code-vb[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxokresultsetcodebehind1)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxokresultsetcodebehind2)]
[!code-vb[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxokresultsetcodebehind2)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxokresultsetcodebehind3)]
[!code-vb[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxokresultsetcodebehind3)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxokresultsetcodebehind4)]
[!code-vb[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxokresultsetcodebehind4)]  
  
 Beachten Sie, dass durch Festlegen der <xref:System.Windows.Window.DialogResult%2A> Eigenschaft bewirkt auch, dass das Fenster automatisch geschlossen, dem die explizit nicht aufgerufen werden muss <xref:System.Windows.Window.Close%2A>.  
  
 Wenn die **Abbrechen** geklickt wird, <xref:System.Windows.Window.ShowDialog%2A> sollte zurückgeben `false`, erfordert ebenfalls die Einstellung der <xref:System.Windows.Window.DialogResult%2A> Eigenschaft.  
  
 [!code-csharp[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxcancelresultsetcodebehind1)]
 [!code-vb[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxcancelresultsetcodebehind1)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxcancelresultsetcodebehind2)]
[!code-vb[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxcancelresultsetcodebehind2)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxcancelresultsetcodebehind3)]
[!code-vb[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxcancelresultsetcodebehind3)]  
  
 Wenn auf einer Schaltfläche <xref:System.Windows.Controls.Button.IsCancel%2A> -Eigenschaft auf festgelegt ist `true` und der Benutzer drückt die **Abbrechen** Schaltfläche oder die ESC-Taste, <xref:System.Windows.Window.DialogResult%2A> automatisch `false`. Das folgende Markup hat denselben Effekt wie der vorhergehende Code, ohne dass behandelt die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis.  
  
 [!code-xml[DialogBoxSample#MarginsDialogDefaultCancelMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsdialogdefaultcancelmarkup)]  
  
 Ein Dialogfeld automatisch zurück `false` Wenn ein Benutzer drückt die **schließen** Schaltfläche in der Titelleiste oder wählt die **schließen** Menüelement aus der **System** Menü.  
  
#### <a name="processing-data-returned-from-a-modal-dialog-box"></a>Verarbeiten von Daten aus einem modalen Dialogfeld zurückgegeben  
 Wenn <xref:System.Windows.Window.DialogResult%2A> wird festgelegt durch ein Dialogfeld kann die Funktion, die es geöffnet hat, das Abrufen, indem Sie überprüfen die <xref:System.Windows.Window.DialogResult%2A> Eigenschaft beim <xref:System.Windows.Window.ShowDialog%2A> gibt.  
  
 [!code-csharp[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogprocessreturncodebehind1)]
 [!code-vb[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogprocessreturncodebehind1)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogprocessreturncodebehind2)]
[!code-vb[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogprocessreturncodebehind2)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogprocessreturncodebehind3)]
[!code-vb[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogprocessreturncodebehind3)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogprocessreturncodebehind4)]
[!code-vb[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogprocessreturncodebehind4)]  
  
 Wenn das Dialogfeldergebnis `true`, die Funktion verwendet, die als Hinweis zum Abrufen und verarbeiten die Daten, die vom Benutzer bereitgestellt werden.  
  
> [!NOTE]
>  Nach dem <xref:System.Windows.Window.ShowDialog%2A> zurückgegeben wurde, wird ein Dialogfeld nicht erneut geöffnet werden. Stattdessen müssen Sie eine neue Instanz erstellen.  
  
 Wenn das Dialogfeldergebnis `false`, sollte die Funktion die Verarbeitung entsprechend beenden.  
  
<a name="Creating_a_Modeless_Custom_Dialog_Box"></a>   
### <a name="creating-a-modeless-custom-dialog-box"></a>Erstellen eines nicht modalen benutzerdefinierten Dialogfelds  
 Ein nicht modales Dialogfeld, hat z. B. das Dialogfeld Suchen in der folgenden Abbildung gezeigt dasselbe grundlegende aussehen wie das modale Dialogfeld.  
  
 ![Dialogfeld "Suchen"](../../../../docs/framework/wpf/app-development/media/dialogboxesoverviewfigure6.PNG "DialogBoxesOverviewFigure6")  
  
 Allerdings ist das Verhalten etwas anders aussehen, wie in den folgenden Abschnitten beschrieben.  
  
#### <a name="opening-a-modeless-dialog-box"></a>Ein nicht modales Dialogfeld Öffnen  
 Ein nicht modales Dialogfeld geöffnet wird, durch Aufrufen der <xref:System.Windows.Window.Show%2A> Methode.  
  
 [!code-xml[DialogBoxSample#OpenFindDialogMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#openfinddialogmarkup1)]  
  
 [!code-csharp[DialogBoxSample#OpenFindDialogCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogcodebehind1)]
 [!code-vb[DialogBoxSample#OpenFindDialogCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogcodebehind1)]  
[!code-csharp[DialogBoxSample#OpenFindDialogCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogcodebehind2)]
[!code-vb[DialogBoxSample#OpenFindDialogCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogcodebehind2)]  
[!code-csharp[DialogBoxSample#OpenFindDialogCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogcodebehind3)]
[!code-vb[DialogBoxSample#OpenFindDialogCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogcodebehind3)]  
  
 Im Gegensatz zu <xref:System.Windows.Window.ShowDialog%2A>, <xref:System.Windows.Window.Show%2A> kehrt sofort zurück. Folglich kann das aufrufende Fenster nicht feststellen, wenn das nicht modale Dialogfeld geschlossen wird und daher nicht weiß, wann ein Dialogfeldergebnis überprüfen oder Abrufen von Daten aus dem Dialogfeld für die weitere Verarbeitung. In diesem Fall muss das Dialogfeld eine alternative Möglichkeit zum Zurückgeben von Daten an das aufrufende Fenster zur Verarbeitung zu erstellen.  
  
#### <a name="processing-data-returned-from-a-modeless-dialog-box"></a>Verarbeiten von Daten aus einem nicht modalen Dialogfeld zurückgegeben  
 In diesem Beispiel die `FindDialogBox` möglicherweise eine oder mehrere Suchergebnisse an das Hauptfenster, je nach den Suchtext ohne besondere Häufigkeit zurück. Wie bei einem modalen Dialogfeld, kann ein nicht modales Dialogfeld Ergebnisse mithilfe von Eigenschaften zurückgeben. Allerdings muss das Fenster, das Besitzer des Dialogfelds ist weiß, wann diese Eigenschaften überprüfen. Eine Möglichkeit, dies zu ermöglichen, ist für das Dialogfeld ein Ereignis implementiert, das ausgelöst wird, wenn Text gefunden wird.                                  `FindDialogBox`implementiert die `TextFoundEvent` zu diesem Zweck muss der zunächst einen Delegaten.  
  
 [!code-csharp[DialogBoxSample#TextFoundEventHandlerCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/TextFoundEventHandler.cs#textfoundeventhandlercode)]
 [!code-vb[DialogBoxSample#TextFoundEventHandlerCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/TextFoundEventHandler.vb#textfoundeventhandlercode)]  
  
 Using the                                  `TextFoundEventHandler` delegate,                                  `FindDialogBox` implements the                                  `TextFoundEvent`.  
  
 [!code-csharp[DialogBoxSample#TextFoundEventCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventcodebehind1)]
 [!code-vb[DialogBoxSample#TextFoundEventCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventcodebehind1)]  
[!code-csharp[DialogBoxSample#TextFoundEventCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventcodebehind2)]
[!code-vb[DialogBoxSample#TextFoundEventCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventcodebehind2)]  
  
 Folglich `Find` können Auslösen des Ereignisses, wenn ein Suchergebnis gefunden wird.  
  
 [!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind1)]
 [!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind1)]  
[!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind2)]
[!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind2)]  
[!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind3)]
[!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind3)]  
[!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind4)]
[!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind4)]  
[!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind5)]
[!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind5)]  
  
 Das Besitzerfenster muss registriert werden und dieses Ereignis behandeln.  
  
 [!code-csharp[DialogBoxSample#OpenFindDialogResultCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogresultcodebehind1)]
 [!code-vb[DialogBoxSample#OpenFindDialogResultCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogresultcodebehind1)]  
[!code-csharp[DialogBoxSample#OpenFindDialogResultCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogresultcodebehind2)]
[!code-vb[DialogBoxSample#OpenFindDialogResultCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogresultcodebehind2)]  
  
#### <a name="closing-a-modeless-dialog-box"></a>Schließen ein nicht modales Dialogfeld  
 Da <xref:System.Windows.Window.DialogResult%2A> muss nicht festgelegt werden kann, ein nicht modales Dialogfeld kann geschlossen werden, mithilfe von System stellen Mechanismen bereit, einschließlich der folgenden:  
  
-   Auf der **schließen** Schaltfläche in der Titelleiste angezeigt.  
  
-   ALT + F4 drücken.  
  
-   Choosing                                          **Close** from the                                          **System** menu.  
  
 Sie können auch Ihren Code Aufrufen <xref:System.Windows.Window.Close%2A> bei der **schließen** geklickt wird.  
  
 [!code-csharp[DialogBoxSample#FindDialogCloseCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#finddialogclosecodebehind1)]
 [!code-vb[DialogBoxSample#FindDialogCloseCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#finddialogclosecodebehind1)]  
[!code-csharp[DialogBoxSample#FindDialogCloseCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#finddialogclosecodebehind2)]
[!code-vb[DialogBoxSample#FindDialogCloseCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#finddialogclosecodebehind2)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Popups](../../../../docs/framework/wpf/controls/popup-overview.md)   
 [Beispiel für ein Dialogfeld](http://go.microsoft.com/fwlink/?LinkID=159984)   
 [Beispiel für benutzerdefinierte Farbwähler](http://go.microsoft.com/fwlink/?LinkID=159977)