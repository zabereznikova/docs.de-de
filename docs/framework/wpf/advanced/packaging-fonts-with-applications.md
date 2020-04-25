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
# <a name="packaging-fonts-with-applications"></a><span data-ttu-id="97294-102">Verpacken von Schriftarten mit Anwendungen</span><span class="sxs-lookup"><span data-stu-id="97294-102">Packaging Fonts with Applications</span></span>
<span data-ttu-id="97294-103">Dieses Thema enthält eine Übersicht über das Verpacken von Schriftarten mit [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="97294-103">This topic provides an overview of how to package fonts with your [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="97294-104">Wie die meisten Arten von Software werden Schriftartdateien eher lizenziert als verkauft.</span><span class="sxs-lookup"><span data-stu-id="97294-104">As with most types of software, font files are licensed, rather than sold.</span></span> <span data-ttu-id="97294-105">Lizenzen, die die Verwendung von Schriftarten steuern, unterscheiden sich von Hersteller zu Hersteller, aber in den meisten Lizenzen, einschließlich derjenigen, die die Schriftarten von Microsoft für Anwendungen und Windows abdecken, ist es nicht zulässig, dass die Schriftarten in Anwendungen eingebettet oder anderweitig neu verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="97294-105">Licenses that govern the use of fonts vary from vendor to vendor but in general most licenses, including those covering the fonts Microsoft supplies with applications and Windows, do not allow the fonts to be embedded within applications or otherwise redistributed.</span></span> <span data-ttu-id="97294-106">Deshalb liegt es in Ihrer Verantwortung als Entwickler sicherzustellen, dass Sie über die erforderlichen Lizenzrechte für alle Schriftarten verfügen, die Sie in eine Anwendung einbetten oder anderweitig verbreiten.</span><span class="sxs-lookup"><span data-stu-id="97294-106">Therefore, as a developer it is your responsibility to ensure that you have the required license rights for any font you embed within an application or otherwise redistribute.</span></span>  

<a name="introduction_to_packaging_fonts"></a>
## <a name="introduction-to-packaging-fonts"></a><span data-ttu-id="97294-107">Einführung in das Verpacken von Schriftarten</span><span class="sxs-lookup"><span data-stu-id="97294-107">Introduction to Packaging Fonts</span></span>  
 <span data-ttu-id="97294-108">Sie können Schriftarten problemlos als Ressourcen in Ihren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen Verpacken, um den Text der Benutzeroberfläche und andere textbasierte Inhaltstypen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="97294-108">You can easily package fonts as resources within your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications to display user interface text and other types of text based content.</span></span> <span data-ttu-id="97294-109">Die Schriftarten können getrennt von den Assemblydateien oder eingebettet in die Assemblydateien der Anwendung vorkommen.</span><span class="sxs-lookup"><span data-stu-id="97294-109">The fonts can be separate from or embedded within the application's assembly files.</span></span> <span data-ttu-id="97294-110">Sie können auch eine Schriftartenbibliothek nur für Ressourcen erstellen, auf die die Anwendung verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="97294-110">You can also create a resource-only font library, which your application can reference.</span></span>  
  
 <span data-ttu-id="97294-111">OpenType-und TrueType-® Schriftarten enthalten das Typflag fstype, das Schriftart Einbettungs Lizenzierungs Rechte für die Schriftart angibt.</span><span class="sxs-lookup"><span data-stu-id="97294-111">OpenType and TrueType® fonts contain a type flag, fsType, that indicates font embedding licensing rights for the font.</span></span> <span data-ttu-id="97294-112">Dieses Typflag bezieht sich jedoch nur auf eingebettete Schriftarten, die in einem Dokument gespeichert sind, und nicht auf Schriftarten, die in eine Anwendung eingebettet sind.</span><span class="sxs-lookup"><span data-stu-id="97294-112">However, this type flag only refers to embedded fonts stored in a document–it does not refer to fonts embedded in an application.</span></span> <span data-ttu-id="97294-113">Sie können die Schriftart Einbettungs Rechte für eine Schriftart abrufen, indem <xref:System.Windows.Media.GlyphTypeface> Sie ein-Objekt erstellen <xref:System.Windows.Media.GlyphTypeface.EmbeddingRights%2A> und auf seine-Eigenschaft verweisen.</span><span class="sxs-lookup"><span data-stu-id="97294-113">You can retrieve the font embedding rights for a font by creating a <xref:System.Windows.Media.GlyphTypeface> object and referencing its <xref:System.Windows.Media.GlyphTypeface.EmbeddingRights%2A> property.</span></span> <span data-ttu-id="97294-114">Weitere Informationen zum fstype-Flag finden Sie im Abschnitt "OS/2 und Windows-Metriken" der [OpenType-Spezifikation](https://www.microsoft.com/typography/otspec/os2.htm) .</span><span class="sxs-lookup"><span data-stu-id="97294-114">Refer to the "OS/2 and Windows Metrics" section of the [OpenType Specification](https://www.microsoft.com/typography/otspec/os2.htm) for more information on the fsType flag.</span></span>  
  
 <span data-ttu-id="97294-115">Die [Microsoft](https://docs.microsoft.com/typography/) -Typografiewebsite enthält Kontaktinformationen, die Ihnen helfen können, einen bestimmten Schriftart Hersteller zu finden oder einen Schriftart Anbieter für benutzerdefinierte arbeiten zu finden.</span><span class="sxs-lookup"><span data-stu-id="97294-115">The [Microsoft Typography](https://docs.microsoft.com/typography/) Web site includes contact information that can help you locate a particular font vendor or find a font vendor for custom work.</span></span>  
  
<a name="adding_fonts_as_content_items"></a>
## <a name="adding-fonts-as-content-items"></a><span data-ttu-id="97294-116">Hinzufügen von Schriftarten als Inhaltselemente</span><span class="sxs-lookup"><span data-stu-id="97294-116">Adding Fonts as Content Items</span></span>  
 <span data-ttu-id="97294-117">Sie können Schriftarten als Projektinhaltselemente zu Ihrer Anwendung hinzufügen, die von den Assemblydateien der Anwendung getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="97294-117">You can add fonts to your application as project content items that are separate from the application's assembly files.</span></span> <span data-ttu-id="97294-118">Dies bedeutet, dass Inhaltselemente nicht als Ressourcen in eine Assembly eingebettet werden.</span><span class="sxs-lookup"><span data-stu-id="97294-118">This means that content items are not embedded as resources within an assembly.</span></span> <span data-ttu-id="97294-119">In der folgenden Beispielprojektdatei wird veranschaulicht, wie Inhaltselemente definiert werden.</span><span class="sxs-lookup"><span data-stu-id="97294-119">The following project file example shows how to define content items.</span></span>  
  
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
  
 <span data-ttu-id="97294-120">Um sicherzustellen, dass die Anwendung die Schriftarten zur Laufzeit verwenden kann, müssen die Schriftarten im Bereitstellungsverzeichnis der Anwendung zugänglich sein.</span><span class="sxs-lookup"><span data-stu-id="97294-120">In order to ensure that the application can use the fonts at run time, the fonts must be accessible in the application's deployment directory.</span></span> <span data-ttu-id="97294-121">Mithilfe `<CopyToOutputDirectory>` des-Elements in der Projektdatei der Anwendung können Sie die Schriftarten während des Buildprozesses automatisch in das Anwendungs Bereitstellungs Verzeichnis kopieren.</span><span class="sxs-lookup"><span data-stu-id="97294-121">The `<CopyToOutputDirectory>` element in the application's project file allows you to automatically copy the fonts to the application deployment directory during the build process.</span></span> <span data-ttu-id="97294-122">In der folgenden Beispielprojektdatei wird veranschaulicht, wie Schriftarten in das Bereitstellungsverzeichnis kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="97294-122">The following project file example shows how to copy fonts to the deployment directory.</span></span>  
  
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
  
 <span data-ttu-id="97294-123">Im folgenden Codebeispiel wird veranschaulicht, wie auf die Schriftart der Anwendung als Inhaltselement verwiesen wird. Das Inhaltselement, auf das verwiesen wird, muss sich im selben Verzeichnis wie die Assemblydateien der Anwendung befinden.</span><span class="sxs-lookup"><span data-stu-id="97294-123">The following code example shows how to reference the application's font as a content item—the referenced content item must be in the same directory as the application's assembly files.</span></span>  
  
 [!code-xaml[FontSnippets#FontPackageSnippet8](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet8)]  
  
<a name="adding_fonts_as_resource_items"></a>
## <a name="adding-fonts-as-resource-items"></a><span data-ttu-id="97294-124">Hinzufügen von Schriftarten als Ressourcenelemente</span><span class="sxs-lookup"><span data-stu-id="97294-124">Adding Fonts as Resource Items</span></span>  
 <span data-ttu-id="97294-125">Sie können Schriftarten als Projektressourcenelemente zu Ihrer Anwendung hinzufügen, die in die Assemblydateien der Anwendung eingebettet werden.</span><span class="sxs-lookup"><span data-stu-id="97294-125">You can add fonts to your application as project resource items that are embedded within the application's assembly files.</span></span> <span data-ttu-id="97294-126">Die Verwendung eines separaten Unterverzeichnisses für Ressourcen hilft beim Organisieren der Projektdateien der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="97294-126">Using a separate subdirectory for resources helps to organize the application's project files.</span></span> <span data-ttu-id="97294-127">In der folgenden Beispielprojektdatei wird veranschaulicht, wie Schriftarten als Ressourcenelemente in einem separaten Unterverzeichnis definiert werden.</span><span class="sxs-lookup"><span data-stu-id="97294-127">The following project file example shows how to define fonts as resource items in a separate subdirectory.</span></span>  
  
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
> <span data-ttu-id="97294-128">Wenn Sie der Anwendung Schriftarten als Ressourcen hinzufügen, stellen Sie sicher, dass `<Resource>` Sie das-Element und `<EmbeddedResource>` nicht das-Element in der Projektdatei der Anwendung festlegen.</span><span class="sxs-lookup"><span data-stu-id="97294-128">When you add fonts as resources to your application, make sure you are setting the `<Resource>` element, and not the `<EmbeddedResource>` element in your application's project file.</span></span> <span data-ttu-id="97294-129">Das `<EmbeddedResource>` -Element für die Buildaktion wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="97294-129">The `<EmbeddedResource>` element for the build action is not supported.</span></span>  
  
 <span data-ttu-id="97294-130">Im folgenden Markupbeispiel wird veranschaulicht, wie auf die Schriftartenressourcen der Anwendung verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="97294-130">The following markup example shows how to reference the application's font resources.</span></span>  
  
 [!code-xaml[FontSnippets#FontPackageSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet1)]  
  
### <a name="referencing-font-resource-items-from-code"></a><span data-ttu-id="97294-131">Verweisen auf Schriftartenressourcenelemente aus Code</span><span class="sxs-lookup"><span data-stu-id="97294-131">Referencing Font Resource Items from Code</span></span>  
 <span data-ttu-id="97294-132">Um auf Schriftart Ressourcen Elemente aus dem Code zu verweisen, müssen Sie einen zweiteiligen Schriftart Ressourcen Verweis angeben: der Basis-Uniform Resource Identifier (URI). und den Schriftart Speicherort Verweis.</span><span class="sxs-lookup"><span data-stu-id="97294-132">In order to reference font resource items from code, you must supply a two-part font resource reference: the base uniform resource identifier (URI); and the font location reference.</span></span> <span data-ttu-id="97294-133">Diese Werte werden als Parameter für die <xref:System.Windows.Media.FontFamily.%23ctor%2A> -Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="97294-133">These values are used as the parameters for the <xref:System.Windows.Media.FontFamily.%23ctor%2A> method.</span></span> <span data-ttu-id="97294-134">Im folgenden Codebeispiel wird gezeigt, wie auf die Schriftarten Ressourcen der Anwendung im Projekt Unterverzeichnis `resources`mit dem Namen verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="97294-134">The following code example shows how to reference the application's font resources in the project subdirectory called `resources`.</span></span>  
  
 [!code-csharp[FontSnippets#FontPackageSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet2)]
 [!code-vb[FontSnippets#FontPackageSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet2)]  
  
 <span data-ttu-id="97294-135">Der Basis-URI (Uniform Resource Identifier) kann das Anwendungs Unterverzeichnis enthalten, in dem sich die Schriftart Ressource befindet.</span><span class="sxs-lookup"><span data-stu-id="97294-135">The base uniform resource identifier (URI) can include the application subdirectory where the font resource resides.</span></span> <span data-ttu-id="97294-136">In diesem Fall muss die Schriftart für den Schriftart Speicherort nicht ein Verzeichnis angeben, sondern eine führende "`./`" enthalten, die angibt, dass sich die Schriftart Ressource in demselben Verzeichnis befindet, das durch den Basis-URI (Uniform Resource Identifier) angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="97294-136">In this case, the font location reference would not need to specify a directory, but would have to include a leading "`./`", which indicates the font resource is in the same directory specified by the base uniform resource identifier (URI).</span></span> <span data-ttu-id="97294-137">Im folgenden Codebeispiel wird eine alternative Möglichkeit veranschaulicht, wie auf das Schriftartenressourcenelement verwiesen werden kann. Es entspricht dem vorherigen Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="97294-137">The following code example shows an alternate way of referencing the font resource item—it is equivalent to the previous code example.</span></span>  
  
 [!code-csharp[FontSnippets#FontPackageSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet5)]
 [!code-vb[FontSnippets#FontPackageSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet5)]  
  
### <a name="referencing-fonts-from-the-same-application-subdirectory"></a><span data-ttu-id="97294-138">Verweisen auf Schriftarten aus dem gleichen Anwendungsunterverzeichnis</span><span class="sxs-lookup"><span data-stu-id="97294-138">Referencing Fonts from the Same Application Subdirectory</span></span>  
 <span data-ttu-id="97294-139">Sie können Anwendungsinhalt und Ressourcendateien im selben benutzerdefinierten Unterverzeichnis Ihres Anwendungsprojekts platzieren.</span><span class="sxs-lookup"><span data-stu-id="97294-139">You can place both application content and resource files within the same user-defined subdirectory of your application project.</span></span> <span data-ttu-id="97294-140">In der folgenden Beispielprojektdatei wird veranschaulicht, wie eine Inhaltsseite und Schriftartenressourcen im selben Unterverzeichnis definiert werden.</span><span class="sxs-lookup"><span data-stu-id="97294-140">The following project file example shows a content page and font resources defined in the same subdirectory.</span></span>  
  
```xml  
<ItemGroup>  
  <Page Include="pages\HomePage.xaml" />  
</ItemGroup>  
<ItemGroup>  
  <Resource Include="pages\Peric.ttf" />  
  <Resource Include="pages\Pericl.ttf" />  
</ItemGroup>  
```  
  
 <span data-ttu-id="97294-141">Da sich Anwendungsinhalt und Schriftart im selben Unterverzeichnis befinden, ist der Schriftartenverweis relativ zum Anwendungsinhalt.</span><span class="sxs-lookup"><span data-stu-id="97294-141">Since the application content and font are in the same subdirectory, the font reference is relative to the application content.</span></span> <span data-ttu-id="97294-142">In den folgenden Beispielen wird veranschaulicht, wie auf die Schriftartenressource der Anwendung verwiesen werden kann, wenn sich die Schriftart im selben Verzeichnis wie die Anwendung befindet.</span><span class="sxs-lookup"><span data-stu-id="97294-142">The following examples show how to reference the application's font resource when the font is in the same directory as the application.</span></span>  
  
 [!code-xaml[FontSnippets#FontPackageSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml#fontpackagesnippet3)]  
  
 [!code-csharp[FontSnippets#FontPackageSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml.cs#fontpackagesnippet4)]
 [!code-vb[FontSnippets#FontPackageSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/pages/homepage.xaml.vb#fontpackagesnippet4)]  
  
### <a name="enumerating-fonts-in-an-application"></a><span data-ttu-id="97294-143">Auflisten von Schriftarten in einer Anwendung</span><span class="sxs-lookup"><span data-stu-id="97294-143">Enumerating Fonts in an Application</span></span>  
 <span data-ttu-id="97294-144">Um Schriftarten als Ressourcen Elemente in Ihrer Anwendung aufzulisten, verwenden Sie entweder <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> die <xref:System.Windows.Media.Fonts.GetTypefaces%2A> -oder die-Methode.</span><span class="sxs-lookup"><span data-stu-id="97294-144">To enumerate fonts as resource items in your application, use either the <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> or <xref:System.Windows.Media.Fonts.GetTypefaces%2A> method.</span></span> <span data-ttu-id="97294-145">Im folgenden Beispiel wird gezeigt, wie die <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> -Methode verwendet wird, um <xref:System.Windows.Media.FontFamily> die Auflistung von-Objekten aus dem Speicherort der Anwendungs Schriftart zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="97294-145">The following example shows how to use the <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> method to return the collection of <xref:System.Windows.Media.FontFamily> objects from the application font location.</span></span> <span data-ttu-id="97294-146">In diesem Fall enthält die Anwendung ein Unterverzeichnis mit dem Namen „Ressourcen“.</span><span class="sxs-lookup"><span data-stu-id="97294-146">In this case, the application contains a subdirectory named "resources".</span></span>  
  
 [!code-csharp[FontSnippets#FontsSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet3)]
 [!code-vb[FontSnippets#FontsSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet3)]  
  
 <span data-ttu-id="97294-147">Im folgenden Beispiel wird gezeigt, wie die <xref:System.Windows.Media.Fonts.GetTypefaces%2A> -Methode verwendet wird, um <xref:System.Windows.Media.Typeface> die Auflistung von-Objekten aus dem Speicherort der Anwendungs Schriftart zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="97294-147">The following example shows how to use the <xref:System.Windows.Media.Fonts.GetTypefaces%2A> method to return the collection of <xref:System.Windows.Media.Typeface> objects from the application font location.</span></span> <span data-ttu-id="97294-148">In diesem Fall enthält die Anwendung ein Unterverzeichnis mit dem Namen „Ressourcen“.</span><span class="sxs-lookup"><span data-stu-id="97294-148">In this case, the application contains a subdirectory named "resources".</span></span>  
  
 [!code-csharp[FontSnippets#FontsSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet7)]
 [!code-vb[FontSnippets#FontsSnippet7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet7)]  
  
<a name="creating_a_font_resource_library"></a>
## <a name="creating-a-font-resource-library"></a><span data-ttu-id="97294-149">Erstellen einer Schriftartenressourcenbibliothek</span><span class="sxs-lookup"><span data-stu-id="97294-149">Creating a Font Resource Library</span></span>  
 <span data-ttu-id="97294-150">Sie können eine Bibliothek nur für Ressourcen erstellen, die ausschließlich Schriftarten enthält. In dieser Art von Bibliothek ist kein Code enthalten.</span><span class="sxs-lookup"><span data-stu-id="97294-150">You can create a resource-only library that contains only fonts—no code is part of this type of library project.</span></span> <span data-ttu-id="97294-151">Das Erstellen einer Bibliothek nur für Ressourcen dient häufig dem Entkoppeln von Ressourcen vom Anwendungscode, der sie verwendet.</span><span class="sxs-lookup"><span data-stu-id="97294-151">Creating a resource-only library is a common technique for decoupling resources from the application code that uses them.</span></span> <span data-ttu-id="97294-152">Dies ermöglicht außerdem, dass die Bibliotheksassembly in mehreren Anwendungsprojekten enthalten sein kann.</span><span class="sxs-lookup"><span data-stu-id="97294-152">This also allows the library assembly to be included with multiple application projects.</span></span> <span data-ttu-id="97294-153">In der folgenden Beispielprojektdatei werden die Hauptbestandteile einer Bibliothek nur für Ressourcen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="97294-153">The following project file example shows the key portions of a resource-only library project.</span></span>  
  
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
  
### <a name="referencing-a-font-in-a-resource-library"></a><span data-ttu-id="97294-154">Verweisen auf eine Schriftart in einer Ressourcenbibliothek</span><span class="sxs-lookup"><span data-stu-id="97294-154">Referencing a Font in a Resource Library</span></span>  
 <span data-ttu-id="97294-155">Um aus Ihrer Anwendung auf eine Schriftart in einer Ressourcenbibliothek zu verweisen, müssen Sie dem Verweis auf die Schriftart den Namen der Bibliotheksassembly voranstellen.</span><span class="sxs-lookup"><span data-stu-id="97294-155">To reference a font in a resource library from your application, you must prefix the font reference with the name of the library assembly.</span></span> <span data-ttu-id="97294-156">In diesem Fall ist die Schriftartenressourcenassembly „FontLibrary“.</span><span class="sxs-lookup"><span data-stu-id="97294-156">In this case, the font resource assembly is "FontLibrary".</span></span> <span data-ttu-id="97294-157">Verwenden Sie ein Semikolon (;), um den Assemblynamen vom Verweis innerhalb der Assembly zu trennen.</span><span class="sxs-lookup"><span data-stu-id="97294-157">To separate the assembly name from the reference within the assembly, use a ';' character.</span></span> <span data-ttu-id="97294-158">Durch Hinzufügen des Schlüsselworts „Component“ gefolgt vom Verweis auf den Namen der Schriftart wird der Verweis auf die Ressource der Schriftartenbibliothek vervollständigt.</span><span class="sxs-lookup"><span data-stu-id="97294-158">Adding the "Component" keyword followed by the reference to the font name completes the full reference to the font library's resource.</span></span> <span data-ttu-id="97294-159">Im folgenden Codebeispiel wird veranschaulicht, wie auf eine Schriftart in einer Ressourcenbibliotheksassembly verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="97294-159">The following code example shows how to reference a font in a resource library assembly.</span></span>  
  
 [!code-xaml[OpenTypeFontsSample#OpenTypeFontsSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontsSample/CS/Kootenay.xaml#opentypefontssample1)]  
  
> [!NOTE]
> <span data-ttu-id="97294-160">Dieses SDK enthält eine Reihe von OpenType-Beispiel Schriftarten, die Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mit-Anwendungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="97294-160">This SDK contains a set of sample OpenType fonts that you can use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span> <span data-ttu-id="97294-161">Die Schriftarten werden in einer Bibliothek nur für Ressourcen definiert.</span><span class="sxs-lookup"><span data-stu-id="97294-161">The fonts are defined in a resource-only library.</span></span> <span data-ttu-id="97294-162">Weitere Informationen finden Sie unter [Sample OpenType Font Pack](sample-opentype-font-pack.md).</span><span class="sxs-lookup"><span data-stu-id="97294-162">For more information, see [Sample OpenType Font Pack](sample-opentype-font-pack.md).</span></span>  
  
<a name="limitations_on_font_usage"></a>
## <a name="limitations-on-font-usage"></a><span data-ttu-id="97294-163">Einschränkungen der Verwendung von Schriftarten</span><span class="sxs-lookup"><span data-stu-id="97294-163">Limitations on Font Usage</span></span>  
 <span data-ttu-id="97294-164">In der folgenden Liste werden verschiedene Einschränkungen beim Verpacken und Verwenden von Schriftarten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in Anwendungen beschrieben:</span><span class="sxs-lookup"><span data-stu-id="97294-164">The following list describes several limitations on the packaging and use of fonts in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications:</span></span>  
  
- <span data-ttu-id="97294-165">\*\*Berechtigungsbits für die Schriftarteneinbettung: Von \*\* [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen werden keine Berechtigungsbits für die Schriftarteneinbettung überprüft oder durchgesetzt.</span><span class="sxs-lookup"><span data-stu-id="97294-165">**Font embedding permission bits:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not check or enforce any font embedding permission bits.</span></span> <span data-ttu-id="97294-166">Weitere Informationen finden Sie im Abschnitt [Introduction_to_Packing Fonts](#introduction_to_packaging_fonts) .</span><span class="sxs-lookup"><span data-stu-id="97294-166">See the [Introduction_to_Packing Fonts](#introduction_to_packaging_fonts) section for more information.</span></span>  
  
- <span data-ttu-id="97294-167">**Ursprungs Schriftarten von Ursprungsorten:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen erlauben keinen Schriftart Verweis auf einen HTTP-oder FTP-URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="97294-167">**Site of origin fonts:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not allow a font reference to an http or ftp uniform resource identifier (URI).</span></span>  
  
- <span data-ttu-id="97294-168">**Absoluter URI unter Verwendung des Pakets: Notation:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen ermöglichen es Ihnen nicht, ein <xref:System.Windows.Media.FontFamily> -Objekt Programm gesteuert mithilfe von "Pack:" als Teil des absoluten URI-Verweises (Uniform Resource Identifier) auf eine Schriftart zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="97294-168">**Absolute URI using the pack: notation:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not allow you to create a <xref:System.Windows.Media.FontFamily> object programmatically using "pack:" as part of the absolute uniform resource identifier (URI) reference to a font.</span></span> <span data-ttu-id="97294-169">Beispielsweise `"pack://application:,,,/resources/#Pericles Light"` ist ein ungültiger Schriftart Verweis.</span><span class="sxs-lookup"><span data-stu-id="97294-169">For example, `"pack://application:,,,/resources/#Pericles Light"` is an invalid font reference.</span></span>  
  
- <span data-ttu-id="97294-170">**Automatische Schriftarteneinbettung:** Zur Entwurfszeit werden die Suche nach der Schriftartenverwendung einer Anwendung und das automatische Einbetten der Schriftarten in die Ressourcen der Anwendung nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="97294-170">**Automatic font embedding:** During design time, there is no support for searching an application's use of fonts and automatically embedding the fonts in the application's resources.</span></span>  
  
- <span data-ttu-id="97294-171">**Schriftartteilmengen:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen unterstützen keine Erstellung von Schriftartteilmengen für Dokumente ohne festes Format.</span><span class="sxs-lookup"><span data-stu-id="97294-171">**Font subsets:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not support the creation of font subsets for non-fixed documents.</span></span>  
  
- <span data-ttu-id="97294-172">Bei einem falschen Verweis greift die Anwendung auf eine verfügbare Schriftart zurück.</span><span class="sxs-lookup"><span data-stu-id="97294-172">In cases where there is an incorrect reference, the application falls back to using an available font.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97294-173">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97294-173">See also</span></span>

- <xref:System.Windows.Documents.Typography>
- <xref:System.Windows.Media.FontFamily>
- [<span data-ttu-id="97294-174">Microsoft Typography: Links, News, and Contacts (Microsoft-Typografie: Links, Neuigkeiten und Kontakte)</span><span class="sxs-lookup"><span data-stu-id="97294-174">Microsoft Typography: Links, News, and Contacts</span></span>](https://docs.microsoft.com/typography/)
- [<span data-ttu-id="97294-175">OpenType-Spezifikation</span><span class="sxs-lookup"><span data-stu-id="97294-175">OpenType Specification</span></span>](https://www.microsoft.com/typography/otspec/)
- [<span data-ttu-id="97294-176">Features für OpenType-Schriftarten</span><span class="sxs-lookup"><span data-stu-id="97294-176">OpenType Font Features</span></span>](opentype-font-features.md)
- [<span data-ttu-id="97294-177">OpenType-Beispielschriftartenpaket</span><span class="sxs-lookup"><span data-stu-id="97294-177">Sample OpenType Font Pack</span></span>](sample-opentype-font-pack.md)
