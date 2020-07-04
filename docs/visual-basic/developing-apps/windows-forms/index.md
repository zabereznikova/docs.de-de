---
title: Grundlagen zu Windows Forms-Anwendungen
ms.date: 07/20/2015
helpviewer_keywords:
- Windows applications
- Windows Forms, Visual Basic
ms.assetid: 0b919d30-7fd6-42db-85c8-543d15312441
ms.openlocfilehash: 11216186a28509e1f10bafa1b24a440bcedaeeb6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "85840307"
---
# <a name="windows-forms-application-basics-visual-basic"></a>Grundlagen zu Windows Forms-Anwendungen (Visual Basic)

Ein wichtiger Aspekt von Visual Basic ist die Möglichkeit, Windows Forms-Anwendungen zu erstellen, die lokal auf Computern der Benutzer ausgeführt werden. Sie können Visual Studio verwenden, um die Anwendung und die Benutzeroberfläche mithilfe von Windows Forms zu erstellen. Eine Windows Forms-Anwendung baut auf Klassen aus dem <xref:System.Windows.Forms>-Namespace auf.

## <a name="designing-windows-forms-applications"></a>Entwerfen von Windows Forms-Anwendungen

Sie können mit Visual Studio Windows Forms- und Windows-Dienstanwendungen erstellen. Weitere Informationen finden Sie unter den folgenden Themen:

- [Erste Schritte mit Windows Forms](../../../framework/winforms/getting-started-with-windows-forms.md). Enthält Informationen zum Erstellen und Programmieren von Windows Forms.

- [Windows Forms-Steuerelemente](../../../framework/winforms/controls/index.md). Sammlung von Themen, in denen die Verwendung von Windows Forms-Steuerelementen beschrieben wird.

- [Windows-Dienstanwendungen](../../../framework/windows-services/index.md). Listet Themen auf, die erläutern, wie Windows-Dienste erstellt werden.

## <a name="building-rich-interactive-user-interfaces"></a>Erstellen von interaktiven Benutzeroberflächen mit anspruchsvollen Grafiken

Windows Forms ist die Komponente von .NET Framework für intelligente Clients und stellt eine Reihe von verwalteten Bibliotheken bereit, die allgemeine Anwendungsaufgaben wie das Lesen aus und das Schreiben in das Dateisystem ermöglichen. Mit einer Entwicklungsumgebung wie Visual Studio können Sie Windows Forms-Anwendungen erstellen, die Informationen anzeigen, Benutzer zur Eingabe von Daten auffordern oder über ein Netzwerk mit Remotecomputern kommunizieren.

In Windows Forms stellt ein Formular eine visuelle Oberfläche dar, auf der Informationen für den Benutzer angezeigt werden. In der Regel erstellen Sie Windows Forms-Anwendungen, indem Sie Steuerelemente in Formularen platzieren und Antworten auf Benutzeraktionen (z. B. Maus- und Tastatureingaben) entwickeln. Ein *Steuerelement* ist ein diskretes Benutzeroberflächenelement (UI-Element), das Daten anzeigt oder Dateneingaben akzeptiert.

### <a name="events"></a>Ereignisse

Wenn ein Benutzer Aktionen im Formular oder in enthaltenen Steuerelementen ausführt, wird ein Ereignis generiert. Die Anwendung reagiert auf diese Ereignisse und verarbeitet sie zum Zeitpunkt ihres Auftretens. Weitere Informationen finden Sie unter [Erstellen von Ereignishandlern in Windows Forms](../../../framework/winforms/creating-event-handlers-in-windows-forms.md).

### <a name="controls"></a>Steuerelemente

Windows Forms enthält eine Vielzahl von Steuerelementen, die Sie in Formularen platzieren können: Steuerelemente zur Anzeige von Textfeldern, Schaltflächen, Dropdownfeldern, Optionsfeldern und sogar Webseiten. Eine Liste aller Steuerelemente, die in einem Formular verwendet werden können, finden Sie unter [Steuerelemente für Windows Forms](../../../framework/winforms/controls/controls-to-use-on-windows-forms.md). Windows Forms unterstützt über die <xref:System.Windows.Forms.UserControl>-Klasse auch das Erstellen benutzerdefinierter Steuerelemente, wenn ein vorhandenes Steuerelement für Ihre Anforderungen nicht geeignet ist.

Windows Forms verfügt über komplexe Steuerelemente für die Benutzeroberfläche, mit denen Funktionen aus Anwendungen wie Microsoft Office emuliert werden können. Mit dem <xref:System.Windows.Forms.ToolStrip>-Steuerelement und dem <xref:System.Windows.Forms.MenuStrip>-Steuerelement können Sie Symbolleisten und Menüs erstellen, die Texte und Bilder, Untermenüs oder weitere Steuerelemente enthalten, z. B. Textfelder und Kombinationsfelder.

