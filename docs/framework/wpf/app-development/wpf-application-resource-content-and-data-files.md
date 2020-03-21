---
title: Anwendungsressourcen, Inhalte und Datendateien
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
ms.openlocfilehash: f17898972eeef66447060db32bae5fae377b710e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186203"
---
# <a name="wpf-application-resource-content-and-data-files"></a>WPF-Anwendungsressource, Inhalts- und Datendateien
Microsoft Windows-Anwendungen hängen häufig von Dateien ab, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]die nicht ausführbare Daten enthalten, z. B. Bilder, Videos und Audiodateien. Windows Presentation Foundation (WPF) bietet spezielle Unterstützung für die Konfiguration, Identifizierung und Verwendung dieser Arten von Datendateien, die als Anwendungsdatendateien bezeichnet werden. Diese Unterstützung bezieht sich auf einen bestimmten Satz von Anwendungsdatendateitypen, einschließlich:  
  
- **Ressourcendateien**: Datendateien, die entweder in eine ausführbare Datei oder eine Bibliotheks-WPF-Assembly kompiliert werden.  
  
- **Inhaltsdateien**: Eigenständige Datendateien, die eine explizite Zuordnung zu einer ausführbaren WPF-Assembly aufweisen.  
  
- **Site of Origin Files**: Eigenständige Datendateien, die keine Zuordnung zu einer ausführbaren WPF-Assembly haben.  
  
 Ein wichtiger Unterschied zwischen diesen drei Dateitypen besteht darin, dass die Ressourcen- und Inhaltsdateien zur Buildzeit bekannt sind. Sie sind einer Assembly explizit bekannt. Bei Ursprungsursprungsdateien kann eine Assembly jedoch überhaupt keine Kenntnis davon oder implizite Kenntnisse über einen URI-Verweis (Uniform Resource Identifier) (Uniform Resource Identifier) haben. im letzteren Fall gibt es keine Garantie dafür, dass die referenzierte Ursprungsdatei tatsächlich existiert.  
  
 Um auf Anwendungsdatendateien zu verweisen, verwendet Windows Presentation Foundation (WPF) das Pack Uniform Resource Identifier (URI)-Schema, das in [Pack-URIs in WPF](pack-uris-in-wpf.md)ausführlich beschrieben wird.  
  
 In diesem Thema wird beschrieben, wie Sie Anwendungsdatendateien konfigurieren und verwenden.  

<a name="Resource_Files"></a>
## <a name="resource-files"></a>Ressourcendateien  
 Wenn eine Anwendungsdatendatei einer Anwendung stets zur Verfügung stehen muss, kann die Verfügbarkeit nur dadurch gewährleistet werden, dass die Datei in eine der ausführbaren Hauptassemblys einer Anwendung oder in eine der Assemblys kompiliert wird, auf die verwiesen wird. Dieser Typ der Anwendungsdatendatei wird als *Ressourcendatei*bezeichnet.  
  
 Verwenden Sie die Ressourcendateien in folgenden Fällen:  
  
- Sie müssen den Inhalt der Ressourcendatei nicht aktualisieren, nachdem sie in eine Assembly kompiliert wurde.  
  
- Sie möchten die Komplexität der Anwendungsverteilung vereinfachen, indem Sie die Anzahl von Dateiabhängigkeiten verringern.  
  
- Ihre Anwendungsdatendatei muss lokalisierbar sein (siehe [WPF-Globalisierungs- und Lokalisierungsübersicht](../advanced/wpf-globalization-and-localization-overview.md)).  
  
> [!NOTE]
> Die in diesem Abschnitt beschriebenen Ressourcendateien unterscheiden sich von den in [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md) beschriebenen Ressourcendateien und unterscheiden sich von den eingebetteten oder verknüpften Ressourcen, die unter Verwalten von [Anwendungsressourcen (.NET)](/visualstudio/ide/managing-application-resources-dotnet)beschrieben werden.  
  
### <a name="configuring-resource-files"></a>Konfigurieren von Ressourcendateien  
 In WPF ist eine Ressourcendatei eine Datei, die in einem Microsoft `Resource` Buildmodul (MSBuild)-Projekt als Element enthalten ist.  
  
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
> In Visual Studio erstellen Sie eine Ressourcendatei, indem Sie `Build Action` `Resource`einem Projekt eine Datei hinzufügen und deren auf festlegen.  
  
 Wenn das Projekt erstellt wird, kompiliert MSBuild die Ressource in die Assembly.  
  
