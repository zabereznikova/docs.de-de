---
title: Hinzufügen von druckbaren Berichten zu Visual Studio-Anwendungen
ms.date: 07/20/2015
helpviewer_keywords:
- printing [Visual Studio], reports
- reports [Visual Basic], printing in Visual Studio
ms.assetid: 93928405-ef41-495e-bce2-9d43d5a7080a
ms.openlocfilehash: 4a7275a665e0c3290c2b3cd55c1af0c7cf0504f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="adding-printable-reports-to-visual-studio-applications"></a>Hinzufügen von druckbaren Berichten zu Visual Studio-Anwendungen
Visual Studio unterstützt eine Vielzahl von Lösungen zur einfacheren Datenberichten Visual Basic-Anwendungen hinzufügen. Sie können erstellen und Hinzufügen von Berichten mithilfe von ReportViewer-Steuerelemente, Crystal Reports oder SQL Server Reporting Services.  
  
> [!NOTE]
>  SQL Server Reporting Services ist Teil von SQL Server 2005 anstelle von Visual Studio. Der Reporting Services nicht auf Ihrem System installiert, es sei denn, Sie SQL Server 2005 installiert haben.  
  
## <a name="overview-of-microsoft-reporting-technology-in-visual-basic-applications"></a>Übersicht über die Microsoft-Berichtstechnologie in Visual Basic-Anwendungen  
 Wählen Sie die folgenden Vorgehensweisen aus eine Microsoft-berichtstechnologie in Ihrer Anwendung verwenden:  
  
-   Fügen Sie eine oder mehrere Instanzen eines ReportViewer-Steuerelements zu einem Visual Basic-Windows-Anwendung hinzu.  
  
-   Integrieren von SQL Server Reporting Services programmgesteuert durch Aufrufe an die Berichtsserver-Webdienst.  
  
-   Verwenden der ReportViewer-Steuerelement und Microsoft SQL Server 2005 Reporting Services zusammen, verwenden das Steuerelement als einen Berichts-Viewer und einem Berichtsserver als eine Berichtsprozessor. (Beachten Sie, dass Sie die SQL Server 2005-Version von Reporting Services verwenden müssen, wenn Sie einen Berichtsserver und das ReportViewer-Steuerelement zusammen verwenden möchten).  
  
## <a name="using-reportviewer-controls"></a>Verwenden von ReportViewer-Steuerelementen  
 Die einfachste Möglichkeit zum Einbetten von Berichtsfunktionen in eine Visual Basic-Windows-Anwendung ist ein Formular in Ihrer Anwendung das ReportViewer-Steuerelement hinzu. Das Steuerelement fügt Funktionen direkt in Ihre Anwendung für die berichtsverarbeitung und bietet einen integrierten Berichts-Designer, damit Sie Berichte mit Daten aus jeder ADO.NET Datenobjekt erstellen können. Eine voll ausgestattete API ermöglicht den programmgesteuerten Zugriff auf das Steuerelement und Berichte, sodass Sie Laufzeitfunktionen konfigurieren können.  
  
 ReportViewer bietet integrierte berichtsverarbeitung und die Funktion in einem einzelnen, kostenlos erhältliche Datensteuerelement anzeigen. Wählen Sie das ReportViewer-Steuerelemente, wenn Sie die folgenden Berichtsfunktionen benötigen:  
  
-   Die berichtsverarbeitung in der Clientanwendung. Ein verarbeiteter Bericht wird in einen vom Steuerelement bereitgestellte Ansichtsbereich angezeigt.  
  
-   Datenbindung an ADO.NET Datentabellen. Sie können Berichte erstellen, die nutzen <xref:System.Data.DataTable> Instanzen, die an das Steuerelement bereitgestellt. Sie können auch direkt an Geschäftsobjekte binden.  
  
-   Weiterverteilbare Steuerelemente, die Sie in der Anwendung einschließen können.  
  
-   Common Language Runtime-Funktionen wie Seitennavigation, drucken, suchen und Exportformate. Eine ReportViewer-Symbolleiste bietet Unterstützung für diese Vorgänge.  
  
 Um das ReportViewer-Steuerelement verwenden, können Sie ziehen es aus der **Daten** Teil der Visual Studio-Toolbox auf ein Formular in der Visual Basic-Windows-Anwendung.  
  