Mit dem Drag & Drop-Formular-Designer von Visual Studio können Sie problemlos Windows Forms-Anwendungen erstellen: Wählen Sie einfach die Steuerelemente mit dem Cursor aus, und platzieren Sie sie im Formular an der gewünschten Position. Der Designer stellt Tools wie Rasterlinien und „Ausrichtungslinien“ bereit, um das Anordnen von Steuerelementen zu erleichtern. Unabhängig davon, ob Sie mit Visual Studio arbeiten oder über die Befehlszeile kompilieren, können Sie die Steuerelemente <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel> und <xref:System.Windows.Forms.SplitContainer> verwenden, um mit geringem Zeitaufwand komplexe Formularlayouts zu erstellen.

### <a name="custom-ui-elements"></a>Benutzerdefinierte Benutzeroberflächenelemente

Schließlich enthält der <xref:System.Drawing>-Namespace zum Erstellen eigener Benutzeroberflächenelemente alle erforderlichen Klassen, um Linien, Kreise und andere Formen direkt auf einem Formular zu rendern.

Ausführliche Informationen zur Verwendung dieser Funktionen finden Sie in den folgenden Hilfethemen.

|Beschreibung|Siehe|
|--------|---------|
|Erstellen einer neuen Windows Forms-Anwendung mit Visual Studio|[Tutorial 1: Erstellen eines Bildanzeigeprogramms](/visualstudio/ide/tutorial-1-create-a-picture-viewer)|
|Verwenden von Steuerelementen in Formularen|[How to: Hinzufügen von Steuerelementen zu Windows Forms](../../../framework/winforms/controls/how-to-add-controls-to-windows-forms.md)|
|Erstellen von Grafiken mithilfe von <xref:System.Drawing>|[Erste Schritte mit Grafikprogrammierung](../../../framework/winforms/advanced/getting-started-with-graphics-programming.md)|
|Erstellen von benutzerdefinierten Steuerelementen|[How to: Erben von der UserControl-Klasse](../../../framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)|

## <a name="displaying-and-manipulating-data"></a>Anzeigen und Bearbeiten von Daten

Viele Anwendungen müssen Daten aus einer Datenbank, einer XML-Datei, einem XML-Webdienst oder einer anderen Datenquelle anzeigen. Mit dem <xref:System.Windows.Forms.DataGridView>-Steuerelement bietet Windows Forms ein flexibles Steuerelement zum Rendern von Tabellendaten im herkömmlichen Zeilen- und Spaltenformat, bei dem jedes Datenelement in einer eigenen Zelle enthalten ist. Mit <xref:System.Windows.Forms.DataGridView> können Sie die Darstellung einzelner Zellen anpassen, die Position beliebiger Zeilen oder Spalten fixieren und komplexe Steuerelemente in einer Zelle anzeigen, um nur einige Features zu nennen.

Mit intelligenten Windows Forms-Clients kann problemlos eine Netzwerkverbindung zu Datenquellen hergestellt werden. Die <xref:System.Windows.Forms.BindingSource>-Komponente, die erstmals für Windows Forms in Visual Studio 2005 und .NET Framework 2.0 verfügbar ist, stellt eine Verbindung mit einer Datenquelle dar und macht Methoden zum Binden von Daten an Steuerelemente, Navigieren zum vorherigen oder nächsten Datensatz, Bearbeiten von Datensätzen und Speichern von Änderungen in der ursprünglichen Quelle verfügbar. Das <xref:System.Windows.Forms.BindingNavigator>-Steuerelement stellt über die <xref:System.Windows.Forms.BindingSource>-Komponente eine einfache Schnittstelle zum Navigieren zwischen Datensätzen bereit.

### <a name="data-bound-controls"></a>Datengebundene Steuerelemente

Sie können datengebundene Steuerelemente problemlos mithilfe des Fensters „Datenquellen“ erstellen, in dem Datenquellen wie Datenbanken, Webdienste und Objekte in Ihrem Projekt angezeigt werden. Zum Erstellen datengebundener Steuerelemente können Sie Elemente aus diesem Fenster auf Formulare im Projekt ziehen. Darüber hinaus können Sie auch bestehende Steuerelemente an Daten binden, indem Sie Objekte aus dem Datenquellenfenster auf bestehende Steuerelemente ziehen.

### <a name="settings"></a>Einstellungen

Ein weiterer Datenbindungstyp, der in Windows Forms verwaltet werden kann, sind Einstellungen. Die meisten intelligenten Clientanwendungen müssen bestimmte Informationen über ihren Laufzeitzustand, z. B. die zuletzt bekannte Größe des Formulars, sowie Benutzereinstellungen wie Standardspeicherorte von Dateien erhalten. Die Funktion „Anwendungseinstellungen“ trägt diesen Anforderungen Rechnung und stellt eine einfache Möglichkeit dar, beide Arten von Einstellungen auf dem Clientcomputer zu speichern. Nachdem Sie diese Einstellungen mit Visual Studio oder einem Code-Editor definiert haben, werden sie im XML-Format gespeichert und zur Laufzeit automatisch in den Arbeitsspeicher eingelesen.

