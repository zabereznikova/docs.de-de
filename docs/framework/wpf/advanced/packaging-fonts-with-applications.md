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
ms.openlocfilehash: a822167ae5b2758a889c61eed5270e5abb01f961
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2019
ms.locfileid: "56583419"
---
# <a name="packaging-fonts-with-applications"></a><span data-ttu-id="9f1e9-102">Verpacken von Schriftarten mit Anwendungen</span><span class="sxs-lookup"><span data-stu-id="9f1e9-102">Packaging Fonts with Applications</span></span>
<span data-ttu-id="9f1e9-103">Dieses Thema enthält eine Übersicht über das Verpacken von Schriftarten mit Ihrem [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendung.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-103">This topic provides an overview of how to package fonts with your [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9f1e9-104">Wie die meisten Arten von Software werden Schriftartdateien eher lizenziert als verkauft.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-104">As with most types of software, font files are licensed, rather than sold.</span></span> <span data-ttu-id="9f1e9-105">Lizenzen, die die Verwendung von Schriftarten steuern, sind von Anbieter zu Anbieter jedoch im Allgemeinen die meisten Lizenzen, darunter auch die Schriftarten unterschiedlich [!INCLUDE[TLA#tla_ms#initcap](../../../../includes/tlasharptla-mssharpinitcap-md.md)] bereitstellt, mit Anwendungen und [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], lassen sich nicht auf die Schriftarten eingebettet in Anwendungen oder auf andere sein neu verteilt.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-105">Licenses that govern the use of fonts vary from vendor to vendor but in general most licenses, including those covering the fonts [!INCLUDE[TLA#tla_ms#initcap](../../../../includes/tlasharptla-mssharpinitcap-md.md)] supplies with applications and [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], do not allow the fonts to be embedded within applications or otherwise redistributed.</span></span> <span data-ttu-id="9f1e9-106">Deshalb liegt es in Ihrer Verantwortung als Entwickler sicherzustellen, dass Sie über die erforderlichen Lizenzrechte für alle Schriftarten verfügen, die Sie in eine Anwendung einbetten oder anderweitig verbreiten.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-106">Therefore, as a developer it is your responsibility to ensure that you have the required license rights for any font you embed within an application or otherwise redistribute.</span></span>  
  

  
<a name="introduction_to_packaging_fonts"></a>   
## <a name="introduction-to-packaging-fonts"></a><span data-ttu-id="9f1e9-107">Einführung in das Verpacken von Schriftarten</span><span class="sxs-lookup"><span data-stu-id="9f1e9-107">Introduction to Packaging Fonts</span></span>  
 <span data-ttu-id="9f1e9-108">Sie können Schriftarten problemlos als Ressourcen in Verpacken Ihrer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] basierende Anwendungen zum Anzeigen von Text der Benutzeroberfläche und anderen Typen von Text-Inhalt.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-108">You can easily package fonts as resources within your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications to display user interface text and other types of text based content.</span></span> <span data-ttu-id="9f1e9-109">Die Schriftarten können getrennt von den Assemblydateien oder eingebettet in die Assemblydateien der Anwendung vorkommen.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-109">The fonts can be separate from or embedded within the application's assembly files.</span></span> <span data-ttu-id="9f1e9-110">Sie können auch eine Schriftartenbibliothek nur für Ressourcen erstellen, auf die die Anwendung verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-110">You can also create a resource-only font library, which your application can reference.</span></span>  
  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] <span data-ttu-id="9f1e9-111">und [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)] Schriftarten ein Typflag, FsType, der angibt, für die schriftarteneinbettung Lizenzierung Rechte für die Schriftart enthalten.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-111">and [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)] fonts contain a type flag, fsType, that indicates font embedding licensing rights for the font.</span></span> <span data-ttu-id="9f1e9-112">Dieses Typflag bezieht sich jedoch nur auf eingebettete Schriftarten, die in einem Dokument gespeichert sind, und nicht auf Schriftarten, die in eine Anwendung eingebettet sind.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-112">However, this type flag only refers to embedded fonts stored in a document–it does not refer to fonts embedded in an application.</span></span> <span data-ttu-id="9f1e9-113">Können Sie abrufen, die für die schriftarteneinbettung Rechte für eine Schriftart durch das Erstellen einer <xref:System.Windows.Media.GlyphTypeface> -Objekt und verweisen auf die <xref:System.Windows.Media.GlyphTypeface.EmbeddingRights%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-113">You can retrieve the font embedding rights for a font by creating a <xref:System.Windows.Media.GlyphTypeface> object and referencing its <xref:System.Windows.Media.GlyphTypeface.EmbeddingRights%2A> property.</span></span> <span data-ttu-id="9f1e9-114">Finden Sie im Abschnitt "OS/2 and Windows Metrics", der die [OpenType-Spezifikation](https://www.microsoft.com/typography/otspec/os2.htm) für Weitere Informationen zum FsType-Flag.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-114">Refer to the "OS/2 and Windows Metrics" section of the [OpenType Specification](https://www.microsoft.com/typography/otspec/os2.htm) for more information on the fsType flag.</span></span>  
  
 <span data-ttu-id="9f1e9-115">Die [Microsoft Typography](https://docs.microsoft.com/typography/) Website enthält Kontaktinformationen, mit denen Sie suchen Sie einen bestimmten Händler oder einen Händler für benutzerdefinierte Schriftarten zu finden.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-115">The [Microsoft Typography](https://docs.microsoft.com/typography/) Web site includes contact information that can help you locate a particular font vendor or find a font vendor for custom work.</span></span>  
  
<a name="adding_fonts_as_content_items"></a>   
## <a name="adding-fonts-as-content-items"></a><span data-ttu-id="9f1e9-116">Hinzufügen von Schriftarten als Inhaltselemente</span><span class="sxs-lookup"><span data-stu-id="9f1e9-116">Adding Fonts as Content Items</span></span>  
 <span data-ttu-id="9f1e9-117">Sie können Schriftarten als Projektinhaltselemente zu Ihrer Anwendung hinzufügen, die von den Assemblydateien der Anwendung getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-117">You can add fonts to your application as project content items that are separate from the application's assembly files.</span></span> <span data-ttu-id="9f1e9-118">Dies bedeutet, dass Inhaltselemente nicht als Ressourcen in eine Assembly eingebettet werden.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-118">This means that content items are not embedded as resources within an assembly.</span></span> <span data-ttu-id="9f1e9-119">In der folgenden Beispielprojektdatei wird veranschaulicht, wie Inhaltselemente definiert werden.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-119">The following project file example shows how to define content items.</span></span>  
  
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
  
 <span data-ttu-id="9f1e9-120">Um sicherzustellen, dass die Anwendung die Schriftarten zur Laufzeit verwenden kann, müssen die Schriftarten im Bereitstellungsverzeichnis der Anwendung zugänglich sein.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-120">In order to ensure that the application can use the fonts at run time, the fonts must be accessible in the application's deployment directory.</span></span> <span data-ttu-id="9f1e9-121">Die `<CopyToOutputDirectory>` -Element in der Projektdatei der Anwendung können Sie die Schriftarten in das Bereitstellungsverzeichnis der Anwendung während des Buildprozesses automatisch zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-121">The `<CopyToOutputDirectory>` element in the application's project file allows you to automatically copy the fonts to the application deployment directory during the build process.</span></span> <span data-ttu-id="9f1e9-122">In der folgenden Beispielprojektdatei wird veranschaulicht, wie Schriftarten in das Bereitstellungsverzeichnis kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-122">The following project file example shows how to copy fonts to the deployment directory.</span></span>  
  
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
  
 <span data-ttu-id="9f1e9-123">Im folgenden Codebeispiel wird veranschaulicht, wie auf die Schriftart der Anwendung als Inhaltselement verwiesen wird. Das Inhaltselement, auf das verwiesen wird, muss sich im selben Verzeichnis wie die Assemblydateien der Anwendung befinden.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-123">The following code example shows how to reference the application's font as a content item—the referenced content item must be in the same directory as the application's assembly files.</span></span>  
  
 [!code-xaml[FontSnippets#FontPackageSnippet8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet8)]  
  
<a name="adding_fonts_as_resource_items"></a>   
## <a name="adding-fonts-as-resource-items"></a><span data-ttu-id="9f1e9-124">Hinzufügen von Schriftarten als Ressourcenelemente</span><span class="sxs-lookup"><span data-stu-id="9f1e9-124">Adding Fonts as Resource Items</span></span>  
 <span data-ttu-id="9f1e9-125">Sie können Schriftarten als Projektressourcenelemente zu Ihrer Anwendung hinzufügen, die in die Assemblydateien der Anwendung eingebettet werden.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-125">You can add fonts to your application as project resource items that are embedded within the application's assembly files.</span></span> <span data-ttu-id="9f1e9-126">Die Verwendung eines separaten Unterverzeichnisses für Ressourcen hilft beim Organisieren der Projektdateien der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-126">Using a separate subdirectory for resources helps to organize the application's project files.</span></span> <span data-ttu-id="9f1e9-127">In der folgenden Beispielprojektdatei wird veranschaulicht, wie Schriftarten als Ressourcenelemente in einem separaten Unterverzeichnis definiert werden.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-127">The following project file example shows how to define fonts as resource items in a separate subdirectory.</span></span>  
  
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
>  <span data-ttu-id="9f1e9-128">Wenn Sie Ihrer Anwendung Schriftarten als Ressourcen hinzufügen, stellen Sie sicher, dass beim Festlegen des der `<Resource>` -Element, und nicht die `<EmbeddedResource>` -Element in Ihrer Anwendung-Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-128">When you add fonts as resources to your application, make sure you are setting the `<Resource>` element, and not the `<EmbeddedResource>` element in your application's project file.</span></span> <span data-ttu-id="9f1e9-129">Die `<EmbeddedResource>` -Element für die Buildaktion wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-129">The `<EmbeddedResource>` element for the build action is not supported.</span></span>  
  
 <span data-ttu-id="9f1e9-130">Im folgenden Markupbeispiel wird veranschaulicht, wie auf die Schriftartenressourcen der Anwendung verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-130">The following markup example shows how to reference the application's font resources.</span></span>  
  
 [!code-xaml[FontSnippets#FontPackageSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet1)]  
  
### <a name="referencing-font-resource-items-from-code"></a><span data-ttu-id="9f1e9-131">Verweisen auf Schriftartenressourcenelemente aus Code</span><span class="sxs-lookup"><span data-stu-id="9f1e9-131">Referencing Font Resource Items from Code</span></span>  
 <span data-ttu-id="9f1e9-132">Um schriftartenressourcenelemente aus Code verweisen zu können, müssen Sie einen zweiteiligen schriftartenressourcenverweis angeben: die Basis [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]; und den Speicherortverweis der Schriftart.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-132">In order to reference font resource items from code, you must supply a two-part font resource reference: the base [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]; and the font location reference.</span></span> <span data-ttu-id="9f1e9-133">Diese Werte werden verwendet, als Parameter für die <xref:System.Windows.Media.FontFamily.%23ctor%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-133">These values are used as the parameters for the <xref:System.Windows.Media.FontFamily.%23ctor%2A> method.</span></span> <span data-ttu-id="9f1e9-134">Im folgenden Codebeispiel wird veranschaulicht, wie auf die schriftartenressourcen der der Anwendung im Projektunterverzeichnis `resources`.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-134">The following code example shows how to reference the application's font resources in the project subdirectory called `resources`.</span></span>  
  
 [!code-csharp[FontSnippets#FontPackageSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet2)]
 [!code-vb[FontSnippets#FontPackageSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet2)]  
  
 <span data-ttu-id="9f1e9-135">Die Basis [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] zählen das Unterverzeichnis der Anwendung, wo sich die schriftartenressource befindet.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-135">The base [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] can include the application subdirectory where the font resource resides.</span></span> <span data-ttu-id="9f1e9-136">In diesem Fall der Verweis auf die Schriftart-Speicherort muss also kein Verzeichnis angeben, jedoch müsste ein vorangestelltes "`./`", womit die schriftartenressource im selben Verzeichnis angegeben, die von den Basis-ist [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f1e9-136">In this case, the font location reference would not need to specify a directory, but would have to include a leading "`./`", which indicates the font resource is in the same directory specified by the base [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)].</span></span> <span data-ttu-id="9f1e9-137">Im folgenden Codebeispiel wird eine alternative Möglichkeit veranschaulicht, wie auf das Schriftartenressourcenelement verwiesen werden kann. Es entspricht dem vorherigen Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-137">The following code example shows an alternate way of referencing the font resource item—it is equivalent to the previous code example.</span></span>  
  
 [!code-csharp[FontSnippets#FontPackageSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet5)]
 [!code-vb[FontSnippets#FontPackageSnippet5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet5)]  
  
### <a name="referencing-fonts-from-the-same-application-subdirectory"></a><span data-ttu-id="9f1e9-138">Verweisen auf Schriftarten aus dem gleichen Anwendungsunterverzeichnis</span><span class="sxs-lookup"><span data-stu-id="9f1e9-138">Referencing Fonts from the Same Application Subdirectory</span></span>  
 <span data-ttu-id="9f1e9-139">Sie können Anwendungsinhalt und Ressourcendateien im selben benutzerdefinierten Unterverzeichnis Ihres Anwendungsprojekts platzieren.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-139">You can place both application content and resource files within the same user-defined subdirectory of your application project.</span></span> <span data-ttu-id="9f1e9-140">In der folgenden Beispielprojektdatei wird veranschaulicht, wie eine Inhaltsseite und Schriftartenressourcen im selben Unterverzeichnis definiert werden.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-140">The following project file example shows a content page and font resources defined in the same subdirectory.</span></span>  
  
```xml  
<ItemGroup>  
  <Page Include="pages\HomePage.xaml" />  
</ItemGroup>  
<ItemGroup>  
  <Resource Include="pages\Peric.ttf" />  
  <Resource Include="pages\Pericl.ttf" />  
</ItemGroup>  
```  
  
 <span data-ttu-id="9f1e9-141">Da sich Anwendungsinhalt und Schriftart im selben Unterverzeichnis befinden, ist der Schriftartenverweis relativ zum Anwendungsinhalt.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-141">Since the application content and font are in the same subdirectory, the font reference is relative to the application content.</span></span> <span data-ttu-id="9f1e9-142">In den folgenden Beispielen wird veranschaulicht, wie auf die Schriftartenressource der Anwendung verwiesen werden kann, wenn sich die Schriftart im selben Verzeichnis wie die Anwendung befindet.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-142">The following examples show how to reference the application's font resource when the font is in the same directory as the application.</span></span>  
  
 [!code-xaml[FontSnippets#FontPackageSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml#fontpackagesnippet3)]  
  
 [!code-csharp[FontSnippets#FontPackageSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml.cs#fontpackagesnippet4)]
 [!code-vb[FontSnippets#FontPackageSnippet4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/pages/homepage.xaml.vb#fontpackagesnippet4)]  
  
### <a name="enumerating-fonts-in-an-application"></a><span data-ttu-id="9f1e9-143">Auflisten von Schriftarten in einer Anwendung</span><span class="sxs-lookup"><span data-stu-id="9f1e9-143">Enumerating Fonts in an Application</span></span>  
 <span data-ttu-id="9f1e9-144">Zum Auflisten von Schriftarten als Ressourcenelemente in Ihrer Anwendung verwenden Sie entweder die <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> oder <xref:System.Windows.Media.Fonts.GetTypefaces%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-144">To enumerate fonts as resource items in your application, use either the <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> or <xref:System.Windows.Media.Fonts.GetTypefaces%2A> method.</span></span> <span data-ttu-id="9f1e9-145">Das folgende Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> Methode zum Zurückgeben der Auflistung der <xref:System.Windows.Media.FontFamily> Objekte aus dem Speicherort der Schriftarten.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-145">The following example shows how to use the <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> method to return the collection of <xref:System.Windows.Media.FontFamily> objects from the application font location.</span></span> <span data-ttu-id="9f1e9-146">In diesem Fall enthält die Anwendung ein Unterverzeichnis mit dem Namen „Ressourcen“.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-146">In this case, the application contains a subdirectory named "resources".</span></span>  
  
 [!code-csharp[FontSnippets#FontsSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet3)]
 [!code-vb[FontSnippets#FontsSnippet3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet3)]  
  
 <span data-ttu-id="9f1e9-147">Das folgende Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.Fonts.GetTypefaces%2A> Methode zum Zurückgeben der Auflistung der <xref:System.Windows.Media.Typeface> Objekte aus dem Speicherort der Schriftarten.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-147">The following example shows how to use the <xref:System.Windows.Media.Fonts.GetTypefaces%2A> method to return the collection of <xref:System.Windows.Media.Typeface> objects from the application font location.</span></span> <span data-ttu-id="9f1e9-148">In diesem Fall enthält die Anwendung ein Unterverzeichnis mit dem Namen „Ressourcen“.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-148">In this case, the application contains a subdirectory named "resources".</span></span>  
  
 [!code-csharp[FontSnippets#FontsSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet7)]
 [!code-vb[FontSnippets#FontsSnippet7](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet7)]  
  
<a name="creating_a_font_resource_library"></a>   
## <a name="creating-a-font-resource-library"></a><span data-ttu-id="9f1e9-149">Erstellen einer Schriftartenressourcenbibliothek</span><span class="sxs-lookup"><span data-stu-id="9f1e9-149">Creating a Font Resource Library</span></span>  
 <span data-ttu-id="9f1e9-150">Sie können eine Bibliothek nur für Ressourcen erstellen, die ausschließlich Schriftarten enthält. In dieser Art von Bibliothek ist kein Code enthalten.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-150">You can create a resource-only library that contains only fonts—no code is part of this type of library project.</span></span> <span data-ttu-id="9f1e9-151">Das Erstellen einer Bibliothek nur für Ressourcen dient häufig dem Entkoppeln von Ressourcen vom Anwendungscode, der sie verwendet.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-151">Creating a resource-only library is a common technique for decoupling resources from the application code that uses them.</span></span> <span data-ttu-id="9f1e9-152">Dies ermöglicht außerdem, dass die Bibliotheksassembly in mehreren Anwendungsprojekten enthalten sein kann.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-152">This also allows the library assembly to be included with multiple application projects.</span></span> <span data-ttu-id="9f1e9-153">In der folgenden Beispielprojektdatei werden die Hauptbestandteile einer Bibliothek nur für Ressourcen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-153">The following project file example shows the key portions of a resource-only library project.</span></span>  
  
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
  
### <a name="referencing-a-font-in-a-resource-library"></a><span data-ttu-id="9f1e9-154">Verweisen auf eine Schriftart in einer Ressourcenbibliothek</span><span class="sxs-lookup"><span data-stu-id="9f1e9-154">Referencing a Font in a Resource Library</span></span>  
 <span data-ttu-id="9f1e9-155">Um aus Ihrer Anwendung auf eine Schriftart in einer Ressourcenbibliothek zu verweisen, müssen Sie dem Verweis auf die Schriftart den Namen der Bibliotheksassembly voranstellen.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-155">To reference a font in a resource library from your application, you must prefix the font reference with the name of the library assembly.</span></span> <span data-ttu-id="9f1e9-156">In diesem Fall ist die Schriftartenressourcenassembly „FontLibrary“.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-156">In this case, the font resource assembly is "FontLibrary".</span></span> <span data-ttu-id="9f1e9-157">Verwenden Sie ein Semikolon (;), um den Assemblynamen vom Verweis innerhalb der Assembly zu trennen.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-157">To separate the assembly name from the reference within the assembly, use a ';' character.</span></span> <span data-ttu-id="9f1e9-158">Durch Hinzufügen des Schlüsselworts „Component“ gefolgt vom Verweis auf den Namen der Schriftart wird der Verweis auf die Ressource der Schriftartenbibliothek vervollständigt.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-158">Adding the "Component" keyword followed by the reference to the font name completes the full reference to the font library's resource.</span></span> <span data-ttu-id="9f1e9-159">Im folgenden Codebeispiel wird veranschaulicht, wie auf eine Schriftart in einer Ressourcenbibliotheksassembly verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-159">The following code example shows how to reference a font in a resource library assembly.</span></span>  
  
 [!code-xaml[OpenTypeFontsSample#OpenTypeFontsSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontsSample/CS/Kootenay.xaml#opentypefontssample1)]  
  
> [!NOTE]
>  <span data-ttu-id="9f1e9-160">Dieses SDK enthält eine Reihe von [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Schriftarten, mit denen Sie mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-160">This SDK contains a set of sample [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] fonts that you can use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span> <span data-ttu-id="9f1e9-161">Die Schriftarten werden in einer Bibliothek nur für Ressourcen definiert.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-161">The fonts are defined in a resource-only library.</span></span> <span data-ttu-id="9f1e9-162">Weitere Informationen finden Sie unter [OpenType-Beispielschriftartenpaket](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md).</span><span class="sxs-lookup"><span data-stu-id="9f1e9-162">For more information, see [Sample OpenType Font Pack](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md).</span></span>  
  
<a name="limitations_on_font_usage"></a>   
## <a name="limitations-on-font-usage"></a><span data-ttu-id="9f1e9-163">Einschränkungen der Verwendung von Schriftarten</span><span class="sxs-lookup"><span data-stu-id="9f1e9-163">Limitations on Font Usage</span></span>  
 <span data-ttu-id="9f1e9-164">Die folgende Liste beschreibt einige Einschränkungen für das Verpacken und die Verwendung von Schriftarten in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen:</span><span class="sxs-lookup"><span data-stu-id="9f1e9-164">The following list describes several limitations on the packaging and use of fonts in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications:</span></span>  
  
-   <span data-ttu-id="9f1e9-165">**Berechtigungsbits für die Schriftarteneinbettung:** Von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen werden keine Berechtigungsbits für die Schriftarteneinbettung überprüft oder durchgesetzt.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-165">**Font embedding permission bits:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not check or enforce any font embedding permission bits.</span></span> <span data-ttu-id="9f1e9-166">Finden Sie unter den [Einführung in das Verpacken von Schriftarten](#introduction_to_packaging_fonts) Abschnitt, um weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-166">See the [Introduction_to_Packing Fonts](#introduction_to_packaging_fonts) section for more information.</span></span>  
  
-   <span data-ttu-id="9f1e9-167">**Site der Ursprungsschriftarten:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen lassen sich nicht auf einen Schriftartverweis auf einen HTTP- oder FTP- [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f1e9-167">**Site of origin fonts:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not allow a font reference to an http or ftp [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)].</span></span>  
  
-   <span data-ttu-id="9f1e9-168">**Absoluter URI mit Pack: Notation:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen nicht erlauben Ihnen die Erstellung einer <xref:System.Windows.Media.FontFamily> -Objekt programmgesteuert mit "Pack:" als Bestandteil des absoluten [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] Verweis auf eine Schriftart.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-168">**Absolute URI using the pack: notation:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not allow you to create a <xref:System.Windows.Media.FontFamily> object programmatically using "pack:" as part of the absolute [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] reference to a font.</span></span> <span data-ttu-id="9f1e9-169">Z. B. `"pack://application:,,,/resources/#Pericles Light"` ist ein ungültiger schriftartenverweis.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-169">For example, `"pack://application:,,,/resources/#Pericles Light"` is an invalid font reference.</span></span>  
  
-   <span data-ttu-id="9f1e9-170">**Automatische schriftarteneinbettung:** Während der Entwurfszeit besteht keine Unterstützung für die Suche nach einer Anwendung die Verwendung von Schriftarten und automatische Einbetten der Schriftarten in die Ressourcen der Anwendung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-170">**Automatic font embedding:** During design time, there is no support for searching an application's use of fonts and automatically embedding the fonts in the application's resources.</span></span>  
  
-   <span data-ttu-id="9f1e9-171">**Schriftartteilmengen:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen unterstützen keine Erstellung von Schriftartteilmengen für Dokumente ohne festes Format.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-171">**Font subsets:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not support the creation of font subsets for non-fixed documents.</span></span>  
  
-   <span data-ttu-id="9f1e9-172">Bei einem falschen Verweis greift die Anwendung auf eine verfügbare Schriftart zurück.</span><span class="sxs-lookup"><span data-stu-id="9f1e9-172">In cases where there is an incorrect reference, the application falls back to using an available font.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f1e9-173">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f1e9-173">See also</span></span>
- <xref:System.Windows.Documents.Typography>
- <xref:System.Windows.Media.FontFamily>
- [<span data-ttu-id="9f1e9-174">Microsoft-Typografie: Links, Neuigkeiten und Kontakte</span><span class="sxs-lookup"><span data-stu-id="9f1e9-174">Microsoft Typography: Links, News, and Contacts</span></span>](https://docs.microsoft.com/typography/)
- [<span data-ttu-id="9f1e9-175">OpenType-Spezifikation</span><span class="sxs-lookup"><span data-stu-id="9f1e9-175">OpenType Specification</span></span>](https://www.microsoft.com/typography/otspec/)
- [<span data-ttu-id="9f1e9-176">Features für OpenType-Schriftarten</span><span class="sxs-lookup"><span data-stu-id="9f1e9-176">OpenType Font Features</span></span>](../../../../docs/framework/wpf/advanced/opentype-font-features.md)
- [<span data-ttu-id="9f1e9-177">OpenType-Beispielschriftartenpaket</span><span class="sxs-lookup"><span data-stu-id="9f1e9-177">Sample OpenType Font Pack</span></span>](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md)
