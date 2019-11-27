---
title: Grundlagen zu Windows Forms-Anwendungen
ms.date: 07/20/2015
helpviewer_keywords:
- Windows applications
- Windows Forms, Visual Basic
ms.assetid: 0b919d30-7fd6-42db-85c8-543d15312441
ms.openlocfilehash: 1aa1edf0130e388c6cc87662d83591f41a8e2325
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349163"
---
# <a name="windows-forms-application-basics-visual-basic"></a>Grundlagen zu Windows Forms-Anwendungen (Visual Basic)

Ein wichtiger Bestandteil von Visual Basic ist die Möglichkeit, Windows Forms Anwendungen zu erstellen, die lokal auf den Computern der Benutzer ausgeführt werden. Mithilfe von Windows Forms können Sie Visual Studio verwenden, um die Anwendung und die Benutzeroberfläche zu erstellen. Eine Windows Forms Anwendung baut auf Klassen aus dem <xref:System.Windows.Forms>-Namespace auf.

## <a name="designing-windows-forms-applications"></a>Entwerfen von Windows Forms Anwendungen

Sie können mit Visual Studio Windows Forms-und Windows-Dienst Anwendungen erstellen. Weitere Informationen finden Sie unter den folgenden Themen:

- Der Einstieg [in Windows Forms](../../../framework/winforms/getting-started-with-windows-forms.md). Enthält Informationen zum Erstellen und Programmieren von Windows Forms.

- [Windows Forms](../../../framework/winforms/controls/index.md)-Steuerelemente. Sammlung von Themen, in denen die Verwendung von Windows Forms Steuerelementen beschrieben wird.

- [Windows-Dienst Anwendungen](../../../framework/windows-services/index.md). Listet Themen auf, die erläutern, wie Windows-Dienste erstellt werden.

## <a name="building-rich-interactive-user-interfaces"></a>Erstellen von interaktiven Benutzeroberflächen mit anspruchsvollen Grafiken

Windows Forms ist die Smart-Client-Komponente des .NET Framework, eine Reihe verwalteter Bibliotheken, die gängige Anwendungsaufgaben ermöglichen, z. b. das Lesen und Schreiben in das Dateisystem. Mithilfe einer Entwicklungsumgebung wie Visual Studio können Sie Windows Forms Anwendungen erstellen, die Informationen anzeigen, Eingaben von Benutzern anfordern und über ein Netzwerk mit Remote Computern kommunizieren.

In Windows Forms stellt ein Form bzw. Formular eine visuelle Oberfläche dar, auf der Informationen für den Benutzer angezeigt werden. Im Allgemeinen erstellen Sie Windows Forms Anwendungen, indem Sie Steuerelemente in Formularen platzieren und Antworten auf Benutzeraktionen wie Mausklicks oder Tastatureingaben entwickeln. Ein *Steuerelement* ist ein diskretes Benutzeroberflächenelement (UI-Element), das Daten anzeigt oder Dateneingaben akzeptiert.

### <a name="events"></a>Ereignisse

Wenn ein Benutzer etwas für das Formular oder eines seiner Steuerelemente durchführt, wird ein Ereignis generiert. Die Anwendung reagiert auf diese Ereignisse und verarbeitet sie zum Zeitpunkt ihres Auftretens. Weitere Informationen finden Sie unter [Erstellen von Ereignishandlern in Windows Forms](../../../framework/winforms/creating-event-handlers-in-windows-forms.md).

### <a name="controls"></a>Steuerelemente

Windows Forms enthält eine Vielzahl von Steuerelementen, die Sie in Formularen platzieren können: Steuerelemente zum Anzeigen von Textfeldern, Schaltflächen, Dropdown Feldern, Options Feldern und sogar Webseiten. Eine Liste aller Steuerelemente, die in einem Formular verwendet werden können, finden Sie unter [Steuerelemente für Windows Forms](../../../framework/winforms/controls/controls-to-use-on-windows-forms.md). Windows Forms unterstützt über die <xref:System.Windows.Forms.UserControl>-Klasse auch das Erstellen benutzerdefinierter Steuerelemente, wenn ein vorhandenes Steuerelement für Ihre Anforderungen nicht geeignet ist.

Windows Forms verfügt über komplexe Steuerelemente für die Benutzeroberfläche, mit denen Funktionen aus Anwendungen wie Microsoft Office emuliert werden können. Mithilfe des Steuer Elements <xref:System.Windows.Forms.ToolStrip> und <xref:System.Windows.Forms.MenuStrip> können Sie Symbolleisten und Menüs erstellen, die Text und Bilder enthalten, Untermenüs anzeigen und andere Steuerelemente wie Textfelder und Kombinations Felder hosten.

