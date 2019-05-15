---
title: Übersicht über Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- smart clients
- Windows Forms, about Windows Forms
ms.assetid: 3a2b6284-c8d6-4e1c-8c69-0bed38f38cd4
ms.openlocfilehash: e9d117b272cea8ebb96dc579fa1d8faf65d42c45
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583459"
---
# <a name="windows-forms-overview"></a>Übersicht über Windows Forms

Der folgende Abschnitt enthält eine Übersicht über die Vorteile von intelligenten Clientanwendungen, die wichtigsten Funktionen der Windows Forms-Programmierung und die Verwendung von Windows Forms zur Erstellung von intelligenten Clients, die die Anforderungen moderner Unternehmen und Endbenutzer erfüllen.

## <a name="windows-forms-and-smart-client-apps"></a>Windows Forms und smart Client-apps

 Windows Forms dient der Entwicklung von intelligenten Clients. *Intelligente Clients* sind grafisch anspruchsvolle Anwendungen, die einfach bereitgestellt und aktualisiert werden können. Darüber hinaus kann eine intelligente Clientanwendung sowohl im Online- als auch im Offlinebetrieb verwendet werden und bietet gegenüber herkömmlichen Windows-Anwendungen erhöhte Sicherheit beim Zugriff auf lokale Computerressourcen.

### <a name="build-rich-interactive-user-interfaces"></a>Erstellen Sie vielseitige, interaktive Benutzeroberflächen

 Windows Forms ist eine smart Clienttechnologie für die .NET Framework, ein Satz verwalteter Bibliotheken, die generelle Anwendungsaufgaben wie Lesen und Schreiben in das Dateisystem zu vereinfachen. Wenn Sie eine Entwicklungsumgebung wie Visual Studio verwenden, können Sie die Windows Forms-Smart Client-Anwendungen, die Informationen anzeigen, Eingaben von Benutzern anfordern, und die Kommunikation mit Remotecomputern erstellen, über ein Netzwerk.

 In Windows Forms stellt ein *Formular* eine visuelle Oberfläche dar, auf der Informationen für den Benutzer angezeigt werden. In der Regel erstellen Sie Windows Forms-Anwendungen, indem Sie Steuerelemente in Formulare einfügen und Antworten auf Benutzeraktionen, wie Maus- und Tastatureingaben, entwickeln. Ein *Steuerelement* ist ein diskretes Benutzeroberflächenelement (UI-Element), das Daten anzeigt oder Dateneingaben akzeptiert.

 Wenn ein Benutzer Aktionen im Formular oder in enthaltenen Steuerelementen ausführt, wird ein Ereignis generiert. Die Anwendung reagiert auf diese Ereignisse und verarbeitet sie zum Zeitpunkt ihres Auftretens. Weitere Informationen finden Sie unter [Erstellen von Ereignishandlern in Windows Forms](creating-event-handlers-in-windows-forms.md).

 Windows Forms enthält eine Vielzahl von Steuerelementen, die Sie Formularen hinzufügen können: Steuerelemente zur Anzeige von Textfeldern, Schaltflächen, Dropdownfeldern, Optionsfeldern und sogar Webseiten. Eine Liste aller Steuerelemente, die in einem Formular verwendet werden können, finden Sie unter [Steuerelemente für Windows Forms](./controls/controls-to-use-on-windows-forms.md). Windows Forms unterstützt über die <xref:System.Windows.Forms.UserControl>-Klasse auch das Erstellen benutzerdefinierter Steuerelemente, wenn ein vorhandenes Steuerelement für Ihre Anforderungen nicht geeignet ist.

 Windows Forms verfügt über komplexe Steuerelemente für die Benutzeroberfläche, mit denen Funktionen aus Anwendungen wie Microsoft Office emuliert werden können. Mit dem <xref:System.Windows.Forms.ToolStrip>-Steuerelement und dem <xref:System.Windows.Forms.MenuStrip>-Steuerelement können Sie Symbolleisten und Menüs erstellen, die Texte und Bilder, Untermenüs oder weitere Steuerelemente enthalten, z. B. Textfelder und Kombinationsfelder.

 Mit der Drag & Drop **Windows Forms-Designer** in Visual Studio können Sie problemlos Windows Forms-Anwendungen erstellen. Wählen Sie Steuerelemente einfach mit dem Mauszeiger aus, und fügen Sie sie an der gewünschten Stelle im Formular ein. Der Designer stellt Tools wie Rasterlinien und Ausrichtungslinien bereit, um das Anordnen von Steuerelementen zu erleichtern. Und, ob Sie Visual Studio oder über die Befehlszeile kompilieren, können Sie die <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel> und <xref:System.Windows.Forms.SplitContainer> Steuerelemente zum Erstellen erweiterter Formularlayouts in kürzerer Zeit.

 Schließlich enthält der <xref:System.Drawing>-Namespace zum Erstellen eigener Benutzeroberflächenelemente eine Vielzahl von Klassen, um Linien, Kreise und andere Formen direkt auf einem Formular zu zeichnen.

