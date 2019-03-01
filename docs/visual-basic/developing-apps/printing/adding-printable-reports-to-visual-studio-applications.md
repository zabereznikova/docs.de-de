---
title: Hinzufügen von druckbaren Berichten zu Visual Studio-Anwendungen
ms.date: 07/20/2015
helpviewer_keywords:
- printing [Visual Studio], reports
- reports [Visual Basic], printing in Visual Studio
ms.assetid: 93928405-ef41-495e-bce2-9d43d5a7080a
ms.openlocfilehash: 65264deea3aeff1a633ea6888b3f175031b7fba5
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "57212013"
---
# <a name="adding-printable-reports-to-visual-studio-applications"></a>Hinzufügen von druckbaren Berichten zu Visual Studio-Anwendungen
Visual Studio unterstützt eine Vielzahl von Lösungen können Sie die Aufnahme umfangreicher Datenberichte in die Visual Basic-Anwendungen hinzufügen. Sie können erstellen und Hinzufügen von Berichten mithilfe von ReportViewer-Steuerelementen, Crystal Reports oder SQL Server Reporting Services.  

  
## <a name="overview-of-microsoft-reporting-technology-in-visual-basic-applications"></a>Übersicht über die Microsoft-Berichtstechnologie in Visual Basic-Anwendungen  
 Der folgenden Vorgehensweisen aus eine Microsoft-berichtstechnologie in Ihrer Anwendung verwenden möchten:  
  
-   Fügen Sie eine oder mehrere Instanzen eines ReportViewer-Steuerelements zu einer Visual Basic-Windows-Anwendung hinzu.  
  
-   Integrieren Sie SQL Server Reporting Services programmgesteuert, indem Sie Aufrufe an die Berichtsserver-Webdienst.  
  
-   Verwenden Sie das ReportViewer-Steuerelement und die Microsoft SQL Server 2005 Reporting Services zusammen, verwenden das Steuerelement als einen Berichts-Viewer und einem Berichtsserver als eine Berichtsprozessor. (Beachten Sie, dass Sie die SQL Server 2005-Version von Reporting Services verwenden müssen, wenn Sie einen Berichtsserver und das ReportViewer-Steuerelement zusammen verwenden möchten).  
  
## <a name="using-reportviewer-controls"></a>Verwenden von ReportViewer-Steuerelementen  
 Die einfachste Möglichkeit zum Einbetten von Berichtsfunktionen in eine Visual Basic-Windows-Anwendung wird ein Formular in Ihrer Anwendung das ReportViewer-Steuerelement hinzugefügt. Das Steuerelement bietet Funktionen direkt in Ihre Anwendung für die berichtsverarbeitung sowie einen integrierten Berichts-Designer, damit Sie Berichte mit Daten aus jedem Datenobjekt ADO.NET erstellen können. Eine voll funktionsfähige API bietet programmgesteuerten Zugriff auf das Steuerelement und Berichte, sodass Sie die Laufzeitfunktionalität konfigurieren können.  
  
 ReportViewer stellt integrierte berichtsverarbeitung und Anzeigen von Funktionen in einem einzigen, kostenlos erhältliche Datensteuerelement. Wählen Sie das ReportViewer-Steuerelemente, wenn Sie die folgenden Berichtsfunktionen benötigen:  
  
-   In der Clientanwendung zur Verarbeitung von Berichten. Ein verarbeiteter Bericht wird in einen Ansichtsbereich, die vom Steuerelement bereitgestellte angezeigt.  
  
-   Datenbindung an ADO.NET Datentabellen. Sie können Berichte erstellen, die nutzen <xref:System.Data.DataTable> Instanzen, die auf das Steuerelement angegeben. Sie können auch direkt an Geschäftsobjekte binden.  
  
-   Weitervertreibbare Steuerelemente, die Sie in der Anwendung einschließen können.  
  
-   Laufzeitfunktionen, etwa Seitennavigation "," Drucken "," Suchen "und" Export formatiert. Eine ReportViewer-Symbolleiste bietet Unterstützung für diese Vorgänge.  
  
 Um das ReportViewer-Steuerelement zu verwenden, können Sie ziehen es von der **Daten** Abschnitt der Visual Studio-Toolbox auf ein Formular in der Visual Basic-Windows-Anwendung.  
  
