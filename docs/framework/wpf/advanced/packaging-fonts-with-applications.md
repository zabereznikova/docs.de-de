---
title: Verpacken von Schriftarten mit Anwendungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], packaging fonts with
- fonts [WPF], packaging with applications
- typography [WPF], packaging fonts with applications
- packaging fonts with applications [WPF]
ms.assetid: db15ee48-4d24-49f5-8b9d-a64460865286
ms.openlocfilehash: cef2ae26ec4fccd25ca193ba7d441969f36b25a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187088"
---
# <a name="packaging-fonts-with-applications"></a>Verpacken von Schriftarten mit Anwendungen
Dieses Thema bietet einen Überblick darüber, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] wie Schriftarten mit Ihrer Anwendung verpackt werden.  
  
> [!NOTE]
> Wie die meisten Arten von Software werden Schriftartdateien eher lizenziert als verkauft. Lizenzen, die die Verwendung von Schriftarten steuern, variieren von Anbieter zu Anbieter, aber im Allgemeinen erlauben die meisten Lizenzen, einschließlich der Lizenzen, die die Schriftarten abdecken, die Microsoft mit Anwendungen und Windows bereitstellt, nicht, dass die Schriftarten in Anwendungen eingebettet oder anderweitig verteilt werden. Deshalb liegt es in Ihrer Verantwortung als Entwickler sicherzustellen, dass Sie über die erforderlichen Lizenzrechte für alle Schriftarten verfügen, die Sie in eine Anwendung einbetten oder anderweitig verbreiten.  

