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
ms.openlocfilehash: 571b8f71ce233011ae6fc7a6d4d53c5029d27d69
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558264"
---
# <a name="wpf-application-resource-content-and-data-files"></a>WPF-Anwendungsressource, Inhalts- und Datendateien
[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] Anwendungen sind Dateien, die nicht ausführbare Daten, z. B. enthalten häufig abhängig [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], Bilder, Video und Audio. Windows Presentation Foundation (WPF) bietet spezielle Unterstützung zum Konfigurieren, identifizieren und Verwendung dieser Typen von Datendateien, die Datendateien der Anwendung aufgerufen werden. Diese Unterstützung bezieht sich auf einen bestimmten Satz von Anwendungsdatendateitypen, einschließlich:  
  
-   **Ressourcendateien**: Datendateien, die entweder eine ausführbare Datei oder Bibliothek kompiliert werden [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Assembly.  
  
-   **Inhaltsdateien**: Standalone-Datendateien, die über eine explizite Zuordnung zu einer ausführbaren Datei [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Assembly.  
  
-   **Dateien der Ursprungssite**: Standalone-Datendateien, die über keine Zuordnung zu einer ausführbaren Datei [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Assembly.  
  
 Ein wichtiger Unterschied zwischen diesen drei Dateitypen besteht darin, dass die Ressourcen- und Inhaltsdateien zur Buildzeit bekannt sind. Sie sind einer Assembly explizit bekannt. Für die Website der Origin-Dateien, jedoch eine Assembly kann haben keine Kenntnis davon überhaupt oder implizite Kenntnisse über eine Pack [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] Referenz; die Groß-/Kleinschreibung letzteren Fall besteht keine Garantie, dass die Website verwiesen wird, für die Ursprungsdatei tatsächlich vorhanden ist.  
  
 Um Anwendungsdatendateien verweisen, verwendet Windows Presentation Foundation (WPF) das Pack [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] Authentifizierungsschema, das ausführlich beschrieben wird [Paket-URIs in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)).  
  
 In diesem Thema wird beschrieben, wie Sie Anwendungsdatendateien konfigurieren und verwenden.  
  
  
<a name="Resource_Files"></a>   
## <a name="resource-files"></a>Ressourcendateien  
 Wenn eine Anwendungsdatendatei einer Anwendung stets zur Verfügung stehen muss, kann die Verfügbarkeit nur dadurch gewährleistet werden, dass die Datei in eine der ausführbaren Hauptassemblys einer Anwendung oder in eine der Assemblys kompiliert wird, auf die verwiesen wird. Diese Art von Anwendung-Datendatei wird als bezeichnet eine *Ressourcendatei*.  
  
 Verwenden Sie die Ressourcendateien in folgenden Fällen:  
  
-   Sie müssen den Inhalt der Ressourcendatei nicht aktualisieren, nachdem sie in eine Assembly kompiliert wurde.  
  
-   Sie möchten die Komplexität der Anwendungsverteilung vereinfachen, indem Sie die Anzahl von Dateiabhängigkeiten verringern.  
  
-   Muss Ihre Anwendungsdatendatei lokalisierbar sein (siehe [WPF-Globalisierung und Lokalisierung (Übersicht)](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)).  
  
> [!NOTE]
>  Die Ressourcendateien, die in diesem Abschnitt beschriebenen unterscheiden, als die Ressourcendateien im beschrieben [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md) und anders als die eingebetteten oder verknüpften Ressourcen, die in beschriebenen [verwalten Anwendung Ressourcen (.NET) ](http://msdn.microsoft.com/library/f2582734-8ada-4baa-8a7c-e2ef943ddf7e).  
  
### <a name="configuring-resource-files"></a>Konfigurieren von Ressourcendateien  
 In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], eine Ressourcendatei ist eine Datei, die in enthalten ist ein [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] -Projekt als eine `Resource` Element.  
  
```xml  
<Project "xmlns=http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Resource Include="ResourceFile.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  In [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], erstellen Sie eine Ressourcendatei durch Hinzufügen einer Datei auf ein Projekt und das Festlegen seiner `Build Action` auf `Resource`.  
  
 Wenn das Projekt erstellt wird, [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] wird die Ressource in die Assembly kompiliert.  
  
### <a name="using-resource-files"></a>Verwenden von Ressourcendateien  
 Um eine Ressourcendatei zu laden, rufen Sie die <xref:System.Windows.Application.GetResourceStream%2A> Methode der <xref:System.Windows.Application> Klasse, und übergeben ein Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , die die gewünschte Ressourcendatei identifiziert. <xref:System.Windows.Application.GetResourceStream%2A> Gibt eine <xref:System.Windows.Resources.StreamResourceInfo> -Objekt, das die Ressourcendatei als macht eine <xref:System.IO.Stream> und den Inhaltstyp beschreibt.  
  
 Als Beispiel der folgende Code wird gezeigt, wie mit <xref:System.Windows.Application.GetResourceStream%2A> beim Laden einer <xref:System.Windows.Controls.Page> Ressource Datei, und legen Sie es als Inhalt eine <xref:System.Windows.Controls.Frame> (`pageFrame`):  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 Beim Aufrufen <xref:System.Windows.Application.GetResourceStream%2A> ermöglicht Ihnen Zugriff auf die <xref:System.IO.Stream>, müssen Sie zum Ausführen von zusätzlichen Maßnahmen Konvertierung in den Typ der Eigenschaft, die Sie ihn festlegen. Stattdessen, lassen Sie [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] kümmern öffnen und zum Konvertieren von der <xref:System.IO.Stream> durch eine Ressourcendatei direkt in die Eigenschaft des Typs mithilfe von Code geladen.  
  
 Im folgende Beispiel wird gezeigt, wie beim Laden einer <xref:System.Windows.Controls.Page> direkt in eine <xref:System.Windows.Controls.Frame> (`pageFrame`) mithilfe von Code.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 Das folgende Beispiel entspricht dem Markup des vorangehenden Beispiels.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a>Anwendungscodedateien als Ressourcendateien  
 Ein speziellen Satz von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendungscodedateien mit Pack verwiesen werden können [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], einschließlich Windows, Seiten, Flow-Dokumente und Ressourcenwörterbücher. Sie können z. B. Festlegen der <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> Eigenschaft mit einem Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , die verweist auf das Fenster oder die Seite, die beim Starten einer Anwendung geladen werden sollen.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 Sie können dieses Vorgehen, wenn eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei befindet sich auf eine [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] -Projekt als eine `Page` Element.  
  
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
>  In [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], Sie fügen Sie einen neuen <xref:System.Windows.Window>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.FlowDocument>, oder <xref:System.Windows.ResourceDictionary> zu einem Projekt der `Build Action` Datei wird standardmäßig für das Markup auf `Page`.  
  
 Beim Erstellen eines Projekts mit `Page` Objekte wird kompiliert, die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Elemente in ein Binärformat konvertiert und in die zugehörige Assembly kompiliert werden. Folglich können diese Dateien auf die gleiche Weise verwendet werden wie typische Ressourcendateien.  
  
> [!NOTE]
>  Wenn eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei wird konfiguriert, als eine `Resource` -Element aus, und verfügt nicht über eine Code-Behind-Datei, die unformatierten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] wird in eine binäre Version von den unformatierten, sondern eine Assembly kompiliert [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
<a name="Content_Files"></a>   
## <a name="content-files"></a>Inhaltsdateien  
 Ein *Inhaltsdatei* als lose Datei zusammen mit der eine ausführbare Assembly verteilt wird. Obwohl Assemblys nicht in eine Assembly kompiliert werden, werden sie mit Metadaten kompiliert, die eine Zuordnung mit den einzelnen Inhaltsdateien herstellen.  
  
 Verwenden Sie Inhaltsdateien, wenn die Anwendung einen speziellen Satz von Anwendungsdatendateien erfordert, die aktualisierbar sein soll, ohne dass die Assembly, die sie verwendet, neu kompiliert werden muss.  
  
### <a name="configuring-content-files"></a>Konfigurieren von Inhaltsdateien  
 Um ein Projekt eine Datei Inhalte hinzuzufügen, muss eine Datendatei für die Anwendung als einbezogen werden ein `Content` Element. Da eine Inhaltsdatei nicht direkt in die Assembly kompiliert wird, müssen Sie außerdem festlegen der [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `CopyToOutputDirectory` Metadatenelement, um anzugeben, dass die Datei an einen Speicherort kopiert wird, relativ zu der erstellten Assembly ist. Wenn Sie die Ressource in den Buildausgabeordner jedes Mal kopiert werden soll, eines Projekts, Festlegen der `CopyToOutputDirectory` Metadatenelement mit der `Always` Wert. Andernfalls können Sie sicherstellen, dass nur die neueste Version der Ressource in den Buildausgabeordner, mithilfe kopiert wird der `PreserveNewest` Wert.  
  
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
>  In [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], Sie erstellen eine Inhaltsdatei durch Hinzufügen einer Datei auf ein Projekt und das Festlegen seiner `Build Action` auf `Content`, und legen Sie seine `Copy to Output Directory` auf `Copy always` (identisch mit `Always`) und `Copy if newer` (identisch mit `PreserveNewest`).  
  
 Wenn das Projekt erstellt wird, ein <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> Attribut wird in den Metadaten der Assembly für jede Inhaltsdatei kompiliert.  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 Der Wert, der die <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> bedeutet, dass der Pfad der Inhaltsdatei relativ zu ihrer Position im Projekt. Z. B. wenn eine Inhaltsdatei in einen Projektunterordner gespeichert wurde, die zusätzlichen Pfadinformationen würde in integriert werden, die <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> Wert.  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 Die <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> Wert ist auch der Wert des Pfads der Inhaltsdatei im Buildausgabeordner.  
  
### <a name="using-content-files"></a>Verwenden von Inhaltsdateien  
 Um eine Datei zu laden, rufen Sie die <xref:System.Windows.Application.GetContentStream%2A> Methode der <xref:System.Windows.Application> Klasse, und übergeben ein Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , die die gewünschte Inhaltsdatei identifiziert. <xref:System.Windows.Application.GetContentStream%2A> Gibt eine <xref:System.Windows.Resources.StreamResourceInfo> -Objekt, das die Inhaltsdatei als macht eine <xref:System.IO.Stream> und den Inhaltstyp beschreibt.  
  
 Als Beispiel der folgende Code wird gezeigt, wie mit <xref:System.Windows.Application.GetContentStream%2A> beim Laden einer <xref:System.Windows.Controls.Page> Inhalt der Datei, und legen Sie es als Inhalt eine <xref:System.Windows.Controls.Frame> (`pageFrame`).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 Beim Aufrufen <xref:System.Windows.Application.GetContentStream%2A> ermöglicht Ihnen Zugriff auf die <xref:System.IO.Stream>, müssen Sie zum Ausführen von zusätzlichen Maßnahmen Konvertierung in den Typ der Eigenschaft, die Sie ihn festlegen. Stattdessen, lassen Sie [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] kümmern öffnen und zum Konvertieren von der <xref:System.IO.Stream> durch eine Ressourcendatei direkt in die Eigenschaft des Typs mithilfe von Code geladen.  
  
 Im folgende Beispiel wird gezeigt, wie beim Laden einer <xref:System.Windows.Controls.Page> direkt in eine <xref:System.Windows.Controls.Frame> (`pageFrame`) mithilfe von Code.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 Das folgende Beispiel entspricht dem Markup des vorangehenden Beispiels.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>   
## <a name="site-of-origin-files"></a>Dateien der Ursprungssite  
 Ressourcendateien sind eine explizite Beziehung mit den Assemblys, die sie zusammen mit, verteilt wurden, gemäß der <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>. Es kann jedoch vorkommen, dass Sie eine implizite oder nicht vorhandene Beziehung zwischen einer Assembly und einer Anwendungsdatendatei herstellen, u. a. in folgenden Fällen:  
  
-   Eine Datei ist zur Kompilierzeit nicht vorhanden.  
  
-   Sie wissen bis zur Laufzeit nicht, welche Dateien von der Assembly benötigt werden.  
  
-   Sie möchten in der Lage sein, Dateien ohne Neukompilierung der Assembly, der sie zugeordnet sind, zu aktualisieren.  
  
-   Die Anwendung verwendet große Datendateien, z. B. Audio und Video. Diese sollen von Benutzern nur heruntergeladen werden, wenn sie dies wünschen.  
  
 Es ist möglich, laden diese Dateitypen mit herkömmlichen [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Authentifizierungsschemas, z. B. die Schemas file:/// und http://.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 Die Schemas „file:///“ und „http://“ erfordern jedoch volle Vertrauenswürdigkeit der Anwendung. Wenn Ihre Anwendung ist eine [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] , aus dem Internet oder Intranet gestartet wurde, und fordert nur den Satz von Berechtigungen, die für Anwendungen, die von diesen Standorten gestartet dürfen lose-Dateien können nur die Anwendung am Standort der Ursprung (geladen werden Starten Sie Speicherort). Solche Dateien werden als bezeichnet *Ursprungssite* Dateien.  
  
 Dateien der Ursprungssite stellen für teilweise vertrauenswürdige Anwendungen die einzige Option dar, obwohl sie nicht auf letztere beschränkt sind. Anwendungen mit voller Vertrauenswürdigkeit müssen ggf. Anwendungsdatendateien laden, die sie zur Buildzeit nicht kennen. Obwohl Anwendungen mit voller Vertrauenswürdigkeit „file:///“ verwenden könnten, ist anzunehmen, dass die Anwendungsdatendateien im selben Ordner oder in einem Unterordner der Anwendungsassembly installiert werden. In einem solchen Fall gestaltet sich die Verwendung des Verweises auf die Ursprungssite einfacher als die Verwendung von „file:///“, da die Verwendung von „file:///“ von Ihnen erfordert, den vollständigen Pfad zur Datei auszuarbeiten.  
  
> [!NOTE]
>  Dateien werden nicht zwischengespeichert, mit Ursprungssite ein [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] auf einem Clientcomputer, während die Inhaltsdateien werden. Folglich werden sie nur heruntergeladen, wenn sie ausdrücklich angefordert werden. Wenn ein [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] Anwendung hat große Mediendateien, die sie konfigurieren, wie die Dateien der Ursprungssite bedeutet, dass der Start der ersten Anwendung wesentlich schneller, und die Dateien werden nur bei Bedarf heruntergeladen.  
  
### <a name="configuring-site-of-origin-files"></a>Konfigurieren der Dateien der Ursprungssite  
 Wenn Ihr Ursprung Dateien zum Zeitpunkt der Kompilierung nicht vorhanden oder unbekannt sind, müssen Sie herkömmliche Bereitstellung verwenden-Mechanismen zur Gewährleistung der erforderlichen Dateien verfügbar sind, zur Laufzeit, einschließlich der Verwendung von entweder der `XCopy` Befehlszeilenprogramm oder dem [!INCLUDE[TLA#tla_wininstall](../../../../includes/tlasharptla-wininstall-md.md)].  
  
 Wenn Sie zum Zeitpunkt der Kompilierung die Dateien, die Sie möchten kennen, auf die Ursprungssite befinden würde, aber dennoch explizite Abhängigkeit vermeiden möchten, können Sie diese Dateien zum Hinzufügen einer [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] -Projekt als `None` Element. Wie bei Inhaltsdateien gespeichert, Sie festlegen müssen der [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `CopyToOutputDirectory` Attribut, um anzugeben, dass der Standort für die Ursprungsdatei an einen Speicherort, die relativ zu der erstellten Assembly ist kopiert wird, indem Sie entweder die `Always` Wert oder die `PreserveNewest` Wert.  
  
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
>  In [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], Sie erstellen einen Standort für die Ursprungsdatei durch Hinzufügen einer Datei auf ein Projekt und das Festlegen seiner `Build Action` auf `None`.  
  
 Wenn das Projekt erstellt wird, [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] kopiert die angegebenen Dateien in den Buildausgabeordner.  
  
### <a name="using-site-of-origin-files"></a>Verwenden der Dateien der Ursprungssite  
 Um einen Standort für die Ursprungsdatei zu laden, rufen Sie die <xref:System.Windows.Application.GetRemoteStream%2A> Methode der <xref:System.Windows.Application> Klasse, und übergeben ein Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , die die gewünschte Website für die Ursprungsdatei identifiziert. <xref:System.Windows.Application.GetRemoteStream%2A> Gibt eine <xref:System.Windows.Resources.StreamResourceInfo> -Objekt, das den Standort für die Ursprungsdatei als macht eine <xref:System.IO.Stream> und den Inhaltstyp beschreibt.  
  
 Als Beispiel der folgende Code wird gezeigt, wie mit <xref:System.Windows.Application.GetRemoteStream%2A> beim Laden einer <xref:System.Windows.Controls.Page> Ursprungssite Datei, und legen Sie es als Inhalt eine <xref:System.Windows.Controls.Frame> (`pageFrame`).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 Beim Aufrufen <xref:System.Windows.Application.GetRemoteStream%2A> ermöglicht Ihnen Zugriff auf die <xref:System.IO.Stream>, müssen Sie zum Ausführen von zusätzlichen Maßnahmen Konvertierung in den Typ der Eigenschaft, die Sie ihn festlegen. Stattdessen, lassen Sie [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] kümmern öffnen und zum Konvertieren von der <xref:System.IO.Stream> durch eine Ressourcendatei direkt in die Eigenschaft des Typs mithilfe von Code geladen.  
  
 Im folgende Beispiel wird gezeigt, wie beim Laden einer <xref:System.Windows.Controls.Page> direkt in eine <xref:System.Windows.Controls.Frame> (`pageFrame`) mithilfe von Code.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 Das folgende Beispiel entspricht dem Markup des vorangehenden Beispiels.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>   
## <a name="rebuilding-after-changing-build-type"></a>Neuerstellung nach Ändern des Buildtyps  
 Nachdem Sie den Buildtyp einer Anwendungsdatendatei geändert haben, müssen Sie die gesamte Anwendung neu erstellen, um zu gewährleisten, dass diese Änderungen übernommen werden. Wenn Sie nur die Anwendung erstellen, werden die Änderungen nicht übernommen.  
  
## <a name="see-also"></a>Siehe auch  
 [Paket-URI in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)
