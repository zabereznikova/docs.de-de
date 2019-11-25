---
title: Serialisierung und Speicherung von Dokumenten
ms.date: 03/30/2017
helpviewer_keywords:
- 'serialization of documents [WPF], , '
- documents [WPF], storage
- documents [WPF], serialization
ms.assetid: 4839cd87-e206-4571-803f-0200098ad37b
ms.openlocfilehash: ff0555105f219db5ed891c02400b0587c825718e
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974658"
---
# <a name="document-serialization-and-storage"></a>Serialisierung und Speicherung von Dokumenten

Microsoft .NET Framework bietet eine leistungsfähige Umgebung zum Erstellen und Anzeigen von Dokumenten mit hoher Qualität.  Erweiterte Funktionen, die sowohl fixierte Dokumente als auch Fluss Dokumente unterstützen, erweiterte Anzeige Steuerelemente in Kombination mit leistungsstarken 2D-und 3D-Grafikfunktionen .NET Framework Anwendungen auf eine neue Stufe der Qualität und Benutzer Funktionalität.  Die flexible Verwaltung einer Speicher internen Darstellung eines Dokuments ist ein wichtiges Feature von .NET Framework, und die Möglichkeit, Dokumente effizient zu speichern und aus einem Datenspeicher zu laden, ist fast jede Anwendung.  Der Prozess der Konvertierung eines Dokuments aus einer speicherinternen Darstellung in einen externen Datenspeicher wird als Serialisierung bezeichnet.  Der umgekehrte Vorgang des Lesens eines Datenspeichers und Neuerstellens der ursprünglichen Instanz im Speicher wird Deserialisierung genannt.

<a name="AboutSerialization"></a>

## <a name="about-document-serialization"></a>Informationen zur Dokumentserialisierung

Im Idealfall ist der Prozess der Serialisierung und Deserialisierung eines Dokuments aus dem Speicher und wieder zurück für die Anwendung transparent.  Die Anwendung ruft die Write-Methode des Serialisierungsprogramms auf, um das Dokument zu speichern. Die Read-Methode des Deserialisierungsprogramms greift dagegen auf den Datenspeicher zu und erstellt die ursprüngliche Instanz im Speicher neu.  Das jeweilige Format, in dem die Daten gespeichert werden, ist für die Anwendung normalerweise nicht relevant, solange der Serialisierungs- und Deserialisierungsprozess das Dokument wieder in seiner ursprünglichen Form erstellt.

Oft bieten Anwendungen mehrere Serialisierungsoptionen, die dem Benutzer die Speicherung von Dokumenten auf ein anderes Medium oder in ein anderes Format ermöglichen.  So kann eine Anwendung z.B. „Speichern unter“-Optionen anbieten, um ein Dokument in eine Datenträgerdatei, Datenbank oder einen Webdienst zu speichern.  Entsprechend können verschiedene Serialisierungsprogramme das Dokument in verschiedenen Formaten speichern, wie etwa HTML, RTF, XML, XPS oder das Format eines Drittanbieters.  Für die Anwendung wird eine Schnittstelle definiert, die die Details des Speichermediums innerhalb der Implementierung jedes einzelnen Serialisierungsprogramms isoliert.  Zusätzlich zu den Vorteilen der Kapselungs Speicherung von Speicher Details bieten die .NET Framework <xref:System.Windows.Documents.Serialization>-APIs verschiedene andere wichtige Features.

### <a name="features-of-net-framework-30-document-serializers"></a>Funktionen der Dokumentserialisierungsprogramme von .NET Framework 3.0

- Durch direkten Zugriff auf Dokumentobjekte der höheren Ebene (logische Struktur und visuelle Elemente) wird eine effiziente Speicherung von aufgeteiltem Inhalt, 2D-/3D-Elementen, Bildern, Medien, Hyperlinks, Anmerkungen und anderen Supportinhalten aktiviert.

- Synchrone und asynchrone Vorgänge

- Unterstützung für Plug-In-Serialisierungsprogramme mit erweiterten Funktionen:

  - System weiter Zugriff auf die Verwendung durch alle .NET Framework Anwendungen.

  - Einfache Erkennbarkeit von Anwendungs-Plug-Ins

  - Einfache Bereitstellung, Installation und Update von benutzerdefinierten Drittanbieter-Plug-Ins

  - Unterstützung von Benutzeroberflächen für benutzerdefinierte Laufzeiteinstellungen und -optionen

### <a name="xps-print-path"></a>XPS-Druckpfad

