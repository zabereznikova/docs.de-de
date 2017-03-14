---
title: "Windows Forms Application Basics (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Windows applications"
  - "Windows Forms, Visual Basic"
ms.assetid: 0b919d30-7fd6-42db-85c8-543d15312441
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Windows Forms Application Basics (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Ein wichtiger Bestandteil von [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] ist die Möglichkeit, Windows Forms\-Anwendungen zu erstellen, die lokal auf dem Computer des Benutzers ausgeführt werden.  Sie können Visual Studio verwenden, um die Anwendung und die Benutzeroberfläche mithilfe der Windows Forms zu erstellen.  Eine Windows Forms\-Anwendung wird auf Grundlage von Klassen aus dem <xref:System.Windows.Forms>\-Namespace erstellt.  
  
## Entwerfen von Windows Forms\-Anwendungen  
 Mit [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] können Sie Windows Forms\- und Windows\-Dienstanwendungen erstellen.  Weitere Informationen finden Sie unter den folgenden Themen:  
  
-   [Erste Schritte mit Windows Forms](../Topic/Getting%20Started%20with%20Windows%20Forms.md).  Stellt Informationen darüber bereit, wie Sie Windows Forms erstellen und programmieren können.  
  
-   [Windows Forms Walkthroughs](http://msdn.microsoft.com/de-de/fd44d13d-4733-416f-aefc-32592e59e5d9).  Enthält Themen mit schrittweisen Entwicklungsverfahren für häufig erstellte Windows Forms\-Anwendungen, die auf Windows Forms basieren.  
  
-   [Windows Forms\-Steuerelemente](../Topic/Windows%20Forms%20Controls.md).  Eine Reihe von Themen, in denen die Verwendung von Windows Forms\-Steuerelementen näher erläutert wird.  
  
-   [Windows Service Applications](../Topic/Developing%20Windows%20Service%20Applications.md).  Enthält Themen, in denen das Erstellen von Windows\-Diensten erklärt wird.  
  
## Erstellen von interaktiven Benutzeroberflächen mit anspruchsvollen Grafiken  
 Windows Forms ist die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]\-Komponente für intelligente Clients, eine Gruppe von verwalteten Bibliotheken, die häufig verwendete Aufgaben wie Lese\- und Schreibzugriffe auf das Dateisystem ermöglichen.  Mithilfe einer Entwicklungsumgebung wie [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] können Sie Windows Forms\-Anwendungen erstellen, die Informationen anzeigen, Benutzereingaben anfordern und mit Remotecomputern über ein Netzwerk kommunizieren.  
  
 In Windows Forms ist ein Formular eine visuelle Oberfläche, auf der Informationen für den Benutzer angezeigt werden.  Windows Forms\-Anwendungen werden in der Regel erstellt, indem Steuerelemente auf Formularen platziert und Reaktionen auf Benutzeraktionen wie Mausklicks oder gedrückte Tasten entwickelt werden.  Ein *Steuerelement* ist ein diskretes Benutzeroberflächenelement \(UI\-Element\), das Daten anzeigt oder Dateneingaben akzeptiert.  
  
### Ereignisse  
 Wenn ein Benutzer mit einem Formular oder einem der zugehörigen Steuerelemente interagiert, wird ein Ereignis ausgelöst.  Die Anwendung reagiert auf diese Ereignisse und verarbeitet sie zum Zeitpunkt ihres Auftretens.  Weitere Informationen hierzu finden Sie unter [Erstellen von Ereignishandlern in Windows Forms](../Topic/Creating%20Event%20Handlers%20in%20Windows%20Forms.md).  
  
### Steuerelemente  
 Windows Forms enthält verschiedene Steuerelemente, die Sie auf Formularen platzieren können, beispielsweise für Textfelder, Schaltflächen, Dropdownlisten, Optionsfelder und sogar Webseiten.  Eine Liste aller Steuerelemente, die Sie auf einem Formular verwenden können, finden Sie unter [Steuerelemente für Windows Forms](../Topic/Controls%20to%20Use%20on%20Windows%20Forms.md).  Windows Forms unterstützt über die <xref:System.Windows.Forms.UserControl>\-Klasse auch das Erstellen benutzerdefinierter Steuerelemente.  
  
 Darüber hinaus verfügt Windows Forms über komplexe Steuerelemente, mit denen Features aus Anwendungen wie Microsoft Office emuliert werden können.  Mithilfe des <xref:System.Windows.Forms.ToolStrip>\-Steuerelements und des <xref:System.Windows.Forms.MenuStrip>\-Steuerelements können Sie Symbolleisten und Menüs mit Texten, Bildern und Untermenüs erstellen, die wiederum andere Steuerelemente wie Textfelder und Kombinationsfelder enthalten können.  
  
 Mit dem Drag & Drop\-Formular\-Designer von [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] können Sie problemlos Windows Forms\-Anwendungen erstellen, indem Sie Steuerelemente mit dem Cursor markieren und an der gewünschten Stelle im Formular platzieren.  Mit Funktionen wie Rasterlinien und Ausrichtungslinien können Steuerelemente mühelos ausgerichtet werden.  Unabhängig davon, ob Sie [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] verwenden oder über die Befehlszeile kompilieren, können Sie mit dem <xref:System.Windows.Forms.FlowLayoutPanel>\-Steuerelement, dem <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement und dem <xref:System.Windows.Forms.SplitContainer>\-Steuerelement einfach und schnell komplexe Formularlayouts erstellen.  
  
### Benutzerdefinierte Benutzeroberflächenelemente  
 Wenn Sie benutzerdefinierte Benutzeroberflächenelemente erstellen möchten, können Sie den <xref:System.Drawing>\-Namespace verwenden, der alle benötigten Klassen zum Darstellen von Linien, Kreisen und anderen Formen auf einem Formular enthält.  
  
 In den folgenden Hilfethemen finden Sie Schritt\-für\-Schritt\-Anweisungen für die Verwendung dieser Features.  
  
|To|Siehe|  
|--------|-----------|  
|Erstellen einer neuen Windows Forms\-Anwendung mit [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]|[Walkthrough: Creating a Simple Windows Form](http://msdn.microsoft.com/de-de/2d9daec0-0543-41d0-acb1-964f685bddbb)|  
|Verwenden von Steuerelementen auf Formularen|[Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../Topic/How%20to:%20Add%20Controls%20to%20Windows%20Forms.md)|  
|Behandeln von Ereignissen aus einem Formular und dessen Steuerelementen|[How to: Create Event Handlers Using the Designer](http://msdn.microsoft.com/de-de/8461e9b8-14e8-406f-936e-3726732b23d2)|  
|Verwenden des <xref:System.Windows.Forms.ToolStrip>\-Steuerelements|[Gewusst wie: Erstellen eines einfachen ToolStrip mit Standardelementen im Designer](../Topic/How%20to:%20Create%20a%20Basic%20Windows%20Forms%20ToolStrip%20with%20Standard%20Items%20Using%20the%20Designer.md)|  
|Erstellen von Grafiken mit <xref:System.Drawing>|[Erste Schritte mit der Grafikprogrammierung](../Topic/Getting%20Started%20with%20Graphics%20Programming.md)|  
|Erstellen von benutzerdefinierten Steuerelementen|[Gewusst wie: Erben von der UserControl\-Klasse](../Topic/How%20to:%20Inherit%20from%20the%20UserControl%20Class.md)|  
  
## Anzeigen und Bearbeiten von Daten  
 Viele Anwendungen müssen Daten aus einer Datenbank, einer XML\-Datei, einem XML\-Webdienst oder einer anderen Datenquelle anzeigen.  Mit dem <xref:System.Windows.Forms.DataGridView>\-Steuerelement bietet Windows Forms ein flexibles Steuerelement für die Anzeige tabellarischer Daten in einem herkömmlichen Format mit Zeilen und Spalten, bei dem jedes Datenelement in einer eigenen Zelle angeordnet ist.  Bei Verwendung von <xref:System.Windows.Forms.DataGridView> können Sie beispielsweise das Aussehen einzelner Zellen anpassen, beliebige Zeilen und Spalten fixieren und innerhalb von Zellen komplexe Steuerelemente anzeigen.  
  
 Mit intelligenten Windows Forms\-Clients kann problemlos eine Netzwerkverbindung zu Datenquellen hergestellt werden.  Die <xref:System.Windows.Forms.BindingSource>\-Komponente, die erstmals für Windows Forms in [!INCLUDE[vsprvslong](~/includes/vsprvslong-md.md)] und [!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)] verfügbar ist, stellt eine Verbindung zu einer Datenquelle dar und macht Methoden zum Binden von Daten an Steuerelemente, Navigieren zum vorherigen oder nächsten Datensatz, Bearbeiten von Datensätzen und Speichern von Änderungen in der ursprünglichen Quelle verfügbar.  Das <xref:System.Windows.Forms.BindingNavigator>\-Steuerelement stellt über die <xref:System.Windows.Forms.BindingSource>\-Komponente eine einfache Schnittstelle zum Navigieren zwischen Datensätzen bereit.  
  
### Datengebundene Steuerelemente  
 Im Datenquellenfenster, in dem projektrelevante Datenquellen wie Datenbanken, Webdienste und Objekte angezeigt werden, können Sie schnell und einfach datengebundene Steuerelemente erstellen.  Zum Erstellen datengebundener Steuerelemente können Sie Elemente aus diesem Fenster auf Formulare im Projekt ziehen.  Darüber hinaus können Sie auch bestehende Steuerelemente an Daten binden, indem Sie Objekte aus dem Datenquellenfenster auf bestehende Steuerelemente ziehen.  
  
### Einstellungen  
 Ein weiterer Typ von Datenbindungen, die in Windows Forms verwaltet werden können, sind Einstellungen.  Bei den meisten Anwendungen für intelligente Clients müssen Informationen zum Laufzeitzustand gespeichert werden, beispielsweise die aktuelle Größe von Formularen, sowie Benutzereinstellungen, beispielsweise Standardverzeichnisse für zu speichernde Dateien.  Mit dem Feature für Anwendungseinstellungen können problemlos beide Arten von Einstellungen auf Clientcomputern gespeichert werden.  Nach dem Definieren von Einstellungen mit [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] oder einem Code\-Editor werden diese als XML gespeichert und zur Laufzeit automatisch wieder eingelesen.  
  
 In den folgenden Hilfethemen finden Sie Schritt\-für\-Schritt\-Anweisungen für die Verwendung dieser Features.  
  
|To|Siehe|  
|--------|-----------|  
|Verwenden der <xref:System.Windows.Forms.BindingSource>\-Komponente|[Gewusst wie: Binden von Windows Forms\-Steuerelementen an die BindingSource\-Komponente mithilfe des Designers](../Topic/How%20to:%20Bind%20Windows%20Forms%20Controls%20with%20the%20BindingSource%20Component%20Using%20the%20Designer.md)|  
|Arbeiten mit [!INCLUDE[vstecado](~/includes/vstecado-md.md)]\-Datenquellen|[Gewusst wie: Sortieren und Filtern von ADO.NET\-Daten mit der BindingSource\-Komponente in Windows Forms](../Topic/How%20to:%20Sort%20and%20Filter%20ADO.NET%20Data%20with%20the%20Windows%20Forms%20BindingSource%20Component.md)|  
|Verwenden des Datenquellenfensters|[Exemplarische Vorgehensweise: Anzeigen von Daten in einem Windows Form](../Topic/Walkthrough:%20Displaying%20Data%20on%20a%20Windows%20Form.md)|  
|Verwenden von Anwendungseinstellungen|[How to: Create Application Settings Using the Designer](http://msdn.microsoft.com/de-de/53b3af80-1c02-4e35-99c6-787663148945)|  
  
## Bereitstellen von Anwendungen auf Clientcomputern  
 Nach dem Erstellen einer Anwendung muss diese an Benutzer gesendet werden, damit sie anschließend auf den Clientcomputern installiert und ausgeführt werden kann.  Mithilfe der [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]\-Technologie können Anwendungen in [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] durch ein paar einfache Klicks bereitgestellt werden, und den Benutzern wird eine URL angegeben, die im Internet auf die Anwendung verweist.  [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] verwaltet alle Elemente und Abhängigkeiten in der Anwendung und stellt sicher, dass die Anwendung auf dem Clientcomputer ordnungsgemäß installiert ist.  
  
 [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]\-Anwendungen können so konfiguriert werden, dass sie nur ausgeführt werden, wenn der Benutzer mit dem Netzwerk verbunden ist, oder dass sie sowohl online als auch offline ausgeführt werden.  Wenn Sie eine Anwendung für den Offlinebetrieb konfigurieren, fügt [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] auf dem Computer des Benutzers im Menü **Start** einen Link zu der Anwendung hinzu, sodass diese auch ohne die URL geöffnet werden kann.  
  
 Wenn Sie die Anwendung aktualisieren, veröffentlichen Sie auf dem Webserver ein neues Bereitstellungsmanifest und eine neue Kopie der Anwendung.  [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] erkennt, dass ein Update verfügbar ist und aktualisiert die Installation des Benutzers; zum Aktualisieren von alten Assemblys ist keine benutzerdefinierte Programmierung erforderlich.  
  
 Eine umfassende Einführung in [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] finden Sie unter [ClickOnce Security and Deployment](/visual-studio/deployment/clickonce-security-and-deployment).  In den folgenden Hilfethemen finden Sie Schritt\-für\-Schritt\-Anweisungen für die Verwendung dieser Features:  
  
|To|Siehe|  
|--------|-----------|  
|Bereitstellen einer Anwendung mit [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]|[How to: Publish a ClickOnce Application using the Publish Wizard](../Topic/How%20to:%20Publish%20a%20ClickOnce%20Application%20using%20the%20Publish%20Wizard.md)<br /><br /> [Walkthrough: Manually Deploying a ClickOnce Application](../Topic/Walkthrough:%20Manually%20Deploying%20a%20ClickOnce%20Application.md)|  
|Aktualisieren einer [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]\-Bereitstellung|[How to: Manage Updates for a ClickOnce Application](../Topic/How%20to:%20Manage%20Updates%20for%20a%20ClickOnce%20Application.md)|  
|Verwalten der Sicherheit mithilfe von [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]|[How to: Enable ClickOnce Security Settings](../Topic/How%20to:%20Enable%20ClickOnce%20Security%20Settings.md)|  
  
## Andere Steuerelemente und Funktionen  
 In Windows Forms stehen viele weitere Features bereit, mit denen häufige Aufgaben schnell und einfach ausgeführt werden können, beispielsweise zum Erstellen von Dialogfeldern, Drucken, Hinzufügen von Hilfe und Dokumentation sowie zum Lokalisieren von Anwendungen in mehrere Sprachen.  Darüber hinaus wird in Windows Forms das robuste Sicherheitssystem von [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] verwendet, sodass Sie problemlos sichere Anwendungen bereitstellen können.  
  
 In den folgenden Hilfethemen finden Sie Schritt\-für\-Schritt\-Anweisungen für die Verwendung dieser Features:  
  
|To|Siehe|  
|--------|-----------|  
|Drucken des Inhalts eines Formulars|[Gewusst wie: Drucken von Grafiken in Windows Forms](../Topic/How%20to:%20Print%20Graphics%20in%20Windows%20Forms.md)<br /><br /> [Gewusst wie: Drucken einer mehrseitigen Textdatei in Windows Forms](../Topic/How%20to:%20Print%20a%20Multi-Page%20Text%20File%20in%20Windows%20Forms.md)|  
|Globalisieren einer Windows Forms\-Anwendung|[Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/de-de/9a96220d-a19b-4de0-9f48-01e5d82679e5)|  
|Weitere Informationen zu Windows Forms\-Sicherheit|[Übersicht über die Sicherheit in Windows Forms](../Topic/Security%20in%20Windows%20Forms%20Overview.md)|  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 [Übersicht über Windows Forms](../Topic/Windows%20Forms%20Overview.md)   
 [My.Forms Object](../../../visual-basic/language-reference/objects/my-forms-object.md)