---
title: Paket-URI in WPF
ms.date: 03/30/2017
helpviewer_keywords:
- pack URI scheme [WPF]
- loading embedded resources [WPF]
- URIs (Uniform Resource Identifiers)
- Uniform Resource Identifiers (URIs)
- loading non-resource files
- application management [WPF]
ms.assetid: 43adb517-21a7-4df3-98e8-09e9cdf764c4
ms.openlocfilehash: ad928fb223ce22c65bb86a78c7d4cd006651a2d5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950758"
---
# <a name="pack-uris-in-wpf"></a>Paket-URI in WPF

In Windows Presentation Foundation (WPF) [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] werden zum Identifizieren und Laden von Dateien in vielerlei Hinsicht verwendet, einschließlich der folgenden:

- Angeben der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] , die beim ersten Start einer Anwendung angezeigt werden soll.

- Laden von Bildern

- Navigieren zu Seiten

- Laden von nicht ausführbaren Datendateien

[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] Ferner kann verwendet werden, um Dateien aus einer Vielzahl von Speicherorten zu identifizieren und zu laden, einschließlich der folgenden:

- Die aktuelle Assembly.

- Eine Assembly, auf die verwiesen wird.

- Ein zu einer Assembly relativer Speicherort.

- Die Ursprungssite der Anwendung.

