---
title: "Serialisierung und Speicherung von Dokumenten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Dokumente, Serialisierung"
  - "Dokumente, storage"
  - "Dokumentserialisierung"
  - "Dokumentspeicherung"
ms.assetid: 4839cd87-e206-4571-803f-0200098ad37b
caps.latest.revision: 24
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# Serialisierung und Speicherung von Dokumenten
[!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] stellt eine leistungsstarke Umgebung für das Erstellen und Anzeigen qualitativ hochwertiger Dokumente bereit.  Erweiterte Features, die einheitlich dargestellte Dokumente und Flussdokumente unterstützen, und erweiterte Anzeigesteuerelemente in Kombination mit leistungsstarken 2D\- und 3D\-Grafikfunktionen heben [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]\-Anwendungen in Bezug auf Qualität und Benutzerfreundlichkeit auf ein neues Niveau.  Die Möglichkeit der flexiblen Verwaltung einer speicherinternen Darstellung eines Dokument ist ein zentrales Feature von [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)], während das effiziente Speichern und Laden von Dokumenten aus einem Datenspeicher eine Anforderung bei fast allen Anwendungen ist.  Der Prozess der Konvertierung eines Dokuments aus einer speicherinternen Darstellung in einen externen Datenspeicher wird als [Serialisierung](GTMT) bezeichnet.  Der umgekehrte Prozess, einen Datenspeicher zu lesen und die ursprüngliche speicherinterne Instanz neu zu erstellen, wird als Deserialisierung bezeichnet.  
  
   
  
<a name="AboutSerialization"></a>   
## Informationen zur Dokumentserialisierung  
 Im Idealfall ist der Prozess der [Serialisierung](GTMT) und Deserialisierung eines Dokuments aus dem Speicher und anschließend zurück in den Speicher für die Anwendung transparent.  Die Anwendung ruft eine Write\-Methode des Serialisierungsprogramms auf, um das Dokument zu speichern, während eine Read\-Methode des Deserialisierungsprogramms auf den Datenspeicher zugreift und die ursprüngliche Instanz im Speicher neu erstellt.  Das spezifische Format, in dem die Daten gespeichert werden, spielt für die Anwendung in der Regel keine Rolle, solange das Dokument im Rahmen des Serialisierungs\- und Deserialisierungsprozesses neu in seiner ursprünglichen Form erstellt wird.  
  
 Häufig bieten Anwendungen mehrere Serialisierungsoptionen, sodass der Benutzer Dokumente auf einem anderen Medium oder in einem anderen Format speichern kann.  Eine Anwendung kann z. B. "Speichern unter"\-Optionen anbieten, um ein Dokument in einer Datenträgerdatei, einer Datenbank oder einem Webdienst zu speichern.  Ebenso können verschiedene Serialisierungsprogramme das Dokument in verschiedenen Formaten wie HTML, RTF, XML, XPS oder alternativ im Format eines Drittanbieters speichern.  Für die Anwendung wird durch die Serialisierung eine Schnittstelle definiert, die die Details des Speichermediums innerhalb der Implementierung jedes einzelnen Serialisierungsprogramms isoliert.  Neben den Vorteilen der Kapselung von Speicherdetails bieten die [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]\-<xref:System.Windows.Documents.Serialization>\-[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] noch weitere wichtige Features.  
  
### Features der Dokumentserialisierungsprogramme von .NET Framework 3.0  
  
-   Der Direktzugriff auf die Dokumentobjekte der höheren Ebene \([logische Struktur](GTMT) und visuelle Elemente\) ermöglicht die effiziente Speicherung von paginierten Inhalten, 2D\/3D\-Elementen, Bildern, Medien, Links, Anmerkungen und anderen Unterstützungsinhalten.  
  
-   [Synchroner](GTMT) und [asynchroner](GTMT) Vorgang.  
  
-   Unterstützung für Plug\-In\-Serialisierungsprogramme mit erweiterten Funktionen:  
  
    -   Systemweiter Zugriff für alle [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]\-Anwendungen.  
  
    -   Einfache Auffindbarkeit von Anwendungs\-Plug\-Ins.  
  
    -   Einfaches Bereitstellen, Installieren und Aktualisieren für benutzerdefinierte Drittanbieter\-Plug\-Ins.  
  
    -   Benutzeroberflächenunterstützung für benutzerdefinierte Laufzeiteinstellungen und Optionen.  
  