### <a name="creating-reports-in-visual-studio-for-reportviewer-controls"></a>Erstellen von Berichten in Visual Studio für ReportViewer-Steuerelemente  
 Um einen Bericht erstellen, die im ReportViewer ausgeführt wird, Hinzufügen einer **Bericht** Vorlage dem Projekt. Visual Studio erstellt eine Client-Berichtsdefinitionsdatei (RDLC), fügt die Datei zu Ihrem Projekt hinzu und öffnet einen integrierten Berichts-Designer in Visual Studio-Arbeitsbereich.  
  
 Die Visual Studio-Berichts-Designer integriert die **Datenquellen** Fenster. Beim Ziehen eines Felds aus der **Datenquellen** auf einen Bericht, den Berichts-Designer Metadaten zu der Datenquelle kopiert, in der Berichtsdefinitionsdatei. Diese Metadaten werden vom ReportViewer-Steuerelement verwendet, um Code für die Datenbindung automatisch zu generieren.  
  
 Die Visual Studio-Berichts-Designer umfasst keine Preview-Funktionen des Berichts. Vorschau des Berichts, führen Sie die Anwendung und eine Vorschau des Berichts, die in den es eingebettet werden.  
  
|Grundlegende Funktionalität für Ihre Anwendung hinzufügen|  
|---|    
|1.  Ziehen Sie ein ReportViewer-Steuerelement aus der **Daten** Registerkarte die **Toolbox** auf das Formular.<br />2.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**. In der **neues Element hinzufügen** wählen Sie im Dialogfeld die **Bericht** Symbol, und klicken Sie auf **hinzufügen**.<br />     Der Berichts-Designer wird geöffnet, in der Entwicklungsumgebung und dem Projekt eine Berichtsdatei (RDLC) hinzugefügt wird.<br />3.  Ziehen Sie Berichtselemente aus der **Toolbox** auf das Berichtslayout und ordnen Sie sie, wie Sie möchten.<br />4.  Ziehen Sie Felder aus der **Datenquellen** Fenster aus, um die Berichtselemente im Berichtslayout.|  
  
## <a name="using-reporting-services-in-visual-basic-applications"></a>Verwendung von Reporting Services in Visual Basic-Anwendungen  
 Reporting Services ist eine serverbasierte berichterstellung-Technologie, die in SQL Server enthalten ist. Reporting Services umfasst zusätzliche Features, die nicht in der ReportViewer-Steuerelemente enthalten sind. Wählen Sie die Reporting Services, wenn Sie eine der folgenden Funktionen benötigen:  
  
-   Bereitstellung für horizontales Skalieren und serverseitige berichtsverarbeitung, die verbesserte Leistung für komplexe oder lang ausgeführte Berichte und hohem Volumen berichtsaktivität bereitstellt.  
  
-   Integrierte Daten- und berichtsverarbeitung, mit Unterstützung für benutzerdefinierte Berichtssteuerelemente und umfassende Ausgabeformate rendern.  
  
-   Geplante berichtsverarbeitung, sodass Sie angeben können, genau, wenn Berichte ausgeführt werden.  
  
-   Abonnenten-basierte Verteilung von Berichten per e-Mail oder Speicherorte für Dateifreigaben.  
  
-   Ad-hoc-berichterstellung, damit geschäftliche Benutzer Berichte erstellen können, je nach Bedarf ein.  
  
-   Datengesteuerte Abonnements, die angepasste Berichtsausgabe an eine dynamische Liste von Empfängern weiterleiten.  
  