Zum Bereitstellen eines konsistenten Mechanismus zum Identifizieren und Laden dieser Dateitypen von diesen Speicher [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Orten nutzt die Erweiterbarkeit des Paket- *URI-Schemas*. Dieses Thema enthält eine Übersicht über das Schema und erläutert, wie Sie ein [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] Paket für eine Vielzahl von Szenarios erstellen, und [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] erläutert [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] absolute und relative und Lösungsmöglichkeiten, bevor [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] Sie zeigen, wie Sie das Paket aus dem Markup verwenden. und Code.

<a name="The_Pack_URI_Scheme"></a>

## <a name="the-pack-uri-scheme"></a>Das Paket-URI-Schema

Das Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Schema wird von der OPC-Spezifikation ( [Open Packaging Conventions](https://go.microsoft.com/fwlink/?LinkID=71255) ) verwendet, mit der ein Modell zum organisieren und Identifizieren von Inhalten beschrieben wird. Die wichtigsten Elemente dieses Modells sind Pakete und Teile, wobei ein *Paket* ein logischer Container für einen oder mehrere logische *Teile*ist. Die folgende Abbildung veranschaulicht dieses Konzept.

![Paket und Teile-Diagramm](./media/pack-uris-in-wpf/wpf-package-parts-diagram.png)

Zur Identifizierung von Teilen nutzt die OPC-Spezifikation die Erweiterbarkeit von RFC 2396 (Uniform Resource Identifier (URI): Generische Syntax), um das Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Schema zu definieren.

Das Schema, das von einem [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] angegeben wird, wird durch das Präfix definiert. http, FTP und File sind bekannte Beispiele. Das Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Schema verwendet "Pack" als Schema und enthält zwei Komponenten: Autorität und Pfad. Im folgenden finden Sie das Format für ein [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]Paket.

Pack://*Authority*/*path*

Die *Autorität* gibt den Pakettyp an, in dem ein Teil enthalten ist, während der *Pfad* den Speicherort eines Teils innerhalb eines Pakets angibt.

Dieses Konzept wird in der folgenden Abbildung verdeutlicht:

![Beziehung zwischen Paket, Zertifizierungsstelle und Pfad](./media/pack-uris-in-wpf/wpf-relationship-diagram.png)

Pakete und Teile entsprechen Anwendungen und Dateien: eine Anwendung (ein Paket) kann eine oder mehrere Dateien (Teile) enthalten, darunter:

- Ressourcendateien, die in die lokale Assembly kompiliert werden

- Ressourcendateien, die in eine Assembly kompiliert werden, auf die verwiesen wird

- Ressourcendateien, die in eine verweisende Assembly kompiliert werden

- Inhaltsdateien

- Dateien der Ursprungssite

Für den Zugriff auf diese Datei [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Typen unterstützt zwei Autoritäten: Application:///und siteoforigin:///. Durch die Autorität „application:///“ werden Anwendungsdatendateien identifiziert, die zur Kompilierungszeit bekannt sind, darunter Ressourcen- und Inhaltsdateien. Durch die Autorität „siteoforigin:///“ werden die Dateien der Ursprungssite identifiziert. Der Bereich der Autoritäten wird in der folgenden Abbildung veranschaulicht.

![Paket-URI-Diagramm](./media/pack-uris-in-wpf/wpf-pack-uri-scheme.png)

> [!NOTE]
> Die Autoritäts Komponente eines [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Pakets ist eine eingebettete [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , die auf ein Paket verweist und RFC 2396 entsprechen muss. Außerdem muss das Zeichen „/“ durch „,“ ersetzt werden, und reservierte Zeichen wie „%“ und „?“ müssen mit Escapezeichen versehen werden. Ausführliche Informationen finden Sie in der OPC.

In den folgenden Abschnitten wird erläutert, wie [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] Sie das Paket mit diesen beiden Autorisierungs Methoden in Verbindung mit den entsprechenden Pfaden zum Identifizieren von Ressourcen, Inhalten und Ursprungs Dateien der Ursprungs Site erstellen.

<a name="Resource_File_Pack_URIs___Local_Assembly"></a>

## <a name="resource-file-pack-uris"></a>Paket-URIs der Ressourcendatei

Ressourcen Dateien werden als MSBuild `Resource` -Elemente konfiguriert und in Assemblys kompiliert. WPF unterstützt die Erstellung von Paket-URIs, die verwendet werden können, um Ressourcen Dateien zu identifizieren, die entweder in der lokalen Assembly kompiliert oder in eine Assembly kompiliert werden, auf die von der lokalen Assembly verwiesen wird.

<a name="Local_Assembly_Resource_File"></a>

### <a name="local-assembly-resource-file"></a>Ressourcendatei der lokalen Assembly

Das Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine Ressourcen Datei, die in die lokale Assembly kompiliert wird, verwendet die folgende Autorität und den folgenden Pfad:

- **Autorität**: application:///.

- **Pfad**: Der Name der Ressourcen Datei, einschließlich des Pfads, relativ zum lokalen assemblyprojektordner Stamm.

Das folgende Beispiel zeigt das Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Ressourcen Datei, die sich im Stammverzeichnis des Projekt Ordners der lokalen Assembly befindet.

`pack://application:,,,/ResourceFile.xaml`

Das folgende Beispiel zeigt das Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Ressourcen Datei, die sich in einem Unterordner des Projekt Ordners der lokalen Assembly befindet.

`pack://application:,,,/Subfolder/ResourceFile.xaml`

<a name="Resource_File_Pack_URIs___Referenced_Assembly"></a>

### <a name="referenced-assembly-resource-file"></a>Ressourcendatei der Assembly, auf die verwiesen wird

Das Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine Ressourcen Datei, die in eine referenzierte Assembly kompiliert wird, verwendet die folgende Autorität und den folgenden Pfad:

- **Autorität**: application:///.

- **Pfad**: Der Name einer Ressourcen Datei, die in eine Assembly kompiliert wird, auf die verwiesen wird. Der Pfad muss dem folgenden Format entsprechen:

  *AssemblyShortName* { *; Version*] { *; PublicKey*]; Komponente/*Pfad*

  - **AssemblyShortName**: Der Kurzname für die Assembly, auf die verwiesen wird.

  - **;Version** [optional]: Die Version der Assembly, auf die verwiesen wird, die die Ressourcendatei enthält. Wird verwendet, wenn mindestens zwei Assemblys, auf die verwiesen wird und die über denselben Kurznamen verfügen, geladen werden.

  - **;PublicKey** [optional]: Der öffentliche Schlüssel, der zum Signieren der Assembly verwendet wird, auf die verwiesen wird. Wird verwendet, wenn mindestens zwei Assemblys, auf die verwiesen wird und die über denselben Kurznamen verfügen, geladen werden.

  - **;component**: Gibt an, dass von der lokalen Assembly auf die Assembly verwiesen wird.

  - **/Path**: Der Name der Ressourcendatei, einschließlich des Pfads, relativ zum Stammverzeichnis des Projektordners der Assembly, auf die verwiesen wird.

Das folgende Beispiel zeigt das Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Ressourcen Datei, die sich im Stammverzeichnis des Projekt Ordners der referenzierten Assembly befindet.

`pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml`

Das folgende Beispiel zeigt das Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Ressourcen Datei, die sich in einem Unterordner des Projekt Ordners der Assembly befindet, auf die verwiesen wird.

`pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml`

Das folgende Beispiel zeigt das Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Ressourcen Datei, die sich im Stamm Ordner des Projekt Ordners einer referenzierten, Versions spezifischen Assembly befindet.

`pack://application:,,,/ReferencedAssembly;v1.0.0.1;component/ResourceFile.xaml`

Beachten Sie, dass [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] die Paket Syntax für referenzierte assemblyressourcendateien nur mit der Application:///Authority verwendet werden kann. Beispielsweise wird Folgendes in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]nicht unterstützt.

`pack://siteoforigin:,,,/SomeAssembly;component/ResourceFile.xaml`

<a name="Content_File_Pack_URIs"></a>

## <a name="content-file-pack-uris"></a>Paket-URIs der Inhaltsdatei

Das Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine Inhalts Datei verwendet die folgende Autorität und den folgenden Pfad:

- **Autorität**: application:///.

- **Pfad**: Der Name der Inhalts Datei, einschließlich des Pfads relativ zum Dateisystem Speicherort der ausführbaren Hauptassembly der Anwendung.

Das folgende Beispiel zeigt das Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Inhalts Datei, die sich im selben Ordner befindet wie die ausführbare Assembly.

`pack://application:,,,/ContentFile.xaml`

Das folgende Beispiel zeigt das Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Inhalts Datei, die sich in einem Unterordner befindet, der relativ zur ausführbaren Assembly der Anwendung ist.

`pack://application:,,,/Subfolder/ContentFile.xaml`

> [!NOTE]
> Auf HTML-Inhalts Dateien kann nicht navigiert werden. Das [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Schema unterstützt nur die Navigation zu HTML-Dateien, die sich an der Ursprungs Site befinden.

<a name="The_siteoforigin_____Authority"></a>

## <a name="site-of-origin-pack-uris"></a>Paket-URIs der Ursprungssite

Das Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine Ursprungs Site Datei verwendet die folgende Autorität und den folgenden Pfad:

- **Autorität**: siteoforigin:///.

- **Pfad**: Der Name der Ursprungs Datei der Site, einschließlich des Pfads relativ zu dem Speicherort, von dem aus die ausführbare Assembly gestartet wurde.

Im folgenden Beispiel wird das Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei der Ursprungs Site angezeigt, die an dem Speicherort gespeichert ist, von dem aus die ausführbare Assembly gestartet wird.

`pack://siteoforigin:,,,/SiteOfOriginFile.xaml`

Das folgende Beispiel zeigt das Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei der Ursprungs Site, die im Unterordner gespeichert ist, der relativ zu dem Speicherort ist, von dem die ausführbare Assembly der Anwendung gestartet wird.

`pack://siteoforigin:,,,/Subfolder/SiteOfOriginFile.xaml`

<a name="Page_Files"></a>

## <a name="page-files"></a>Seitendateien

XAML-Dateien, die als MSBuild `Page` -Elemente konfiguriert werden, werden auf die gleiche Weise wie Ressourcen Dateien in Assemblys kompiliert. Folglich können MSBuild `Page` -Elemente mithilfe von Paket-URIs für Ressourcen Dateien identifiziert werden.

Die Typen von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Dateien, die im Allgemeinen als MSBuild`Page` -Elemente konfiguriert werden, haben eines der folgenden Elemente als Stamm Element:

- <xref:System.Windows.Window?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Page?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.PageFunction%601?displayProperty=nameWithType>

- <xref:System.Windows.ResourceDictionary?displayProperty=nameWithType>

- <xref:System.Windows.Documents.FlowDocument?displayProperty=nameWithType>

- <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>

<a name="Absolute_vs_Relative_Pack_URIs"></a>

## <a name="absolute-vs-relative-pack-uris"></a>Absolute und relative Paket-URIs

Ein voll qualifizierter Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] umfasst das Schema, die Autorität und den Pfad, und es wird als absolutes Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]betrachtet. Als Vereinfachung für Entwickler [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] können Sie mithilfe von Elementen in der Regel geeignete Attribute mit einem relativen Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]festlegen, das nur den Pfad enthält.

Sehen Sie sich beispielsweise das folgende absolute [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Paket für eine Ressourcen Datei in der lokalen Assembly an.

`pack://application:,,,/ResourceFile.xaml`

Das relative Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , das auf diese Ressourcen Datei verweist, wäre die folgende.

`/ResourceFile.xaml`

> [!NOTE]
> Da Dateien der Ursprungs Site nicht Assemblys zugeordnet sind, kann auf Sie nur mit dem absoluten Paket [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]verwiesen werden.

Standardmäßig wird ein relativer Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] als relativ zum Speicherort des Markups oder Codes betrachtet, das den Verweis enthält. Wenn jedoch ein führender umgekehrter Schrägstrich verwendet wird, wird der [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] relative Paket Verweis als relativ zum Stamm der Anwendung betrachtet. Betrachten Sie beispielsweise die folgende Projektstruktur:

`App.xaml`

`Page2.xaml`

`\SubFolder`

`+ Page1.xaml`

`+ Page2.xaml`

Wenn "Page1. XAML ein [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] -Element enthält, das auf *root*\subfolder\page2.XAML verweist, kann für den Verweis [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]das folgende relative Paket verwendet werden.

`Page2.xaml`

Wenn "Page1. XAML ein [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] -Element enthält, das auf *root*\page2.XAML verweist, kann für den Verweis [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]das folgende relative Paket verwendet werden.

`/Page2.xaml`

<a name="Pack_URI_Resolution"></a>

## <a name="pack-uri-resolution"></a>Paket-URI-Auflösung

Das Format von Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] ermöglicht es, dass das [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] Paket für unterschiedliche Dateitypen identisch aussieht. Sehen Sie sich beispielsweise das folgende absolute [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]Pack an.

`pack://application:,,,/ResourceOrContentFile.xaml`

Dieses absolute Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] kann entweder auf eine Ressourcen Datei in der lokalen Assembly oder auf eine Inhalts Datei verweisen. Das gleiche gilt für den folgenden relativen [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].

`/ResourceOrContentFile.xaml`

Um den Typ der Datei zu bestimmen, auf die ein [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Paket verweist, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] wird [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] für Ressourcen Dateien in lokalen Assemblys und Inhalts Dateien mithilfe der folgenden Heuristik aufgelöst:

1. Überprüfen Sie die Assemblymetadaten nach einem <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> Attribut, das dem Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]entspricht.

2. Wenn das <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> Attribut gefunden wird, verweist der Pfad des Pakets [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] auf eine Inhalts Datei.

3. Wenn das <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> Attribut nicht gefunden wird, überprüfen Sie die festgelegten Ressourcen Dateien, die in die lokale Assembly kompiliert werden.

4. Wenn eine Ressourcen Datei gefunden wird, die mit dem Paketpfad [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] übereinstimmt, verweist der Pfad des Pakets [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] auf eine Ressourcen Datei.

5. Wenn die Ressource nicht gefunden wird, ist die intern <xref:System.Uri> erstellte ungültig.

[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]die Auflösung gilt nicht für [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] die folgenden Informationen:

- Inhalts Dateien in referenzierten Assemblys: diese Dateitypen werden [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]von nicht unterstützt.

- Eingebettete Dateien in referenzierten [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] Assemblys: diese identifizieren eindeutig, weil Sie sowohl den Namen der referenzierten Assembly `;component` als auch das Suffix enthalten.

- Dateien der Ursprungs Site: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] diese identifizieren eindeutige Dateien, da Sie die einzigen Dateien sind, die mit dem Paket [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] identifiziert werden können, das die siteoforigin:///-Autorität enthält.

