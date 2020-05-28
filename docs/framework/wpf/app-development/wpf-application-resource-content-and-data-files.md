---
title: Anwendungs Ressourcen-, Inhalts-und Datendateien
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
ms.openlocfilehash: 19cb530fc5c70df3a7af7ac41836b3dfd97594e9
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144811"
---
# <a name="wpf-application-resource-content-and-data-files"></a>WPF-Anwendungsressource, Inhalts- und Datendateien
Microsoft Windows-Anwendungen sind häufig von Dateien abhängig, die nicht ausführbare Daten enthalten, z [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] . b. Bilder, Videos und Audiodaten. Windows Presentation Foundation (WPF) bietet spezielle Unterstützung für das konfigurieren, identifizieren und Verwenden dieser Daten Dateitypen, die als Anwendungs Datendateien bezeichnet werden. Diese Unterstützung bezieht sich auf einen bestimmten Satz von Anwendungsdatendateitypen, einschließlich:  
  
- **Ressourcen Dateien**: Datendateien, die entweder in eine ausführbare Datei oder in eine WPF-Bibliotheks Assembly kompiliert werden.  
  
- **Inhalts Dateien**: eigenständige Datendateien, die über eine explizite Zuordnung zu einer ausführbaren WPF-Assembly verfügen.  
  
- **Dateien der Ursprungs Site**: eigenständige Datendateien, die keiner ausführbaren WPF-Assembly zugeordnet sind.  
  
 Ein wichtiger Unterschied zwischen diesen drei Dateitypen besteht darin, dass die Ressourcen- und Inhaltsdateien zur Buildzeit bekannt sind. Sie sind einer Assembly explizit bekannt. Für Dateien der Ursprungs Site ist eine Assembly jedoch möglicherweise überhaupt nicht bekannt oder implizites Wissen durch einen URI-Verweis (Uniform Resource Identifier) des Pakets. bei letzterem gibt es keine Garantie dafür, dass die referenzierte Site der Ursprungs Datei tatsächlich vorhanden ist.  
  
 Um auf Anwendungs Datendateien zu verweisen, verwendet Windows Presentation Foundation (WPF) das Paket-URI-Schema (Uniform Resource Identifier), das unter [Paket-URIs in WPF](pack-uris-in-wpf.md)ausführlich beschrieben wird.  
  
 In diesem Thema wird beschrieben, wie Sie Anwendungsdatendateien konfigurieren und verwenden.  

<a name="Resource_Files"></a>
## <a name="resource-files"></a>Ressourcendateien  
 Wenn eine Anwendungsdatendatei einer Anwendung stets zur Verfügung stehen muss, kann die Verfügbarkeit nur dadurch gewährleistet werden, dass die Datei in eine der ausführbaren Hauptassemblys einer Anwendung oder in eine der Assemblys kompiliert wird, auf die verwiesen wird. Diese Art von Anwendungs Datendatei wird als *Ressourcen Datei*bezeichnet.  
  
 Verwenden Sie die Ressourcendateien in folgenden Fällen:  
  
- Sie müssen den Inhalt der Ressourcendatei nicht aktualisieren, nachdem sie in eine Assembly kompiliert wurde.  
  
- Sie möchten die Komplexität der Anwendungsverteilung vereinfachen, indem Sie die Anzahl von Dateiabhängigkeiten verringern.  
  
- Die Anwendungs Datendatei muss lokalisiert werden können (Weitere Informationen finden Sie unter [Übersicht über WPF-Globalisierung und-Lokalisierung](../advanced/wpf-globalization-and-localization-overview.md)).  
  
> [!NOTE]
> Die in diesem Abschnitt beschriebenen Ressourcen Dateien unterscheiden sich von den in [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md) beschriebenen Ressourcen Dateien und unterscheiden sich von den in [Verwalten von Anwendungs Ressourcen (.net)](/visualstudio/ide/managing-application-resources-dotnet)beschriebenen eingebetteten oder verknüpften Ressourcen.  
  
### <a name="configuring-resource-files"></a>Konfigurieren von Ressourcendateien  
 In WPF ist eine Ressourcen Datei eine Datei, die in einem Microsoft Build Engine (MSBuild)-Projekt als-Element enthalten ist `Resource` .  
  
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
> In Visual Studio erstellen Sie eine Ressourcen Datei, indem Sie einem Projekt eine Datei hinzufügen und `Build Action` auf festlegen `Resource` .  
  
 Wenn das Projekt erstellt wird, kompiliert MSBuild die Ressource in die Assembly.  
  