Mit dem Drag & Drop-Formular-Designer von Visual Studio können Sie problemlos Windows Forms Anwendungen erstellen: Wählen Sie einfach die Steuerelemente mit dem Cursor aus, und platzieren Sie Sie auf dem Formular an der gewünschten Position. Der Designer stellt Tools wie Rasterlinien und Ausrichtungs Linien bereit, um das Ausrichten von Steuerelementen zu erleichtern. Und unabhängig davon, ob Sie Visual Studio oder die Kompilierung in der Befehlszeile verwenden, können Sie die Steuerelemente <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel> und <xref:System.Windows.Forms.SplitContainer> verwenden, um erweiterte Formularlayouts mit minimalem Zeitaufwand und Aufwand zu erstellen.

### <a name="custom-ui-elements"></a>Benutzerdefinierte Benutzeroberflächen Elemente

Wenn Sie Ihre eigenen benutzerdefinierten Benutzeroberflächen Elemente erstellen müssen, enthält der <xref:System.Drawing>-Namespace alle Klassen, die Sie benötigen, um Linien, Kreise und andere Formen direkt in einem Formular zu Rendering.

Schritt-für-Schritt-Informationen zur Verwendung dieser Funktionen finden Sie in den folgenden Hilfe Themen.

|Zweck|Weitere Informationen finden Sie unter|
|--------|---------|
|Erstellen einer neuen Windows Forms-Anwendung mit Visual Studio|[Tutorial 1: Erstellen eines Bild Anzeige Programms](/visualstudio/ide/tutorial-1-create-a-picture-viewer)|
|Verwenden von Steuerelementen in Formularen|[Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../framework/winforms/controls/how-to-add-controls-to-windows-forms.md)|
|Erstellen von Grafiken mit <xref:System.Drawing>|[Erste Schritte mit Grafikprogrammierung](../../../framework/winforms/advanced/getting-started-with-graphics-programming.md)|
|Erstellen benutzerdefinierter Steuerelemente|[Gewusst wie: Erben von der UserControl-Klasse](../../../framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)|

## <a name="displaying-and-manipulating-data"></a>Anzeigen und Bearbeiten von Daten

Viele Anwendungen müssen Daten aus einer Datenbank, einer XML-Datei, einem XML-Webdienst oder einer anderen Datenquelle anzeigen. Windows Forms bietet ein flexibles Steuerelement, das <xref:System.Windows.Forms.DataGridView> Steuerelement zum Rendern derartiger Tabellendaten in einem herkömmlichen Zeilen-und Spalten Format, sodass jedes Datenelement seine eigene Zelle einnimmt. Mithilfe <xref:System.Windows.Forms.DataGridView> können Sie die Darstellung einzelner Zellen anpassen, beliebige Zeilen und Spalten an Ort und Stelle Sperren und komplexe Steuerelemente in den Zellen anzeigen.

Mit intelligenten Windows Forms-Clients kann problemlos eine Netzwerkverbindung zu Datenquellen hergestellt werden. Die <xref:System.Windows.Forms.BindingSource>-Komponente, die neu mit Windows Forms in Visual Studio 2005 und der .NET Framework 2,0 ist, stellt eine Verbindung mit einer Datenquelle dar und macht Methoden zum Binden von Daten an Steuerelemente, zum Navigieren zu den vorherigen und nächsten Datensätzen, zum Bearbeiten von Datensätzen und zum Speichern von Änderungen in der ursprünglichen Quelle verfügbar. Das <xref:System.Windows.Forms.BindingNavigator>-Steuerelement stellt über die <xref:System.Windows.Forms.BindingSource>-Komponente eine einfache Schnittstelle zum Navigieren zwischen Datensätzen bereit.

### <a name="data-bound-controls"></a>Daten gebundene Steuerelemente

Sie können Daten gebundene Steuerelemente problemlos mithilfe des Fensters Datenquellen erstellen, in dem Datenquellen wie Datenbanken, Webdienste und Objekte in Ihrem Projekt angezeigt werden. Zum Erstellen datengebundener Steuerelemente können Sie Elemente aus diesem Fenster auf Formulare im Projekt ziehen. Darüber hinaus können Sie auch bestehende Steuerelemente an Daten binden, indem Sie Objekte aus dem Datenquellenfenster auf bestehende Steuerelemente ziehen.

### <a name="settings"></a>Einstellungen

Ein weiterer Typ von Datenbindungen, die in Windows Forms verwaltet werden können, sind Einstellungen. Die meisten intelligenten Client Anwendungen müssen einige Informationen über ihren Lauf Zeit Zustand, z. b. die zuletzt bekannte Formular Größe, beibehalten und Benutzer Einstellungsdaten beibehalten, wie z. b. Standard Speicherorte für gespeicherte Dateien. Die Funktion "Anwendungseinstellungen" erfüllt diese Anforderungen, indem es eine einfache Möglichkeit bietet, beide Arten von Einstellungen auf dem Client Computer zu speichern. Nachdem Sie entweder mit Visual Studio oder einem Code-Editor definiert wurden, werden diese Einstellungen als XML beibehalten und zur Laufzeit automatisch in den Arbeitsspeicher eingelesen.