Eine Vereinfachung, die [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] die Paket Auflösung ermöglicht, besteht darin, dass Code in gewisser Weise von den Speicherorten von Ressourcen-und Inhalts Dateien unabhängig ist. Wenn Sie z. b. über eine Ressourcen Datei in der lokalen Assembly verfügen, die als Inhalts Datei neu konfiguriert wird, bleibt [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] das Paket für die Ressource unverändert, ebenso wie der Code, der das Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]verwendet.

<a name="Programming_with_Pack_URIs"></a>

## <a name="programming-with-pack-uris"></a>Programmieren mit Paket-URIs

Viele [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Klassen implementieren Eigenschaften, die mit Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]festgelegt werden können, einschließlich:

- <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Frame.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Documents.Hyperlink.NavigateUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Window.Icon%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Image.Source%2A?displayProperty=nameWithType>

Diese Eigenschaften können sowohl im Markup als auch im Code festgelegt werden. In diesem Abschnitt werden die grundlegenden Konstruktionen beider Varianten beschrieben, und es werden Beispiele für allgemeine Szenarien gezeigt.

<a name="Using_Pack_URIs_in_Markup"></a>

### <a name="using-pack-uris-in-markup"></a>Verwenden von Paket-URIs im Markup

Ein Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] wird in Markup angegeben, indem das-Element eines Attributs mit dem [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]Paket festgelegt wird. Beispiel:

`<element attribute="pack://application:,,,/File.xaml" />`

Tabelle 1 veranschaulicht das verschiedene absolute Paket [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] , das Sie im Markup angeben können.

Tabelle 1: Absolute Pack-URIs im Markup

|Datei|Absolutes Paket[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|Ressourcendatei – lokale Assembly|`"pack://application:,,,/ResourceFile.xaml"`|
|Ressourcendatei im Unterordner – lokale Assembly|`"pack://application:,,,/Subfolder/ResourceFile.xaml"`|
|Ressourcendatei – Assembly, auf die verwiesen wird|`"pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml"`|
|Ressourcendatei im Unterordner der Assembly, auf die verwiesen wird|`"pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|Ressourcendatei in Assembly mit Versionsangabe, auf die verwiesen wird|`"pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml"`|
|Inhaltsdatei|`"pack://application:,,,/ContentFile.xaml"`|
|Inhaltsdatei im Unterordner|`"pack://application:,,,/Subfolder/ContentFile.xaml"`|
|Datei der Ursprungssite|`"pack://siteoforigin:,,,/SOOFile.xaml"`|
|Datei der Ursprungssite im Unterordner|`"pack://siteoforigin:,,,/Subfolder/SOOFile.xaml"`|

Tabelle 2 zeigt die verschiedenen relativen Paket [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] -, die Sie im Markup angeben können.

Tabelle 2: Relative Paket-URIs im Markup

|Datei|Relativer Paket[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|Ressourcendatei in lokaler Assembly|`"/ResourceFile.xaml"`|
|Ressourcendatei im Unterordner der lokalen Assembly|`"/Subfolder/ResourceFile.xaml"`|
|Ressourcendatei in Assembly, auf die verwiesen wird|`"/ReferencedAssembly;component/ResourceFile.xaml"`|
|Ressourcendatei im Unterordner der Assembly, auf die verwiesen wird|`"/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|Inhaltsdatei|`"/ContentFile.xaml"`|
|Inhaltsdatei im Unterordner|`"/Subfolder/ContentFile.xaml"`|

<a name="Using_Pack_URIs_in_Code"></a>

### <a name="using-pack-uris-in-code"></a>Verwenden von Paket-URIs im Code

Sie geben ein Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] im Code an, indem Sie die <xref:System.Uri> -Klasse instanziieren [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] und das Paket als Parameter an den-Konstruktor übergeben. Dies wird im folgenden Beispiel dargestellt.