### XPS\-Druckpfad  
 Der [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] bietet auch einen erweiterbaren Mechanismus für das Schreiben von Dokumenten durch die Druckausgabe.  Dabei dient [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] sowohl als Dokumentdateiformat als auch als systemeigenes Druckerspoolformat für [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)].  [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]\-Dokumente können ohne vorherige Konvertierung in ein Zwischenformat direkt an [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]\-kompatible Drucker gesendet werden.  Weitere Informationen über Optionen und Funktionen für die Druckpfadausgabe finden Sie unter [Übersicht über das Drucken](../../../../docs/framework/wpf/advanced/printing-overview.md).  
  
<a name="PluginSerializers"></a>   
## Plug\-In\-Serialisierungsprogramme  
 Die <xref:System.Windows.Documents.Serialization>\-APIs bieten Unterstützung sowohl für Plug\-In\-Serialisierungsprogramme als auch für verknüpfte Serialisierungsprogramme, die separat von der Anwendung installiert, zur Laufzeit gebunden und vom <xref:System.Windows.Documents.Serialization.SerializerProvider>\-Discovery\-Mechanismus aufgerufen werden.  Plug\-In\-Serialisierungsprogramme bieten mehr Vorteile im Bezug auf Bereitstellung und systemweite Verwendung.  Verknüpfte Serialisierungsprogramme können auch für [teilweise vertrauenswürdige](GTMT) Umgebungen wie [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] implementiert werden, in denen nicht auf Plug\-In\-Serialisierungsprogramme zugegriffen werden kann.  Verknüpfte Serialisierungsprogramme, die auf einer abgeleiteten Implementierung der <xref:System.Windows.Documents.Serialization.SerializerWriter>\-Klasse basieren, werden kompiliert und direkt mit der Anwendung verknüpft.  Plug\-In\-Serialisierungsprogramme und verknüpfte Serialisierungsprogramme verwenden dieselben öffentlichen Methoden und Ereignisse. Dadurch können beide problemlos in einer Anwendung verwendet werden.  
  
 Plug\-In\-Serialisierungsprogramme bieten Entwicklern die Möglichkeit, Anwendungen um neue Speicherentwürfe und Dateiformate zu erweitern, ohne jedes potenzielle Format bereits zur Erstellungszeit codieren zu müssen.  Darüber hinaus profitieren auch Drittanbieterentwickler von Plug\-In\-Serialisierungsprogrammen, weil sie damit eine standardisierte Methode zum Bereitstellen, Installieren und Aktualisieren der für das System zugänglichen Plug\-Ins für benutzerdefinierte oder proprietäre Dateiformate erhalten.  
  
