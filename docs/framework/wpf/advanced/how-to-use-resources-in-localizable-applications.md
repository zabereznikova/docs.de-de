---
title: 'Vorgehensweise: Verwenden von Ressourcen in lokalisierbaren Anwendungen'
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
ms.openlocfilehash: 3634bb72cbacfb02b0a1230a47a1664cb8ce5009
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68238461"
---
# <a name="how-to-use-resources-in-localizable-applications"></a><span data-ttu-id="a4c93-102">Vorgehensweise: Verwenden von Ressourcen in lokalisierbaren Anwendungen</span><span class="sxs-lookup"><span data-stu-id="a4c93-102">How to: Use Resources in Localizable Applications</span></span>
<span data-ttu-id="a4c93-103">Lokalisierung bezeichnet die Anpassung einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für andere Kulturen.</span><span class="sxs-lookup"><span data-stu-id="a4c93-103">Localization means to adapt a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to different cultures.</span></span> <span data-ttu-id="a4c93-104">Dazu müssen Text (z.B. Titel), Beschriftungen, Listenfeldelemente usw. übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="a4c93-104">To do this, text such as titles, captions, list box items and so forth have to be translated.</span></span> <span data-ttu-id="a4c93-105">Damit die Übersetzung vereinfacht wird, werden die zu übersetzten Elemente in Ressourcendateien gesammelt.</span><span class="sxs-lookup"><span data-stu-id="a4c93-105">To make translation easier the items to be translated are collected into resource files.</span></span> <span data-ttu-id="a4c93-106">Finden Sie unter [Lokalisieren einer Anwendung](how-to-localize-an-application.md) für Informationen zum Erstellen einer Ressourcendatei für die Lokalisierung.</span><span class="sxs-lookup"><span data-stu-id="a4c93-106">See [Localize an Application](how-to-localize-an-application.md) for information on how to create a resource file for localization.</span></span> <span data-ttu-id="a4c93-107">Zu einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Anwendung lokalisierbar sein, müssen Entwickler alle lokalisierbaren Ressourcen in einer Ressourcenassembly erstellen.</span><span class="sxs-lookup"><span data-stu-id="a4c93-107">To make a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application localizable, developers need to build all the localizable resources into a resource assembly.</span></span> <span data-ttu-id="a4c93-108">Die Ressourcenassembly wird in verschiedenen Sprachen lokalisiert, und das Code-Behind verwendet Ressourcenverwaltungs-API zum Laden.</span><span class="sxs-lookup"><span data-stu-id="a4c93-108">The resource assembly is localized into different languages, and the code-behind uses resource management API to load.</span></span> <span data-ttu-id="a4c93-109">Einer der erforderlichen Dateien für eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung ist eine Projektdatei (.proj).</span><span class="sxs-lookup"><span data-stu-id="a4c93-109">One of the files required for a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application is a project file (.proj).</span></span> <span data-ttu-id="a4c93-110">Alle Ressourcen, die Sie in Ihrer Anwendung verwenden, sollten in der Projektdatei enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="a4c93-110">All resources that you use in your application should be included in the project file.</span></span> <span data-ttu-id="a4c93-111">Dies wird im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a4c93-111">The following code example shows this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4c93-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a4c93-112">Example</span></span>  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 `<Resource Include="data\picture1.jpg"/>`  
  
 `<EmbeddedResource Include="data\stringtable.en-US.restext"/>`  
  
 <span data-ttu-id="a4c93-113">Um eine Ressource in Ihrer Anwendung verwenden zu können, instanziieren Sie <xref:System.Resources.ResourceManager> und Laden Sie die Ressource, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a4c93-113">To use a resource in your application, you instantiate <xref:System.Resources.ResourceManager> and load the resource you want to use.</span></span> <span data-ttu-id="a4c93-114">Im folgenden Beispiel wird die hierfür erforderliche Vorgehensweise veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="a4c93-114">The following demonstrates how to do this.</span></span>  
  
 [!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]