```csharp
Uri uri = new Uri("pack://application:,,,/File.xaml");
```

Standardmäßig betrachtet die <xref:System.Uri> Klasse Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] als absolut. Folglich wird eine Ausnahme ausgelöst, wenn eine Instanz der <xref:System.Uri> -Klasse mit einem relativen Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]erstellt wird.

```csharp
Uri uri = new Uri("/File.xaml");
```

Glücklicherweise akzeptiert die <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> - <xref:System.Uri> Überladung des-Klassenkonstruktors einen Parameter <xref:System.UriKind> vom Typ, mit dem Sie angeben können [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , ob ein Paket entweder absolut oder relativ ist.

```csharp
// Absolute URI (default)
Uri absoluteUri = new Uri("pack://application:,,,/File.xaml", UriKind.Absolute);
// Relative URI
Uri relativeUri = new Uri("/File.xaml",
                        UriKind.Relative);
```

Sie sollten nur <xref:System.UriKind.Absolute> oder <xref:System.UriKind.Relative> angeben, wenn Sie sicher sind, dass das [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] bereitgestellte Paket ein oder das andere Paket ist. Wenn Sie den Typ des verwendeten Pakets [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] nicht kennen, z. b. Wenn ein Benutzer zur Laufzeit ein Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] eingibt, verwenden <xref:System.UriKind.RelativeOrAbsolute> Sie stattdessen.

