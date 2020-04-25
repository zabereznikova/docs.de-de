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
ms.openlocfilehash: 7bdf3b11557d94ab39c93a21ac53b917e3a1767d
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141121"
---
# <a name="packaging-fonts-with-applications"></a>Verpacken von Schriftarten mit Anwendungen
Dieses Thema enthält eine Übersicht über das Verpacken von Schriftarten mit [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Ihrer Anwendung.  
  
> [!NOTE]
> Wie die meisten Arten von Software werden Schriftartdateien eher lizenziert als verkauft. Lizenzen, die die Verwendung von Schriftarten steuern, unterscheiden sich von Hersteller zu Hersteller, aber in den meisten Lizenzen, einschließlich derjenigen, die die Schriftarten von Microsoft für Anwendungen und Windows abdecken, ist es nicht zulässig, dass die Schriftarten in Anwendungen eingebettet oder anderweitig neu verteilt werden. Deshalb liegt es in Ihrer Verantwortung als Entwickler sicherzustellen, dass Sie über die erforderlichen Lizenzrechte für alle Schriftarten verfügen, die Sie in eine Anwendung einbetten oder anderweitig verbreiten.  

<a name="introduction_to_packaging_fonts"></a>
## <a name="introduction-to-packaging-fonts"></a>Einführung in das Verpacken von Schriftarten  
 Sie können Schriftarten problemlos als Ressourcen in Ihren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen Verpacken, um den Text der Benutzeroberfläche und andere textbasierte Inhaltstypen anzuzeigen. Die Schriftarten können getrennt von den Assemblydateien oder eingebettet in die Assemblydateien der Anwendung vorkommen. Sie können auch eine Schriftartenbibliothek nur für Ressourcen erstellen, auf die die Anwendung verweisen kann.  
  
 OpenType-und TrueType-® Schriftarten enthalten das Typflag fstype, das Schriftart Einbettungs Lizenzierungs Rechte für die Schriftart angibt. Dieses Typflag bezieht sich jedoch nur auf eingebettete Schriftarten, die in einem Dokument gespeichert sind, und nicht auf Schriftarten, die in eine Anwendung eingebettet sind. Sie können die Schriftart Einbettungs Rechte für eine Schriftart abrufen, indem <xref:System.Windows.Media.GlyphTypeface> Sie ein-Objekt erstellen <xref:System.Windows.Media.GlyphTypeface.EmbeddingRights%2A> und auf seine-Eigenschaft verweisen. Weitere Informationen zum fstype-Flag finden Sie im Abschnitt "OS/2 und Windows-Metriken" der [OpenType-Spezifikation](https://www.microsoft.com/typography/otspec/os2.htm) .  
  
 Die [Microsoft](https://docs.microsoft.com/typography/) -Typografiewebsite enthält Kontaktinformationen, die Ihnen helfen können, einen bestimmten Schriftart Hersteller zu finden oder einen Schriftart Anbieter für benutzerdefinierte arbeiten zu finden.  
  
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
  
 Um sicherzustellen, dass die Anwendung die Schriftarten zur Laufzeit verwenden kann, müssen die Schriftarten im Bereitstellungsverzeichnis der Anwendung zugänglich sein. Mithilfe `<CopyToOutputDirectory>` des-Elements in der Projektdatei der Anwendung können Sie die Schriftarten während des Buildprozesses automatisch in das Anwendungs Bereitstellungs Verzeichnis kopieren. In der folgenden Beispielprojektdatei wird veranschaulicht, wie Schriftarten in das Bereitstellungsverzeichnis kopiert werden.  
  
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
> Wenn Sie der Anwendung Schriftarten als Ressourcen hinzufügen, stellen Sie sicher, dass `<Resource>` Sie das-Element und `<EmbeddedResource>` nicht das-Element in der Projektdatei der Anwendung festlegen. Das `<EmbeddedResource>` -Element für die Buildaktion wird nicht unterstützt.  
  
 Im folgenden Markupbeispiel wird veranschaulicht, wie auf die Schriftartenressourcen der Anwendung verwiesen wird.  
  
 [!code-xaml[FontSnippets#FontPackageSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet1)]  
  
### <a name="referencing-font-resource-items-from-code"></a>Verweisen auf Schriftartenressourcenelemente aus Code  
 Um auf Schriftart Ressourcen Elemente aus dem Code zu verweisen, müssen Sie einen zweiteiligen Schriftart Ressourcen Verweis angeben: der Basis-Uniform Resource Identifier (URI). und den Schriftart Speicherort Verweis. Diese Werte werden als Parameter für die <xref:System.Windows.Media.FontFamily.%23ctor%2A> -Methode verwendet. Im folgenden Codebeispiel wird gezeigt, wie auf die Schriftarten Ressourcen der Anwendung im Projekt Unterverzeichnis `resources`mit dem Namen verwiesen wird.  
  
 [!code-csharp[FontSnippets#FontPackageSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet2)]
 [!code-vb[FontSnippets#FontPackageSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet2)]  
  
 Der Basis-URI (Uniform Resource Identifier) kann das Anwendungs Unterverzeichnis enthalten, in dem sich die Schriftart Ressource befindet. In diesem Fall muss die Schriftart für den Schriftart Speicherort nicht ein Verzeichnis angeben, sondern eine führende "`./`" enthalten, die angibt, dass sich die Schriftart Ressource in demselben Verzeichnis befindet, das durch den Basis-URI (Uniform Resource Identifier) angegeben wird. Im folgenden Codebeispiel wird eine alternative Möglichkeit veranschaulicht, wie auf das Schriftartenressourcenelement verwiesen werden kann. Es entspricht dem vorherigen Codebeispiel.  
  
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
 Um Schriftarten als Ressourcen Elemente in Ihrer Anwendung aufzulisten, verwenden Sie entweder <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> die <xref:System.Windows.Media.Fonts.GetTypefaces%2A> -oder die-Methode. Im folgenden Beispiel wird gezeigt, wie die <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> -Methode verwendet wird, um <xref:System.Windows.Media.FontFamily> die Auflistung von-Objekten aus dem Speicherort der Anwendungs Schriftart zurückzugeben. In diesem Fall enthält die Anwendung ein Unterverzeichnis mit dem Namen „Ressourcen“.  
  
 [!code-csharp[FontSnippets#FontsSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet3)]
 [!code-vb[FontSnippets#FontsSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet3)]  
  
 Im folgenden Beispiel wird gezeigt, wie die <xref:System.Windows.Media.Fonts.GetTypefaces%2A> -Methode verwendet wird, um <xref:System.Windows.Media.Typeface> die Auflistung von-Objekten aus dem Speicherort der Anwendungs Schriftart zurückzugeben. In diesem Fall enthält die Anwendung ein Unterverzeichnis mit dem Namen „Ressourcen“.  
  
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
> Dieses SDK enthält eine Reihe von OpenType-Beispiel Schriftarten, die Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mit-Anwendungen verwenden können. Die Schriftarten werden in einer Bibliothek nur für Ressourcen definiert. Weitere Informationen finden Sie unter [Sample OpenType Font Pack](sample-opentype-font-pack.md).  
  
<a name="limitations_on_font_usage"></a>
## <a name="limitations-on-font-usage"></a>Einschränkungen der Verwendung von Schriftarten  
 In der folgenden Liste werden verschiedene Einschränkungen beim Verpacken und Verwenden von Schriftarten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in Anwendungen beschrieben:  
  
- **Berechtigungsbits für die Schriftarteneinbettung: Von ** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen werden keine Berechtigungsbits für die Schriftarteneinbettung überprüft oder durchgesetzt. Weitere Informationen finden Sie im Abschnitt [Introduction_to_Packing Fonts](#introduction_to_packaging_fonts) .  
  
- **Ursprungs Schriftarten von Ursprungsorten:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen erlauben keinen Schriftart Verweis auf einen HTTP-oder FTP-URI (Uniform Resource Identifier).  
  
- **Absoluter URI unter Verwendung des Pakets: Notation:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen ermöglichen es Ihnen nicht, ein <xref:System.Windows.Media.FontFamily> -Objekt Programm gesteuert mithilfe von "Pack:" als Teil des absoluten URI-Verweises (Uniform Resource Identifier) auf eine Schriftart zu erstellen. Beispielsweise `"pack://application:,,,/resources/#Pericles Light"` ist ein ungültiger Schriftart Verweis.  
  
- **Automatische Schriftarteneinbettung:** Zur Entwurfszeit werden die Suche nach der Schriftartenverwendung einer Anwendung und das automatische Einbetten der Schriftarten in die Ressourcen der Anwendung nicht unterstützt.  
  
- **Schriftartteilmengen:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen unterstützen keine Erstellung von Schriftartteilmengen für Dokumente ohne festes Format.  
  
- Bei einem falschen Verweis greift die Anwendung auf eine verfügbare Schriftart zurück.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Documents.Typography>
- <xref:System.Windows.Media.FontFamily>
- [Microsoft Typography: Links, News, and Contacts (Microsoft-Typografie: Links, Neuigkeiten und Kontakte)](https://docs.microsoft.com/typography/)
- [OpenType-Spezifikation](https://www.microsoft.com/typography/otspec/)
- [Features für OpenType-Schriftarten](opentype-font-features.md)
- [OpenType-Beispielschriftartenpaket](sample-opentype-font-pack.md)
