---
title: WPF-Anwendungsressource, Inhalts- und Datendateien
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WPF application [WPF], files
- loose resources [WPF]
- content files [WPF]
- Site of Origin files [WPF]
- resource files [WPF]
- remote files [WPF]
- embedded resources [WPF]
- files [WPF]
- referencing application files [WPF]
- application development [WPF], files
- application management [WPF]
ms.assetid: 7ad2943b-3961-41d3-8fc6-1582d43f5d99
ms.openlocfilehash: 075f70e3ef053507dfe3d408246d179bb57c5891
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59211921"
---
# <a name="wpf-application-resource-content-and-data-files"></a>WPF-Anwendungsressource, Inhalts- und Datendateien
[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] -Anwendungen hängen oftmals Dateien, die nicht ausführbare Daten, z. B. enthalten [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], Bilder, Video und Audio. Windows Presentation Foundation (WPF) bietet spezielle Unterstützung für das Konfigurieren, identifizieren und die Verwendung dieser Typen von Datendateien, die als Anwendungsdatendateien bezeichnet werden. Diese Unterstützung bezieht sich auf einen bestimmten Satz von Anwendungsdatendateitypen, einschließlich:  
  
-   **Ressourcendateien**: Datendateien, die in eine ausführbare Datei oder Bibliothek kompiliert werden [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Assembly.  
  
-   **Inhaltsdateien**: Eigenständige Datendateien, die eine explizite Zuordnung mit einer ausführbaren Datei [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Assembly.  
  
-   **Dateien der Ursprungssite**: Eigenständige Datendateien, die keine Zuordnung zu einer ausführbaren Datei [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Assembly.  
  
 Ein wichtiger Unterschied zwischen diesen drei Dateitypen besteht darin, dass die Ressourcen- und Inhaltsdateien zur Buildzeit bekannt sind. Sie sind einer Assembly explizit bekannt. Für die Website der Dateien der Ursprungssite, jedoch einer Assembly u. u. keine Kenntnis davon, oder ein implizites Wissen über eine Pack [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] Verweis, der im letzteren Fall besteht keine Garantie, dass die Website auf die verwiesen wird, Datei der Ursprungssite tatsächlich vorhanden ist.  
  
 Anwendungsdatendateien verweisen möchten, verwendet Windows Presentation Foundation (WPF) das Pack [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] Schema, das ausführlich beschrieben wird [Paket-URIs in WPF](pack-uris-in-wpf.md)).  
  
 In diesem Thema wird beschrieben, wie Sie Anwendungsdatendateien konfigurieren und verwenden.  

<a name="Resource_Files"></a>   
## <a name="resource-files"></a>Ressourcendateien  
 Wenn eine Anwendungsdatendatei einer Anwendung stets zur Verfügung stehen muss, kann die Verfügbarkeit nur dadurch gewährleistet werden, dass die Datei in eine der ausführbaren Hauptassemblys einer Anwendung oder in eine der Assemblys kompiliert wird, auf die verwiesen wird. Dieser Typ von Anwendungsdatendatei wird als bezeichnet ein *Ressourcendatei*.  
  
 Verwenden Sie die Ressourcendateien in folgenden Fällen:  
  
-   Sie müssen den Inhalt der Ressourcendatei nicht aktualisieren, nachdem sie in eine Assembly kompiliert wurde.  
  
-   Sie möchten die Komplexität der Anwendungsverteilung vereinfachen, indem Sie die Anzahl von Dateiabhängigkeiten verringern.  
  
-   Die Anwendungsdatendatei muss lokalisierbar sein (siehe [WPF-Globalisierung und Lokalisierung (Übersicht)](../advanced/wpf-globalization-and-localization-overview.md)).  
  
> [!NOTE]
>  Die in diesem Abschnitt beschriebenen Ressourcendateien unterscheiden sich, als die Ressourcendateien im beschrieben [XAML-Ressourcen](../advanced/xaml-resources.md) und unterscheidet sich die eingebetteten oder verknüpften Ressourcen, die in beschriebenen [verwalten Ressourcen (.NET) ](/visualstudio/ide/managing-application-resources-dotnet).  
  
### <a name="configuring-resource-files"></a>Konfigurieren von Ressourcendateien  
 In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], eine Ressourcendatei handelt, eine Datei, die in enthalten ist ein [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] -Projekt als eine `Resource` Element.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Resource Include="ResourceFile.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  In [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], erstellen Sie eine Ressourcendatei durch Hinzufügen einer Datei zu einem Projekt und die Einstellung der `Build Action` zu `Resource`.  
  
 Wenn das Projekt erstellt wird, [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] wird die Ressource in die Assembly kompiliert.  
  
### <a name="using-resource-files"></a>Verwenden von Ressourcendateien  
 Um eine Ressourcendatei laden möchten, rufen Sie die <xref:System.Windows.Application.GetResourceStream%2A> Methode der <xref:System.Windows.Application> Klasse, und übergeben ein Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , der die gewünschte Ressourcendatei identifiziert. <xref:System.Windows.Application.GetResourceStream%2A> Gibt eine <xref:System.Windows.Resources.StreamResourceInfo> -Objekt, das die Ressourcendatei als macht eine <xref:System.IO.Stream> und den Inhaltstyp beschreibt.  
  
 Beispielsweise der folgende Code zeigt, wie mit <xref:System.Windows.Application.GetResourceStream%2A> zum Laden einer <xref:System.Windows.Controls.Page> Ressource Datei, und legen Sie es als den Inhalt des eine <xref:System.Windows.Controls.Frame> (`pageFrame`):  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 Beim Aufrufen <xref:System.Windows.Application.GetResourceStream%2A> erhalten Sie Zugriff auf die <xref:System.IO.Stream>, müssen Sie zum Ausführen der Konvertierung in den Typ der Eigenschaft, die Sie ihn festlegen zusätzlichen Aufwand. Stattdessen lassen Sie [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] kümmert sich öffnen und konvertieren die <xref:System.IO.Stream> durch Laden einer Ressourcendatei direkt in die Eigenschaft eines Typs, die mithilfe von Code.  
  
 Das folgende Beispiel zeigt, wie Sie laden eine <xref:System.Windows.Controls.Page> direkt in eine <xref:System.Windows.Controls.Frame> (`pageFrame`) mithilfe von Code.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 Das folgende Beispiel entspricht dem Markup des vorangehenden Beispiels.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a>Anwendungscodedateien als Ressourcendateien  
 Einen speziellen Satz von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] -Anwendungscodedateien können verwiesen werden, mithilfe von Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], einschließlich Windows, Seiten, Flussdokumenten und Ressourcenverzeichnissen. Sie können z. B. Festlegen der <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> Eigenschaft mit einem Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , die verweist auf das Fenster oder eine Seite, die beim Start einer Anwendung geladen werden sollen.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 Sie können dieses Vorgehen, wenn eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei befindet sich in einer [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] -Projekt als eine `Page` Element.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Page Include="MainWindow.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  In [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], Hinzufügen eines neuen <xref:System.Windows.Window>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.FlowDocument>, oder <xref:System.Windows.ResourceDictionary> zu einem Projekt der `Build Action` für das Markup wird standardmäßig auf `Page`.  
  
 Wenn ein Projekt mit `Page` -Elementen kompiliert wird, die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Elemente in das Binärformat konvertiert und in die zugehörige Assembly kompiliert werden. Folglich können diese Dateien auf die gleiche Weise verwendet werden wie typische Ressourcendateien.  
  