### <a name="creating-reports-in-visual-studio-for-reportviewer-controls"></a>Erstellen von Berichten in Visual Studio für ReportViewer-Steuerelemente  
 Um einen Bericht erstellen, die im ReportViewer ausgeführt wird, fügen einen **Bericht** aus, um das Projekt. Visual Studio erstellt eine Client-Berichtsdefinitionsdatei (RDLC), fügt die Datei dem Projekt hinzu und öffnet einen integrierten Berichts-Designer in Visual Studio-Arbeitsbereich.  
  
 Der Visual Studio-Berichts-Designer integriert die **Datenquellen** Fenster. Beim Ziehen eines Felds aus der **Datenquellen** Fenster aus, um den Bericht, den Berichts-Designer Metadaten zu der Datenquelle in der Berichtsdefinitionsdatei kopiert. Diese Metadaten werden vom ReportViewer-Steuerelement zum automatischen Generieren von Code für die Datenbindung verwendet.  
  
 Der Visual Studio-Berichts-Designer schließt keine Vorschaufunktion Bericht ein. Vorschau des Berichts, führen Sie die Anwendung und den darin eingebetteten Bericht in der Vorschau anzeigen.  
  
|Grundlegende Berichtsfunktionen Ihrer Anwendung hinzu|  
|---|    
|1.  Ziehen Sie ein ReportViewer-Steuerelement aus der **Daten** auf der Registerkarte die **Toolbox** auf das Formular.<br />2.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**. In der **neues Element hinzufügen** wählen Sie im Dialogfeld die **Bericht** Symbol, und klicken Sie auf **hinzufügen**.<br />     Der Berichts-Designer wird geöffnet, in der Entwicklungsumgebung, und eine Berichtsdatei (RDLC) wird dem Projekt hinzugefügt.<br />3.  Ziehen Sie Berichtselemente aus der **Toolbox** auf das Berichtslayout und wie gewünscht anordnen.<br />4.  Ziehen Sie Felder aus der **Datenquellen** Fenster aus, um die Berichtselemente im Berichtslayout.|  
  
## <a name="using-reporting-services-in-visual-basic-applications"></a>Verwenden von Reporting Services in Visual Basic-Anwendungen  
 Reporting Services ist eine serverbasierte reporting-Technologie, die mit SQL Server enthalten ist. Reporting Services enthält weitere Funktionen, die in den ReportViewer-Steuerelementen nicht gefunden werden. Wählen Sie die Reporting Services, wenn Sie keines der folgenden Features erforderlich:  
  
-   Bereitstellung für horizontales Skalieren und serverseitige berichtsverarbeitung, die verbesserte Leistung für komplexe oder lang andauernden Berichte und für hohes Volumen berichtsaktivität bereitstellt.  
  
-   Integrierte Daten- und berichtsverarbeitung, mit Unterstützung für benutzerdefinierte Berichtssteuerelemente und Rich Ausgabeformate rendern.  
  
-   Geplante berichtsverarbeitung, damit Sie beim Ausführen von Berichten exakt angeben können.  
  
-   Abonnenten-basierter berichtsverteilung per e-Mail oder Speicherorte für Dateifreigaben.  
  
-   Ad-hoc-Berichte, damit geschäftlichen Bereich Berichte erstellen können, je nach Bedarf.  
  
-   Datengesteuerte Abonnements, die angepasste Berichtsausgabe an eine dynamische Liste von Empfängern weiterleiten.  
  
-   Benutzerdefinierte Erweiterungen für Datenverarbeitung, Berichtsübermittlung, benutzerdefinierte Authentifizierung und Berichtsrendering.  
  
 Der Berichtsserver wird als Webdienst implementiert. Der Anwendungscode muss Aufrufe an den Webdienst den Zugriff auf Berichte und andere Metadaten enthalten. Der Web-Dienst bietet vollständige programmgesteuerten Zugriff auf eine Berichtsserverinstanz.  
  
 Reporting Services eine webbasierte reporting Technologie handelt, wird die Standard-Viewer Berichte, die gerendert werden im HTML-Format. Wenn Sie nicht HTML als das Standardpräsentationsformat für den Bericht verwenden möchten, müssen Sie einen benutzerdefinierten Berichts-Viewer für Ihre Anwendung zu schreiben.  
  