### <a name="using-resource-files"></a>Verwenden von Ressourcendateien  
 Um eine Ressourcendatei zu laden, können Sie die <xref:System.Windows.Application.GetResourceStream%2A> Methode der <xref:System.Windows.Application> Klasse aufrufen und einen Pack-URI übergeben, der die gewünschte Ressourcendatei identifiziert. <xref:System.Windows.Application.GetResourceStream%2A>gibt <xref:System.Windows.Resources.StreamResourceInfo> ein Objekt zurück, das die <xref:System.IO.Stream> Ressourcendatei als a verfügbar macht und ihren Inhaltstyp beschreibt.  
  
 Der folgende Code zeigt beispielsweise, <xref:System.Windows.Application.GetResourceStream%2A> wie Sie <xref:System.Windows.Controls.Page> eine Ressourcendatei laden und <xref:System.Windows.Controls.Frame> als`pageFrame`Inhalt eines ( ) festlegen.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 Während <xref:System.Windows.Application.GetResourceStream%2A> Sie anrufen, <xref:System.IO.Stream>haben Sie Zugriff auf die , die Sie benötigen, um die zusätzliche Arbeit des Konvertierens in den Typ der Eigenschaft auszuführen, mit der Sie sie festlegen. Stattdessen können Sie WPF das Öffnen und <xref:System.IO.Stream> Konvertieren der übernehmen, indem Sie eine Ressourcendatei direkt mithilfe von Code in die Eigenschaft eines Typs laden.  
  
 Das folgende Beispiel zeigt, <xref:System.Windows.Controls.Page> wie <xref:System.Windows.Controls.Frame> ein`pageFrame`direkt in ein ( ) mit Code geladen wird.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 Das folgende Beispiel entspricht dem Markup des vorangehenden Beispiels.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a>Anwendungscodedateien als Ressourcendateien  
 Auf einen speziellen Satz von WPF-Anwendungscodedateien kann mithilfe von Pack-URIs verwiesen werden, einschließlich Fenstern, Seiten, Flussdokumenten und Ressourcenwörterbüchern. Sie können die Eigenschaft <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> beispielsweise mit einem Pack-URI festlegen, der auf das Fenster oder die Seite verweist, das Sie laden möchten, wenn eine Anwendung gestartet wird.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 Sie können dies tun, wenn eine XAML-Datei `Page` in einem MSBuild-Projekt als Element enthalten ist.  
  
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
> In Visual Studio fügen <xref:System.Windows.Window>Sie <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Page>ein <xref:System.Windows.Documents.FlowDocument>neues <xref:System.Windows.ResourceDictionary> , , `Build Action` , oder zu einem `Page`Projekt hinzu, die für die Markupdatei wird standardmäßig auf .  
  
 Wenn ein `Page` Projekt mit Elementen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] kompiliert wird, werden die Elemente in das Binärformat konvertiert und in die zugehörige Assembly kompiliert. Folglich können diese Dateien auf die gleiche Weise verwendet werden wie typische Ressourcendateien.  
  
> [!NOTE]
> Wenn [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] eine Datei als `Resource` Element konfiguriert ist und keine CodeBehind-Datei [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] enthält, wird die Rohdatei in eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]Assembly und nicht in eine Binärversion der raw kompiliert.  
  
<a name="Content_Files"></a>
## <a name="content-files"></a>Inhaltsdateien  
 Eine *Inhaltsdatei* wird als lose Datei neben einer ausführbaren Assembly verteilt. Obwohl Assemblys nicht in eine Assembly kompiliert werden, werden sie mit Metadaten kompiliert, die eine Zuordnung mit den einzelnen Inhaltsdateien herstellen.  
  
 Verwenden Sie Inhaltsdateien, wenn die Anwendung einen speziellen Satz von Anwendungsdatendateien erfordert, die aktualisierbar sein soll, ohne dass die Assembly, die sie verwendet, neu kompiliert werden muss.  
  
### <a name="configuring-content-files"></a>Konfigurieren von Inhaltsdateien  
 Um einem Projekt eine Inhaltsdatei hinzuzufügen, muss eine `Content` Anwendungsdatendatei als Element enthalten sein. Da eine Inhaltsdatei nicht direkt in die Assembly kompiliert wird, müssen Sie außerdem das MSBuild-Metadatenelement `CopyToOutputDirectory` festlegen, um anzugeben, dass die Inhaltsdatei an einen Speicherort kopiert wird, der relativ zur erstellten Assembly ist. Wenn die Ressource jedes Mal, wenn ein Projekt erstellt wird, in `CopyToOutputDirectory` den Buildausgabeordner kopiert werden soll, legen Sie das Metadatenelement mit dem `Always` Wert fest. Andernfalls können Sie sicherstellen, dass nur die neueste Version der Ressource `PreserveNewest` mithilfe des Werts in den Buildausgabeordner kopiert wird.  
  
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
> In Visual Studio erstellen Sie eine Inhaltsdatei, indem Sie `Build Action` `Content`einem Projekt `Copy to Output Directory` eine `Copy always` Datei `Always`hinzufügen `Copy if newer` und auf `PreserveNewest`festlegen und auf (gleich ) und (gleich ) festlegen.  
  
 Wenn das Projekt erstellt <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> wird, wird ein Attribut in die Metadaten der Assembly für jede Inhaltsdatei kompiliert.  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 Der Wert <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> des impliziert den Pfad zur Inhaltsdatei relativ zu seiner Position im Projekt. Wenn sich z. B. eine Inhaltsdatei in einem Projektunterordner befindet, werden die zusätzlichen Pfadinformationen in den <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> Wert integriert.  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 Der <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> Wert ist auch der Wert des Pfads zur Inhaltsdatei im Buildausgabeordner.  
  
