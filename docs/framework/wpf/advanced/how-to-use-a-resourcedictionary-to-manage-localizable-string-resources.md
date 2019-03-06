---
title: 'Vorgehensweise: Verwalten lokalisierbarer Zeichenfolgenressourcen mit einem ResourceDictionary'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resources [WPF], packaging string resources
- packaging string resources [WPF]
- ResourceDictionary [WPF]
- localization [WPF], packaging string resources
ms.assetid: 19e7d9a5-20df-4ad3-b157-fe6515902e5e
ms.openlocfilehash: e28086d8c97070b854ebdea35fe347c64c5cd7ac
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377936"
---
# <a name="how-to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="de5d7-102">Vorgehensweise: Verwalten lokalisierbarer Zeichenfolgenressourcen mit einem ResourceDictionary</span><span class="sxs-lookup"><span data-stu-id="de5d7-102">How to: Use a ResourceDictionary to Manage Localizable String Resources</span></span>
<span data-ttu-id="de5d7-103">Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.ResourceDictionary> zum Paket lokalisierbarer Zeichenfolgenressourcen für Windows Presentation Foundation (WPF)-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="de5d7-103">This example shows how to use a <xref:System.Windows.ResourceDictionary> to package localizable string resources for Windows Presentation Foundation (WPF) applications.</span></span>  
  
### <a name="to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="de5d7-104">So verwenden Sie ResourceDictionary zum Verwalten lokalisierbarer Zeichenfolgenressourcen</span><span class="sxs-lookup"><span data-stu-id="de5d7-104">To use a ResourceDictionary to manage localizable string resources</span></span>  
  
1.  <span data-ttu-id="de5d7-105">Erstellen Sie eine <xref:System.Windows.ResourceDictionary> , enthält die Zeichenfolgen, die Sie lokalisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="de5d7-105">Create a <xref:System.Windows.ResourceDictionary> that contains the strings you would like to localize.</span></span> <span data-ttu-id="de5d7-106">Der folgende Code zeigt ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="de5d7-106">The following code shows an example.</span></span>  
  
     [!code-xaml[StringLocalizationSample#StringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     <span data-ttu-id="de5d7-107">Dieser Code definiert eine Zeichenfolgenressource `localizedMessage`, des Typs <xref:System.String>, aus der <xref:System> Namespace in "mscorlib.dll".</span><span class="sxs-lookup"><span data-stu-id="de5d7-107">This code defines a string resource, `localizedMessage`, of type <xref:System.String>, from the <xref:System> namespace in mscorlib.dll.</span></span>  
  
2.  <span data-ttu-id="de5d7-108">Hinzufügen der <xref:System.Windows.ResourceDictionary> an Ihre Anwendung mithilfe des folgenden Codes.</span><span class="sxs-lookup"><span data-stu-id="de5d7-108">Add the <xref:System.Windows.ResourceDictionary> to your application, using the following code.</span></span>  
  
     [!code-xaml[StringLocalizationSample#ReferencingStringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3.  <span data-ttu-id="de5d7-109">Verwenden Sie die Zeichenfolge vom Markup mithilfe von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] wie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="de5d7-109">Use the string resource from markup, using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] like the following.</span></span>  
  
     [!code-xaml[StringLocalizationSample#GetLocalizedResourceFromMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4.  <span data-ttu-id="de5d7-110">Verwenden Sie die Zeichenfolge von CodeBehind mithilfe von Code so wie folgt.</span><span class="sxs-lookup"><span data-stu-id="de5d7-110">Use the string resource from code-behind, using code like the following.</span></span>  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5.  <span data-ttu-id="de5d7-111">Lokalisieren Sie die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="de5d7-111">Localize the application.</span></span> <span data-ttu-id="de5d7-112">Weitere Informationen finden Sie unter [Lokalisieren einer Anwendung](how-to-localize-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="de5d7-112">For more information, see [Localize an Application](how-to-localize-an-application.md).</span></span>
