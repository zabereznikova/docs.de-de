---
title: 'Gewusst wie: Verwenden von Ressourcen in lokalisierbaren Anwendungen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d803989292e2fc6b0945c397df5ce32d318147fc
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-resources-in-localizable-applications"></a><span data-ttu-id="725ce-102">Gewusst wie: Verwenden von Ressourcen in lokalisierbaren Anwendungen</span><span class="sxs-lookup"><span data-stu-id="725ce-102">How to: Use Resources in Localizable Applications</span></span>
<span data-ttu-id="725ce-103">Lokalisierung bezeichnet die Anpassung einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] auf unterschiedliche Kulturen.</span><span class="sxs-lookup"><span data-stu-id="725ce-103">Localization means to adapt a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to different cultures.</span></span> <span data-ttu-id="725ce-104">Dazu müssen Text (z.B. Titel), Beschriftungen, Listenfeldelemente usw. übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="725ce-104">To do this, text such as titles, captions, list box items and so forth have to be translated.</span></span> <span data-ttu-id="725ce-105">Damit die Übersetzung vereinfacht wird, werden die zu übersetzten Elemente in Ressourcendateien gesammelt.</span><span class="sxs-lookup"><span data-stu-id="725ce-105">To make translation easier the items to be translated are collected into resource files.</span></span> <span data-ttu-id="725ce-106">Finden Sie unter [Lokalisieren einer Anwendung](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md) Informationen zum Erstellen einer Ressourcendatei für die Lokalisierung.</span><span class="sxs-lookup"><span data-stu-id="725ce-106">See [Localize an Application](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md) for information on how to create a resource file for localization.</span></span> <span data-ttu-id="725ce-107">Vornehmen einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung lokalisiert werden kann. Entwickler müssen alle lokalisierbaren Ressourcen in einer Ressourcenassembly zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="725ce-107">To make a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application localizable, developers need to build all the localizable resources into a resource assembly.</span></span> <span data-ttu-id="725ce-108">Die Ressourcenassembly wird in verschiedenen Sprachen lokalisiert und das Code-Behind-Modell verwendet ressourcenverwaltung [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] geladen.</span><span class="sxs-lookup"><span data-stu-id="725ce-108">The resource assembly is localized into different languages, and the code-behind uses resource management [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] to load.</span></span> <span data-ttu-id="725ce-109">Eine der erforderlichen Dateien für eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung ist eine Projektdatei (".proj").</span><span class="sxs-lookup"><span data-stu-id="725ce-109">One of the files required for a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application is a project file (.proj).</span></span> <span data-ttu-id="725ce-110">Alle Ressourcen, die Sie in Ihrer Anwendung verwenden, sollten in der Projektdatei enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="725ce-110">All resources that you use in your application should be included in the project file.</span></span> <span data-ttu-id="725ce-111">Dies wird im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="725ce-111">The following code example shows this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="725ce-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="725ce-112">Example</span></span>  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 `<Resource Include="data\picture1.jpg"/>`  
  
 `<EmbeddedResource Include="data\stringtable.en-US.restext"/>`  
  
 <span data-ttu-id="725ce-113">Um eine Ressource in der Anwendung zu verwenden, instanziieren Sie <xref:System.Resources.ResourceManager> und Laden Sie die Ressource, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="725ce-113">To use a resource in your application, you instantiate <xref:System.Resources.ResourceManager> and load the resource you want to use.</span></span> <span data-ttu-id="725ce-114">Im folgenden Beispiel wird die hierfür erforderliche Vorgehensweise veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="725ce-114">The following demonstrates how to do this.</span></span>  
  
 [!code-csharp[LocalizationResources#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]