<a name="introduction_to_packaging_fonts"></a>
## <a name="introduction-to-packaging-fonts"></a>Einführung in das Verpacken von Schriftarten  
 Sie können Schriftarten ganz einfach [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] als Ressourcen in Ihren Anwendungen verpacken, um Text der Benutzeroberfläche und andere Arten von textbasiertem Inhalt anzuzeigen. Die Schriftarten können getrennt von den Assemblydateien oder eingebettet in die Assemblydateien der Anwendung vorkommen. Sie können auch eine Schriftartenbibliothek nur für Ressourcen erstellen, auf die die Anwendung verweisen kann.  
  
 OpenType und TrueType® Schriftarten enthalten ein Typflag fsType, das Die Berechtigung zum Einbetten von Schriftart für die Schriftart angibt. Dieses Typflag bezieht sich jedoch nur auf eingebettete Schriftarten, die in einem Dokument gespeichert sind, und nicht auf Schriftarten, die in eine Anwendung eingebettet sind. Sie können die Schriftarteinbettungsrechte <xref:System.Windows.Media.GlyphTypeface> für eine Schriftart <xref:System.Windows.Media.GlyphTypeface.EmbeddingRights%2A> abrufen, indem Sie ein Objekt erstellen und auf seine Eigenschaft verweisen. Weitere Informationen zum fsType-Flag finden Sie im Abschnitt "OS/2 und Windows-Metriken" in der [OpenType-Spezifikation.](https://www.microsoft.com/typography/otspec/os2.htm)  
  
 Die [Microsoft Typography-Website](https://docs.microsoft.com/typography/) enthält Kontaktinformationen, mit denen Sie einen bestimmten Schriftartanbieter oder einen Schriftartanbieter für benutzerdefinierte Arbeiten finden können.  
  
<a name="adding_fonts_as_content_items"></a>
## <a name="adding-fonts-as-content-items"></a>Hinzufügen von Schriftarten als Inhaltselemente  
 Sie können Schriftarten als Projektinhaltselemente zu Ihrer Anwendung hinzufügen, die von den Assemblydateien der Anwendung getrennt sind. Dies bedeutet, dass Inhaltselemente nicht als Ressourcen in eine Assembly eingebettet werden. In der folgenden Beispielprojektdatei wird veranschaulicht, wie Inhaltselemente definiert werden.  
  
```xml  
<Project DefaultTargets="Build"  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- Other project build settings ... -->  
  
  <ItemGroup>  
    <Content Include="Peric.ttf" />  
    <Content Include="Pericl.ttf" />  
  </ItemGroup>  
</Project>  
```  
  
 Um sicherzustellen, dass die Anwendung die Schriftarten zur Laufzeit verwenden kann, müssen die Schriftarten im Bereitstellungsverzeichnis der Anwendung zugänglich sein. Mit `<CopyToOutputDirectory>` dem Element in der Projektdatei der Anwendung können Sie die Schriftarten während des Buildvorgangs automatisch in das Anwendungsbereitstellungsverzeichnis kopieren. In der folgenden Beispielprojektdatei wird veranschaulicht, wie Schriftarten in das Bereitstellungsverzeichnis kopiert werden.  
  
```xml  
<ItemGroup>  
  <Content Include="Peric.ttf">  
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
  </Content>  
  <Content Include="Pericl.ttf">  
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
  </Content>  
</ItemGroup>  
```  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie auf die Schriftart der Anwendung als Inhaltselement verwiesen wird. Das Inhaltselement, auf das verwiesen wird, muss sich im selben Verzeichnis wie die Assemblydateien der Anwendung befinden.  
  
 [!code-xaml[FontSnippets#FontPackageSnippet8](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet8)]  
  
<a name="adding_fonts_as_resource_items"></a>
## <a name="adding-fonts-as-resource-items"></a>Hinzufügen von Schriftarten als Ressourcenelemente  
 Sie können Schriftarten als Projektressourcenelemente zu Ihrer Anwendung hinzufügen, die in die Assemblydateien der Anwendung eingebettet werden. Die Verwendung eines separaten Unterverzeichnisses für Ressourcen hilft beim Organisieren der Projektdateien der Anwendung. In der folgenden Beispielprojektdatei wird veranschaulicht, wie Schriftarten als Ressourcenelemente in einem separaten Unterverzeichnis definiert werden.  
  
```xml  
<Project DefaultTargets="Build"  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- Other project build settings ... -->  
  
  <ItemGroup>  
    <Resource Include="resources\Peric.ttf" />  
    <Resource Include="resources\Pericl.ttf" />  
  </ItemGroup>  
</Project>  
```  
  
> [!NOTE]
> Wenn Sie Ihrer Anwendung Schriftarten als Ressourcen hinzufügen, `<Resource>` stellen Sie `<EmbeddedResource>` sicher, dass Sie das Element und nicht das Element in der Projektdatei Der Anwendung festlegen. Das `<EmbeddedResource>` Element für die Buildaktion wird nicht unterstützt.  
  
 Im folgenden Markupbeispiel wird veranschaulicht, wie auf die Schriftartenressourcen der Anwendung verwiesen wird.  
  
 [!code-xaml[FontSnippets#FontPackageSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet1)]  
  
### <a name="referencing-font-resource-items-from-code"></a>Verweisen auf Schriftartenressourcenelemente aus Code  
 Um auf Schriftartressourcenelemente aus Code zu verweisen, müssen Sie einen zweiteiligen Schriftartenressourcenverweis angeben: den Urbezeichner (Base Uniform Resource Identifier, URI); und die Schriftortreferenz. Diese Werte werden als Parameter <xref:System.Windows.Media.FontFamily.%23ctor%2A> für die Methode verwendet. Das folgende Codebeispiel zeigt, wie sie auf die Schriftartressourcen der Anwendung im Projektunterverzeichnis mit dem Namen verweisen. `resources`  
  
 [!code-csharp[FontSnippets#FontPackageSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet2)]
 [!code-vb[FontSnippets#FontPackageSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet2)]  
  
 Der Uri (Base Uniform Resource Identifier) kann das Anwendungsunterverzeichnis enthalten, in dem sich die Schriftartressource befindet. In diesem Fall müsste der Schriftortspeicherortverweis kein Verzeichnis angeben, sondern`./`ein führendes " " enthalten, das angibt, dass sich die Schriftartressource in demselben Verzeichnis befindet, das durch den Urbezeichner (Uri) angegeben wird. Im folgenden Codebeispiel wird eine alternative Möglichkeit veranschaulicht, wie auf das Schriftartenressourcenelement verwiesen werden kann. Es entspricht dem vorherigen Codebeispiel.  
  
 [!code-csharp[FontSnippets#FontPackageSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet5)]
 [!code-vb[FontSnippets#FontPackageSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet5)]  
  
### <a name="referencing-fonts-from-the-same-application-subdirectory"></a>Verweisen auf Schriftarten aus dem gleichen Anwendungsunterverzeichnis  
 Sie können Anwendungsinhalt und Ressourcendateien im selben benutzerdefinierten Unterverzeichnis Ihres Anwendungsprojekts platzieren. In der folgenden Beispielprojektdatei wird veranschaulicht, wie eine Inhaltsseite und Schriftartenressourcen im selben Unterverzeichnis definiert werden.  
  
```xml  
<ItemGroup>  
  <Page Include="pages\HomePage.xaml" />  
</ItemGroup>  
<ItemGroup>  
  <Resource Include="pages\Peric.ttf" />  
  <Resource Include="pages\Pericl.ttf" />  
</ItemGroup>  
```  
  
 Da sich Anwendungsinhalt und Schriftart im selben Unterverzeichnis befinden, ist der Schriftartenverweis relativ zum Anwendungsinhalt. In den folgenden Beispielen wird veranschaulicht, wie auf die Schriftartenressource der Anwendung verwiesen werden kann, wenn sich die Schriftart im selben Verzeichnis wie die Anwendung befindet.  
  
 [!code-xaml[FontSnippets#FontPackageSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml#fontpackagesnippet3)]  
  
 [!code-csharp[FontSnippets#FontPackageSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml.cs#fontpackagesnippet4)]
 [!code-vb[FontSnippets#FontPackageSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/pages/homepage.xaml.vb#fontpackagesnippet4)]  
  
### <a name="enumerating-fonts-in-an-application"></a>Auflisten von Schriftarten in einer Anwendung  
 Um Schriftarten als Ressourcenelemente in ihrer Anwendung aufzulisten, verwenden Sie entweder die <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> oder-Methode. <xref:System.Windows.Media.Fonts.GetTypefaces%2A> Das folgende Beispiel zeigt, <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> wie Sie die <xref:System.Windows.Media.FontFamily> Methode verwenden, um die Auflistung von Objekten vom Speicherort der Anwendungsschriftart zurückzugeben. In diesem Fall enthält die Anwendung ein Unterverzeichnis mit dem Namen „Ressourcen“.  
  
 [!code-csharp[FontSnippets#FontsSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet3)]
 [!code-vb[FontSnippets#FontsSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet3)]  
  
 Das folgende Beispiel zeigt, <xref:System.Windows.Media.Fonts.GetTypefaces%2A> wie Sie die <xref:System.Windows.Media.Typeface> Methode verwenden, um die Auflistung von Objekten vom Speicherort der Anwendungsschriftart zurückzugeben. In diesem Fall enthält die Anwendung ein Unterverzeichnis mit dem Namen „Ressourcen“.  
  
 [!code-csharp[FontSnippets#FontsSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet7)]
 [!code-vb[FontSnippets#FontsSnippet7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet7)]  
  
<a name="creating_a_font_resource_library"></a>
## <a name="creating-a-font-resource-library"></a>Erstellen einer Schriftartenressourcenbibliothek  
 Sie können eine Bibliothek nur für Ressourcen erstellen, die ausschließlich Schriftarten enthält. In dieser Art von Bibliothek ist kein Code enthalten. Das Erstellen einer Bibliothek nur für Ressourcen dient häufig dem Entkoppeln von Ressourcen vom Anwendungscode, der sie verwendet. Dies ermöglicht außerdem, dass die Bibliotheksassembly in mehreren Anwendungsprojekten enthalten sein kann. In der folgenden Beispielprojektdatei werden die Hauptbestandteile einer Bibliothek nur für Ressourcen gezeigt.  
  
```xml  
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
  
### <a name="referencing-a-font-in-a-resource-library"></a>Verweisen auf eine Schriftart in einer Ressourcenbibliothek  
 Um aus Ihrer Anwendung auf eine Schriftart in einer Ressourcenbibliothek zu verweisen, müssen Sie dem Verweis auf die Schriftart den Namen der Bibliotheksassembly voranstellen. In diesem Fall ist die Schriftartenressourcenassembly „FontLibrary“. Verwenden Sie ein Semikolon (;), um den Assemblynamen vom Verweis innerhalb der Assembly zu trennen. Durch Hinzufügen des Schlüsselworts „Component“ gefolgt vom Verweis auf den Namen der Schriftart wird der Verweis auf die Ressource der Schriftartenbibliothek vervollständigt. Im folgenden Codebeispiel wird veranschaulicht, wie auf eine Schriftart in einer Ressourcenbibliotheksassembly verwiesen wird.  
  
 [!code-xaml[OpenTypeFontsSample#OpenTypeFontsSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontsSample/CS/Kootenay.xaml#opentypefontssample1)]  
  
> [!NOTE]
> Dieses SDK enthält eine Reihe von OpenType-Beispielschriftarten, die Sie mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen verwenden können. Die Schriftarten werden in einer Bibliothek nur für Ressourcen definiert. Weitere Informationen finden Sie unter [Beispiel OpenType Font Pack](sample-opentype-font-pack.md).  
  
<a name="limitations_on_font_usage"></a>
## <a name="limitations-on-font-usage"></a>Einschränkungen der Verwendung von Schriftarten  
 In der folgenden Liste werden mehrere Einschränkungen beim [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Verpacken und Verwenden von Schriftarten in Anwendungen beschrieben:  
  
- **Berechtigungsbits für die Schriftarteneinbettung: Von ** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen werden keine Berechtigungsbits für die Schriftarteneinbettung überprüft oder durchgesetzt. Weitere Informationen finden Sie im Abschnitt [Introduction_to_Packing Schriftarten.](#introduction_to_packaging_fonts)  
  
- **Ursprungsort-Schriftarten:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen erlauben keinen Schriftartenverweis auf einen http- oder FTP-Uri (Uniform Resource Identifier).  
  
- **Absoluter URI mit dem Pack: Notation:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen <xref:System.Windows.Media.FontFamily> erlauben es Ihnen nicht, ein Objekt programmgesteuert mit "pack:" als Teil des absolut einheitlichen Ressourcenbezeichners (URI) auf eine Schriftart zu erstellen. Beispielsweise `"pack://application:,,,/resources/#Pericles Light"` handelt es sich um einen ungültigen Schriftverweis.  
  
- **Automatische Schriftarteneinbettung:** Zur Entwurfszeit werden die Suche nach der Schriftartenverwendung einer Anwendung und das automatische Einbetten der Schriftarten in die Ressourcen der Anwendung nicht unterstützt.  
  
- **Schriftartteilmengen:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen unterstützen keine Erstellung von Schriftartteilmengen für Dokumente ohne festes Format.  
  
- Bei einem falschen Verweis greift die Anwendung auf eine verfügbare Schriftart zurück.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Documents.Typography>
- <xref:System.Windows.Media.FontFamily>
- [Microsoft Typography: Links, News, and Contacts (Microsoft-Typografie: Links, Neuigkeiten und Kontakte)](https://docs.microsoft.com/typography/)
- [OpenType-Spezifikation](https://www.microsoft.com/typography/otspec/)
- [Features für OpenType-Schriftarten](opentype-font-features.md)
- [OpenType-Beispielschriftartenpaket](sample-opentype-font-pack.md)
