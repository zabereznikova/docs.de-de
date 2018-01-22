---
title: "Grundlagen zu Windows Forms-Anwendungen (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Windows applications
- Windows Forms, Visual Basic
ms.assetid: 0b919d30-7fd6-42db-85c8-543d15312441
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7872d3c7b19ec9cd7059cccf41e5fab50d85123b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="windows-forms-application-basics-visual-basic"></a>Grundlagen zu Windows Forms-Anwendungen (Visual Basic)
Ein wichtiger Bestandteil der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] ist die Fähigkeit zum Erstellen von Windows Forms-Anwendungen, die lokal auf Benutzercomputern ausgeführt. Sie können Visual Studio verwenden, um die mit Windows Forms-Anwendung und die Benutzeroberfläche zu erstellen. Eine Windows Forms-Anwendung baut auf Klassen aus der <xref:System.Windows.Forms> Namespace.  
  
## <a name="designing-windows-forms-applications"></a>Entwerfen von Windows Forms-Anwendungen  
 Sie können Windows Forms und Windows-dienstanwendungen mit erstellen [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]. Weitere Informationen finden Sie unter den folgenden Themen:  
  
-   [Erste Schritte mit Windows Forms](../../../framework/winforms/getting-started-with-windows-forms.md). Enthält Informationen zum Erstellen und ein Programm Windows Forms bereit.  
   
-   [Windows Forms-Steuerelemente](../../../framework/winforms/controls/index.md). Die Auflistung von Themen, die Verwendung von Windows Forms-Steuerelemente.  
  
-   [Windows-Dienstanwendungen](../../../framework/windows-services/index.md). Enthält Themen, die erläutern, wie Windows-Dienste zu erstellen.  
  
## <a name="building-rich-interactive-user-interfaces"></a>Erstellen von interaktiven Benutzeroberflächen mit anspruchsvollen Grafiken  
 Windows Forms ist die Smartcard-Client-Komponente von der [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], einen Satz verwalteter Bibliotheken, die allgemeine Anwendungsaufgaben, z. B. Lesen und Schreiben in das Dateisystem zu ermöglichen. Verwenden einer Entwicklungsumgebung wie [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], Sie können Windows Forms-Anwendungen, die Informationen anzeigen, die Eingabe von Benutzer anfordern und die Kommunikation mit Remotecomputern über ein Netzwerk erstellen.  
  
 In Windows Forms ist ein Formular eine visuelle Oberfläche, die auf der Sie die Informationen für den Benutzer anzuzeigen. Im Allgemeinen erstellen Sie Windows Forms-Anwendungen durch Platzieren von Steuerelementen auf Formularen und Entwickeln von Antworten auf Benutzeraktionen, wie z. B. Mausklicks oder Tastatureingaben. Ein *Steuerelement* ist ein diskretes Benutzeroberflächenelement (UI-Element), das Daten anzeigt oder Dateneingaben akzeptiert.  
  
### <a name="events"></a>Ereignisse  
 Wenn ein Benutzer im Formular oder eines der Steuerelemente verfügt, wird ein Ereignis generiert. Die Anwendung reagiert auf diese Ereignisse und verarbeitet sie zum Zeitpunkt ihres Auftretens. Weitere Informationen finden Sie unter [Erstellen von Ereignishandlern in Windows Forms](../../../framework/winforms/creating-event-handlers-in-windows-forms.md).  
  
