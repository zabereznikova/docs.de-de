---
title: 'Gewusst wie: Verwenden von Ressourcen in lokalisierbaren Anwendungen'
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
ms.openlocfilehash: 8f516a86036656b98add23d38c588b5c19be4d7a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212474"
---
# <a name="how-to-use-resources-in-localizable-apps"></a><span data-ttu-id="f9c91-102">Gewusst wie: Verwenden von Ressourcen in lokalisierbaren apps</span><span class="sxs-lookup"><span data-stu-id="f9c91-102">How to: Use resources in localizable apps</span></span>

<span data-ttu-id="f9c91-103">Lokalisierung bedeutet, dass eine Benutzeroberfläche an verschiedene Kulturen angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="f9c91-103">Localization means to adapt a user interface to different cultures.</span></span> <span data-ttu-id="f9c91-104">Zu diesem Zweck müssen Text wie Titel, Beschriftungen und Listenfeld Elemente übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="f9c91-104">To do this, text such as titles, captions, and list box items must be translated.</span></span> <span data-ttu-id="f9c91-105">Um die Übersetzung zu vereinfachen, werden die zu über setzenden Elemente in Ressourcen Dateien gesammelt.</span><span class="sxs-lookup"><span data-stu-id="f9c91-105">To make translation easier, the items to be translated are collected into resource files.</span></span> <span data-ttu-id="f9c91-106">Informationen zum Erstellen einer Ressourcen Datei für die Lokalisierung finden Sie unter [Lokalisieren einer APP](how-to-localize-an-application.md) .</span><span class="sxs-lookup"><span data-stu-id="f9c91-106">See [Localize an app](how-to-localize-an-application.md) for information on how to create a resource file for localization.</span></span> <span data-ttu-id="f9c91-107">Um eine WPF-Anwendung lokalisierbar zu machen, müssen Entwickler alle lokalisierbaren Ressourcen in einer Ressourcenassembly erstellen.</span><span class="sxs-lookup"><span data-stu-id="f9c91-107">To make a WPF application localizable, developers need to build all the localizable resources into a resource assembly.</span></span> <span data-ttu-id="f9c91-108">Die Ressourcenassembly wird in verschiedene Sprachen lokalisiert, und der Code Behind verwendet die Ressourcenverwaltungs-API zum Laden.</span><span class="sxs-lookup"><span data-stu-id="f9c91-108">The resource assembly is localized into different languages, and the code-behind uses resource management API to load.</span></span>

## <a name="example"></a><span data-ttu-id="f9c91-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f9c91-109">Example</span></span>

<span data-ttu-id="f9c91-110">Eine der erforderlichen Dateien für eine WPF-Anwendung ist eine Projektdatei (. proj).</span><span class="sxs-lookup"><span data-stu-id="f9c91-110">One of the files required for a WPF application is a project file (.proj).</span></span> <span data-ttu-id="f9c91-111">Alle Ressourcen, die Sie in Ihrer Anwendung verwenden, sollten in der Projektdatei enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="f9c91-111">All resources that you use in your application should be included in the project file.</span></span> <span data-ttu-id="f9c91-112">Dies wird im folgenden XAML-Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f9c91-112">The following XAML example shows this.</span></span>

```xaml
<Resource Include="data\picture1.jpg"/>  
<EmbeddedResource Include="data\stringtable.en-US.restext"/>
```

<span data-ttu-id="f9c91-113">Um eine Ressource in Ihrer Anwendung zu verwenden, instanziieren <xref:System.Resources.ResourceManager> und laden Sie die gewünschte Ressource.</span><span class="sxs-lookup"><span data-stu-id="f9c91-113">To use a resource in your application, instantiate <xref:System.Resources.ResourceManager> and load the resource you want to use.</span></span> <span data-ttu-id="f9c91-114">Dies wird im folgenden c#-Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f9c91-114">The following C# code demonstrates how to do this.</span></span>

[!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]

## <a name="see-also"></a><span data-ttu-id="f9c91-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9c91-115">See also</span></span>

- [<span data-ttu-id="f9c91-116">Lokalisieren einer APP</span><span class="sxs-lookup"><span data-stu-id="f9c91-116">Localize an app</span></span>](how-to-localize-an-application.md)
