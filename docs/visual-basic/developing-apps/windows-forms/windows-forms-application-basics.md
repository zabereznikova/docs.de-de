---
title: Windows Forms-Anwendung Grundlagen (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Windows applications
- Windows Forms, Visual Basic
ms.assetid: 0b919d30-7fd6-42db-85c8-543d15312441
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8275d3c06ebd89254a07127b4850d32ef0580830
ms.lasthandoff: 03/13/2017

---
# <a name="windows-forms-application-basics-visual-basic"></a>Grundlagen zu Windows Forms-Anwendungen (Visual Basic)
Ein wichtiger Bestandteil der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ist die Möglichkeit, Windows Forms-Anwendung erstellen, die lokal auf dem Computer des Benutzers ausgeführt. Sie können Visual Studio verwenden, die mithilfe von Windows Forms-Anwendung und die Benutzeroberfläche zu erstellen. Windows Forms-Anwendung baut auf Klassen aus dem <xref:System.Windows.Forms>Namespace.</xref:System.Windows.Forms>  
  
## <a name="designing-windows-forms-applications"></a>Entwerfen von Windows Forms-Anwendung  
 Sie können Windows Forms und Windows-dienstanwendungen mit erstellen [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]. Weitere Informationen finden Sie unter den folgenden Themen:  
  
-   [Erste Schritte mit Windows Forms](https://msdn.microsoft.com/library/ms229601.aspx). Enthält Informationen zum Erstellen und Programmieren von Windows Forms.  
   
-   [Windows Forms-Steuerelemente](https://msdn.microsoft.com/library/ettb6e2a.aspx). Auflistung der Themen, die Verwendung von Windows Forms-Steuerelemente.  
  
-   [Windows-Dienstanwendungen](https://msdn.microsoft.com/library/y817hyb6.aspx). Enthält Themen, in denen Erstellen von Windows-Diensten erläutert.  
  
## <a name="building-rich-interactive-user-interfaces"></a>Erstellen von interaktiven Benutzeroberflächen mit anspruchsvollen Grafiken  
 Windows Forms ist die Smart Client-Komponente von der [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], ein Satz verwalteter Bibliotheken, die generelle Anwendungsaufgaben wie Lesen und Schreiben in das Dateisystem ermöglichen. Mit einer Entwicklungsumgebung wie [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], Sie können Windows Forms-Anwendung, die Informationen anzeigen, Eingaben von Benutzern anfordern und die Kommunikation über ein Netzwerk mit Remotecomputern erstellen.  
  
 In Windows Forms ist ein Formular eine visuelle Oberfläche, auf der Informationen für den Benutzer angezeigt. Im Allgemeinen erstellen Sie Windows Forms-Anwendung durch Platzieren von Steuerelementen auf Formularen und Antworten auf Benutzeraktionen wie Mausklicks oder Tastatureingaben entwickeln. Ein *Steuerelement* ist ein Element der Benutzeroberfläche (UI), das Daten anzeigt oder Dateneingaben akzeptiert.  
  
### <a name="events"></a>Ereignisse  
 Wenn ein Benutzer Aktionen im Formular oder in enthaltenen Steuerelementen ausführt, wird ein Ereignis generiert. Die Anwendung reagiert auf diese Ereignisse und verarbeitet sie zum Zeitpunkt ihres Auftretens. Weitere Informationen finden Sie unter [Erstellen von Ereignishandlern in Windows Forms](https://msdn.microsoft.com/library/dacysss4.aspx).  
  
### <a name="controls"></a>Steuerelemente  
 Windows Forms enthält eine Vielzahl von Steuerelementen, die Sie in Formularen platzieren können: Steuerelemente zur Anzeige von Textfeldern, Schaltflächen, Dropdownfeldern, Optionsfeldern und sogar Webseiten. Eine Liste aller Steuerelemente, die Sie in einem Formular verwenden können, finden Sie unter [Steuerelemente für Windows Forms](https://msdn.microsoft.com/library/3xdhey7w.aspx). Wenn ein vorhandenes Steuerelement nicht Ihren Bedürfnissen entspricht, unterstützt Windows Forms auch Erstellen Ihrer eigenen benutzerdefinierten Steuerelemente mithilfe der <xref:System.Windows.Forms.UserControl>Klasse.</xref:System.Windows.Forms.UserControl>  
  
 Windows Forms verfügt über komplexe Steuerelemente für die Benutzeroberfläche, mit denen Funktionen aus Anwendungen wie Microsoft Office emuliert werden können. Mithilfe der <xref:System.Windows.Forms.ToolStrip>und <xref:System.Windows.Forms.MenuStrip>-Steuerelement können Sie Symbolleisten und Menüs, die Text und Bilder enthalten, Untermenüs und andere Steuerelemente wie Textfelder und Kombinationsfelder erstellen.</xref:System.Windows.Forms.MenuStrip> </xref:System.Windows.Forms.ToolStrip>  
  
 Mit der [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Drag-and-Drop-Forms-Designer können Sie problemlos Windows Forms-Anwendung erstellen: einfach wählen Sie die Steuerelemente mit dem Cursor und platzieren sie Sie auf dem Formular möchten. Der Designer bietet Tools wie Rasterlinien und "Snap" Steuerelemente ausgerichtet werden. Und ob verwendet [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] oder Kompilieren in der Befehlszeile können Sie die <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel>und <xref:System.Windows.Forms.SplitContainer>Steuerelemente erstellen Formularlayouts mit minimalem Zeit- und Arbeitsaufwand.</xref:System.Windows.Forms.SplitContainer> </xref:System.Windows.Forms.TableLayoutPanel> </xref:System.Windows.Forms.FlowLayoutPanel>  
  
### <a name="custom-ui-elements"></a>Benutzerdefinierte Benutzeroberflächenelemente  
 Schließlich, wenn Sie eigene benutzerdefinierte Benutzeroberflächenelemente erstellen, müssen die <xref:System.Drawing>-Namespace enthält alle Klassen Sie Linien, Kreise und andere Formen direkt auf einem Formular zu rendern müssen.</xref:System.Drawing>  
  
 Detaillierte Informationen zur Verwendung dieser Funktionen finden Sie unter den folgenden Hilfethemen.  
  
|Beschreibung|Siehe|  
|--------|---------|  
|Erstellen einer neuen Windows Forms-Anwendung mit[!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]|[Exemplarische Vorgehensweise: Erstellen eines einfachen Windows Forms](http://msdn.microsoft.com/en-us/2d9daec0-0543-41d0-acb1-964f685bddbb)|  
|Verwenden von Steuerelementen auf Formularen|[Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](https://msdn.microsoft.com/library/0h5y8567.aspx)|   
|Erstellen von Grafiken mit<xref:System.Drawing></xref:System.Drawing>|[Erste Schritte mit Grafikprogrammierung](https://msdn.microsoft.com/library/da0f23z7.aspx)|  
|Erstellen benutzerdefinierter Steuerelemente|[Gewusst wie: erben von der UserControl-Klasse](https://msdn.microsoft.com/library/00ctb4z0.aspx)|  
  
## <a name="displaying-and-manipulating-data"></a>Anzeigen und Bearbeiten von Daten  
 Viele Anwendungen müssen Daten aus einer Datenbank, einer XML-Datei, einem XML-Webdienst oder einer anderen Datenquelle anzeigen. Windows Forms bietet ein flexibles Steuerelement namens der <xref:System.Windows.Forms.DataGridView>Steuerelement zum Rendern von Tabellendaten in einem herkömmlichen Zeilen- und Format, sodass jedes Datenelement seine eigene Zelle belegt.</xref:System.Windows.Forms.DataGridView> Mit <xref:System.Windows.Forms.DataGridView>können Sie die Darstellung einzelner Zellen anpassen, beliebige Zeilen und Spalten fixieren und komplexe Steuerelemente innerhalb von Zellen andere Funktionen anzeigen.</xref:System.Windows.Forms.DataGridView>  
  
 Mit intelligenten Windows Forms-Clients kann problemlos eine Netzwerkverbindung zu Datenquellen hergestellt werden. Die <xref:System.Windows.Forms.BindingSource>Komponente, die neu für Windows Forms in [!INCLUDE[vsprvslong](../../../csharp/misc/includes/vsprvslong_md.md)] und [!INCLUDE[dnprdnlong](../../../csharp/programming-guide/events/includes/dnprdnlong_md.md)], stellt eine Verbindung mit einer Datenquelle dar und macht Methoden zum Binden von Daten an Steuerelemente, Navigieren zum vorherigen bzw. nächsten Datensatz, Bearbeiten von Datensätzen und Speichern von Änderungen in der ursprünglichen Quelle verfügbar.</xref:System.Windows.Forms.BindingSource> Die <xref:System.Windows.Forms.BindingNavigator>Steuerelement stellt eine einfache Schnittstelle bereit, über die <xref:System.Windows.Forms.BindingSource>zum Navigieren zwischen Datensätzen-Komponente.</xref:System.Windows.Forms.BindingSource> </xref:System.Windows.Forms.BindingNavigator>  
  
### <a name="data-bound-controls"></a>Datengebundene Steuerelemente  
 Sie können datengebundene Steuerelemente problemlos mit dem Fenster "Datenquellen", das Datenquellen wie Datenbanken, Webdienste und Objekte in Ihrem Projekt anzeigt erstellen. Zum Erstellen datengebundener Steuerelemente können Sie Elemente aus diesem Fenster auf Formulare im Projekt ziehen. Darüber hinaus können Sie auch bestehende Steuerelemente an Daten binden, indem Sie Objekte aus dem Datenquellenfenster auf bestehende Steuerelemente ziehen.  
  
### <a name="settings"></a>Einstellungen  
 Ein weiterer ist Datenbindungsfunktionen in Windows Forms verwalten können Einstellungen. Die meisten intelligenten Clientanwendungen müssen bestimmte Informationen über ihren Laufzeitzustand, z. B. die zuletzt bekannte Größe des Formulars, und Einstellungen Benutzer Daten, z. B. Standardspeicherorte für gespeicherte Dateien beibehalten. Die anwendungseinstellungsfunktion erfüllt diese Anforderungen durch eine einfache Möglichkeit zum Speichern von beide Arten von Einstellungen auf dem Clientcomputer bereitstellen. Einmal definiert entweder [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] oder einem Code-Editor diese Einstellungen als XML beibehalten und zur Laufzeit automatisch in den Arbeitsspeicher eingelesen.  
  
 Detaillierte Informationen zur Verwendung dieser Funktionen finden Sie unter den folgenden Hilfethemen.  
  
|Beschreibung|Siehe|  
|--------|---------|  
|Verwenden Sie die <xref:System.Windows.Forms.BindingSource>Komponente</xref:System.Windows.Forms.BindingSource>|[Gewusst wie: Binden von Windows Forms-Steuerelementen an die BindingSource-Komponente mithilfe des Designers](https://msdn.microsoft.com/library/801dxw2t.aspx)|  
|Arbeiten mit [!INCLUDE[vstecado](../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)] -Datenquellen|[Gewusst wie: Sortieren und Filtern von ADO.NET-Daten mit der BindingSource-Komponente in Windows Forms](https://msdn.microsoft.com/library/ya3sah92.aspx)|  
|Verwenden Sie das Datenquellenfenster|[Exemplarische Vorgehensweise: Anzeigen von Daten in einem Windows Form](https://docs.microsoft.com/visualstudio/data-tools/accessing-data-in-visual-studio)|  
  
## <a name="deploying-applications-to-client-computers"></a>Bereitstellen von Anwendungen auf Clientcomputern  
 Nachdem Sie Ihre Anwendung geschrieben haben, müssen Sie es an Ihre Benutzer senden, damit sie installieren und auf dem eigenen Clientcomputer ausführen können. Mithilfe der [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] -Technologie können Sie Anwendungen in bereitstellen [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] unter Verwendung von nur wenigen Mausklicks und Benutzern eine URL verweist auf die Anwendung im Web zur Verfügung stellen. [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]verwaltet alle Elemente und Abhängigkeiten in Ihrer Anwendung, und stellt sicher, dass die Anwendung auf dem Clientcomputer installiert ist.  
  
 [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]-Anwendungen können so konfiguriert werden, dass sie nur ausgeführt werden, wenn der Benutzer mit dem Netzwerk verbunden ist, oder dass sie sowohl online als auch offline ausgeführt werden können. Wenn Sie angeben, dass eine Anwendung den Offlinebetrieb unterstützen soll [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] Fügt einen Link zu der Anwendung des Benutzers **Start** Menü, damit der Benutzer ohne die URL geöffnet werden kann.  
  
 Wenn Sie die Anwendung aktualisieren, veröffentlichen Sie auf dem Webserver ein neues Bereitstellungsmanifest und eine neue Kopie der Anwendung. [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]erkennt, dass ein Update verfügbar ist und aktualisiert die Installation des Benutzers. zum Aktualisieren von alten Assemblys ist keine benutzerdefinierte Programmierung erforderlich.  
  
 Eine umfassende Einführung in [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)], finden Sie unter [ClickOnce-Sicherheit und Bereitstellung](https://docs.microsoft.com/visualstudio/deployment/clickonce-security-and-deployment). Detaillierte Informationen zur Verwendung dieser Funktionen finden Sie unter den folgenden Hilfethemen:  
  
|Beschreibung|Siehe|  
|--------|---------|  
|Bereitstellen einer Anwendung mit[!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]|[Gewusst wie: Veröffentlichen einer ClickOnce-Anwendung mit dem Webpublishing-Assistenten](https://docs.microsoft.com/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [Exemplarische Vorgehensweise: Manuelles Bereitstellen einer ClickOnce-Anwendung](https://docs.microsoft.com/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|  
|Aktualisieren einer [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] Bereitstellung|[Gewusst wie: Verwalten von Aktualisierungen für eine ClickOnce-Anwendung](https://docs.microsoft.com/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|  
|Verwalten der Sicherheit mit[!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]|[Gewusst wie: Aktivieren von ClickOnce-Sicherheitseinstellungen](https://docs.microsoft.com/visualstudio/deployment/how-to-enable-clickonce-security-settings)|  
  
## <a name="other-controls-and-features"></a>Andere Steuerelemente und Funktionen  
 In Windows Forms stehen viele weitere Features bereit, mit denen häufige Aufgaben schnell und einfach ausgeführt werden können, beispielsweise zum Erstellen von Dialogfeldern, Drucken, Hinzufügen von Hilfe und Dokumentation sowie zum Lokalisieren von Anwendungen in mehrere Sprachen. Darüber hinaus bedient sich Windows Forms des stabilen Sicherheitssystems von der [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], aktivieren Sie sicherer Anwendungen für Ihre Kunden freigeben.  
  
 Detaillierte Informationen zur Verwendung dieser Funktionen finden Sie unter den folgenden Hilfethemen:  
  
|Beschreibung|Siehe|  
|--------|---------|  
|Drucken des Inhalts eines Formulars|[Gewusst wie: Drucken von Grafiken in Windows Forms](https://msdn.microsoft.com/library/741a0ktc.aspx)<br /><br /> [Gewusst wie: Drucken einer mehrseitigen Textdatei in Windows Forms](https://msdn.microsoft.com/library/cwbe712d.aspx)|   
|Weitere Informationen zur Windows Forms-Sicherheit|[Sicherheit in Windows Forms (Übersicht)](https://msdn.microsoft.com/library/90k49ccb.aspx)|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 [Übersicht über Windows Forms](https://msdn.microsoft.com/library/8bxxy49h.aspx)   
 [My.Forms-Objekt](../../../visual-basic/language-reference/objects/my-forms-object.md)