Ausführliche Informationen zur Verwendung dieser Funktionen finden Sie in den folgenden Hilfethemen.

|Beschreibung|Siehe|
|--------|---------|
|Verwenden der <xref:System.Windows.Forms.BindingSource>-Komponente|[How to: Binden von Windows Forms-Steuerelementen an die BindingSource-Komponente mithilfe des Designers](../../../framework/winforms/controls/bind-wf-controls-with-the-bindingsource.md)|
|Arbeiten mit ADO.NET-Datenquellen|[How to: Sortieren und Filtern von ADO.NET-Daten mit der BindingSource-Komponente in Windows Forms](../../../framework/winforms/controls/sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)|
|Verwenden des Fensters „Datenquellen“|[Exemplarische Vorgehensweise: Anzeigen von Daten in einem Windows Forms-Formular](/visualstudio/data-tools/accessing-data-in-visual-studio)|

## <a name="deploying-applications-to-client-computers"></a>Bereitstellen von Anwendungen auf Clientcomputern

Nach dem Erstellen müssen Sie die Anwendung an Ihre Benutzer senden, damit diese die Anwendung auf dem eigenen Clientcomputer installieren und ausführen können. Mithilfe der ClickOnce-Technologie können Sie Anwendungen in Visual Studio mit wenigen Klicks bereitstellen und Benutzern eine URL zur Verfügung stellen, die auf die Anwendung im Internet verweist. ClickOnce verwaltet alle Elemente und Abhängigkeiten in der Anwendung und stellt sicher, dass die Anwendung auf dem Clientcomputer ordnungsgemäß installiert ist.

ClickOnce-Anwendungen können so konfiguriert werden, dass sie nur ausgeführt werden, wenn der Benutzer mit dem Netzwerk verbunden ist, oder dass sie sowohl online als auch offline ausgeführt werden können. Wenn Sie angeben, dass eine Anwendung den Offlinebetrieb unterstützen soll, fügt ClickOnce im Menü **Start** des Benutzers einen Link zur Anwendung hinzu, damit der Benutzer diese ohne Verwendung der URL öffnen kann.

Wenn Sie die Anwendung aktualisieren, veröffentlichen Sie auf dem Webserver ein neues Bereitstellungsmanifest und eine neue Kopie der Anwendung. ClickOnce erkennt, dass ein Update verfügbar ist, und aktualisiert die Installation des Benutzers. Zum Aktualisieren von alten Assemblys ist keine benutzerdefinierte Programmierung erforderlich.

Eine umfassende Einführung in ClickOnce finden Sie unter [ClickOnce-Sicherheit und -Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment). Ausführliche Informationen zur Verwendung dieser Funktionen finden Sie in den folgenden Hilfethemen:

|Beschreibung|Siehe|
|--------|---------|
|Bereitstellen einer Anwendung mit ClickOnce|[How to: Veröffentlichen einer ClickOnce-Anwendung mit dem Webpublishing-Assistenten](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [Exemplarische Vorgehensweise: Manuelles Bereitstellen einer ClickOnce-Anwendung](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|
|Aktualisieren einer ClickOnce-Bereitstellung.|[How to: Verwalten von Aktualisierungen für eine ClickOnce-Anwendung](/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|
|Verwalten der Sicherheit mit ClickOnce|[How to: Aktivieren von ClickOnce-Sicherheitseinstellungen](/visualstudio/deployment/how-to-enable-clickonce-security-settings)|

## <a name="other-controls-and-features"></a>Andere Steuerelemente und Funktionen

In Windows Forms stehen viele weitere Features bereit, mit denen häufige Aufgaben schnell und einfach ausgeführt werden können, beispielsweise zum Erstellen von Dialogfeldern, Drucken, Hinzufügen von Hilfe und Dokumentation sowie zum Lokalisieren von Anwendungen in mehrere Sprachen. Außerdem basiert Windows Forms auf dem robusten Sicherheitssystem von .NET Framework, sodass Sie für Ihre Kunden sicherere Anwendungen freigeben können.

Ausführliche Informationen zur Verwendung dieser Funktionen finden Sie in den folgenden Hilfethemen:

|Beschreibung|Siehe|
|--------|---------|
|Ausgeben des Inhalts eines Formulars|[How to: Drucken von Grafiken in Windows Forms](../../../framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)<br /><br /> [How to: Drucken einer mehrseitigen Textdatei in Windows Forms](../../../framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)|
|Weitere Informationen zur Windows Forms-Sicherheit|[Übersicht über die Sicherheit in Windows Forms](../../../framework/winforms/security-in-windows-forms-overview.md)|

## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- [Übersicht über Windows Forms](../../../framework/winforms/windows-forms-overview.md)
- [My.Forms-Objekt](../../language-reference/objects/my-forms-object.md)
