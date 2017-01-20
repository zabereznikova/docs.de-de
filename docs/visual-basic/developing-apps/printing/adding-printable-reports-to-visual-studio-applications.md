---
title: "Adding Printable Reports to Visual Studio Applications | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "printing [Visual Studio], reports"
  - "reports, printing in Visual Studio"
ms.assetid: 93928405-ef41-495e-bce2-9d43d5a7080a
caps.latest.revision: 27
caps.handback.revision: 27
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Adding Printable Reports to Visual Studio Applications
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Visual Studio unterstützt eine Reihe von Berichtslösungen, mit denen Sie Ihre Visual Basic\-Anwendungen um umfangreiche Datenberichtsfunktionen ergänzen können.  Sie können Berichte mithilfe von ReportViewer\-Steuerelementen, Crystal Reports oder SQL Server Reporting Services erstellen und hinzufügen.  
  
> [!NOTE]
>  SQL Server Reporting Services ist dabei Bestandteil von SQL Server 2005, nicht von Visual Studio.  Reporting Services sind nur bei Installation von SQL Server 2005 auf dem System installiert.  
  
## Übersicht über Microsoft\-Berichterstellungstechnologie in Visual Basic\-Anwendungen  
 Sie können Microsoft\-Berichterstellungstechnologie auf eine der folgenden Arten in Ihrer Anwendung verwenden:  
  
-   Fügen Sie einer Visual Basic\-Windows\-Anwendung eine oder mehrere Instanzen eines ReportViewer\-Steuerelements hinzu.  
  
-   Integrieren Sie SQL Server Reporting Services programmgesteuert, indem Sie den Berichtsserver\-Webdienst aufrufen.  
  
-   Verwenden Sie das ReportViewer\-Steuerelement und Microsoft SQL Server 2005 Reporting Services zusammen, indem Sie das Steuerelement für die Berichtsanzeige und einen Berichtsserver für die Berichtsverarbeitung verwenden.  \(Wenn Sie einen Berichtsserver und das ReportViewer\-Steuerelement zusammen verwenden möchten, müssen Sie die SQL Server 2005\-Version von Reporting Services verwenden.\)  
  
## Verwenden von ReportViewer\-Steuerelementen  
 Berichtsfunktionen lassen sich am einfachsten in eine Visual Basic Windows\-Anwendung einbetten, indem Sie das ReportViewer\-Steuerelement in ein Formular in Ihrer Anwendung einfügen.  Das Steuerelement erweitert Ihre Anwendung direkt um Berichtsfunktionen und stellt einen integrierten Berichts\-Designer bereit, sodass Sie Berichte mit Daten aus allen ADO.NET\-Datenobjekten erstellen können.  Die umfassende API ermöglicht programmgesteuerten Zugriff auf das Steuerelement und die Berichte, sodass Sie Laufzeitfunktionen konfigurieren können.  
  
 ReportViewer stellt in einem einzelnen, frei verteilbaren Datensteuerelement integrierte Verarbeitungs\- und Anzeigefunktionen für Berichte bereit.  ReportViewer\-Steuerelemente empfehlen sich, wenn Sie die folgenden Berichtsfunktionen benötigen:  
  
-   Berichtsverarbeitung in der Clientanwendung.  Ein verarbeiteter Bericht wird in einem vom Steuerelement bereitgestellten Ansichtsbereich angezeigt.  
  
-   Datenbindung an ADO.NET\-Datentabellen.  Sie können Berichte erstellen, die dem Steuerelement bereitgestellte <xref:System.Data.DataTable>\-Instanzen verwenden.  Es ist auch eine direkte Bindung an Geschäftsobjekte möglich.  
  
-   Verteilbare Steuerelemente, die Sie in Ihre Anwendung einschließen können.  
  
-   Laufzeitfunktionen wie Seitennavigation, Drucken, Durchsuchen und Exportformate.  Diese Vorgänge werden durch eine ReportViewer\-Symbolleiste unterstützt.  
  
 Sie verwenden das ReportViewer\-Steuerelement, indem Sie es aus dem Abschnitt **Daten** in der Visual Studio\-Toolbox auf ein Formular der Visual Basic Windows\-Anwendung ziehen.  
  