### <a name="creating-reports-in-visual-studio-for-reporting-services"></a>Erstellen von Berichten in Visual Studio für Reporting Services  
 Zum Erstellen von Berichten, die auf einem Berichtsserver ausgeführt werden, erstellen Sie Berichtsdefinitionen (RDL)-Dateien in Visual Studio über Business Intelligence Development Studio, die in SQL Server 2005 enthalten ist.  
  
> [!NOTE]
>  Sie müssen SQL Server 2005 installiert, damit SQL Server Reporting Services und Business Intelligence Development Studio verwendet haben.  
  
 Business Intelligence Development Studio fügt Projektvorlagen, die spezifisch für SQL Server-Komponenten sind. Zum Erstellen von Berichten können Sie aus der **Berichtsserverprojekt** oder **Berichtsserverprojekt-Assistent** Vorlagen. Sie können datenquellenverbindungen und Abfragen zu einer Vielzahl von Datentypen, einschließlich SQL Server, Oracle, Analysis Services, XML und SQL Server Integration Services angeben. Ein **Daten** Registerkarte **Layout** Registerkarte und **Vorschau** Registerkarte ermöglichen es Ihnen, Daten definieren, ein Berichtslayout erstellen und den Bericht in den gleichen Arbeitsbereich in der Vorschau anzeigen.  
  
 Berichtsdefinitionen, die Sie für das Steuerelement oder dem Berichtsserver erstellen, können in beiden Technologie wiederverwendet werden.  
  
|Zum Erstellen eines Berichts, das auf einem Berichtsserver ausgeführt wird.|  
|---|    
|1.  Auf der **Datei** Menü wählen **neu**.<br />     Das Dialogfeld **Neues Projekt** wird angezeigt.<br />2.  In der **-Projekttypen** Bereich, klicken Sie auf **Business Intelligence-Projekte**.<br />3.  Wählen Sie im Vorlagenbereich **Berichtsserverprojekt** oder **Berichtsserverprojekt-Assistent**.|  
  
## <a name="using-reportviewer-controls-and-sql-server-reporting-services-together"></a>Verwenden von ReportViewer-Steuerelemente und SQLServer Reporting Services  
 Die ReportViewer-Steuerelemente und SQL Server 2005 Reporting Services können zusammen in derselben Anwendung verwendet werden.  
  
-   Das ReportViewer-Steuerelement stellt einen Viewer, der zum Anzeigen von Berichten in der Anwendung verwendet wird.  
  
-   Reporting Services stellt die Berichte bereit und führt die gesamte Verarbeitung auf einem Remoteserver.  
  
 Das ReportViewer-Steuerelement kann für das Anzeigen von Berichten, die gespeichert und verarbeitet werden auf einem Remoteserver Reporting Services-Berichtsserver konfiguriert werden. Diese Art von Konfiguration heißt *Remoteverarbeitungsmodus*. Im Remoteverarbeitungsmodus fordert das Steuerelement einen Bericht, der auf einem Remoteberichtsserver gespeichert ist. Der Berichtsserver führt alle berichtsverarbeitung, die Datenverarbeitung und Rendern von Berichten. Ein nicht mehr benötigen, gerenderter Bericht wird an das Steuerelement zurückgegeben und im Ansichtsbereich angezeigt.  
  
 Berichte, die auf einen Report Server unterstützen zusätzliche ausgeführt Exportformate, verfügen über einen anderen Bericht Parametrisierung-Implementierung, verwenden Sie die Datenquellentypen, die vom Berichtsserver unterstützt werden und erfolgt über das rollenbasierte Autorisierungsmodell auf die Berichtsserver.  
  
 Um den Remoteverarbeitungsmodus verwenden zu können, geben Sie die URL und den Pfad zu einem Serverbericht, beim Konfigurieren des ReportViewer-Steuerelements.
