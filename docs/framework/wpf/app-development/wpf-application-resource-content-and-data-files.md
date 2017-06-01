---
title: "WPF-Anwendungsressource, Inhalts- und Datendateien | Microsoft Docs"
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
  - "Anwendungsentwicklung [WPF], Dateien"
  - "Anwendungsverwaltung [WPF]"
  - "Inhaltsdateien [WPF]"
  - "Eingebettete Ressourcen [WPF]"
  - "Dateien [WPF]"
  - "Lose Ressourcen [WPF]"
  - "Verweisen auf Anwendungsdateien [WPF]"
  - "Remotedateien [WPF]"
  - "Ressourcendateien [WPF]"
  - "Dateien der Ursprungssite [WPF]"
  - "WPF-Anwendung, Dateien"
ms.assetid: 7ad2943b-3961-41d3-8fc6-1582d43f5d99
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# WPF-Anwendungsressource, Inhalts- und Datendateien
[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)]\-Anwendungen hängen oftmals von Dateien ab, die nicht ausführbare Daten enthalten, z. B. [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Bilder, \-Video und \-Audio.  [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] bietet spezielle Unterstützung zum Konfigurieren, Identifizieren und Verwenden dieser Datendateitypen, die als Anwendungsdatendateien bezeichnet werden.  Diese Unterstützung bezieht sich auf einen bestimmten Satz von Anwendungsdatendateitypen, einschließlich:  
  
-   **Ressourcendateien**: Datendateien, die entweder in eine ausführbare oder in eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Bibliotheksassembly kompiliert werden.  
  
-   **Inhaltsdateien**: Eigenständige Datendateien, die einer ausführbaren [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Assembly explizit zugeordnet sind.  
  
-   **Dateien der Ursprungssite**: Eigenständige Datendateien, die keiner ausführbaren [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Assembly zugeordnet sind.  
  
 Ein wichtiger Unterschied zwischen diesen drei Dateitypen besteht darin, dass die Ressourcen\- und Inhaltsdateien zur Buildzeit bekannt sind. Sie sind einer Assembly explizit bekannt.  Dateien der Ursprungssite sind einer Assembly u. U. überhaupt nicht oder lediglich implizit über den Verweis auf einen Paket\-[!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] bekannt. Im letzteren Fall kann nicht garantiert werden, dass die Datei der Ursprungssite, auf die verwiesen wurde, tatsächlich vorhanden ist.  
  
 Wenn Sie auf Anwendungsdatendateien verweisen möchten, verwendet [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] das Paket\-[!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]\-Schema, das unter [Paket\-URI in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md) ausführlich beschrieben wird.  
  
 In diesem Thema wird beschrieben, wie Sie Anwendungsdatendateien konfigurieren und verwenden.  
  
   
  
<a name="Resource_Files"></a>   
## Ressourcendateien  
 Wenn eine Anwendungsdatendatei einer Anwendung stets zur Verfügung stehen muss, kann die Verfügbarkeit nur dadurch gewährleistet werden, dass die Datei in eine der ausführbaren Hauptassemblys einer Anwendung oder in eine der Assemblys kompiliert wird, auf die verwiesen wird.  Dieser Typ von Anwendungsdatendatei wird als *Ressourcendatei* bezeichnet.  
  
 Verwenden Sie die Ressourcendateien in folgenden Fällen:  
  
-   Sie müssen den Inhalt der Ressourcendatei nicht aktualisieren , nachdem sie in eine Assembly kompiliert wurde.  
  
-   Sie möchten die Komplexität der Anwendungsverteilung vereinfachen, indem Sie die Anzahl von Dateiabhängigkeiten verringern.  
  
-   Die Anwendungsdatendatei muss lokalisierbar sein \(siehe [Übersicht über WPF\-Globalisierung und \-Lokalisierung](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)\).  
  
> [!NOTE]
>  Die Ressourcendateien, die in diesem Abschnitt beschriebenen sind anders als die Ressourcendateien, die in [XAML\-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md) beschriebenen und als eingebetteten oder verknüpften Ressourcen, die sich in [Verwalten von Anwendungsressourcen \(.NET\)](../Topic/Managing%20Application%20Resources%20\(.NET\).md)beschrieben werden.  
  
### Konfigurieren von Ressourcendateien  
 In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ist eine Ressourcendatei eine Datei, die als `Resource`\-Element in ein [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)]\-Projekt eingefügt wird.  
  
```  
<Project "xmlns=http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Resource Include="ResourceFile.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  In [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] erstellen Sie eine Ressourcendatei, indem Sie einem Projekt eine Datei hinzufügen und `Build Action` auf `Resource` festlegen.  
  
 Wenn das Projekt erstellt wird, kompiliert [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] die Ressource in die Assembly.  
  
### Verwenden von Ressourcendateien  
 Wenn Sie eine Ressourcendatei laden möchten, können Sie die <xref:System.Windows.Application.GetResourceStream%2A>\-Methode der <xref:System.Windows.Application>\-Klasse aufrufen, die einen Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] übergibt, der die gewünschte Ressourcendatei identifiziert.  <xref:System.Windows.Application.GetResourceStream%2A> gibt ein <xref:System.Windows.Resources.StreamResourceInfo>\-Objekt zurück, das die Ressourcendatei als <xref:System.IO.Stream> verfügbar macht und den Inhaltstyp beschreibt.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie <xref:System.Windows.Application.GetResourceStream%2A> zum Laden einer <xref:System.Windows.Controls.Page>\-Ressourcendatei verwendet und als Inhalt von <xref:System.Windows.Controls.Frame> \(`pageFrame`\) festgelegt wird:  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 Durch den Aufruf von <xref:System.Windows.Application.GetResourceStream%2A> erhalten Sie zwar Zugriff auf <xref:System.IO.Stream>, es ist jedoch zusätzlicher Aufwand erforderlich, um ihn in den Typ der Eigenschaft zu konvertieren, mit der Sie ihn festlegen.  Stattdessen kann [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] das Öffnen und Konvertieren von <xref:System.IO.Stream> übernehmen, indem eine Ressourcendatei mithilfe von Code direkt in die Eigenschaft eines Typs geladen wird.  
  
 Im folgenden Beispiel wird veranschaulicht, wie Sie <xref:System.Windows.Controls.Page> mithilfe von Code direkt in <xref:System.Windows.Controls.Frame> \(`pageFrame`\) laden.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 Das folgende Beispiel entspricht dem Markup des vorangehenden Beispiels.  
  
 [!code-xml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### Anwendungscodedateien als Ressourcendateien  
 Auf einen speziellen Satz von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendungscodedateien kann mithilfe von Paket\-[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] verwiesen werden, einschließlich Fenstern, Seiten, Flussdokumenten und Ressourcenwörterbüchern.  Sie können beispielsweise die <xref:System.Windows.Application.StartupUri%2A?displayProperty=fullName>\-Eigenschaft mit einem Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] festlegen, der auf das Fenster oder die Seite verweist, das bzw. die beim Starten einer Anwendung geladen werden soll.  
  
 [!code-xml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 Diese Vorgehensweise bietet sich an, wenn eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Datei als `Page`\-Element in ein [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)]\-Projekt eingefügt wird.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Page Include="MainWindow.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  In [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] fügen Sie einem Projekt eine neue <xref:System.Windows.Window>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.FlowDocument> oder <xref:System.Windows.ResourceDictionary> hinzu. `Build Action` für das Markup wird standardmäßig auf `Page` festgelegt.  
  
 Wenn ein Projekt mit `Page`\-Elementen kompiliert wird, werden die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Elemente in das Binärformat konvertiert und in die zugeordnete Assembly kompiliert.  Folglich können diese Dateien auf die gleiche Weise verwendet werden wie typische Ressourcendateien.  
  
> [!NOTE]
>  Wenn eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Datei als ein `Resource`\-Element konfiguriert wird und über keine Code\-Behind\-Datei verfügt, wird die Rohdaten\-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in eine Assembly und nicht in eine Binärversion der Rohdaten\-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] kompiliert.  
  
<a name="Content_Files"></a>   
## Inhaltsdateien  
 Eine *Inhaltsdatei* wird zusammen mit einer ausführbaren Assembly als lose Datei verteilt.  Obwohl Assemblys nicht in eine Assembly kompiliert werden, werden sie mit Metadaten kompiliert, die eine Zuordnung mit den einzelnen Inhaltsdateien herstellen.  
  
 Verwenden Sie Inhaltsdateien, wenn die Anwendung einen speziellen Satz von Anwendungsdatendateien erfordert, die aktualisierbar sein soll, ohne dass die Assembly, die sie verwendet, neu kompiliert werden muss.  
  
### Konfigurieren von Inhaltsdateien  
 Um einem Projekt eine Inhaltsdatei hinzuzufügen, muss eine Anwendungsdatendatei als `Content`\-Element enthalten sein.  Da eine Inhaltsdatei nicht direkt in die Assembly kompiliert wird, müssen Sie außerdem das [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]```CopyToOutputDirectory`\-Metadatenelement festlegen, um anzugeben, dass die Inhaltsdatei an einen Ort kopiert wird, der relativ zur erstellten Assembly ist.  Wenn die Ressource beim Erstellen eines Projekts in den Buildausgabeordner kopiert werden soll, legen Sie das `CopyToOutputDirectory`\-Metadatenelement mit dem `Always`\-Wert fest.  Andernfalls können Sie sicherstellen, dass lediglich die neueste Version der Ressource mithilfe des `PreserveNewest`\-Wertes in den Buildausgabeordner kopiert wird.  
  
 Im Folgenden wird eine Datei gezeigt, die als Inhaltsdatei konfiguriert ist und nur dann in den Buildausgabeordner kopiert wird, wenn dem Projekt eine neue Version der Ressource hinzugefügt wird.  
  
```  
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
>  In [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] erstellen Sie eine Inhaltsdatei durch Hinzufügen einer Datei zu einem Projekt und Festlegen von `Build Action` auf `Content` und von `Copy to Output Directory` auf `Copy always` \(entspricht `Always`\) und `Copy if newer` \(entspricht `PreserveNewest`\).  
  
 Beim Erstellen des Projekts wird ein <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>\-Attribut in die Metadaten der Assembly für jede Inhaltsdatei kompiliert.  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 Der Wert <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> bedeutet, dass der Pfad zur Inhaltsdatei relativ zu deren Position im Projekt ist.  Wenn sich eine Inhaltsdatei beispielsweise in einem Projektunterordner befand, werden die zusätzlichen Pfadinformationen in den <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>\-Wert integriert.  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 Der <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>\-Wert entspricht außerdem dem Wert des Pfades zur Inhaltsdatei im Buildausgabeordner.  
  
### Verwenden von Inhaltsdateien  
 Um eine Inhaltsdatei zu laden, können Sie die <xref:System.Windows.Application.GetContentStream%2A>\-Methode der <xref:System.Windows.Application>\-Klasse aufrufen. Dabei wird ein Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] übergeben, der die gewünschte Inhaltsdatei identifiziert.  <xref:System.Windows.Application.GetContentStream%2A> gibt ein <xref:System.Windows.Resources.StreamResourceInfo>\-Objekt zurück, das die Inhaltsdatei als <xref:System.IO.Stream> verfügbar macht und den Inhaltstyp beschreibt.  
  
 Das folgende Codebeispiel veranschaulicht, wie Sie <xref:System.Windows.Application.GetContentStream%2A> zum Laden einer <xref:System.Windows.Controls.Page>\-Inhaltsdatei verwenden und als Inhalt von <xref:System.Windows.Controls.Frame> \(`pageFrame`\) festlegen.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 Durch den Aufruf von <xref:System.Windows.Application.GetContentStream%2A> erhalten Sie zwar Zugriff auf <xref:System.IO.Stream>, es ist jedoch zusätzlicher Aufwand erforderlich, um ihn in den Typ der Eigenschaft zu konvertieren, mit der Sie ihn festlegen.  Stattdessen kann [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] das Öffnen und Konvertieren von <xref:System.IO.Stream> übernehmen, indem eine Ressourcendatei mithilfe von Code direkt in die Eigenschaft eines Typs geladen wird.  
  
 Im folgenden Beispiel wird veranschaulicht, wie Sie <xref:System.Windows.Controls.Page> mithilfe von Code direkt in <xref:System.Windows.Controls.Frame> \(`pageFrame`\) laden.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 Das folgende Beispiel entspricht dem Markup des vorangehenden Beispiels.  
  
 [!code-xml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>   
## Dateien der Ursprungssite  
 Ressourcendateien sind durch eine explizite Beziehung an die Assemblys gebunden, mit denen sie entsprechend dem <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> verteilt wurden.  Es kann jedoch vorkommen, dass Sie eine implizite oder nicht vorhandene Beziehung zwischen einer Assembly und einer Anwendungsdatendatei herstellen, u. a. in folgenden Fällen:  
  
-   Eine Datei ist zur Kompilierzeit nicht vorhanden.  
  
-   Sie wissen bis zur Laufzeit nicht, welche Dateien von der Assembly benötigt werden.  
  
-   Sie möchten in der Lage sein, Dateien ohne Neukompilierung der Assembly, der sie zugeordnet sind, zu aktualisieren.  
  
-   Die Anwendung verwendet große Datendateien, z. B. Audio und Video. Diese sollen von Benutzern nur heruntergeladen werden, wenn sie dies wünschen.  
  
 Diese Dateitypen lassen sich mithilfe der bewährten [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]\-Schemas herunterladen, z. B. das file:\/\/\/\-Schema oder das http:\/\/\-Schema.  
  
 [!code-xml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 Die Schemas file:\/\/\/ und http:\/\/ erfordern jedoch volle Vertrauenswürdigkeit der Anwendung.  Wenn die Anwendung eine [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] ist und vom Internet oder Intranet aus gestartet wurde und nur diejenigen Berechtigungen anfordert, die für Anwendungen gewährt werden, die von diesen Orten aus gestartet werden, können lose Dateien nur von der Ursprungssite der Anwendung \(Startspeicherort\) aus geladen werden.  Solche Dateien werden als Dateien der *Ursprungssite* bezeichnet.  
  
 Dateien der Ursprungssite stellen für teilweise vertrauenswürdige Anwendungen die einzige Option dar, obwohl sie nicht auf letztere beschränkt sind.  Anwendungen mit voller Vertrauenswürdigkeit müssen ggf. Anwendungsdatendateien laden, die sie zur Buildzeit nicht kennen. Obwohl Anwendungen mit voller Vertrauenswürdigkeit file:\/\/\/ verwenden könnten, ist anzunehmen, dass die Anwendungsdatendateien im selben Ordner oder in einem Unterordner der Anwendungsassembly installiert werden.  In einem solchen Fall gestaltet sich die Verwendung des Verweises auf die Ursprungssite einfacher als die Verwendung von , da Sie für  den vollständigen Dateipfad ausarbeiten müssen.  
  
> [!NOTE]
>  Dateien der Ursprungssite werden nicht mit einer [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] auf einem Clientcomputer zwischengespeichert, Inhaltsdateien dagegen schon.  Folglich werden sie nur heruntergeladen, wenn sie ausdrücklich angefordert werden.  Wenn eine [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]\-Anwendung große Mediendateien enthält, führt die Konfiguration dieser Dateien als Dateien der Ursprungssite zu einem erheblich schnelleren Start der Originalanwendung. Außerdem werden die Dateien nur auf Anforderung heruntergeladen.  
  
### Konfigurieren der Dateien der Ursprungssite  
 Wenn die Dateien der Ursprungssite zur Kompilierungszeit nicht vorhanden oder unbekannt sind, müssen Sie die bewährten Bereitstellungsmechanismen verwenden, um zu gewährleisten, dass die angeforderten Dateien zur Laufzeit verfügbar sind, einschließlich des `XCopy`\-Befehlszeilenprogramms oder [!INCLUDE[TLA#tla_wininstall](../../../../includes/tlasharptla-wininstall-md.md)].  
  
 Wenn Sie die Dateien, die auf der Ursprungssite gespeichert werden sollen, zur Kompilierungszeit kennen, aber dennoch explizite Abhängigkeit vermeiden möchten, können Sie diese Dateien einem [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)]\-Projekt als `None`\-Element hinzufügen.  Wie bei Inhaltsdateien müssen Sie das [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `CopyToOutputDirectory`\-Attribut festlegen, um anzugeben, dass die Datei der Ursprungssite an einen Speicherort kopiert wird, der relativ zur erstellten Assembly ist. Dabei wird entweder der `Always`\-Wert oder der `PreserveNewest`\-Wert angegeben.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <None Include="PageSiteOfOriginFile.xaml">  
    <CopyToOutputDirectory>Always</CopyToOutputDirectory>  
  </None>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  In [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] erstellen Sie eine Datei der Ursprungssite, indem Sie einem Projekt eine Datei hinzufügen und seine `Build Action` auf `None` festlegen.  
  
 Beim Erstellen des Projekts kopiert [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] die angegebenen Dateien in den Buildausgabeordner.  
  
### Verwenden der Dateien der Ursprungssite  
 Um eine Datei der Ursprungssite zu laden, können Sie die <xref:System.Windows.Application.GetRemoteStream%2A>\-Methode der <xref:System.Windows.Application>\-Klasse aufrufen. Dabei wird ein Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] übergeben, der die gewünschte Datei der Ursprungssite identifiziert.  <xref:System.Windows.Application.GetRemoteStream%2A> gibt ein <xref:System.Windows.Resources.StreamResourceInfo>\-Objekt zurück, das die Datei der Ursprungssite als <xref:System.IO.Stream> verfügbar macht und den Inhaltstyp beschreibt.  
  
 Das folgende Codebeispiel veranschaulicht, wie <xref:System.Windows.Application.GetRemoteStream%2A> zum Laden einer <xref:System.Windows.Controls.Page>\-Datei der Ursprungssite verwendet und als Inhalt von <xref:System.Windows.Controls.Frame> \(`pageFrame`\) festgelegt wird.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 Durch den Aufruf von <xref:System.Windows.Application.GetRemoteStream%2A> erhalten Sie zwar Zugriff auf <xref:System.IO.Stream>, es ist jedoch zusätzlicher Aufwand erforderlich, um ihn in den Typ der Eigenschaft zu konvertieren, mit der Sie ihn festlegen.  Stattdessen kann [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] das Öffnen und Konvertieren von <xref:System.IO.Stream> übernehmen, indem eine Ressourcendatei mithilfe von Code direkt in die Eigenschaft eines Typs geladen wird.  
  
 Im folgenden Beispiel wird veranschaulicht, wie Sie <xref:System.Windows.Controls.Page> mithilfe von Code direkt in <xref:System.Windows.Controls.Frame> \(`pageFrame`\) laden.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 Das folgende Beispiel entspricht dem Markup des vorangehenden Beispiels.  
  
 [!code-xml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>   
## Neuerstellung nach Ändern des Buildtyps  
 Nachdem Sie den Buildtyp einer Anwendungsdatendatei geändert haben, müssen Sie die gesamte Anwendung neu erstellen, um zu gewährleisten, dass diese Änderungen übernommen werden.  Wenn Sie nur die Anwendung erstellen, werden die Änderungen nicht übernommen.  
  
## Siehe auch  
 [Paket\-URI in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)