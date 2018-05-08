---
title: Übersicht über Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- smart clients
- Windows Forms, about Windows Forms
ms.assetid: 3a2b6284-c8d6-4e1c-8c69-0bed38f38cd4
ms.openlocfilehash: 50c88aec8ac57be2ab317ac91464d68503607738
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="windows-forms-overview"></a>Übersicht über Windows Forms
Der folgende Abschnitt enthält eine Übersicht über die Vorteile von intelligenten Clientanwendungen, die wichtigsten Funktionen der Windows Forms-Programmierung und die Verwendung von Windows Forms zur Erstellung von intelligenten Clients, die die Anforderungen moderner Unternehmen und Endbenutzer erfüllen.  
  
## <a name="windows-forms-and-smart-client-applications"></a>Windows Forms und intelligente Clientanwendungen  
 Windows Forms dient der Entwicklung von intelligenten Clients. *Intelligente Clients* sind grafisch anspruchsvolle Anwendungen, die einfach bereitgestellt und aktualisiert werden können. Darüber hinaus kann eine intelligente Clientanwendung sowohl im Online- als auch im Offlinebetrieb verwendet werden und bietet gegenüber herkömmlichen Windows-Anwendungen erhöhte Sicherheit beim Zugriff auf lokale Computerressourcen.  
  
### <a name="building-rich-interactive-user-interfaces"></a>Erstellen von interaktiven Benutzeroberflächen mit anspruchsvollen Grafiken  
 Windows Forms ist die Technologie zur Erstellung intelligenter Clients für [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]. Dieser Satz verwalteter Bibliotheken erleichtert allgemeine Anwendungsaufgaben, z. B. Lese- und Schreibzugriffe auf das Dateisystem. Wenn Sie eine Entwicklungsumgebung wie Visual Studio verwenden, können Sie Windows Forms intelligenten Clientanwendungen, die Informationen anzeigen, die Eingabe von Benutzer anfordern und die Kommunikation mit Remotecomputern erstellen, über ein Netzwerk.  
  
 In Windows Forms stellt ein *Formular* eine visuelle Oberfläche dar, auf der Informationen für den Benutzer angezeigt werden. In der Regel erstellen Sie Windows Forms-Anwendungen, indem Sie Steuerelemente in Formulare einfügen und Antworten auf Benutzeraktionen, wie Maus- und Tastatureingaben, entwickeln. Ein *Steuerelement* ist ein diskretes Benutzeroberflächenelement (UI-Element), das Daten anzeigt oder Dateneingaben akzeptiert.  
  
 Wenn ein Benutzer Aktionen im Formular oder in enthaltenen Steuerelementen ausführt, wird ein Ereignis generiert. Die Anwendung reagiert auf diese Ereignisse und verarbeitet sie zum Zeitpunkt ihres Auftretens. Weitere Informationen finden Sie unter [Erstellen von Ereignishandlern in Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md).  
  
 Windows Forms enthält eine Vielzahl von Steuerelementen, die Sie Formularen hinzufügen können: Steuerelemente zur Anzeige von Textfeldern, Schaltflächen, Dropdownfeldern, Optionsfeldern und sogar Webseiten. Eine Liste aller Steuerelemente, die in einem Formular verwendet werden können, finden Sie unter [Steuerelemente für Windows Forms](../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md). Windows Forms unterstützt über die <xref:System.Windows.Forms.UserControl>-Klasse auch das Erstellen benutzerdefinierter Steuerelemente, wenn ein vorhandenes Steuerelement für Ihre Anforderungen nicht geeignet ist.  
  
 Windows Forms verfügt über komplexe Steuerelemente für die Benutzeroberfläche, mit denen Features aus Anwendungen wie Microsoft Office emuliert werden können. Mit dem <xref:System.Windows.Forms.ToolStrip>-Steuerelement und dem <xref:System.Windows.Forms.MenuStrip>-Steuerelement können Sie Symbolleisten und Menüs erstellen, die Texte und Bilder, Untermenüs oder weitere Steuerelemente enthalten, z. B. Textfelder und Kombinationsfelder.  
  
 Mit dem Visual Studio Drag & Drop-Windows Forms-Designer können Sie Windows Forms-Anwendungen problemlos erstellen. Wählen Sie Steuerelemente einfach mit dem Mauszeiger aus, und fügen Sie sie an der gewünschten Stelle im Formular ein. Der Designer stellt Tools wie Rasterlinien und Ausrichtungslinien bereit, um das Anordnen von Steuerelementen zu erleichtern. Und, ob Sie mithilfe von Visual Studio oder über die Befehlszeile kompilieren, können Sie die <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel> und <xref:System.Windows.Forms.SplitContainer> Steuerelemente zum Erstellen erweiterter Formularlayouts weniger Zeit.  
  
 Schließlich enthält der <xref:System.Drawing>-Namespace zum Erstellen eigener Benutzeroberflächenelemente eine Vielzahl von Klassen, um Linien, Kreise und andere Formen direkt auf einem Formular zu zeichnen.  
  