Schritt-für-Schritt-Informationen zur Verwendung dieser Funktionen finden Sie in den folgenden Hilfe Themen.

|Zweck|Weitere Informationen finden Sie unter|
|--------|---------|
|Verwenden der <xref:System.Windows.Forms.BindingSource> Komponente|[Vorgehensweise: Binden von Windows Forms-Steuerelementen an die BindingSource-Komponente mithilfe des Designers](../../../framework/winforms/controls/bind-wf-controls-with-the-bindingsource.md)|
|Arbeiten mit ADO.NET-Datenquellen|[Vorgehensweise: Sortieren und Filtern von ADO.NET-Daten mit der BindingSource-Komponente in Windows Forms](../../../framework/winforms/controls/sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)|
|Verwenden des Datenquellen Fensters|[Exemplarische Vorgehensweise: Anzeigen von Daten in einem Windows Form](/visualstudio/data-tools/accessing-data-in-visual-studio)|

## <a name="deploying-applications-to-client-computers"></a>Bereitstellen von Anwendungen auf Clientcomputern

Nachdem Sie die Anwendung geschrieben haben, müssen Sie Sie an Ihre Benutzer senden, damit Sie Sie auf Ihren eigenen Client Computern installieren und ausführen können. Mithilfe der ClickOnce-Technologie können Sie Ihre Anwendungen in Visual Studio mit wenigen Klicks bereitstellen und Benutzern eine URL bereitstellen, die auf Ihre Anwendung im Web verweist. ClickOnce verwaltet alle Elemente und Abhängigkeiten in der Anwendung und stellt sicher, dass die Anwendung ordnungsgemäß auf dem Client Computer installiert ist.

ClickOnce-Anwendungen können so konfiguriert werden, dass Sie nur ausgeführt werden, wenn der Benutzer mit dem Netzwerk verbunden ist oder sowohl online als auch offline ausgeführt wird. Wenn Sie angeben, dass eine Anwendung den Offline Betrieb unterstützen soll, fügt ClickOnce im **Startmenü** des Benutzers einen Link zur Anwendung hinzu, sodass der Benutzer ihn ohne Verwendung der URL öffnen kann.

Wenn Sie die Anwendung aktualisieren, veröffentlichen Sie auf dem Webserver ein neues Bereitstellungsmanifest und eine neue Kopie der Anwendung. ClickOnce erkennt, dass ein Update verfügbar ist, und aktualisiert die Installation des Benutzers. zum Aktualisieren von alten Assemblys ist keine benutzerdefinierte Programmierung erforderlich.

Eine vollständige Einführung in ClickOnce finden Sie unter [ClickOnce-Sicherheit und-Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment). Schritt-für-Schritt-Informationen zur Verwendung dieser Funktionen finden Sie in den folgenden Hilfe Themen:

|Zweck|Weitere Informationen finden Sie unter|
|--------|---------|
|Bereitstellen einer Anwendung mit ClickOnce|[Gewusst wie: Veröffentlichen einer ClickOnce-Anwendung mit dem Webpublishing-Assistenten](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [Exemplarische Vorgehensweise: Manuelles Bereitstellen einer ClickOnce-Anwendung](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|
|Aktualisieren einer ClickOnce-Bereitstellung|[Gewusst wie: Verwalten von Aktualisierungen für eine ClickOnce-Anwendung](/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|
|Verwalten der Sicherheit mit ClickOnce|[Gewusst wie: Aktivieren von ClickOnce-Sicherheitseinstellungen](/visualstudio/deployment/how-to-enable-clickonce-security-settings)|

## <a name="other-controls-and-features"></a>Andere Steuerelemente und Funktionen

In Windows Forms stehen viele weitere Features bereit, mit denen häufige Aufgaben schnell und einfach ausgeführt werden können, beispielsweise zum Erstellen von Dialogfeldern, Drucken, Hinzufügen von Hilfe und Dokumentation sowie zum Lokalisieren von Anwendungen in mehrere Sprachen. Außerdem ist Windows Forms auf dem robusten Sicherheitssystem des .NET Framework basiert, sodass Sie für Ihre Kunden sicherere Anwendungen freigeben können.

Schritt-für-Schritt-Informationen zur Verwendung dieser Funktionen finden Sie in den folgenden Hilfe Themen:

|Zweck|Weitere Informationen finden Sie unter|
|--------|---------|
|Drucken des Inhalts eines Formulars|[Vorgehensweise: Drucken von Grafiken in Windows Forms](../../../framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)<br /><br /> [Vorgehensweise: Drucken einer mehrseitigen Textdatei in Windows Forms](../../../framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)|
|Weitere Informationen zur Windows Forms-Sicherheit|[Übersicht über die Sicherheit in Windows Forms](../../../framework/winforms/security-in-windows-forms-overview.md)|

## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- [Übersicht über Windows Forms](../../../framework/winforms/windows-forms-overview.md)
- [My.Forms-Objekt](../../../visual-basic/language-reference/objects/my-forms-object.md)