### <a name="using-resource-files"></a>Verwenden von Ressourcendateien  
 Wenn Sie eine Ressourcen Datei laden möchten, können Sie die- <xref:System.Windows.Application.GetResourceStream%2A> Methode der-Klasse aufzurufen <xref:System.Windows.Application> , indem Sie einen Paket-URI übergeben, der die gewünschte Ressourcen Datei identifiziert. <xref:System.Windows.Application.GetResourceStream%2A>Gibt ein <xref:System.Windows.Resources.StreamResourceInfo> -Objekt zurück, das die Ressourcen Datei als verfügbar macht <xref:System.IO.Stream> und den Inhaltstyp beschreibt.  
  
 Der folgende Code zeigt beispielsweise, wie <xref:System.Windows.Application.GetResourceStream%2A> Sie mit eine <xref:System.Windows.Controls.Page> Ressourcen Datei laden und als Inhalt einer <xref:System.Windows.Controls.Frame> () festlegen `pageFrame` :  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 Beim Aufrufen <xref:System.Windows.Application.GetResourceStream%2A> von haben Sie Zugriff auf das- <xref:System.IO.Stream> Objekt, das Sie zum Festlegen der Eigenschaft in den Typ der Eigenschaft, mit der Sie ihn festlegen, benötigen. Stattdessen können Sie das Öffnen und wandeln von WPF durchführen, <xref:System.IO.Stream> indem Sie eine Ressourcen Datei direkt in die-Eigenschaft eines Typs mithilfe von Code laden.  
  
 Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.Page> direkt in ein <xref:System.Windows.Controls.Frame> ( `pageFrame` ) mithilfe von Code geladen wird.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 Das folgende Beispiel entspricht dem Markup des vorangehenden Beispiels.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a>Anwendungscodedateien als Ressourcendateien  
 Ein spezieller Satz von WPF-Anwendungscode Dateien kann mithilfe von Paket-URIs referenziert werden, einschließlich Fenstern, Seiten, Fluss Dokumenten und Ressourcen Wörterbüchern. Beispielsweise können Sie die- <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> Eigenschaft mit einem Paket-URI festlegen, der auf das Fenster oder die Seite verweist, das Sie beim Starten einer Anwendung laden möchten.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 Dies ist möglich, wenn eine XAML-Datei in einem MSBuild-Projekt als- `Page` Element enthalten ist.  
  
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
> In Visual Studio fügen Sie einem Projekt ein neues-,-,-oder-Element hinzu <xref:System.Windows.Window> <xref:System.Windows.Navigation.NavigationWindow> , das-Element <xref:System.Windows.Controls.Page> <xref:System.Windows.Documents.FlowDocument> <xref:System.Windows.ResourceDictionary> `Build Action` für die Markup Datei wird standardmäßig auf eingestellt `Page` .  
  
 Wenn ein Projekt mit `Page` Elementen kompiliert wird, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] werden die Elemente in das Binärformat konvertiert und in die zugehörige Assembly kompiliert. Folglich können diese Dateien auf die gleiche Weise verwendet werden wie typische Ressourcendateien.  
  
> [!NOTE]
> Wenn eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei als `Resource` -Element konfiguriert ist und keine Code-Behind-Datei enthält, wird die Rohdaten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in eine Assembly anstatt in eine binäre Version der RAW-Datei kompiliert [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] .  
  
<a name="Content_Files"></a>
## <a name="content-files"></a>Inhaltsdateien  
 Eine *Inhalts Datei* wird neben einer ausführbaren Assembly als lose Datei verteilt. Obwohl Assemblys nicht in eine Assembly kompiliert werden, werden sie mit Metadaten kompiliert, die eine Zuordnung mit den einzelnen Inhaltsdateien herstellen.  
  
 Verwenden Sie Inhaltsdateien, wenn die Anwendung einen speziellen Satz von Anwendungsdatendateien erfordert, die aktualisierbar sein soll, ohne dass die Assembly, die sie verwendet, neu kompiliert werden muss.  
  
### <a name="configuring-content-files"></a>Konfigurieren von Inhaltsdateien  
 Wenn Sie einem Projekt eine Inhalts Datei hinzufügen möchten, muss eine Anwendungs Datendatei als Element eingeschlossen werden `Content` . Da eine Inhalts Datei nicht direkt in die Assembly kompiliert wird, müssen Sie außerdem das MSBuild- `CopyToOutputDirectory` Metadatenelement festlegen, um anzugeben, dass die Inhalts Datei an einen Speicherort kopiert wird, der relativ zur erstellten Assembly ist. Wenn Sie möchten, dass die Ressource bei jedem Erstellen eines Projekts in den Buildausgabeordner kopiert wird, legen Sie das `CopyToOutputDirectory` Metadatenelement mit dem `Always` Wert fest. Andernfalls können Sie mithilfe des-Werts sicherstellen, dass nur die neueste Version der Ressource in den Buildausgabeordner kopiert wird `PreserveNewest` .  
  
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
> In Visual Studio erstellen Sie eine Inhalts Datei, indem Sie einem Projekt eine Datei hinzufügen und `Build Action` auf festlegen `Content` , und legen Sie `Copy to Output Directory` auf fest `Copy always` (identisch mit `Always` ) und `Copy if newer` (identisch mit `PreserveNewest` ).  
  
 Wenn das Projekt erstellt wird, <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> wird ein Attribut in die Metadaten der Assembly für jede Inhalts Datei kompiliert.  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 Der Wert der <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> impliziert den Pfad zur Inhalts Datei relativ zur Position im Projekt. Wenn sich eine Inhalts Datei z. b. in einem Unterordner des Projekts befindet, werden die zusätzlichen Pfadinformationen in den <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> Wert eingefügt.  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 Der <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> Wert ist auch der Wert des Pfads zur Inhalts Datei im Buildausgabeordner.  
  