> [!NOTE]
>  Windows Forms-Steuerelemente wurden nicht für das Marshallen über Anwendungsdomänen hinweg entwickelt. Daher unterstützt Microsoft die Übergabe eines Windows Forms-Steuerelements über eine <xref:System.AppDomain>-Grenze hinweg nicht, auch wenn der <xref:System.Windows.Controls.Control>-Basistyp von <xref:System.MarshalByRefObject> den Anschein erweckt, als ob dies möglich wäre. Windows Forms-Anwendungen mit mehreren Anwendungsdomänen werden unterstützt, solange keine Windows Forms-Steuerelemente über die Grenzen von Anwendungsdomänen hinweg übergeben werden.  
  
#### <a name="help-creating-forms-and-controls"></a>Hilfe beim Erstellen von Formularen und Steuerelementen  
 Ausführliche Informationen zur Verwendung dieser Features finden Sie in den folgenden Hilfethemen.  
  
|Beschreibung|Hilfethema|  
|-----------------|----------------|  
|Verwenden von Steuerelementen auf Formularen|[Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)|  
|Verwenden des <xref:System.Windows.Forms.ToolStrip>-Steuerelements|[Vorgehensweise: Erstellen eines einfachen ToolStrip mit Standardelementen im Designer](../../../docs/framework/winforms/controls/create-a-basic-wf-toolstrip-with-standard-items-using-the-designer.md)|  
|Erstellen von Grafiken mithilfe von <xref:System.Drawing>|[Erste Schritte mit Grafikprogrammierung](../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)|  
|Erstellen benutzerdefinierter Steuerelemente|[Vorgehensweise: Erben von der UserControl-Klasse](../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)|  
  