Der XPS-Druckpfad des Microsoft .NET Frameworks bietet auch einen erweiterbaren Mechanismus zum Schreiben von Dokumenten durch die Druckausgabe.  XPS dient als Dokument Dateiformat und ist das Native druckspool-Format für Windows Vista.  XPS-Dokumente können direkt an XPS-kompatible Drucker gesendet werden, ohne dass eine Konvertierung in ein zwischen Format erforderlich ist.  Weitere Informationen zu Optionen und Funktionen der Druckpfadausgabe finden Sie unter [Übersicht über das Drucken](printing-overview.md).

<a name="PluginSerializers"></a>

## <a name="plug-in-serializers"></a>Plug-In-Serialisierungsprogramme

Die <xref:System.Windows.Documents.Serialization>-APIs bieten Unterstützung für Plug-in-Serialisierungsprogrammen und verknüpfte Serialisierungsprogrammen, die separat von der Anwendung installiert werden, zur Laufzeit gebunden werden und mithilfe des <xref:System.Windows.Documents.Serialization.SerializerProvider> Discovery-Mechanismus aufgerufen werden.  Plug-In-Serialisierungsprogramme bieten mehr Vorteile hinsichtlich einfacher Bereitstellung und systemweiter Verwendung.  Verknüpfte serialisierungssoren können auch für teilweise vertrauenswürdige Umgebungen wie XAML-Browser Anwendungen (XBAPs) implementiert werden, bei denen nicht auf Plug-in-serialisierungssoren zugegriffen werden kann.  Verknüpfte Serialisierungsprogrammen, die auf einer abgeleiteten Implementierung der <xref:System.Windows.Documents.Serialization.SerializerWriter>-Klasse basieren, werden kompiliert und direkt mit der Anwendung verknüpft.  Plug-In-Serialisierungsprogramme und verknüpfte Serialisierungsprogramme verwenden identische öffentliche Methoden und Ereignisse. Daher können eine oder beide Arten von Serialisierungsprogrammen problemlos in der gleichen Anwendung verwendet werden.

Plug-In-Serialisierungsprogramme helfen Anwendungsentwicklern durch die Möglichkeit zur Erweiterung bei neuen Speicherentwürfen und Dateiformaten, ohne dass sie bereits bei der Erstellung für jedes mögliche Format programmieren müssen.  Von Plug-In-Serialisierungsprogrammen profitieren auch Drittanbieterentwickler durch eine standardisierte Methode, barrierefrei Plug-Ins für benutzerdefinierte oder geschützte Dateiformate bereitzustellen, zu installieren und zu aktualisieren.

### <a name="using-a-plug-in-serializer"></a>Verwenden eines Plug-In-Serialisierungsprogramms

Plug-In-Serialisierungsprogramme sind einfach zu verwenden.  Die <xref:System.Windows.Documents.Serialization.SerializerProvider>-Klasse listet ein <xref:System.Windows.Documents.Serialization.SerializerDescriptor>-Objekt für jedes im System installierte Plug-in auf.  Die <xref:System.Windows.Documents.Serialization.SerializerDescriptor.IsLoadable%2A>-Eigenschaft filtert die installierten Plug-ins basierend auf der aktuellen Konfiguration und überprüft, ob das Serialisierungsprogramm geladen und von der Anwendung verwendet werden kann.  Der <xref:System.Windows.Documents.Serialization.SerializerDescriptor> bietet auch weitere Eigenschaften, z. b. <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DisplayName%2A> und <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DefaultFileExtension%2A>, die von der Anwendung verwendet werden können, um den Benutzer aufzufordern, ein Serialisierungsprogramm für ein verfügbares Ausgabeformat auszuwählen.  Ein Standard-Plug-in-Serialisierungsprogramm für XPS wird mit .NET Framework bereitgestellt und wird immer aufgelistet.  Nachdem der Benutzer ein Ausgabeformat ausgewählt hat, wird die <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A>-Methode verwendet, um eine <xref:System.Windows.Documents.Serialization.SerializerWriter> für das jeweilige Format zu erstellen.  Die <xref:System.Windows.Documents.Serialization.SerializerWriter.Write%2A?displayProperty=nameWithType>-Methode kann dann aufgerufen werden, um den Dokument Datenstrom an den Datenspeicher auszugeben.

Im folgenden Beispiel wird eine Anwendung veranschaulicht, die die <xref:System.Windows.Documents.Serialization.SerializerProvider>-Methode in einer "pluginfilefilter"-Eigenschaft verwendet.  Pluginfilefilter listet die installierten Plug-Ins auf und erstellt eine Filter Zeichenfolge mit den verfügbaren Datei Optionen für eine <xref:Microsoft.Win32.SaveFileDialog>.