### Erstellen von Berichten in Visual Studio für ReportViewer\-Steuerelemente  
 Um einen Bericht zu erstellen, der in ReportViewer ausgeführt werden kann, fügen Sie dem Projekt eine **Berichtsvorlage** hinzu.  Visual Studio erstellt eine Definitionsdatei für einen Clientbericht \(.rdlc\), fügt diese Datei dem Projekt hinzu, und öffnet im Arbeitsbereich einen integrierten Berichts\-Designer.  
  
 Der Berichts\-Designer von Visual Studio ist mit dem **Datenquellenfenster** synchronisiert.  Wenn Sie ein Feld aus dem **Datenquellenfenster** auf einen Bericht ziehen, kopiert der Berichts\-Designer Metadaten zur Datenquelle in die Berichtsdefinitionsdatei.  Mithilfe dieser Metadaten wird vom ReportViewer\-Steuerelement automatisch Datenbindungscode generiert.  
  
 Der Visual Studio\-Report\-Designer bietet keine Berichtsvorschaufunktionen.  Wenn Sie eine Berichtsvorschau anzeigen möchten, führen Sie die Anwendung aus, und zeigen Sie den eingebetteten Bericht an.  
  
||  
|-|  
|So fügen Sie Ihrer Anwendung einfache Berichtsfunktionen hinzu|  
|1.  Ziehen Sie ein ReportViewer\-Steuerelement von der Registerkarte **Daten** der **Toolbox** auf das Formular.<br />2.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.  Wählen Sie im Dialogfeld **Neues Element hinzufügen** das Symbol **Bericht** aus, und klicken Sie dann auf **Hinzufügen**.<br />     In der Entwicklungsumgebung wird nun der Berichts\-Designer geöffnet, und dem Projekt wird eine Berichtsdatei \(.rdlc\) hinzugefügt.<br />3.  Ziehen Sie Berichtselemente aus der **Toolbox** auf das Berichtslayout, und ordnen Sie diese nach Ihren Wünschen an.<br />4.  Ziehen Sie Felder aus dem **Datenquellenfenster** auf die Berichtselemente im Berichtslayout.|  
  
## Verwenden von Reporting Services in Visual Basic\-Anwendungen  
 Reporting Services ist eine in SQL Server integrierte serverbasierte Berichterstellungstechnologie.  Reporting Services stellen Zusatzfeatures bereit, die in ReportViewer\-Steuerelementen nicht verfügbar sind.  Reporting Services empfehlen sich, wenn Sie die folgenden Features benötigen:  
  
-   Dezentralisierte Bereitstellung und serverseitige Berichtsverarbeitung, die bei komplexen oder über einen langen Zeitraum ausgeführten Berichten und umfangreicher Berichterstellung bessere Leistung bietet.  
  
-   Integrierte Daten\- und Berichtsverarbeitung mit Unterstützung benutzerdefinierter Berichtsteuerelemente und Berichtsausgabe in verschiedenen Formaten.  
  
-   Geplante Berichtsverarbeitung, sodass Berichte zu einem genauen Zeitpunkt ausgeführt werden können.  
  
-   Berichtsweiterleitung an Abonnenten per E\-Mail oder über freigegebene Dateispeicherorte.  
  
-   Ad\-hoc\-Berichterstellung, um Geschäftsbenutzern die bedarfsgerechte Berichterstellung zu ermöglichen.  
  
-   Datengesteuerte Abonnements, anhand derer benutzerdefinierte Berichtsausgaben an eine dynamischen Empfängerliste weitergeleitet wird.  
  
-   Benutzerdefinierte Erweiterungen für Datenverarbeitung, Berichtszustellung, benutzerdefinierte Authentifizierung und Berichtsdarstellung.  
  
 Der Berichtsserver wird als Webdienst implementiert.  Der Anwendungscode muss Aufrufe des Webdiensts enthalten, um auf Berichte und andere Metadaten zugreifen zu können.  Der Webdienst stellt einen vollständig programmgesteuerten Zugriff auf eine Berichtsserverinstanz bereit.  
  
 Da es sich bei Reporting Services um eine webbasierte Berichtstechnologie handelt, werden die Berichte im Standard\-Viewer im HTML\-Format ausgegeben.  Wenn die Berichte nicht standardmäßig im HTML\-Format dargestellt werden sollen, müssen Sie für Ihre Anwendung einen eigenen Berichts\-Viewer schreiben.  
  
