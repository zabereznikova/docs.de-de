---
title: Anwendungsentwicklung
ms.date: 01/26/2018
helpviewer_keywords:
- WPF [WPF], about application development
- application development [WPF], about
ms.assetid: 2996ce5e-81e9-49ae-881b-952db3dd1b7e
ms.openlocfilehash: 5ff9f58b72982f79e70b80f60c10828c3b54e5bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186001"
---
# <a name="application-development"></a>Anwendungsentwicklung
<a name="introduction"></a>Windows Presentation Foundation (WPF) ist ein Präsentationsframework, das zum Entwickeln der folgenden Anwendungstypen verwendet werden kann:  
  
- Eigenständige Anwendungen (herkömmliche Windows-Anwendungen, die als ausführbare Assemblys erstellt wurden und auf dem Clientcomputer installiert und ausgeführt werden).  
  
- XAML-Browseranwendungen (XBAPs) (Anwendungen, die aus Navigationsseiten bestehen, die als ausführbare Assemblys erstellt und von Webbrowsern wie Microsoft Internet Explorer oder Mozilla Firefox gehostet werden).  
  
- Benutzerdefinierte Steuerelementbibliotheken: Nicht ausführbare Assemblys mit wiederverwendbaren Steuerelementen.  
  
- Klassenbibliotheken: Nicht ausführbare Assemblys mit wiederverwendbaren Klassen.  
  
> [!NOTE]
> Es wird dringend davon abgeraten, WPF-Typen in einem Windows-Dienst zu verwenden. Diese Funktionen funktionieren in einem Windows-Dienst möglicherweise nicht wie erwartet.  
  
 Zum Erstellen dieses Anwendungssatzes implementiert WPF eine Vielzahl von Diensten. Dieses Thema bietet eine Übersicht über diese Dienste sowie Verweise auf weitere Informationen.  

<a name="Application_Management"></a>
## <a name="application-management"></a>Anwendungsverwaltung  
 Ausführbare WPF-Anwendungen erfordern in der Regel einen Kernsatz von Funktionen, der Folgendes umfasst:  
  
- Erstellen und Verwalten einer allgemeinen Anwendungsinfrastruktur (einschließlich der Erstellung einer Einstiegspunktmethode und einer Windows-Meldungsschleife zum Empfangen von System- und Eingabenachrichten)  
  
- Verfolgen und Beeinflussen der Lebensdauer einer Anwendung  
  
- Befehlszeilenparameter abrufen und verarbeiten  
  