```csharp
// Relative or Absolute URI provided by user via a text box
TextBox userProvidedUriTextBox = new TextBox();
Uri uri = new Uri(userProvidedUriTextBox.Text, UriKind.RelativeOrAbsolute);
```

Tabelle 3 veranschaulicht das verschiedene relative Paket [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] , das Sie mithilfe <xref:System.Uri?displayProperty=nameWithType>von im Code angeben können.

Tabelle 3: Absolute Pack-URIs im Code

|Datei|Absolutes Paket[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|Ressourcendatei – lokale Assembly|`Uri uri = new Uri("pack://application:,,,/ResourceFile.xaml", UriKind.Absolute);`|
|Ressourcendatei im Unterordner – lokale Assembly|`Uri uri = new Uri("pack://application:,,,/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|
|Ressourcendatei – Assembly, auf die verwiesen wird|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Absolute);`|
|Ressourcendatei im Unterordner der Assembly, auf die verwiesen wird|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|
|Ressourcendatei in Assembly mit Versionsangabe, auf die verwiesen wird|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml", UriKind.Absolute);`|
|Inhaltsdatei|`Uri uri = new Uri("pack://application:,,,/ContentFile.xaml", UriKind.Absolute);`|
|Inhaltsdatei im Unterordner|`Uri uri = new Uri("pack://application:,,,/Subfolder/ContentFile.xaml", UriKind.Absolute);`|
|Datei der Ursprungssite|`Uri uri = new Uri("pack://siteoforigin:,,,/SOOFile.xaml", UriKind.Absolute);`|
|Datei der Ursprungssite im Unterordner|`Uri uri = new Uri("pack://siteoforigin:,,,/Subfolder/SOOFile.xaml", UriKind.Absolute);`|

Tabelle 4 veranschaulicht das verschiedene relative Paket [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] , das Sie im Code mithilfe <xref:System.Uri?displayProperty=nameWithType>von angeben können.

Tabelle 4: Relative Paket-URIs im Code

|Datei|Relativer Paket[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|Ressourcendatei – lokale Assembly|`Uri uri = new Uri("/ResourceFile.xaml", UriKind.Relative);`|
|Ressourcendatei im Unterordner – lokale Assembly|`Uri uri = new Uri("/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|Ressourcendatei – Assembly, auf die verwiesen wird|`Uri uri = new Uri("/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Relative);`|
|Ressourcendatei im Unterordner – Assembly, auf die verwiesen wird|`Uri uri = new Uri("/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|Inhaltsdatei|`Uri uri = new Uri("/ContentFile.xaml", UriKind.Relative);`|
|Inhaltsdatei im Unterordner|`Uri uri = new Uri("/Subfolder/ContentFile.xaml", UriKind.Relative);`|

<a name="Common_Pack_URI_Scenarios"></a>

### <a name="common-pack-uri-scenarios"></a>Häufige Szenarien mit Paket-URIs

In den vorherigen Abschnitten wurde erläutert, wie Sie [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] ein Paket erstellen, um Ressourcen, Inhalte und Ursprungs Dateien zu identifizieren. In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]werden diese Konstruktionen auf verschiedene Weise verwendet, und in den folgenden Abschnitten werden verschiedene gängige Verwendungen behandelt.

<a name="Specifying_the_UI_to_Show_when_an_Application_Starts"></a>

#### <a name="specifying-the-ui-to-show-when-an-application-starts"></a>Angeben der Benutzeroberfläche, die beim Starten einer Anwendung angezeigt werden soll

<xref:System.Windows.Application.StartupUri%2A>Gibt den ersten [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] an, der beim [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Starten einer Anwendung angezeigt werden soll. Bei eigenständigen Anwendungen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] kann ein Fenster sein, wie im folgenden Beispiel gezeigt.

[!code-xaml[PackURIOverviewSnippets#StartupUriWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/Copy of App.xaml#startupuriwindow)]

Eigenständige Anwendungen [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] und können auch eine Seite als anfängliche Benutzeroberfläche angeben, wie im folgenden Beispiel gezeigt.

[!code-xaml[PackURIOverviewSnippets#StartupUriPage](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/App.xaml#startupuripage)]

Wenn es sich bei der Anwendung um eine eigenständige Anwendung handelt und <xref:System.Windows.Application.StartupUri%2A>eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Seite mit <xref:System.Windows.Navigation.NavigationWindow> angegeben wird, wird eine zum Hosten der Seite geöffnet. Für [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]wird die Seite im Host Browser angezeigt.

<a name="Navigating_to_a_Page"></a>

#### <a name="navigating-to-a-page"></a>Navigieren zu einer Seite

Im folgenden Beispiel wird das Navigieren zu einer Seite veranschaulicht.

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

Weitere Informationen zu den verschiedenen Möglichkeiten zum Navigieren in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]finden Sie unter [Übersicht](navigation-overview.md)über die Navigation.

<a name="Specifying_a_Window_Icon"></a>

#### <a name="specifying-a-window-icon"></a>Angeben eines Fenstersymbols

Im folgenden Beispiel wird gezeigt, wie Sie mithilfe eines URIs das Symbol eines Fensters angeben.

[!code-xaml[WindowIconSnippets#WindowIconSetXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/WindowIconSnippets/XAML/MainWindow.xaml#windowiconsetxaml)]

Weitere Informationen finden Sie unter <xref:System.Windows.Window.Icon%2A>.

<a name="Loading_Image__Audio__and_Video_Files"></a>

#### <a name="loading-image-audio-and-video-files"></a>Laden von Bild-, Audio- und Videodateien

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]ermöglicht Anwendungen die Verwendung einer Vielzahl von Medientypen, die alle identifiziert und mit Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]geladen werden können, wie in den folgenden Beispielen gezeigt.

[!code-xaml[MediaPlayerVideoSample#VideoPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerVideoSample/CS/HomePage.xaml#videopackuriatsoo)]

[!code-xaml[MediaPlayerAudioSample#AudioPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerAudioSample/CS/HomePage.xaml#audiopackuriatsoo)]

[!code-xaml[ImageSample#ImagePackURIContent](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageSample/CS/HomePage.xaml#imagepackuricontent)]

Weitere Informationen zum Arbeiten mit Medieninhalten finden Sie unter [Grafiken und Multimedia](../graphics-multimedia/index.md).

<a name="Loading_a_Resource_Dictionary_from_the_Site_of_Origin"></a>

#### <a name="loading-a-resource-dictionary-from-the-site-of-origin"></a>Laden eines Ressourcenverzeichnisses von der Ursprungssite

Ressourcen Wörterbücher (<xref:System.Windows.ResourceDictionary>) können verwendet werden, um Anwendungs Designs zu unterstützen. Eine Möglichkeit, Designs zu erstellen und zu verwalten, besteht darin, mehrere Designs als Ressourcenverzeichnisse zu erstellen, die auf der Ursprungssite einer Anwendung gespeichert sind. Dadurch können Designs hinzugefügt und aktualisiert werden, ohne dass eine Anwendung erneut kompiliert und bereitgestellt werden muss. Diese Ressourcen Wörterbücher können mithilfe von Paket [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]identifiziert und geladen werden, wie im folgenden Beispiel gezeigt.

[!code-xaml[ResourceDictionarySnippets#ResourceDictionaryPackURI](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourceDictionarySnippets/CS/App.xaml#resourcedictionarypackuri)]

Eine Übersicht über die Designs in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]finden Sie unter Erstellen von Formaten [und](../controls/styling-and-templating.md)Vorlagen.

## <a name="see-also"></a>Siehe auch

- [WPF-Anwendungsressource, Inhalts- und Datendateien](wpf-application-resource-content-and-data-files.md)