> [!NOTE]
> Windows Forms-Steuerelemente wurden nicht für das Marshallen über Anwendungsdomänen hinweg entwickelt. Daher unterstützt Microsoft die Übergabe eines Windows Forms-Steuerelements über eine <xref:System.AppDomain>-Grenze hinweg nicht, auch wenn der <xref:System.Windows.Controls.Control>-Basistyp von <xref:System.MarshalByRefObject> den Anschein erweckt, als ob dies möglich wäre. Windows Forms-Anwendungen mit mehreren Anwendungsdomänen werden unterstützt, solange keine Windows Forms-Steuerelemente über die Grenzen von Anwendungsdomänen hinweg übergeben werden.

#### <a name="create-forms-and-controls"></a>Erstellen von Formularen und Steuerelementen

Ausführliche Informationen zur Verwendung dieser Features finden Sie in den folgenden Hilfethemen.

|Beschreibung|Hilfethema|
|-----------------|----------------|
|Verwenden von Steuerelementen auf Formularen|[Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](./controls/how-to-add-controls-to-windows-forms.md)|
|Verwenden des <xref:System.Windows.Forms.ToolStrip>-Steuerelements|[Vorgehensweise: Erstellen eines einfachen ToolStrip mit Standardelementen mithilfe des Designers](./controls/create-a-basic-wf-toolstrip-with-standard-items-using-the-designer.md)|
|Erstellen von Grafiken mithilfe von <xref:System.Drawing>|[Erste Schritte mit Grafikprogrammierung](./advanced/getting-started-with-graphics-programming.md)|
|Erstellen benutzerdefinierter Steuerelemente|[Vorgehensweise: Erben von der UserControl-Klasse](./controls/how-to-inherit-from-the-usercontrol-class.md)|