### <a name="using-content-files"></a>Verwenden von Inhaltsdateien  
 Wenn Sie eine Inhalts Datei laden möchten, können Sie die- <xref:System.Windows.Application.GetContentStream%2A> Methode der-Klasse aufzurufen <xref:System.Windows.Application> , indem Sie einen Paket-URI übergeben, der die gewünschte Inhalts Datei identifiziert. <xref:System.Windows.Application.GetContentStream%2A>Gibt ein <xref:System.Windows.Resources.StreamResourceInfo> -Objekt zurück, das die Inhalts Datei als verfügbar macht <xref:System.IO.Stream> und den Inhaltstyp beschreibt.  
  
 Im folgenden Codebeispiel wird gezeigt, wie verwendet wird, <xref:System.Windows.Application.GetContentStream%2A> um eine <xref:System.Windows.Controls.Page> Inhalts Datei zu laden und als Inhalt einer <xref:System.Windows.Controls.Frame> () festzulegen `pageFrame` .  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 Beim Aufrufen <xref:System.Windows.Application.GetContentStream%2A> von haben Sie Zugriff auf das- <xref:System.IO.Stream> Objekt, das Sie zum Festlegen der Eigenschaft in den Typ der Eigenschaft, mit der Sie ihn festlegen, benötigen. Stattdessen können Sie das Öffnen und wandeln von WPF durchführen, <xref:System.IO.Stream> indem Sie eine Ressourcen Datei direkt in die-Eigenschaft eines Typs mithilfe von Code laden.  
  
 Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.Page> direkt in ein <xref:System.Windows.Controls.Frame> ( `pageFrame` ) mithilfe von Code geladen wird.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 Das folgende Beispiel entspricht dem Markup des vorangehenden Beispiels.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>
## <a name="site-of-origin-files"></a>Dateien der Ursprungssite  
 Ressourcen Dateien haben eine explizite Beziehung zu den Assemblys, die Sie zusammen mit den von definierten Assemblys verteilen <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> . Es kann jedoch vorkommen, dass Sie eine implizite oder nicht vorhandene Beziehung zwischen einer Assembly und einer Anwendungsdatendatei herstellen, u. a. in folgenden Fällen:  
  
- Zum Zeitpunkt der Kompilierung ist keine Datei vorhanden.  
  
- Sie wissen bis zur Laufzeit nicht, welche Dateien von der Assembly benötigt werden.  
  
- Sie möchten in der Lage sein, Dateien ohne Neukompilierung der Assembly, der sie zugeordnet sind, zu aktualisieren.  
  
- Die Anwendung verwendet große Datendateien, z. B. Audio und Video. Diese sollen von Benutzern nur heruntergeladen werden, wenn sie dies wünschen.  
  
 Es ist möglich, diese Dateitypen mithilfe herkömmlicher URI-Schemas (z. b `file:///` . die Schemas und) zu laden `http://` .  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 Die `file:///` -und- `http://` Schemas erfordern jedoch, dass Ihre Anwendung über volle Vertrauenswürdigkeit verfügt. Wenn es sich bei Ihrer Anwendung um eine XAML-Browser Anwendung (XBAP) handelt, die über das Internet oder Intranet gestartet wurde, und nur den Berechtigungs Satz anfordert, der für Anwendungen zulässig ist, die von diesen Speicherorten aus gestartet werden, können lose Dateien nur aus der Ursprungs Site der Anwendung (Start Speicherort) geladen werden. Solche Dateien werden als Dateien *der Ursprungs Site* bezeichnet.  
  
 Dateien der Ursprungssite stellen für teilweise vertrauenswürdige Anwendungen die einzige Option dar, obwohl sie nicht auf letztere beschränkt sind. Anwendungen mit voller Vertrauenswürdigkeit müssen ggf. Anwendungsdatendateien laden, die sie zur Buildzeit nicht kennen. Obwohl Anwendungen mit voller Vertrauenswürdigkeit „file:///“ verwenden könnten, ist anzunehmen, dass die Anwendungsdatendateien im selben Ordner oder in einem Unterordner der Anwendungsassembly installiert werden. In einem solchen Fall gestaltet sich die Verwendung des Verweises auf die Ursprungssite einfacher als die Verwendung von „file:///“, da die Verwendung von „file:///“ von Ihnen erfordert, den vollständigen Pfad zur Datei auszuarbeiten.  
  