### Verwenden eines Plug\-In\-Serialisierungsprogramms  
 Plug\-In\-Serialisierungsprogramme sind einfach zu verwenden.  Die <xref:System.Windows.Documents.Serialization.SerializerProvider>\-Klasse listet ein <xref:System.Windows.Documents.Serialization.SerializerDescriptor>\-Objekt für jedes auf dem System installierte Plug\-In auf.  Die <xref:System.Windows.Documents.Serialization.SerializerDescriptor.IsLoadable%2A>\-Eigenschaft filtert die installierten Plug\-Ins auf Basis der aktuellen Konfiguration und prüft, ob das Serialisierungsprogramm von der Anwendung geladen und verwendet werden kann.  <xref:System.Windows.Documents.Serialization.SerializerDescriptor> stellt noch weitere Eigenschaften wie <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DisplayName%2A> und <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DefaultFileExtension%2A> bereit, mit denen die Anwendung den Benutzer aufordern kann, ein Serialisierungsprogramm für ein verfügbares Ausgabeformat auszuwählen.  [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] beinhaltet ein Standard\-Plug\-In\-Serialisierungsprogramm für [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)], das immer aufgelistet wird.  Nachdem der Benutzer ein Ausgabeformat ausgewählt hat, wird mit der <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A>\-Methode ein <xref:System.Windows.Documents.Serialization.SerializerWriter> für das bestimmte Format erstellt.  Anschließend kann die <xref:System.Windows.Documents.Serialization.SerializerWriter>.<xref:System.Windows.Documents.Serialization.SerializerWriter.Write%2A>\-Methode aufgerufen werden, um den Dokumentstream in den Datenspeicher auszugeben.  
  
 Im folgenden Beispiel wird eine Anwendung veranschaulicht, die die <xref:System.Windows.Documents.Serialization.SerializerProvider>\-Methode in einer PlugInFileFilter\-Eigenschaft verwendet.  PlugInFileFilter listet die installierten Plug\-Ins auf und erstellt eine Filterzeichenfolge mit den verfügbaren Dateioptionen für ein <xref:Microsoft.Win32.SaveFileDialog>\-Element.  
  
 [!code-csharp[DocumentSerialize#DocSerializeFileFilter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializefilefilter)]  
  
 Im folgende Beispiel wird die Verwendung der <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A>\-Methode veranschaulicht, um ein bestimmtes Dokument in einem angegebenen Format zu speichern, nachdem der Benutzer einen Namen für die Ausgabedatei ausgewählt hat.  
  
 [!code-csharp[DocumentSerialize#DocSerializePlugIn](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializeplugin)]  
  
<a name="InstallingPluginSerializers"></a>   
### Installieren von Plug\-In\-Serialisierungsprogrammen  
 Die <xref:System.Windows.Documents.Serialization.SerializerProvider>\-Klasse liefert die Anwendungsschnittstelle der höheren Ebene für das Auffinden und den Zugriff des Plug\-In\-Serialisierungsprogramms.  <xref:System.Windows.Documents.Serialization.SerializerProvider> sucht und stellt der Anwendung eine Liste der Serialisierungsprogramme bereit, die auf dem System installiert sind, und auf die Sie zugreifen können.  Die Einzelheiten der installierten Serialisierungsprogramme werden durch Registrierungseinstellungen definiert.  Plug\-In\-Serialisierungsprogramme können der Registrierung mithilfe der <xref:System.Windows.Documents.Serialization.SerializerProvider.RegisterSerializer%2A>\-Methode hinzugefügt werden. Wenn [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] nicht installiert ist, kann das Plug\-In\-Installationsskript die Registrierungswerte auch direkt selbst festlegen.  Zuvor installierte Plug\-Ins können mithilfe der <xref:System.Windows.Documents.Serialization.SerializerProvider.UnregisterSerializer%2A>\-Methode entfernt werden, oder ein Deinstallationsskript setzt die Registrierungseinstellungen wieder zurück.  
  
### Erstellen eines Plug\-In\-Serialisierungsprogramms  
 Plug\-In\-Serialisierungsprogramme und verknüpfte Serialisierungsprogramme verwenden dieselben verfügbar gemachten öffentlichen Methoden und Ereignisse und können daher auch für den [synchronen](GTMT) oder [asynchronen](GTMT) Vorgang konfiguriert werden.  Es gibt in der Regel drei grundlegende Schritte, um ein Plug\-In\-Serialisierungsprogramm zu erstellen:  
  
1.  Implementieren und debuggen Sie das Serialisierungsprogramm zuerst als verknüpftes Serialisierungsprogramm.  Durch anfängliche Erstellung des Serialisierungsprogramms als kompilierte und direkt mit einer Testanwendung verknüpfte Version, erhalten Sie vollständigen Zugriff auf Haltepunkte und andere Debugdienste, die für das Testen hilfreich sind.  
  
2.  Nach dem vollständigen Testen des Serialisierungsprogramms wird eine <xref:System.Windows.Documents.Serialization.ISerializerFactory>\-Schnittstelle hinzugefügt, um ein Plug\-In zu erstellen.  Die <xref:System.Windows.Documents.Serialization.ISerializerFactory>\-Schnittstelle erlaubt den vollständigen Zugriff auf alle [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]\-Objekte einschließlich der lokalen Struktur, <xref:System.Windows.UIElement>\-Objekte, <xref:System.Windows.Documents.IDocumentPaginatorSource>\-Elemente und <xref:System.Windows.Media.Visual>\-Elemente.  Darüber hinaus stellt <xref:System.Windows.Documents.Serialization.ISerializerFactory> dieselben synchronen und asynchronen Methoden und Ereignisse wie für verknüpfte Serialisierungsprogramme bereit.  Da die Ausgabe großer Dokumente länger dauern kann, werden asynchrone Vorgänge empfohlen, um weiterhin auf Benutzerinteraktionen reagieren und eine Option "Abbrechen" anbieten zu können, wenn ein Problem mit dem Datenspeicher auftritt.  
  
3.  Nach der Erstellung des Plug\-In\-Serialisierungsprogramms wird ein Installationsskript für die Verteilung und Installation \(sowie die Deinstallation\) des Plug\-Ins implementiert \(weitere Informationen finden Sie weiter oben unter [Installieren von Plug\-In\-Serialisierungsprogrammen](#InstallingPluginSerializers)\).  
  
## Siehe auch  
 <xref:System.Windows.Documents.Serialization>   
 <xref:System.Windows.Xps.XpsDocumentWriter>   
 <xref:System.Windows.Xps.Packaging.XpsDocument>   
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Übersicht über das Drucken](../../../../docs/framework/wpf/advanced/printing-overview.md)   
 [XML Paper Specification: Übersicht](http://go.microsoft.com/fwlink?LinkID=106246)