### <a name="displaying-and-manipulating-data"></a>Anzeigen und Bearbeiten von Daten  
 Viele Anwendungen müssen Daten aus einer Datenbank, einer XML-Datei, einem XML-Webdienst oder einer anderen Datenquelle anzeigen. Mit dem <xref:System.Windows.Forms.DataGridView>-Steuerelement bietet Windows Forms ein flexibles Steuerelement zum Anzeigen von Tabellendaten im herkömmlichen Zeilen- und Spaltenformat, bei dem jedes Datenelement in einer eigenen Zelle enthalten ist. Mit <xref:System.Windows.Forms.DataGridView> können Sie die Darstellung einzelner Zellen anpassen, die Position beliebiger Zeilen oder Spalten fixieren und komplexe Steuerelemente in einer Zelle anzeigen, um nur einige Features zu nennen.  
  
 Mit intelligenten Windows Forms-Clients kann problemlos eine Netzwerkverbindung zu Datenquellen hergestellt werden. Die <xref:System.Windows.Forms.BindingSource>-Komponente, die erstmals für Windows Forms in [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] und [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)] verfügbar ist, stellt eine Verbindung zu einer Datenquelle dar und macht Methoden zum Binden von Daten an Steuerelemente, Navigieren zum vorherigen oder nächsten Datensatz, Bearbeiten von Datensätzen und Speichern von Änderungen in der ursprünglichen Quelle verfügbar. Das <xref:System.Windows.Forms.BindingNavigator>-Steuerelement stellt über die <xref:System.Windows.Forms.BindingSource>-Komponente eine einfache Schnittstelle zum Navigieren zwischen Datensätzen bereit.  
  
 Mit dem Datenquellenfenster können datengebundene Steuerelemente problemlos erstellt werden. In diesem Fenster werden die Datenquellen in Ihrem Projekt angezeigt, z. B. Datenbanken, Webdienste oder Objekte. Zum Erstellen datengebundener Steuerelemente können Sie Elemente aus diesem Fenster auf Formulare im Projekt ziehen. Darüber hinaus können Sie auch bestehende Steuerelemente an Daten binden, indem Sie Objekte aus dem Datenquellenfenster auf bestehende Steuerelemente ziehen.  
  
 Ein weiterer Datenbindungstyp, der in Windows Forms verwaltet werden kann, lautet *Einstellungen*. Die meisten intelligenten Clientanwendungen müssen bestimmte Informationen über ihren Laufzeitzustand, z. B. die zuletzt bekannte Größe des Formulars, sowie Benutzereinstellungen wie Standardspeicherorte von Dateien erhalten. Die Funktion "Anwendungseinstellungen" trägt diesen Anforderungen Rechnung und stellt eine einfache Möglichkeit dar, beide Arten von Einstellungen auf dem Clientcomputer zu speichern. Nachdem Sie diese Einstellungen mithilfe von Visual Studio oder einem Code-Editor definiert haben, werden die Einstellungen als XML beibehalten und automatisch zur Laufzeit in den Arbeitsspeicher eingelesen.  
  
#### <a name="help-displaying-and-manipulating-data"></a>Hilfe beim Anzeigen und Bearbeiten von Daten  
 Ausführliche Informationen zur Verwendung dieser Features finden Sie in den folgenden Hilfethemen.  
  
|Beschreibung|Hilfethema|  
|-----------------|----------------|  
|Verwenden der <xref:System.Windows.Forms.BindingSource>-Komponente|[Vorgehensweise: Binden von Windows Forms-Steuerelementen an die BindingSource-Komponente mithilfe des Designers](../../../docs/framework/winforms/controls/bind-wf-controls-with-the-bindingsource.md)|  
|Arbeiten mit [!INCLUDE[vstecado](../../../includes/vstecado-md.md)]-Datenquellen|[Vorgehensweise: Sortieren und Filtern von ADO.NET-Daten mit der BindingSource-Komponente in Windows Forms](../../../docs/framework/winforms/controls/sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)|  
|Verwenden des Datenquellenfensters|[Exemplarische Vorgehensweise: Anzeigen von Daten in einem Windows Form](http://msdn.microsoft.com/library/f6e08c2c-c792-43de-adf3-3e52c0100225)|  
|Verwenden von Anwendungseinstellungen|[Vorgehensweise: Erstellen von Anwendungseinstellungen](../../../docs/framework/winforms/advanced/how-to-create-application-settings.md)|  
  
### <a name="deploying-applications-to-client-computers"></a>Bereitstellen von Anwendungen auf Clientcomputern  
 Nach dem Erstellen müssen Sie die Anwendung an Ihre Benutzer senden, damit diese die Anwendung auf dem eigenen Clientcomputer installieren und ausführen können. Bei Verwendung der [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] Technologie, Sie können Anwendungen in Visual Studio mit nur wenigen Klicks bereitstellen und geben Sie Ihre Benutzer mit einer URL verweist auf die Anwendung im Web. [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] verwaltet alle Elemente und Abhängigkeiten in der Anwendung und stellt sicher, dass die Anwendung auf dem Clientcomputer ordnungsgemäß installiert ist.  
  
 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)]-Anwendungen können so konfiguriert werden, dass sie nur ausgeführt werden, wenn der Benutzer mit dem Netzwerk verbunden ist, oder dass sie sowohl online als auch offline ausgeführt werden können. Wenn Sie angeben, dass eine Anwendung den Offlinebetrieb unterstützen soll, fügt [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] im Menü **Start** des Benutzers einen Link zur Anwendung hinzu. Der Benutzer kann die Anwendung dann auch ohne die URL öffnen.  
  
 Wenn Sie die Anwendung aktualisieren, veröffentlichen Sie auf dem Webserver ein neues Bereitstellungsmanifest und eine neue Kopie der Anwendung. [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] erkennt, dass ein Update verfügbar ist, und aktualisiert die Installation des Benutzers. Zum Aktualisieren von alten Assemblys ist keine benutzerdefinierte Programmierung erforderlich.  
  