- Freigeben von Eigenschaften für den Anwendungsbereich und [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Ressourcen  
  
- Erkennen und Verarbeiten von Ausnahmefehlern (unbehandelten Ausnahmen)  
  
- Zurückgeben von Exitcodes  
  
- Fenster in eigenständigen Anwendungen verwalten  
  
- Tracking-Navigation in XAML-Browseranwendungen (XBAPs) und eigenständige Anwendungen mit Navigationsfenstern und -rahmen.  
  
 Diese Funktionen werden von der <xref:System.Windows.Application>-Klasse implementiert, die Sie Ihren Anwendungen mit einer *Anwendungsdefinition* hinzufügen.  
  
 Weitere Informationen finden Sie unter [Übersicht über die Anwendungsverwaltung](application-management-overview.md).  
  
<a name="WPF_Application_Resource__Content__and_Data_Files"></a>
## <a name="wpf-application-resource-content-and-data-files"></a>WPF-Anwendungsressource, Inhalts- und Datendateien  
 WPF erweitert die Kernunterstützung in Microsoft .NET Framework für eingebettete Ressourcen mit Unterstützung für drei Arten von nicht ausführbaren Datendateien: Ressource, Inhalt und Daten. Weitere Informationen finden Sie unter [WPF-Anwendungsressource, Inhalts- und Datendateien](wpf-application-resource-content-and-data-files.md).  
  
 Eine wichtige Komponente der Unterstützung für Nicht ausführbare WPF-Datendateien ist die Möglichkeit, sie mithilfe eines eindeutigen URI zu identifizieren und zu laden. Weitere Informationen finden Sie unter Packen von [URIs in WPF](pack-uris-in-wpf.md).  
  
<a name="Windows_and_Dialog_Boxes"></a>
## <a name="windows-and-dialog-boxes"></a>Fenster und Dialogfelder  
 Benutzer interagieren über Windows mit eigenständigen WPF-Anwendungen. Fenster dienen dazu, Anwendungsinhalte zu hosten und Anwendungsfunktionen, über die Benutzer mit diesen Inhalten interagieren können, verfügbar zu machen. In WPF werden Fenster von der <xref:System.Windows.Window> Klasse gekapselt, die folgende Unterstützungs-  
  
- Erstellen und Anzeigen von Fenstern  
  
- Einrichten von Beziehungen „Besitzer/zum Besitzer gehöriges Fenster“  
  
- Konfigurieren der Fensterdarstellung (z. B. Größe, Position, Symbole, Titelleistentext und Rahmen)  
  
- Verfolgen und Beeinflussen der Lebensdauer eines Fensters  
  
 Weitere Informationen finden Sie unter [Übersicht über WPF-Fenster](wpf-windows-overview.md).  
  
 <xref:System.Windows.Window> unterstützt die Erstellung einer besonderen Art von Fenster, nämlich von Dialogfeldern. Es können sowohl modale als auch nicht modale Dialogfelder (Dialogfelder ohne Modus) erstellt werden.  
  
 Aus Gründen der Benutzerfreundlichkeit und der Vorteile der Wiederverwendbarkeit und einer konsistenten <xref:Microsoft.Win32.OpenFileDialog>Benutzerfreundlichkeit in allen Anwendungen stellt WPF drei der allgemeinen Windows-Dialogfelder bereit: , <xref:Microsoft.Win32.SaveFileDialog>und <xref:System.Windows.Controls.PrintDialog>.  
  
 Ein Meldungsfeld ist eine besondere Art von Dialogfeld, in dem Benutzern wichtige Informationen angezeigt und einfache Ja/Nein/OK/Abbrechen-Fragen gestellt werden. Sie verwenden die <xref:System.Windows.MessageBox>-Klasse zum Erstellen und Anzeigen von Meldungsfeldern.  
  
 Weitere Informationen finden Sie unter [Übersicht über Dialogfelder](dialog-boxes-overview.md).  
  
<a name="Navigation"></a>
## <a name="navigation"></a>Navigation  
 WPF unterstützt die Navigation im<xref:System.Windows.Controls.Page>Webstil mithilfe<xref:System.Windows.Documents.Hyperlink>von Seiten ( ) und Hyperlinks ( ). Die Navigation kann unter anderem auf folgende Weise implementiert werden:  
  
- Eigenständige Seiten, die in einem Webbrowser gehostet werden  
  
- Seiten, die in einen XBAP kompiliert wurden, der in einem Webbrowser gehostet wird.  
  
- Als eigenständige Anwendung kompilierte Seiten, die von einem Navigationsfenster (<xref:System.Windows.Navigation.NavigationWindow>) gehostet werden  
  
- Seiten, die von einem<xref:System.Windows.Controls.Frame>Frame ( ) gehostet werden, der auf einer eigenständigen Seite gehostet werden kann, oder einer Seite, die entweder in eine XBAP- oder eine eigenständige Anwendung kompiliert wird.  
  
 Um die Navigation zu erleichtern, implementiert WPF Folgendes:  
  
- <xref:System.Windows.Navigation.NavigationService>, das freigegebene Navigationsmodul für die <xref:System.Windows.Controls.Frame> <xref:System.Windows.Navigation.NavigationWindow>Verarbeitung von Navigationsanforderungen, das von verwendet wird, und XBAPs zur Unterstützung der anwendungsinternen Navigation.  
  
- Navigationsmethoden zur Einleitung der Navigation  
  
- Navigationsereignisse zum Verfolgen und Beeinflussen der Navigationslebensdauer  
  
- Aufzeichnung von Vorwärts- und Rückwärtsnavigation mithilfe eines „Journals“, das auch überprüft und bearbeitet werden kann  
  
 Weitere Informationen finden Sie unter [Übersicht über die Navigation](navigation-overview.md).  
  
 WPF unterstützt auch einen speziellen Navigationstyp, der als strukturierte Navigation bezeichnet wird. Die strukturierte Navigation kann zum Aufruf einer oder mehrerer Seiten verwendet werden, die Daten auf strukturierte und vorhersagbare Weise in Übereinstimmung mit den aufrufenden Funktionen zurückgeben. Diese Funktion ist abhängig von der <xref:System.Windows.Navigation.PageFunction%601>-Klasse, die unter [Übersicht über die strukturierte Navigation](structured-navigation-overview.md) genauer beschrieben wird. <xref:System.Windows.Navigation.PageFunction%601> vereinfacht zudem die Erstellung komplexer Navigationstopologien, die unter [Übersicht über Navigationstopologien](navigation-topologies-overview.md) vorgestellt werden.  
  
<a name="Hosting"></a>
## <a name="hosting"></a>Hosting  
 XBAPs können in Microsoft Internet Explorer oder Firefox gehostet werden. Bei jedem Hostmodell sind spezifische Punkte und Einschränkungen zu beachten, die unter [Hosten](hosting-wpf-applications.md) erläutert werden.  
  
<a name="Build_and_Deploy"></a>
## <a name="build-and-deploy"></a>Erstellen und Bereitstellen  
 Obwohl einfache WPF-Anwendungen über eine Eingabeaufforderung mithilfe von Befehlszeilencompilern erstellt werden können, lässt sich WPF in Visual Studio integrieren, um zusätzliche Unterstützung bereitzustellen, die den Entwicklungs- und Buildprozess vereinfacht. Weitere Informationen finden Sie unter [Erstellen einer WPF-Anwendung](building-a-wpf-application-wpf.md).  
  
 Je nach Art der erstellten Anwendung können Sie eine oder mehrere Bereitstellungsoptionen wählen. Weitere Informationen finden Sie unter [Bereitstellen von WPF-Anwendungen](deploying-a-wpf-application-wpf.md).  
  
<a name="related_topics"></a>
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Übersicht über die Anwendungsverwaltung](application-management-overview.md)|Hier finden Sie eine Übersicht über die <xref:System.Windows.Application>-Klasse. Erörtert wird u.a. die Verwaltung von Anwendungslebensdauer, Fenstern, Anwendungsressourcen und Navigation.|  
|[Fenster in WPF](windows-in-wpf-applications.md)|Hier finden Sie Informationen zur Verwaltung von Fenstern in der Anwendung. Erörtert wird u.a. die Verwendung der <xref:System.Windows.Window>-Klasse und von Dialogfeldern.|  
|[Übersicht über die Navigation](navigation-overview.md)|Hier finden Sie eine Übersicht über die Verwaltung der Navigation zwischen Seiten der Anwendung.|  
|[Hosting](hosting-wpf-applications.md)|Bietet einen Überblick über XAML-Browseranwendungen (XBAPs).|  
|[Erstellen und Bereitstellen](building-and-deploying-wpf-applications.md)|Hier wird beschrieben, wie Sie die WPF-Anwendung erstellen und bereitstellen.|  
|[Einführung in WPF in Visual Studio](../getting-started/introduction-to-wpf-in-vs.md)|Hier werden die wichtigsten Funktionen von WPF beschrieben.|  
|[Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../getting-started/walkthrough-my-first-wpf-desktop-application.md)|In dieser exemplarischen Vorgehensweise wird gezeigt, wie Sie eine WPF-Anwendung mit Seitennavigation, Layout, Steuerelementen, Bildern, Stilen und Bindung erstellen.|