### Erstellen von Berichten für Reporting Services in Visual Studio  
 Zum Erstellen von Berichten, die auf einem Berichtsserver ausgeführt werden, müssen Sie in Visual Studio über Business Intelligence Development Studio \(in SQL Server 2005 enthalten\) Berichtsdefinitionsdateien \(.rdl\) erstellen.  
  
> [!NOTE]
>  Für die Verwendung von SQL Server Reporting Services und Business Intelligence Development Studio muss SQL Server 2005 installiert sein.  
  
 Business Intelligence Development Studio fügt spezielle, für die SQL Server\-Komponenten bestimmte Projektvorlagen hinzu.  Zum Erstellen von Berichten können Sie aus den Vorlagen **Berichtsserverprojekt** oder **Berichtsserverprojekt\-Assistent** auswählen.  Sie können Datenquellenverbindungen und Abfragen für unterschiedliche Datenquellentypen angeben, z. B. SQL Server, Oracle, Analysis Services, XML und SQL Server Integration Services.  Auf den Registerkarten **Daten**, **Layout** und **Vorschau** im Arbeitsbereich können Sie Daten definieren, ein Berichtslayout erstellen und den Bericht in der Vorschau anzeigen.  
  
 Die für das Steuerelement oder den Berichtsserver erstellten Berichtsdefinitionen können in beiden Technologien wiederverwendet werden.  
  
||  
|-|  
|So erstellen Sie einen Bericht, der auf einem Berichtsserver ausgeführt wird|  
|1.  Wählen Sie im Menü **Datei** den Befehl **Neu** aus.<br />     Das Dialogfeld **Neues Projekt** wird angezeigt.<br />2.  Klicken Sie im Bereich **Projekttypen** auf **Business Intelligence\-Projekte**.<br />3.  Wählen Sie im Bereich Vorlagen **Berichtsserverprojekt** oder **Berichtsserverprojekt\-Assistent** aus.|  
  
## Verwenden von ReportViewer\-Steuerelementen mit SQL Server Reporting Services  
 ReportViewer\-Steuerelemente und SQL Server 2005 Reporting Services können zusammen in der gleichen Anwendung verwendet werden.  
  
-   Das ReportViewer\-Steuerelement stellt einen Viewer bereit, in dem die Berichte in der Anwendung angezeigt werden.  
  
-   Reporting Services stellt die Berichte bereit und führt die gesamte Verarbeitung auf einem Remoteserver aus.  
  
 Das ReportViewer\-Steuerelement kann so konfiguriert werden, dass die auf einem Reporting Services\-Remoteberichtsserver gespeicherten und verarbeiteten Berichte angezeigt werden.  Diese Konfiguration wird als *Remoteverarbeitungsmodus* bezeichnet.  Im Remoteverarbeitungsmodus fordert das Steuerelement einen auf einem Remoteberichtsserver gespeicherten Bericht an.  Der Berichtsserver führt die gesamte Berichtsverarbeitung, Datenverarbeitung und das Berichtsrendering aus.  Anschließend wird ein vollständiger, gerenderter Bericht an das Steuerelement zurückgegeben und im Ansichtsbereich angezeigt.  
  
 Auf dem Berichtsserver ausgeführte Berichte unterstützen zusätzliche Exportformate, weisen eine andere Implementierung der Berichtsparametrisierung auf und verwenden die vom Berichtsserver unterstützten Datenquellentypen. Der Zugriff erfolgt über die auf dem Berichtsserver eingerichtete rollenbasierte Autorisierung.  
  
 Wenn Sie den Remoteverarbeitungsmodus verwenden möchten, müssen Sie beim Konfigurieren des ReportViewer\-Steuerelements die URL und den Pfad zu einem Serverbericht angeben.