> [!NOTE]
>  Wenn eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei konfiguriert ist, als eine `Resource` Element aus, und verfügt nicht über eine CodeBehind-Datei, die die unformatierte [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] wird in eine Binärversion der Rohdaten-, anstatt eine Assembly kompiliert [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
<a name="Content_Files"></a>   
## <a name="content-files"></a>Inhaltsdateien  
 Ein *Inhaltsdatei* als lose Datei zusammen mit einer ausführbaren Assembly verteilt wird. Obwohl Assemblys nicht in eine Assembly kompiliert werden, werden sie mit Metadaten kompiliert, die eine Zuordnung mit den einzelnen Inhaltsdateien herstellen.  
  
 Verwenden Sie Inhaltsdateien, wenn die Anwendung einen speziellen Satz von Anwendungsdatendateien erfordert, die aktualisierbar sein soll, ohne dass die Assembly, die sie verwendet, neu kompiliert werden muss.  
  
### <a name="configuring-content-files"></a>Konfigurieren von Inhaltsdateien  
 Um ein Projekt eine Inhaltsdatei hinzuzufügen, muss eine Anwendungsdatendatei als einbezogen werden eine `Content` Element. Da eine Inhaltsdatei nicht direkt in die Assembly kompiliert wird, müssen Sie außerdem zum Festlegen der [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `CopyToOutputDirectory` Metadata-Element, um anzugeben, dass die Inhaltsdatei an einen Speicherort kopiert wird, der relativ zur erstellten Assembly ist. Wenn Sie die Ressource in den Buildausgabeordner kopiert werden soll, ein Projekt erstellt wird, Festlegen der `CopyToOutputDirectory` Metadata-Element mit der `Always` Wert. Andernfalls können Sie sicherstellen, dass nur die neueste Version der Ressource in den Buildausgabeordner, mithilfe kopiert wird der `PreserveNewest` Wert.  
  
 Im Folgenden wird eine Datei gezeigt, die als Inhaltsdatei konfiguriert ist und nur dann in den Buildausgabeordner kopiert wird, wenn dem Projekt eine neue Version der Ressource hinzugefügt wird.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Content Include="ContentFile.xaml">  
      <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
    </Content>  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  In [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], Sie erstellen eine Inhaltsdatei durch Hinzufügen einer Datei zu einem Projekt und die Einstellung der `Build Action` zu `Content`, und legen Sie dessen `Copy to Output Directory` zu `Copy always` (identisch mit `Always`) und `Copy if newer` (identisch mit `PreserveNewest`).  
  
 Wenn das Projekt erstellt wird, eine <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> Attribut wird in den Metadaten der Assembly für jede Inhaltsdatei kompiliert.  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 Der Wert des der <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> bedeutet, dass der Pfad zur Inhaltsdatei relativ zu dessen Position im Projekt. Z. B. wenn eine Datei mit Inhalte in einem Projektunterordner befand, die zusätzlichen Pfadinformationen integriert in die <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> Wert.  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 Die <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> Wert ist auch der Wert des Pfades zur Inhaltsdatei im Buildausgabeordner.  
  
### <a name="using-content-files"></a>Verwenden von Inhaltsdateien  
 Um eine Inhaltsdatei zu laden, rufen Sie die <xref:System.Windows.Application.GetContentStream%2A> -Methode der der <xref:System.Windows.Application> Klasse, und übergeben ein Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , der die gewünschte Inhaltsdatei identifiziert. <xref:System.Windows.Application.GetContentStream%2A> Gibt eine <xref:System.Windows.Resources.StreamResourceInfo> -Objekt, das die Inhaltsdatei als macht eine <xref:System.IO.Stream> und den Inhaltstyp beschreibt.  
  
 Beispielsweise der folgende Code zeigt, wie mit <xref:System.Windows.Application.GetContentStream%2A> zum Laden einer <xref:System.Windows.Controls.Page> Inhalt der Datei, und legen Sie ihn als Inhalt eine <xref:System.Windows.Controls.Frame> (`pageFrame`).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 Beim Aufrufen <xref:System.Windows.Application.GetContentStream%2A> erhalten Sie Zugriff auf die <xref:System.IO.Stream>, müssen Sie zum Ausführen der Konvertierung in den Typ der Eigenschaft, die Sie ihn festlegen zusätzlichen Aufwand. Stattdessen lassen Sie [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] kümmert sich öffnen und konvertieren die <xref:System.IO.Stream> durch Laden einer Ressourcendatei direkt in die Eigenschaft eines Typs, die mithilfe von Code.  
  
 Das folgende Beispiel zeigt, wie Sie laden eine <xref:System.Windows.Controls.Page> direkt in eine <xref:System.Windows.Controls.Frame> (`pageFrame`) mithilfe von Code.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 Das folgende Beispiel entspricht dem Markup des vorangehenden Beispiels.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>   
## <a name="site-of-origin-files"></a>Dateien der Ursprungssite  
 Ressourcendateien sind eine explizite Beziehung mit den Assemblys, die sie verteilt wurden, gemäß der <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>. Es kann jedoch vorkommen, dass Sie eine implizite oder nicht vorhandene Beziehung zwischen einer Assembly und einer Anwendungsdatendatei herstellen, u. a. in folgenden Fällen:  
  
-   Eine Datei existiert nicht zum Zeitpunkt der Kompilierung.  
  
-   Sie wissen bis zur Laufzeit nicht, welche Dateien von der Assembly benötigt werden.  
  
-   Sie möchten in der Lage sein, Dateien ohne Neukompilierung der Assembly, der sie zugeordnet sind, zu aktualisieren.  
  
-   Die Anwendung verwendet große Datendateien, z. B. Audio und Video. Diese sollen von Benutzern nur heruntergeladen werden, wenn sie dies wünschen.  
  
 Es ist möglich, diese Arten von Dateien mit herkömmlichen laden [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Authentifizierungsschemas, z. B. die Schemas "file:///" und "http://.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 Die Schemas „file:///“ und „http://“ erfordern jedoch volle Vertrauenswürdigkeit der Anwendung. Wenn Ihre Anwendung ist eine [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] aus dem Internet oder Intranet gestartet wurde und er Anforderungen nur den Satz von Berechtigungen, die für Anwendungen, die von diesen Orten aus gestartet zulässig sind lose Dateien können nur am Standort Ursprung (der Anwendung geladen werden Starten Sie Speicherort). Solche Dateien werden als bezeichnet *Ursprungssite* Dateien.  
  
 Dateien der Ursprungssite stellen für teilweise vertrauenswürdige Anwendungen die einzige Option dar, obwohl sie nicht auf letztere beschränkt sind. Anwendungen mit voller Vertrauenswürdigkeit müssen ggf. Anwendungsdatendateien laden, die sie zur Buildzeit nicht kennen. Obwohl Anwendungen mit voller Vertrauenswürdigkeit „file:///“ verwenden könnten, ist anzunehmen, dass die Anwendungsdatendateien im selben Ordner oder in einem Unterordner der Anwendungsassembly installiert werden. In einem solchen Fall gestaltet sich die Verwendung des Verweises auf die Ursprungssite einfacher als die Verwendung von „file:///“, da die Verwendung von „file:///“ von Ihnen erfordert, den vollständigen Pfad zur Datei auszuarbeiten.  
  
> [!NOTE]
>  Der Ursprungssite, die Dateien werden nicht zwischengespeichert, mit einem [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] auf einem Clientcomputer, Inhaltsdateien dagegen. Folglich werden sie nur heruntergeladen, wenn sie ausdrücklich angefordert werden. Wenn ein [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] Anwendung verfügt über große Mediendateien, die sie konfigurieren, wie die Dateien der Ursprungssite bedeutet, dass Start der originalanwendung viel schneller, und die Dateien werden nur bei Bedarf heruntergeladen.  
  
### <a name="configuring-site-of-origin-files"></a>Konfigurieren der Dateien der Ursprungssite  
 Wenn die Dateien der Ursprungssite zur Kompilierungszeit nicht vorhanden oder unbekannt sind, müssen Sie herkömmliche Bereitstellung verwenden Mechanismen zum gewährleisten, dass die erforderlichen Dateien verfügbar sind, zur Laufzeit, einschließlich der `XCopy` Befehlszeilenprogramm oder dem [!INCLUDE[TLA#tla_wininstall](../../../../includes/tlasharptla-wininstall-md.md)].  
  
 Wenn Sie zum Zeitpunkt der Kompilierung die Dateien kennen, die Sie gerne auf der Ursprungssite befinden würde, aber dennoch explizite Abhängigkeit vermeiden möchten, können Sie diese Dateien zum Hinzufügen einer [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] -Projekt als `None` Element. Wie bei Inhaltsdateien Sie müssen die [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `CopyToOutputDirectory` Attribut, um anzugeben, dass die Website Datei der Ursprungssite an einen Speicherort kopiert wird, der relativ zur erstellten Assembly ist entweder der `Always` Wert oder die `PreserveNewest` Wert.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <None Include="PageSiteOfOriginFile.xaml">  
    <CopyToOutputDirectory>Always</CopyToOutputDirectory>  
  </None>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  In [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], Sie erstellen eine der Ursprungsdatei durch Hinzufügen einer Datei zu einem Projekt und die Einstellung der `Build Action` zu `None`.  
  
 Wenn das Projekt erstellt wird, [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] die angegebenen Dateien in den Buildausgabeordner kopiert.  
  
### <a name="using-site-of-origin-files"></a>Verwenden der Dateien der Ursprungssite  
 Um einen Standort Datei der Ursprungssite zu laden, rufen Sie die <xref:System.Windows.Application.GetRemoteStream%2A> -Methode der der <xref:System.Windows.Application> Klasse, und übergeben ein Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , die die gewünschte Website Datei der Ursprungssite identifiziert. <xref:System.Windows.Application.GetRemoteStream%2A> Gibt eine <xref:System.Windows.Resources.StreamResourceInfo> -Objekt, das die Datei der Ursprungssite als Website bietet eine <xref:System.IO.Stream> und den Inhaltstyp beschreibt.  
  
 Beispielsweise der folgende Code zeigt, wie mit <xref:System.Windows.Application.GetRemoteStream%2A> zum Laden einer <xref:System.Windows.Controls.Page> Ursprungssite Datei, und legen Sie es als den Inhalt des eine <xref:System.Windows.Controls.Frame> (`pageFrame`).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 Beim Aufrufen <xref:System.Windows.Application.GetRemoteStream%2A> erhalten Sie Zugriff auf die <xref:System.IO.Stream>, müssen Sie zum Ausführen der Konvertierung in den Typ der Eigenschaft, die Sie ihn festlegen zusätzlichen Aufwand. Stattdessen lassen Sie [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] kümmert sich öffnen und konvertieren die <xref:System.IO.Stream> durch Laden einer Ressourcendatei direkt in die Eigenschaft eines Typs, die mithilfe von Code.  
  
 Das folgende Beispiel zeigt, wie Sie laden eine <xref:System.Windows.Controls.Page> direkt in eine <xref:System.Windows.Controls.Frame> (`pageFrame`) mithilfe von Code.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 Das folgende Beispiel entspricht dem Markup des vorangehenden Beispiels.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>   
## <a name="rebuilding-after-changing-build-type"></a>Neuerstellung nach Ändern des Buildtyps  
 Nachdem Sie den Buildtyp einer Anwendungsdatendatei geändert haben, müssen Sie die gesamte Anwendung neu erstellen, um zu gewährleisten, dass diese Änderungen übernommen werden. Wenn Sie nur die Anwendung erstellen, werden die Änderungen nicht übernommen.  
  
## <a name="see-also"></a>Siehe auch

- [Paket-URI in WPF](pack-uris-in-wpf.md)