### <a name="controls"></a>Steuerelemente  
 Windows Forms enthält eine Vielzahl von Steuerelementen, die Sie in Formularen platzieren können: Steuerelemente zur Anzeige von Textfeldern, Schaltflächen, Dropdownfeldern, Optionsfeldern und sogar Webseiten. Eine Liste aller Steuerelemente, die in einem Formular verwendet werden können, finden Sie unter [Steuerelemente für Windows Forms](../../../framework/winforms/controls/controls-to-use-on-windows-forms.md). Windows Forms unterstützt über die <xref:System.Windows.Forms.UserControl>-Klasse auch das Erstellen benutzerdefinierter Steuerelemente, wenn ein vorhandenes Steuerelement für Ihre Anforderungen nicht geeignet ist.  
  
 Windows Forms verfügt über komplexe Steuerelemente für die Benutzeroberfläche, mit denen Funktionen aus Anwendungen wie Microsoft Office emuliert werden können. Mithilfe der <xref:System.Windows.Forms.ToolStrip> und <xref:System.Windows.Forms.MenuStrip> -Steuerelement, können Sie Symbolleisten und Menüs, die Text und Bilder enthalten, Untermenüs oder weitere Steuerelemente wie z. B. Textfelder und Kombinationsfelder erstellen.  
  
 Mit der [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Drag-and-Drop-Forms-Designer können Sie problemlos Windows Forms-Anwendungen erstellen: Wählen Sie die Steuerelemente mit dem Mauszeiger einfach und ablegen, auf dem auf dem Formular werden sollen. Der Designer stellt Tools wie Rasterlinien und "Ausrichtungslinien" wird das Anordnen von Steuerelementen. Und gibt an, ob Sie [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] oder Kompilierung in der Befehlszeile können Sie die <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel> und <xref:System.Windows.Forms.SplitContainer> Steuerelemente zum Erstellen erweiterter komplexe Formularlayouts mit minimalem Aufwand.  
  
### <a name="custom-ui-elements"></a>Benutzerdefinierte Benutzeroberflächenelemente  
 Abschließend, wenn Sie eine eigene benutzerdefinierte UI-Elemente erstellen, müssen die <xref:System.Drawing> -Namespace enthält alle Klassen Sie Linien, Kreise und andere Formen direkt auf einem Formular zu rendern müssen.  
  
 Ausführliche Informationen zur Verwendung dieser Funktionen finden Sie unter den folgenden Hilfethemen.  
  
|Beschreibung|Siehe|  
|--------|---------|  
|Erstellen einer neuen Windows Forms-Anwendung mit[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]|[Exemplarische Vorgehensweise: Erstellen eines einfachen Windows Forms](http://msdn.microsoft.com/library/2d9daec0-0543-41d0-acb1-964f685bddbb)|  
|Verwenden von Steuerelementen auf Formularen|[Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../framework/winforms/controls/how-to-add-controls-to-windows-forms.md)|   
|Erstellen von Grafiken mit<xref:System.Drawing>|[Erste Schritte mit Grafikprogrammierung](../../../framework/winforms/advanced/getting-started-with-graphics-programming.md)|  
|Erstellen benutzerdefinierter Steuerelemente|[Vorgehensweise: Erben von der UserControl-Klasse](../../../framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)|  
  
## <a name="displaying-and-manipulating-data"></a>Anzeigen und Bearbeiten von Daten  
 Viele Anwendungen müssen Daten aus einer Datenbank, einer XML-Datei, einem XML-Webdienst oder einer anderen Datenquelle anzeigen. Windows Forms bietet ein flexibles Steuerelement die <xref:System.Windows.Forms.DataGridView> Steuerelement für das Rendern von Tabellendaten in einem herkömmlichen Zeilen- und Spaltenformat, damit jedes Datenelement eigenen Zelle enthalten. Mit <xref:System.Windows.Forms.DataGridView> können Sie die Darstellung einzelner Zellen anpassen, beliebiger Zeilen und Spalten zu sperren und komplexe Steuerelemente in einer Zelle, für andere Funktionen anzeigen.  
  
 Mit intelligenten Windows Forms-Clients kann problemlos eine Netzwerkverbindung zu Datenquellen hergestellt werden. Die <xref:System.Windows.Forms.BindingSource>-Komponente, die erstmals für Windows Forms in [!INCLUDE[vsprvslong](~/includes/vsprvslong-md.md)] und [!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)] verfügbar ist, stellt eine Verbindung zu einer Datenquelle dar und macht Methoden zum Binden von Daten an Steuerelemente, Navigieren zum vorherigen oder nächsten Datensatz, Bearbeiten von Datensätzen und Speichern von Änderungen in der ursprünglichen Quelle verfügbar. Das <xref:System.Windows.Forms.BindingNavigator>-Steuerelement stellt über die <xref:System.Windows.Forms.BindingSource>-Komponente eine einfache Schnittstelle zum Navigieren zwischen Datensätzen bereit.  
  
### <a name="data-bound-controls"></a>Datengebundene Steuerelemente  
 Sie können angeben, Erstellen von datengebundenen Steuerelementen, die leicht mit dem Fenster "Datenquellen", in dem Datenquellen wie Datenbanken, Webdienste und Objekte in Ihrem Projekt angezeigt. Zum Erstellen datengebundener Steuerelemente können Sie Elemente aus diesem Fenster auf Formulare im Projekt ziehen. Darüber hinaus können Sie auch bestehende Steuerelemente an Daten binden, indem Sie Objekte aus dem Datenquellenfenster auf bestehende Steuerelemente ziehen.  
  
### <a name="settings"></a>Einstellungen  
 Einen anderen Typ von datenbindungen, die Sie in Windows Forms verwalten können, ist Einstellungen. Die meisten intelligenten Clientanwendungen müssen bestimmte Informationen über ihren Laufzeitzustand, z. B. die zuletzt bekannte Größe des Formulars, und behalten Sie benutzereinstellung Daten, wie Standardspeicherorte gespeicherten Dateien. Die Funktion "-Anwendungseinstellungen" trägt diesen Anforderungen Rechnung bietet eine einfache Möglichkeit zum beide Arten von Einstellungen auf dem Clientcomputer zu speichern. Einmal definiert entweder [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] oder einem Code-Editor, diese Einstellungen als XML beibehalten und automatisch zur Laufzeit in den Arbeitsspeicher eingelesen werden.  
  
 Ausführliche Informationen zur Verwendung dieser Funktionen finden Sie unter den folgenden Hilfethemen.  
  
|Beschreibung|Siehe|  
|--------|---------|  
|Verwenden der <xref:System.Windows.Forms.BindingSource> Komponente|[Vorgehensweise: Binden von Windows Forms-Steuerelementen an die BindingSource-Komponente mithilfe des Designers](../../../framework/winforms/controls/bind-wf-controls-with-the-bindingsource.md)|  
|Arbeiten mit [!INCLUDE[vstecado](~/includes/vstecado-md.md)] -Datenquellen|[Vorgehensweise: Sortieren und Filtern von ADO.NET-Daten mit der BindingSource-Komponente in Windows Forms](https://msdn.microsoft.com/library/ya3sah92.aspx)|  
|Verwenden Sie das Fenster "Datenquellen"|[Exemplarische Vorgehensweise: Anzeigen von Daten in einem Windows Form](/visualstudio/data-tools/accessing-data-in-visual-studio)|  
  
## <a name="deploying-applications-to-client-computers"></a>Bereitstellen von Anwendungen auf Clientcomputern  
 Nachdem Sie Ihre Anwendung geschrieben haben, müssen Sie es für Ihre Benutzer senden, damit sie installieren können, und führen Sie es auf dem eigenen Clientcomputer. Mithilfe der [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] -Technologie können Sie Anwendungen in bereitstellen [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] mithilfe von nur wenigen Klicks und Benutzern eine URL verweist auf die Anwendung im Web zur Verfügung stellen. [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]verwaltet alle Elemente und Abhängigkeiten in Ihrer Anwendung, und stellt sicher, dass die Anwendung ordnungsgemäß auf dem Clientcomputer installiert ist.  
  
 [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]-Anwendungen können so konfiguriert werden, dass sie nur ausgeführt werden, wenn der Benutzer mit dem Netzwerk verbunden ist, oder dass sie sowohl online als auch offline ausgeführt werden können. Wenn Sie angeben, dass eine Anwendung den Offlinebetrieb unterstützen soll [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] Fügt einen Link zur Anwendung des Benutzers **starten** Menü, damit der Benutzer es öffnen kann, ohne die URL.  
  
 Wenn Sie die Anwendung aktualisieren, veröffentlichen Sie auf dem Webserver ein neues Bereitstellungsmanifest und eine neue Kopie der Anwendung. [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]erkennt, dass ein Update verfügbar ist und aktualisiert die Installation des Benutzers. zum Aktualisieren von alten Assemblys ist keine benutzerdefinierte Programmierung erforderlich.  
  
 Eine umfassende Einführung in [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] finden Sie unter [ClickOnce-Sicherheit und -Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment). Ausführliche Informationen zur Verwendung dieser Funktionen finden Sie unter den folgenden Hilfethemen:  
  
|Beschreibung|Siehe|  
|--------|---------|  
|Bereitstellen einer Anwendung mit[!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]|[Gewusst wie: Veröffentlichen einer ClickOnce-Anwendung mit dem Webpublishing-Assistenten](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [Exemplarische Vorgehensweise: Manuelles Bereitstellen einer ClickOnce-Anwendung](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|  
|Update einer [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] Bereitstellung|[Gewusst wie: Verwalten von Aktualisierungen für eine ClickOnce-Anwendung](/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|  
|Verwalten der Sicherheit mit[!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]|[Gewusst wie: Aktivieren von ClickOnce-Sicherheitseinstellungen](/visualstudio/deployment/how-to-enable-clickonce-security-settings)|  
  
## <a name="other-controls-and-features"></a>Andere Steuerelemente und Funktionen  
 In Windows Forms stehen viele weitere Features bereit, mit denen häufige Aufgaben schnell und einfach ausgeführt werden können, beispielsweise zum Erstellen von Dialogfeldern, Drucken, Hinzufügen von Hilfe und Dokumentation sowie zum Lokalisieren von Anwendungen in mehrere Sprachen. Darüber hinaus bedient sich Windows Forms des stabilen Sicherheitssystems von der [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], sodass Sie sicherere Anwendungen an Ihre Kunden freigeben.  
  
 Ausführliche Informationen zur Verwendung dieser Funktionen finden Sie unter den folgenden Hilfethemen:  
  
|Beschreibung|Siehe|  
|--------|---------|  
|Drucken des Inhalts eines Formulars|[Vorgehensweise: Drucken von Grafiken in Windows Forms](../../../framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)<br /><br /> [Vorgehensweise: Drucken einer mehrseitigen Textdatei in Windows Forms](../../../framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)|   
|Weitere Informationen zur Windows Forms-Sicherheit|[Übersicht über die Sicherheit in Windows Forms](../../../framework/winforms/security-in-windows-forms-overview.md)|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>  
 [Übersicht über Windows Forms](../../../framework/winforms/windows-forms-overview.md)  
 [My.Forms-Objekt](../../../visual-basic/language-reference/objects/my-forms-object.md)