[!code-csharp[DocumentSerialize#DocSerializeFileFilter](~/samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializefilefilter)]

Nachdem ein Ausgabe Dateiname vom Benutzer ausgewählt wurde, wird im folgenden Beispiel veranschaulicht, wie die <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A>-Methode verwendet wird, um ein bestimmtes Dokument in einem angegebenen Format zu speichern.

[!code-csharp[DocumentSerialize#DocSerializePlugIn](~/samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializeplugin)]

<a name="InstallingPluginSerializers"></a>

### <a name="installing-plug-in-serializers"></a>Installieren von Plug-In-Serialisierungsprogrammen

Die <xref:System.Windows.Documents.Serialization.SerializerProvider>-Klasse stellt die Anwendungs Schnittstelle auf der obersten Ebene für das Plug-in-Serialisierungsprogramm und den Zugriff bereit.  <xref:System.Windows.Documents.Serialization.SerializerProvider> sucht und stellt der Anwendung eine Liste der Serialisierungsprogrammen zur Verfügung, die auf dem System installiert und zugänglich sind.  Die Einzelheiten der installierten Serialisierungsprogramme werden durch Registrierungseinstellungen definiert.  Plug-in-serialisierungssalizer können mit der <xref:System.Windows.Documents.Serialization.SerializerProvider.RegisterSerializer%2A>-Methode zur Registrierung hinzugefügt werden. Wenn .NET Framework noch nicht installiert ist, kann das Plug-in-Installationsskript die Registrierungs Werte selbst direkt festlegen.  Die <xref:System.Windows.Documents.Serialization.SerializerProvider.UnregisterSerializer%2A>-Methode kann verwendet werden, um ein zuvor installiertes Plug-in zu entfernen, oder die Registrierungs Einstellungen können auf ähnliche Weise durch ein Deinstallations Skript zurückgesetzt werden.

### <a name="creating-a-plug-in-serializer"></a>Erstellen eines Plug-In-Serialisierungsprogramms

Plug-In-Serialisierungsprogramme und verknüpfte Serialisierungsprogramme verwenden dieselben verfügbar gemachten, öffentlichen Methoden und Ereignisse und können daher so entworfen werden, dass sie synchron oder asynchron ausgeführt werden.  Folgen Sie diesen drei grundlegenden Schritten zum Erstellen eines Plug-In-Serialisierungsprogramms:

1. Implementieren und debuggen Sie das Serialisierungsprogramm zuerst als verknüpftes Serialisierungsprogramm.  Das vorherige Erstellen des Serialisierungsprogramms, das kompiliert und direkt mit der Testanwendung verknüpft wird, ermöglicht vollen Zugriff auf Haltepunkte und weitere für den Test nützliche Debugdienste.

2. Nachdem das Serialisierungsprogramm vollständig getestet wurde, wird eine <xref:System.Windows.Documents.Serialization.ISerializerFactory>-Schnittstelle hinzugefügt, um ein Plug-in zu erstellen.  Die <xref:System.Windows.Documents.Serialization.ISerializerFactory>-Schnittstelle ermöglicht den Vollzugriff auf alle .NET Framework Objekte, die die logische Struktur, <xref:System.Windows.UIElement> Objekte, <xref:System.Windows.Documents.IDocumentPaginatorSource>und <xref:System.Windows.Media.Visual> Elemente enthalten.  Darüber hinaus stellt <xref:System.Windows.Documents.Serialization.ISerializerFactory> dieselben synchronen und asynchronen Methoden und Ereignisse bereit, die von verknüpften serialisierungssoren verwendet werden.  Da die Ausgabe großer Dokumente mehr Zeit in Anspruch nehmen kann, sind asynchrone Vorgänge empfehlenswert, um eine reaktionsfähige Benutzerinteraktion und eine Abbrechen-Option zu gewährleisten, falls ein Problem mit dem Datenspeicher auftreten sollte.

3. Nach Erstellen des Plug-In-Serialisierungsprogramms wird ein Installationsskript für die Verteilung und Installation (und Deinstallation) des Plug-Ins implementiert (siehe oben unter „[Installieren von Plug-In-Serialisierungsprogrammen](#InstallingPluginSerializers)“).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Documents.Serialization>
- <xref:System.Windows.Xps.XpsDocumentWriter>
- <xref:System.Windows.Xps.Packaging.XpsDocument>
- [Dokumente in WPF](documents-in-wpf.md)
- [Übersicht über das Drucken](printing-overview.md)
- [Übersicht über XML Paper Specification](https://go.microsoft.com/fwlink?LinkID=106246)