#### <a name="help-deploying-clickonce-applications"></a>Hilfe beim Bereitstellen von ClickOnce-Anwendungen  
 Eine umfassende Einführung in [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] finden Sie unter [ClickOnce-Sicherheit und -Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment). Ausführliche Informationen zur Verwendung dieser Funktionen finden Sie in den folgenden Hilfethemen.  
  
|Beschreibung|Hilfethema|  
|-----------------|----------------|  
|Bereitstellung einer Anwendung mithilfe von [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)]|[Gewusst wie: Veröffentlichen einer ClickOnce-Anwendung mit dem Webpublishing-Assistenten](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [Exemplarische Vorgehensweise: Manuelles Bereitstellen einer ClickOnce-Anwendung](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|  
|Aktualisieren einer [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)]-Bereitstellung|[Gewusst wie: Verwalten von Aktualisierungen für eine ClickOnce-Anwendung](/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|  
|Verwalten der Sicherheit mithilfe von [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)]|[Gewusst wie: Aktivieren von ClickOnce-Sicherheitseinstellungen](/visualstudio/deployment/how-to-enable-clickonce-security-settings)|  
  
### <a name="other-controls-and-features"></a>Andere Steuerelemente und Funktionen  
 In Windows Forms stehen viele weitere Features bereit, mit denen häufige Aufgaben schnell und einfach ausgeführt werden können, beispielsweise zum Erstellen von Dialogfeldern, Drucken, Hinzufügen von Hilfe und Dokumentation sowie zum Lokalisieren von Anwendungen in mehrere Sprachen. Darüber hinaus bedient sich Windows Forms des stabilen Sicherheitssystems von [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]. Mit diesem System können Sie für Ihre Kunden Anwendungen bereitstellen, die erhöhte Sicherheitsanforderungen erfüllen.  
  
#### <a name="help-implementing-other-controls-and-features"></a>Hilfe beim Implementieren weiterer Steuerelemente und Features   
 Ausführliche Informationen zur Verwendung dieser Features finden Sie in den folgenden Hilfethemen.  
  
|Beschreibung|Hilfethema|  
|-----------------|----------------|  
|Drucken des Inhalts eines Formulars|[Vorgehensweise: Drucken von Grafiken in Windows Forms](../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)<br /><br /> [Vorgehensweise: Drucken einer mehrseitigen Textdatei in Windows Forms](../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)|  
|Weitere Informationen zur Windows Forms-Sicherheit|[Übersicht über die Sicherheit in Windows Forms](../../../docs/framework/winforms/security-in-windows-forms-overview.md)|  
  
## <a name="see-also"></a>Siehe auch  
 [Erste Schritte mit Windows Forms](../../../docs/framework/winforms/getting-started-with-windows-forms.md)  
 [Erstellen neuer Windows Forms](../../../docs/framework/winforms/creating-a-new-windows-form.md)  
 [Übersicht über das ToolStrip-Steuerelement](../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [Übersicht über das DataGridView-Steuerelement](../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)  
 [Übersicht über die BindingSource-Komponente](../../../docs/framework/winforms/controls/bindingsource-component-overview.md)  
 [Übersicht über Anwendungseinstellungen](../../../docs/framework/winforms/advanced/application-settings-overview.md)  
 [ClickOnce-Sicherheit und Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment)