### <a name="using-content-files"></a>Verwenden von Inhaltsdateien  
 Um eine Inhaltsdatei zu laden, können Sie die <xref:System.Windows.Application.GetContentStream%2A> Methode der <xref:System.Windows.Application> Klasse aufrufen und einen Pack-URI übergeben, der die gewünschte Inhaltsdatei identifiziert. <xref:System.Windows.Application.GetContentStream%2A>gibt <xref:System.Windows.Resources.StreamResourceInfo> ein Objekt zurück, das die <xref:System.IO.Stream> Inhaltsdatei als a verfügbar macht und ihren Inhaltstyp beschreibt.  
  
 Der folgende Code zeigt beispielsweise, <xref:System.Windows.Application.GetContentStream%2A> wie Sie <xref:System.Windows.Controls.Page> eine Inhaltsdatei laden und <xref:System.Windows.Controls.Frame> als`pageFrame`Inhalt eines ( . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 Während <xref:System.Windows.Application.GetContentStream%2A> Sie anrufen, <xref:System.IO.Stream>haben Sie Zugriff auf die , die Sie benötigen, um die zusätzliche Arbeit des Konvertierens in den Typ der Eigenschaft auszuführen, mit der Sie sie festlegen. Stattdessen können Sie WPF das Öffnen und <xref:System.IO.Stream> Konvertieren der übernehmen, indem Sie eine Ressourcendatei direkt mithilfe von Code in die Eigenschaft eines Typs laden.  
  
 Das folgende Beispiel zeigt, <xref:System.Windows.Controls.Page> wie <xref:System.Windows.Controls.Frame> ein`pageFrame`direkt in ein ( ) mit Code geladen wird.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 Das folgende Beispiel entspricht dem Markup des vorangehenden Beispiels.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>
## <a name="site-of-origin-files"></a>Dateien der Ursprungssite  
 Ressourcendateien haben eine explizite Beziehung zu den Assemblys, <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>mit denen sie verteilt werden, wie im definiert. Es kann jedoch vorkommen, dass Sie eine implizite oder nicht vorhandene Beziehung zwischen einer Assembly und einer Anwendungsdatendatei herstellen, u. a. in folgenden Fällen:  
  
- Zum Zeitpunkt der Kompilierung ist keine Datei vorhanden.  
  
- Sie wissen bis zur Laufzeit nicht, welche Dateien von der Assembly benötigt werden.  
  
- Sie möchten in der Lage sein, Dateien ohne Neukompilierung der Assembly, der sie zugeordnet sind, zu aktualisieren.  
  
- Die Anwendung verwendet große Datendateien, z. B. Audio und Video. Diese sollen von Benutzern nur heruntergeladen werden, wenn sie dies wünschen.  
  
 Es ist möglich, diese Dateitypen mithilfe herkömmlicher URI-Schemas wie file:/// und http://-Schemas zu laden.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 Die Schemas „file:///“ und „http://“ erfordern jedoch volle Vertrauenswürdigkeit der Anwendung. Wenn es sich bei Ihrer Anwendung um eine XAML-Browseranwendung (XBAP) handelt, die aus dem Internet oder Intranet gestartet wurde, und sie nur den Satz von Berechtigungen anfordert, die für Anwendungen zulässig sind, die von diesen Speicherorten gestartet werden, können lose Dateien nur aus dem Herkunftsort der Anwendung (Startort). Solche Dateien werden als *Standort der Herkunft* Dateien bekannt.  
  
 Dateien der Ursprungssite stellen für teilweise vertrauenswürdige Anwendungen die einzige Option dar, obwohl sie nicht auf letztere beschränkt sind. Anwendungen mit voller Vertrauenswürdigkeit müssen ggf. Anwendungsdatendateien laden, die sie zur Buildzeit nicht kennen. Obwohl Anwendungen mit voller Vertrauenswürdigkeit „file:///“ verwenden könnten, ist anzunehmen, dass die Anwendungsdatendateien im selben Ordner oder in einem Unterordner der Anwendungsassembly installiert werden. In einem solchen Fall gestaltet sich die Verwendung des Verweises auf die Ursprungssite einfacher als die Verwendung von „file:///“, da die Verwendung von „file:///“ von Ihnen erfordert, den vollständigen Pfad zur Datei auszuarbeiten.  
  
> [!NOTE]
> Ursprungsursprungsdateien werden nicht mit einer XAML-Browseranwendung (XBAP) auf einem Clientcomputer zwischengespeichert, während Inhaltsdateien vorhanden sind. Folglich werden sie nur heruntergeladen, wenn sie ausdrücklich angefordert werden. Wenn eine XBAP-Anwendung (XAML-Browseranwendung) über große Mediendateien verfügt, bedeutet die Konfiguration als Ursprungsstandort, dass der anfängliche Anwendungsstart viel schneller erfolgt und die Dateien nur bei Bedarf heruntergeladen werden.  
  
### <a name="configuring-site-of-origin-files"></a>Konfigurieren der Dateien der Ursprungssite  
 Wenn Ihre Ursprungsstandortdateien zum Zeitpunkt der Kompilierung nicht vorhanden oder unbekannt sind, müssen Sie herkömmliche Bereitstellungsmechanismen `XCopy` verwenden, um sicherzustellen, dass die erforderlichen Dateien zur Laufzeit verfügbar sind, einschließlich der Verwendung des Befehlszeilenprogramms oder des Microsoft Windows Installers.  
  
 Wenn Sie zum Zeitpunkt der Kompilierung die Dateien kennen, die Sie am Ursprungsort befinden möchten, aber dennoch eine explizite Abhängigkeit vermeiden möchten, können Sie diese Dateien einem MSBuild-Projekt als `None` Element hinzufügen. Wie bei Inhaltsdateien müssen Sie das `CopyToOutputDirectory` MSBuild-Attribut festlegen, um anzugeben, dass die Ursprungsdatei an einen Speicherort `Always` kopiert wird, der relativ zur erstellten Assembly ist, indem Sie entweder den Wert oder den `PreserveNewest` Wert angeben.  
  
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
> In Visual Studio erstellen Sie eine Ursprungsdatei, indem Sie einem `Build Action` `None`Projekt eine Datei hinzufügen und deren auf festlegen.  
  
 Wenn das Projekt erstellt wird, kopiert MSBuild die angegebenen Dateien in den Buildausgabeordner.  
  
### <a name="using-site-of-origin-files"></a>Verwenden der Dateien der Ursprungssite  
 Um eine Ursprungsdatei zu laden, <xref:System.Windows.Application.GetRemoteStream%2A> können Sie <xref:System.Windows.Application> die Methode der Klasse aufrufen und einen Pack-URI übergeben, der die gewünschte Ursprungsdatei identifiziert. <xref:System.Windows.Application.GetRemoteStream%2A>gibt <xref:System.Windows.Resources.StreamResourceInfo> ein Objekt zurück, das die Ursprungsdatei als eine <xref:System.IO.Stream> verfügbar macht und deren Inhaltstyp beschreibt.  
  
 Der folgende Code zeigt beispielsweise, <xref:System.Windows.Application.GetRemoteStream%2A> wie Sie <xref:System.Windows.Controls.Page> eine Ursprungsdatei laden und als <xref:System.Windows.Controls.Frame> Inhalt`pageFrame`einer ( .  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 Während <xref:System.Windows.Application.GetRemoteStream%2A> Sie anrufen, <xref:System.IO.Stream>haben Sie Zugriff auf die , die Sie benötigen, um die zusätzliche Arbeit des Konvertierens in den Typ der Eigenschaft auszuführen, mit der Sie sie festlegen. Stattdessen können Sie WPF das Öffnen und <xref:System.IO.Stream> Konvertieren der übernehmen, indem Sie eine Ressourcendatei direkt mithilfe von Code in die Eigenschaft eines Typs laden.  
  
 Das folgende Beispiel zeigt, <xref:System.Windows.Controls.Page> wie <xref:System.Windows.Controls.Frame> ein`pageFrame`direkt in ein ( ) mit Code geladen wird.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 Das folgende Beispiel entspricht dem Markup des vorangehenden Beispiels.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>
## <a name="rebuilding-after-changing-build-type"></a>Neuerstellung nach Ändern des Buildtyps  
 Nachdem Sie den Buildtyp einer Anwendungsdatendatei geändert haben, müssen Sie die gesamte Anwendung neu erstellen, um zu gewährleisten, dass diese Änderungen übernommen werden. Wenn Sie nur die Anwendung erstellen, werden die Änderungen nicht übernommen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Paket-URI in WPF](pack-uris-in-wpf.md)