### <a name="display-and-manipulate-data"></a>Anzeigen und Bearbeiten von Daten
 Viele Anwendungen müssen Daten aus einer Datenbank, einer XML-Datei, einem XML-Webdienst oder einer anderen Datenquelle anzeigen. Mit dem <xref:System.Windows.Forms.DataGridView>-Steuerelement bietet Windows Forms ein flexibles Steuerelement zum Anzeigen von Tabellendaten im herkömmlichen Zeilen- und Spaltenformat, bei dem jedes Datenelement in einer eigenen Zelle enthalten ist. Mit <xref:System.Windows.Forms.DataGridView> können Sie die Darstellung einzelner Zellen anpassen, die Position beliebiger Zeilen oder Spalten fixieren und komplexe Steuerelemente in einer Zelle anzeigen, um nur einige Features zu nennen.

 Mit intelligenten Windows Forms-Clients kann problemlos eine Netzwerkverbindung zu Datenquellen hergestellt werden. Die <xref:System.Windows.Forms.BindingSource> Komponente stellt eine Verbindung mit einer Datenquelle dar und stellt Methoden zum Binden von Daten an Steuerelemente, Navigieren zum vorherigen oder nächsten Datensatz, Bearbeiten von Datensätzen und Speichern von Änderungen in der ursprünglichen Quelle zurück. Das <xref:System.Windows.Forms.BindingNavigator>-Steuerelement stellt über die <xref:System.Windows.Forms.BindingSource>-Komponente eine einfache Schnittstelle zum Navigieren zwischen Datensätzen bereit.

 Mit dem Datenquellenfenster können datengebundene Steuerelemente problemlos erstellt werden. In diesem Fenster werden die Datenquellen in Ihrem Projekt angezeigt, z. B. Datenbanken, Webdienste oder Objekte. Zum Erstellen datengebundener Steuerelemente können Sie Elemente aus diesem Fenster auf Formulare im Projekt ziehen. Darüber hinaus können Sie auch bestehende Steuerelemente an Daten binden, indem Sie Objekte aus dem Datenquellenfenster auf bestehende Steuerelemente ziehen.

 Ein weiterer Datenbindungstyp, der in Windows Forms verwaltet werden kann, lautet *Einstellungen*. Die meisten intelligenten Clientanwendungen müssen bestimmte Informationen über ihren Laufzeitzustand, z. B. die zuletzt bekannte Größe des Formulars, sowie Benutzereinstellungen wie Standardspeicherorte von Dateien erhalten. Die Funktion "Anwendungseinstellungen" trägt diesen Anforderungen Rechnung und stellt eine einfache Möglichkeit dar, beide Arten von Einstellungen auf dem Clientcomputer zu speichern. Nachdem Sie diese Einstellungen mithilfe von Visual Studio oder einem Code-Editor definiert haben, werden die Einstellungen als XML beibehalten und zur Laufzeit automatisch in den Arbeitsspeicher eingelesen.

#### <a name="display-and-manipulate-data"></a>Anzeigen und Bearbeiten von Daten

Ausführliche Informationen zur Verwendung dieser Features finden Sie in den folgenden Hilfethemen.

|Beschreibung|Hilfethema|
|-----------------|----------------|
|Verwenden der <xref:System.Windows.Forms.BindingSource>-Komponente|[Vorgehensweise: Binden von Windows Forms-Steuerelementen mithilfe der BindingSource-Komponente, die mithilfe des Designers](./controls/bind-wf-controls-with-the-bindingsource.md)|
|Arbeiten mit [!INCLUDE[vstecado](../../../includes/vstecado-md.md)]-Datenquellen|[Vorgehensweise: Sortieren und Filtern von ADO.NET-Daten mit der Windows Forms-BindingSource-Komponente](./controls/sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)|
|Verwenden des Datenquellenfensters|[Binden von Windows Forms-Steuerelementen an Daten in Visual Studio](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)|
|Verwenden von Anwendungseinstellungen|[Vorgehensweise: Erstellen von Anwendungseinstellungen](./advanced/how-to-create-application-settings.md)|

### <a name="deploy-apps-to-client-computers"></a>Bereitstellen von apps auf Client-Computern

Nach dem Erstellen müssen Sie die Anwendung an Ihre Benutzer senden, damit diese die Anwendung auf dem eigenen Clientcomputer installieren und ausführen können. Bei Verwendung der [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] -Technologie, Sie können Ihre Anwendungen innerhalb von Visual Studio mithilfe von ein paar Mausklicks bereitstellen und Ihren Benutzern eine URL verweist auf die Anwendung im Web bereitstellen. [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] verwaltet alle Elemente und Abhängigkeiten in der Anwendung und stellt sicher, dass die Anwendung auf dem Clientcomputer ordnungsgemäß installiert ist.