> [!NOTE]
> Dateien der Ursprungs Site werden nicht mit einer XAML-Browser Anwendung (XBAP) auf einem Client Computer zwischengespeichert, während Inhalts Dateien gleich sind. Folglich werden sie nur heruntergeladen, wenn sie ausdrücklich angefordert werden. Wenn eine XBAP-Anwendung (XAML-Browser Anwendung) große Mediendateien enthält und diese als Dateien der Ursprungs Site konfiguriert werden, ist der erste Anwendungsstart wesentlich schneller, und die Dateien werden nur bei Bedarf heruntergeladen.  
  
### <a name="configuring-site-of-origin-files"></a>Konfigurieren der Dateien der Ursprungssite  
 Wenn die Dateien der Ursprungs Site zum Zeitpunkt der Kompilierung nicht vorhanden oder unbekannt sind, müssen Sie herkömmliche Bereitstellungs Mechanismen verwenden, um sicherzustellen, dass die erforderlichen Dateien zur Laufzeit verfügbar sind, einschließlich der Verwendung des `XCopy` Befehlszeilen Programms oder des Microsoft Windows Installer.  
  
 Wenn Sie zum Zeitpunkt der Kompilierung wissen, dass Sie sich auf der Ursprungs Site befinden möchten, aber trotzdem eine explizite Abhängigkeit vermeiden möchten, können Sie diese Dateien einem MSBuild-Projekt als Element hinzufügen `None` . Wie bei Inhalts Dateien müssen Sie das MSBuild-Attribut festlegen, `CopyToOutputDirectory` um anzugeben, dass die Ursprungs Site Datei an einen Speicherort kopiert wird, der relativ zur erstellten Assembly ist, indem Sie entweder den `Always` Wert oder den `PreserveNewest` Wert angeben.  
  
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
> In Visual Studio erstellen Sie eine Website der Ursprungs Datei, indem Sie einem Projekt eine Datei hinzufügen und `Build Action` auf festlegen `None` .  
  
 Wenn das Projekt erstellt wird, kopiert MSBuild die angegebenen Dateien in den Buildausgabeordner.  
  
### <a name="using-site-of-origin-files"></a>Verwenden der Dateien der Ursprungssite  
 Zum Laden einer Ursprungs Site Datei können Sie die- <xref:System.Windows.Application.GetRemoteStream%2A> Methode der-Klasse aufzurufen <xref:System.Windows.Application> , indem Sie einen Paket-URI übergeben, der die gewünschte Ursprungs Site Datei identifiziert. <xref:System.Windows.Application.GetRemoteStream%2A>Gibt ein <xref:System.Windows.Resources.StreamResourceInfo> -Objekt zurück, das die Datei der Ursprungs Site als bereitstellt <xref:System.IO.Stream> und den Inhaltstyp beschreibt.  
  
 Der folgende Code zeigt beispielsweise, wie verwendet wird, <xref:System.Windows.Application.GetRemoteStream%2A> um eine <xref:System.Windows.Controls.Page> Datei der Ursprungs Site zu laden und als Inhalt eines <xref:System.Windows.Controls.Frame> () festzulegen `pageFrame` .  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 Beim Aufrufen <xref:System.Windows.Application.GetRemoteStream%2A> von haben Sie Zugriff auf das- <xref:System.IO.Stream> Objekt, das Sie zum Festlegen der Eigenschaft in den Typ der Eigenschaft, mit der Sie ihn festlegen, benötigen. Stattdessen können Sie das Öffnen und wandeln von WPF durchführen, <xref:System.IO.Stream> indem Sie eine Ressourcen Datei direkt in die-Eigenschaft eines Typs mithilfe von Code laden.  
  
 Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.Page> direkt in ein <xref:System.Windows.Controls.Frame> ( `pageFrame` ) mithilfe von Code geladen wird.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 Das folgende Beispiel entspricht dem Markup des vorangehenden Beispiels.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>
## <a name="rebuilding-after-changing-build-type"></a>Neuerstellung nach Ändern des Buildtyps  
 Nachdem Sie den Buildtyp einer Anwendungsdatendatei geändert haben, müssen Sie die gesamte Anwendung neu erstellen, um zu gewährleisten, dass diese Änderungen übernommen werden. Wenn Sie nur die Anwendung erstellen, werden die Änderungen nicht übernommen.  
  
## <a name="see-also"></a>Siehe auch

- [Paket-URI in WPF](pack-uris-in-wpf.md)