-   Benutzerdefinierte Erweiterungen für Datenverarbeitung, Berichtsübermittlung, benutzerdefinierte Authentifizierung und Berichtsrendering.  
  
 Der Berichtsserver wird als Webdienst implementiert. Ihr Anwendungscode muss es sich um die Aufrufe an den Webdienst den Zugriff auf Berichte und andere Metadaten enthalten. Der Webdienst bietet vollständige programmgesteuerten Zugriff auf eine Berichtsserver-Instanz.  
  
 Da Reporting Services über eine webbasierte berichterstellung Technologie ist, zeigt die Standardanzeige Berichte, die gerendert wird, werden im HTML-Format. Wenn Sie nicht HTML als das Standardpräsentationsformat für den Bericht verwenden möchten, müssen Sie einen benutzerdefinierten Berichts-Viewer für Ihre Anwendung zu schreiben.  
  
### <a name="creating-reports-in-visual-studio-for-reporting-services"></a>Erstellen von Berichten in Visual Studio für Reporting Services  
 Um Berichte zu erstellen, die auf einem Berichtsserver ausgeführt werden, erstellen Sie Berichtsdefinitionen (RDL) Dateien in Visual Studio über die Business Intelligence Development Studio, die in SQL Server 2005 enthalten ist.  
  
 Business Intelligence Development Studio fügt Projektvorlagen, die für SQL Server-Komponenten spezifisch sind. Zum Erstellen von Berichten können Sie aus der **Berichtsserverprojekt** oder **Berichtsserverprojekt-Assistent** Vorlagen. Sie können datenquellenverbindungen und Abfragen mit einer Vielzahl von Datentypen, einschließlich SQL Server, Oracle, Analysis Services, XML und SQL Server Integration Services angeben. Ein **Daten** Registerkarte **Layout** Registerkarte und **Vorschau** können Sie Daten definieren, die ein Berichtslayout erstellen und die Vorschau des Berichts alle im selben Arbeitsbereich anzuzeigen.  
  
 Berichtsdefinitionen, die Sie für das Steuerelement oder dem Berichtsserver erstellen, können in beiden Technologie wiederverwendet werden.  
  
|Um einen Bericht erstellen, der auf einem Berichtsserver ausgeführt wird.|  
|---|    
|1.  Auf der **Datei** Menü wählen **neu**.<br />     Das Dialogfeld **Neues Projekt** wird angezeigt.<br />2.  In der **Projekttypen** Bereich, klicken Sie auf **Business Intelligence-Projekte**.<br />3.  Wählen Sie im Vorlagenbereich **Berichtsserverprojekt** oder **Berichtsserverprojekt-Assistent**.|  
  
## <a name="using-reportviewer-controls-and-sql-server-reporting-services-together"></a>Verwenden von ReportViewer-Steuerelemente und SQLServer Reporting Services  
 Die ReportViewer-Steuerelemente und SQL Server 2005 Reporting Services können zusammen in derselben Anwendung verwendet werden.  
  
-   Das ReportViewer-Steuerelement bietet einen Viewer, der zum Anzeigen von Berichten in Ihrer Anwendung verwendet wird.  
  
-   Reporting Services stellt die Berichte bereit und führt die gesamte Verarbeitung auf einem Remoteserver.  
  
 Das ReportViewer-Steuerelement kann für das Anzeigen von Berichten, die gespeichert und verarbeitet werden auf einem Remoteserver Reporting Services-Berichtsserver konfiguriert werden. Diese Art der Konfiguration wird aufgerufen, *Remoteverarbeitungsmodus*. Im Remoteverarbeitungsmodus fordert das Steuerelement einen Bericht, der auf einem Remoteberichtsserver gespeichert ist. Der Berichtsserver führt alle berichtsverarbeitung, Data-Verarbeitung und Rendern von Berichten. Ein vollständiger, gerenderter Bericht wird an das Steuerelement zurückgegeben und im Ansichtsbereich angezeigt.  
  
 Berichte, die auf einen Report Server unterstützen zusätzliche ausgeführt Exportformate, verfügen über einen anderen Bericht Parametrisierung-Implementierung, verwenden Sie die Datenquellentypen, die vom Berichtsserver unterstützt werden und erfolgt über das rollenbasierte Autorisierungsmodell auf der Berichtsserver.  
  
 Um den Remoteverarbeitungsmodus verwenden zu können, geben Sie die URL und den Pfad zu einem Serverbericht beim Konfigurieren des ReportViewer-Steuerelements.