[!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)]-Anwendungen können so konfiguriert werden, dass sie nur ausgeführt werden, wenn der Benutzer mit dem Netzwerk verbunden ist, oder dass sie sowohl online als auch offline ausgeführt werden können. Wenn Sie angeben, dass eine Anwendung den Offlinebetrieb unterstützen soll, fügt [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] im Menü **Start** des Benutzers einen Link zur Anwendung hinzu. Der Benutzer kann die Anwendung dann auch ohne die URL öffnen.

Wenn Sie die Anwendung aktualisieren, veröffentlichen Sie auf dem Webserver ein neues Bereitstellungsmanifest und eine neue Kopie der Anwendung. [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] erkennt, dass ein Update verfügbar ist, und aktualisiert die Installation des Benutzers. Zum Aktualisieren von alten Assemblys ist keine benutzerdefinierte Programmierung erforderlich.

#### <a name="deploy-clickonce-apps"></a>Bereitstellen von ClickOnce-apps

Eine umfassende Einführung in [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] finden Sie unter [ClickOnce-Sicherheit und -Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment). Ausführliche Informationen zur Verwendung dieser Funktionen finden Sie in den folgenden Hilfethemen.

|Beschreibung|Hilfethema|
|-----------------|----------------|
|Bereitstellung einer Anwendung mithilfe von [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)]|[Vorgehensweise: Veröffentlichen einer ClickOnce-Anwendung mit dem Webpublishing-Assistenten](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [Exemplarische Vorgehensweise: Manuelles Bereitstellen einer ClickOnce-Anwendung](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|
|Aktualisieren einer [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)]-Bereitstellung|[Vorgehensweise: Verwalten von Aktualisierungen für eine ClickOnce-Anwendung](/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|
|Verwalten der Sicherheit mithilfe von [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)]|[Vorgehensweise: Aktivieren von ClickOnce-Sicherheitseinstellungen](/visualstudio/deployment/how-to-enable-clickonce-security-settings)|

### <a name="other-controls-and-features"></a>Andere Steuerelemente und features

In Windows Forms stehen viele weitere Features bereit, mit denen häufige Aufgaben schnell und einfach ausgeführt werden können, beispielsweise zum Erstellen von Dialogfeldern, Drucken, Hinzufügen von Hilfe und Dokumentation sowie zum Lokalisieren von Anwendungen in mehrere Sprachen. Darüber hinaus verwendet die stabiles Sicherheitssystem von .NET Framework Windows Forms. Mit diesem System können Sie für Ihre Kunden Anwendungen bereitstellen, die erhöhte Sicherheitsanforderungen erfüllen.

#### <a name="implement-other-controls-and-features"></a>Implementieren Sie weiterer Steuerelemente und features

Ausführliche Informationen zur Verwendung dieser Features finden Sie in den folgenden Hilfethemen.

|Beschreibung|Hilfethema|
|-----------------|----------------|
|Drucken des Inhalts eines Formulars|[Vorgehensweise: Drucken von Grafiken in Windows Forms](./advanced/how-to-print-graphics-in-windows-forms.md)<br /><br /> [Vorgehensweise: Drucken einer mehrseitigen Textdatei in Windows Forms](./advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)|
|Weitere Informationen zur Windows Forms-Sicherheit|[Übersicht über die Sicherheit in Windows Forms](security-in-windows-forms-overview.md)|

## <a name="see-also"></a>Siehe auch

- [Erste Schritte mit Windows Forms](getting-started-with-windows-forms.md)
- [Erstellen neuer Windows Forms](creating-a-new-windows-form.md)
- [Übersicht über das ToolStrip-Steuerelement](./controls/toolstrip-control-overview-windows-forms.md)
- [Übersicht über das DataGridView-Steuerelement](./controls/datagridview-control-overview-windows-forms.md)
- [Übersicht über die BindingSource-Komponente](./controls/bindingsource-component-overview.md)
- [Übersicht über Anwendungseinstellungen](./advanced/application-settings-overview.md)
- [ClickOnce-Sicherheit und Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment)
