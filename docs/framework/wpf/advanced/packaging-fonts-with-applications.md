---
title: "Verpacken von Schriftarten mit Anwendungen | Microsoft Docs"
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
  - "Anwendungen, Verpacken von Schriftarten mit"
  - "Schriftarten, Verpacken mit Anwendungen"
  - "Verpacken von Schriftarten mit Anwendungen"
  - "Typografie, Verpacken von Schriftarten mit Anwendungen"
ms.assetid: db15ee48-4d24-49f5-8b9d-a64460865286
caps.latest.revision: 29
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# Verpacken von Schriftarten mit Anwendungen
Dieses Thema enthält eine Übersicht über das Verpacken von Schriftarten mit der [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Anwendung.  
  
> [!NOTE]
>  Wie die meisten Arten von Software werden Schriftartdateien eher lizenziert als verkauft.  Lizenzen, die die Verwendung von Schriftarten steuern, sind von Anbieter zu Anbieter unterschiedlich. Im Allgemeinen lassen es die meisten Lizenzen, darunter auch die für die von [!INCLUDE[TLA#tla_ms#initcap](../../../../includes/tlasharptla-mssharpinitcap-md.md)] in Anwendungen und [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] bereitgestellten Schriftarten, nicht zu, dass die Schriftarten in Anwendungen eingebettet oder anders verbreitet werden.  Deshalb liegt es in Ihrer Verantwortung als Entwickler sicherzustellen, dass Sie über die erforderlichen Lizenzrechte für alle Schriftarten verfügen, die Sie in eine Anwendung einbetten oder anders verteilen.  
  
   
  
<a name="introduction_to_packaging_fonts"></a>   
## Einführung in das Verpacken von Schriftarten  
 Sie können Schriftarten leicht als Ressourcen in Ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen verpacken, um den Text der Benutzeroberfläche und anderen textbasierten Inhalt anzuzeigen.  Die Schriftarten können getrennt von den oder eingebettet in die Assemblydateien der Anwendung vorkommen.  Sie können auch eine reine Ressourcenbibliothek für Schriftarten erstellen, auf die die Anwendung verweisen kann.  
  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]\- und [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)]\-Schriftarten enthalten ein Typflag, fsType, mit dem für die Schriftart die Lizenzierungsrechte zur Einbettung der Schriftart angegeben werden.  Dieses Typflag bezieht sich jedoch nur auf eingebettete Schriftarten, die in einem Dokument gespeichert sind. Es bezieht sich nicht auf Schriftarten, die in eine Anwendung eingebettet sind.  Sie können die Rechte für die Schriftarteneinbettung für eine Schriftart abrufen, indem Sie ein <xref:System.Windows.Media.GlyphTypeface>\-Objekt erstellen und auf dessen <xref:System.Windows.Media.GlyphTypeface.EmbeddingRights%2A>\-Eigenschaft verweisen.  Weitere Informationen zum fsType\-Flag finden Sie im Abschnitt "OS\/2 and Windows Metrics" der [OpenType\-Spezifikation](http://www.microsoft.com/typography/otspec/os2.htm).  
  
 Die Website [Microsoft\-Typografie](http://www.microsoft.com/typography/links/) enthält Kontaktinformationen, damit Sie einen bestimmten Schriftartanbieter leichter finden können oder damit Sie einen Schriftartanbieter für benutzerdefinierte Schriftarten finden können.  
  
<a name="adding_fonts_as_content_items"></a>   
## Hinzufügen von Schriftarten als Inhaltselemente  
 Sie können Ihrer Anwendung Schriftarten als Projektinhaltselemente hinzufügen, die von den Assemblydateien der Anwendung getrennt sind.  Dies bedeutet, dass Inhaltselemente nicht als Ressourcen in eine Assembly eingebettet werden.  Im folgenden Projektdateibeispiel wird gezeigt, wie Inhaltselemente definiert werden.  
  
```  
<Project DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- Other project build settings ... -->  
  
  <ItemGroup>  
    <Content Include="Peric.ttf" />  
    <Content Include="Pericl.ttf" />  
  </ItemGroup>  
</Project>  
```  
  
 Um sicherzustellen, dass die Anwendung die Schriftarten zur Laufzeit verwenden kann, muss ein Zugriff auf die Schriftarten über das Bereitstellungsverzeichnis der Anwendung möglich sein.  Mit dem `<CopyToOutputDirectory>`\-Element in der Projektdatei der Anwendung können Sie die Schriftarten automatisch während des Buildprozesses in das Bereitstellungsverzeichnis der Anwendung kopieren.  Im folgenden Projektdateibeispiel wird gezeigt, wie Schriftarten ins Bereitstellungsverzeichnis kopiert werden.  
  
```  
<ItemGroup>  
  <Content Include="Peric.ttf">  
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
  </Content>  
  <Content Include="Pericl.ttf">  
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
  </Content>  
</ItemGroup>  
```  
  
 Mit dem folgenden Codebeispiel wird gezeigt, wie auf die Schriftart einer Anwendung als Inhaltselement verwiesen wird \(das Inhaltselement, auf das verwiesen wird, muss sich im gleichen Verzeichnis befinden wie die Assemblydateien der Anwendung\).  
  
 [!code-xml[FontSnippets#FontPackageSnippet8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet8)]  
  
<a name="adding_fonts_as_resource_items"></a>   
## Hinzufügen von Schriftarten als Ressourcenelemente  
 Sie können Ihrer Anwendung Schriftarten als Projektressourcenelemente hinzufügen, die in die Assemblydateien der Anwendung eingebettet sind.  Die Verwendung eines separaten Unterverzeichnisses für Ressourcen hilft bei der Strukturierung der Projektdateien der Anwendung.  Im folgenden Projektdateibeispiel wird gezeigt, wie Schriftarten als Ressourcenelemente in einem separaten Unterverzeichnis definiert werden.  
  
```  
<Project DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- Other project build settings ... -->  
  
  <ItemGroup>  
    <Resource Include="resources\Peric.ttf" />  
    <Resource Include="resources\Pericl.ttf" />  
  </ItemGroup>  
</Project>  
```  
  
> [!NOTE]
>  Wenn Sie der Anwendung Schriftarten als Ressourcen hinzufügen, stellen Sie sicher, dass Sie das `<Resource>`\-Element festlegen, und nicht das `<EmbeddedResource>`\-Element in der Projektdatei der Anwendung.  Das `<EmbeddedResource>`\-Element für den Buildvorgang wird nicht unterstützt.  
  
 Im folgenden Markupbeispiel wird gezeigt, wie auf die Schriftartressourcen der Anwendung verwiesen wird.  
  
 [!code-xml[FontSnippets#FontPackageSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet1)]  
  
### Verweisen auf Schriftartressourcen\-Elemente über Code  
 Um über Code auf Schriftartressourcen\-Elemente zu verweisen, müssen Sie einen zweiteiligen Schriftartressourcen\-Verweis angeben: den grundlegenden [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] und den Verweis auf den Speicherort der Schriftart.  Diese Werte werden als Parameter für die <xref:System.Windows.Media.FontFamily.%23ctor%2A>\-Methode verwendet.  Das folgende Codebeispiel veranschaulicht, wie auf die Schriftartressourcen der Anwendung im Projektunterverzeichnis namens `resources` verwiesen wird.  
  
 [!code-csharp[FontSnippets#FontPackageSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet2)]
 [!code-vb[FontSnippets#FontPackageSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet2)]  
  
 Der grundlegende [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] kann das Anwendungsunterverzeichnis einschließen, in dem sich die Schriftartressource befindet.  In diesem Fall müsste der Verweis auf den Speicherort der Schriftart kein Verzeichnis angeben, sondern müsste ein führendes "`./`"\-Zeichen aufweisen, mit dem gekennzeichnet wird, dass sich die Schriftartressource in dem Verzeichnis befindet, das vom grundlegenden [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] angegeben wird.  Das folgende Codebeispiel zeigt eine andere Möglichkeit, auf das Schriftartressourcen\-Element zu verweisen. Es entspricht dem vorherigen Beispiel.  
  
 [!code-csharp[FontSnippets#FontPackageSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet5)]
 [!code-vb[FontSnippets#FontPackageSnippet5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet5)]  
  
### Verweisen auf Schriftarten über das gleiche Anwendungsunterverzeichnis  
 Sie können den Anwendungsinhalt und die Ressourcendateien im gleichen benutzerdefinierten Unterverzeichnis Ihres Anwendungsprojekts platzieren.  Das folgende Projektdateibeispiel zeigt eine Inhaltsseite und Schriftartressourcen an, die im gleichen Unterverzeichnis definiert werden.  
  
```  
<ItemGroup>  
  <Page Include="pages\HomePage.xaml" />  
</ItemGroup>  
<ItemGroup>  
  <Resource Include="pages\Peric.ttf" />  
  <Resource Include="pages\Pericl.ttf" />  
</ItemGroup>  
```  
  
 Da sich der Anwendungsinhalt und die Schriftart im gleichen Unterverzeichnis befinden, ist der Schriftartverweis relativ zum Anwendungsinhalt.  Das folgende Beispiel veranschaulicht, wie auf die Schriftartressourcen der Anwendung verwiesen wird, wenn sich die Schriftart im gleichen Verzeichnis befindet wie die Anwendung.  
  
 [!code-xml[FontSnippets#FontPackageSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml#fontpackagesnippet3)]  
  
 [!code-csharp[FontSnippets#FontPackageSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml.cs#fontpackagesnippet4)]
 [!code-vb[FontSnippets#FontPackageSnippet4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/pages/homepage.xaml.vb#fontpackagesnippet4)]  
  
### Auflisten von Schriftarten in einer Anwendung  
 Verwenden Sie zum Auflisten von Schriftarten als Ressourcenelemente in der Anwendung die <xref:System.Windows.Media.Fonts.GetFontFamilies%2A>\-Methode oder die <xref:System.Windows.Media.Fonts.GetTypefaces%2A>\-Methode.  Im folgenden Beispiel wird veranschaulicht, wie Sie mit der <xref:System.Windows.Media.Fonts.GetFontFamilies%2A>\-Methode die Auflistung von <xref:System.Windows.Media.FontFamily>\-Objekten aus dem Schriftartspeicherort der Anwendung zurückgeben.  In diesem Fall enthält die Anwendung ein Unterverzeichnis mit dem Namen "resources".  
  
 [!code-csharp[FontSnippets#FontsSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet3)]
 [!code-vb[FontSnippets#FontsSnippet3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet3)]  
  
 Im folgenden Beispiel wird veranschaulicht, wie Sie mit der <xref:System.Windows.Media.Fonts.GetTypefaces%2A>\-Methode die Auflistung von <xref:System.Windows.Media.Typeface>\-Objekten aus dem Schriftartspeicherort der Anwendung zurückgeben.  In diesem Fall enthält die Anwendung ein Unterverzeichnis mit dem Namen "resources".  
  
 [!code-csharp[FontSnippets#FontsSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet7)]
 [!code-vb[FontSnippets#FontsSnippet7](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet7)]  
  
<a name="creating_a_font_resource_library"></a>   
## Erstellen einer Schriftartressourcen\-Bibliothek  
 Sie können eine reine Ressourcenbibliothek erstellen, die ausschließlich Schriftarten enthält. Code ist nicht Bestandteil eines solchen Bibliothekprojekts.  Das Erstellen einer reinen Ressourcenbibliothek ist eine verbreitete Technik für das Entkoppeln von Ressourcen vom Anwendungscode, in dem sie verwendet werden.  Dadurch ist es auch möglich, dass die Bibliotheksassembly in mehrere Anwendungsprojekte aufgenommen werden kann.  Im folgenden Projektdateibeispiel werden die Hauptbestandteile eines reinen Ressourcenbibliotheksprojekts veranschaulicht.  
  
```  
<PropertyGroup>  
  <AssemblyName>FontLibrary</AssemblyName>  
  <OutputType>library</OutputType>  
  ...  
</PropertyGroup>  
...  
<ItemGroup>  
  <Resource Include="Kooten.ttf" />  
  <Resource Include="Pesca.ttf" />  
</ItemGroup  
```  
  
### Verweisen auf eine Schriftart in einer Ressourcenbibliothek  
 Um über die Anwendung auf eine Schriftart in einer Ressourcenbibliothek zu verweisen, müssen Sie dem Schriftartverweis den Namen der Bibliotheksassembly voranstellen.  In diesem Fall ist die Schriftartressourcen\-Assembly "FontLibrary".  Um den Assemblynamen innerhalb der Assembly vom Verweis zu trennen, verwenden Sie ein ";"\-Zeichen.  Durch Hinzufügen des Schlüsselworts "Component" gefolgt vom Verweis auf den Schriftartnamen wird der Verweis auf die Ressource der Schriftartbibliothek vervollständigt.  Im folgenden Codebeispiel wird gezeigt, wie auf eine Schriftart in einer Ressourcenbibliotheksassembly verwiesen wird.  
  
 [!code-xml[OpenTypeFontsSample#OpenTypeFontsSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontsSample/CS/Kootenay.xaml#opentypefontssample1)]  
  
> [!NOTE]
>  Dieses SDK enthält einen Satz von Beispielen für [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]\-Schriftarten, die Sie in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen verwenden können.  Die Schriftarten werden in einer reinen Ressourcenbibliothek definiert.  Weitere Informationen finden Sie unter [OpenType\-Beispielschriftartenpaket](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md).  
  
<a name="limitations_on_font_usage"></a>   
## Einschränkungen der Schriftartverwendung  
 In der folgenden Liste werden mehrere Einschränkungen des Verpackens und Verwendens von Schriftarten in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen beschrieben:  
  
-   **Berechtigungsbits für die Schriftarteinbettung:** Mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen werden Berechtigungsbits für die Schriftarteinbettung nicht überprüft oder durchgesetzt.  Weitere Informationen finden Sie unter [Einführung in das Verpacken von Schriftarten](#introduction_to_packaging_fonts).  
  
-   **Site der Ursprungsschriftarten:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen lassen keine Schriftartenverweise auf einen http\- oder ftp\-[!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] zu.  
  
-   **Absoluter URI mit der pack:\-Notation:** Mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen können Sie programmgesteuert kein <xref:System.Windows.Media.FontFamily>\-Objekt mit "pack:" als Bestandteil des absoluten [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]\-Verweises auf eine Schriftart erstellen.  Beispielsweise ist `"pack://application:,,,/resources/#Pericles Light"` ein ungültiger Schriftartverweis.  
  
-   **Automatische Schriftarteinbettung:** Zur Entwurfszeit erfolgt keine Unterstützung für die Suche der Schriftartverwendung einer Anwendung und für das automatische Einbetten der Schriftarten in die Ressourcen der Anwendung.  
  
-   **Schriftartteilmengen:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen unterstützen die Erstellung von Schriftartteilmengen für nicht einheitlich dargestellte Dokumente nicht.  
  
-   Bei einem falschen Verweis greift die Anwendung wieder auf die Verwendung einer verfügbaren Schriftart zurück.  
  
## Siehe auch  
 <xref:System.Windows.Documents.Typography>   
 <xref:System.Windows.Media.FontFamily>   
 [Microsoft\-Typografie: Links, Neuigkeiten und Kontakte](http://www.microsoft.com/typography/links/)   
 [OpenType\-Spezifikation](http://www.microsoft.com/typography/otspec/)   
 [Features für OpenType\-Schriftarten](../../../../docs/framework/wpf/advanced/opentype-font-features.md)   
 [OpenType\-Beispielschriftartenpaket](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md)