---
title: 'Vorgehensweise: Verwenden eines anwendungsspezifischen Ressourcenverzeichnisses'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
ms.openlocfilehash: 589e28b3c05496e3fc17055b98240e389faed068
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007486"
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a><span data-ttu-id="58899-102">Vorgehensweise: Verwenden eines anwendungsspezifischen Ressourcenverzeichnisses</span><span class="sxs-lookup"><span data-stu-id="58899-102">How to: Use an Application-Scope Resource Dictionary</span></span>
<span data-ttu-id="58899-103">In diesem Beispiel wird gezeigt, wie ein benutzerdefiniertes Ressourcenverzeichnis für den Anwendungsbereich definiert und verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="58899-103">This example shows how to define and use an application-scope custom resource dictionary.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58899-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="58899-104">Example</span></span>  
 <span data-ttu-id="58899-105"><xref:System.Windows.Application> macht einen Anwendungsbereichspeicher für freigegebene Ressourcen: <xref:System.Windows.Application.Resources%2A>.</span><span class="sxs-lookup"><span data-stu-id="58899-105"><xref:System.Windows.Application> exposes an application-scope store for shared resources: <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="58899-106">In der Standardeinstellung die <xref:System.Windows.Application.Resources%2A> -Eigenschaft wird mit einer Instanz von initialisiert die <xref:System.Windows.ResourceDictionary> Typ.</span><span class="sxs-lookup"><span data-stu-id="58899-106">By default, the <xref:System.Windows.Application.Resources%2A> property is initialized with an instance of the <xref:System.Windows.ResourceDictionary> type.</span></span> <span data-ttu-id="58899-107">Sie verwenden diese Instanz, wenn Sie abrufen und Festlegen von Eigenschaften für den Anwendungsbereich über <xref:System.Windows.Application.Resources%2A>.</span><span class="sxs-lookup"><span data-stu-id="58899-107">You use this instance when you get and set application-scope properties using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="58899-108">Weitere Informationen finden Sie unter [Vorgehensweise: Abrufen und festlegen eine Ressource für den Anwendungsbereich](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="58899-108">For more information, see [How to: Get and Set an Application-Scope Resource](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100)).</span></span>
  
 <span data-ttu-id="58899-109">Wenn Sie mehrere Ressourcen, die Sie festlegen, über <xref:System.Windows.Application.Resources%2A>, Sie können stattdessen ein benutzerdefiniertes Ressourcenverzeichnis verwenden, um diese Ressourcen zu speichern, und legen Sie <xref:System.Windows.Application.Resources%2A> mit stattdessen.</span><span class="sxs-lookup"><span data-stu-id="58899-109">If you have multiple resources that you set using <xref:System.Windows.Application.Resources%2A>, you can instead use a custom resource dictionary to store those resources and set <xref:System.Windows.Application.Resources%2A> with it instead.</span></span> <span data-ttu-id="58899-110">Das folgende Beispiel zeigt, wie Sie ein benutzerdefiniertes Ressourcenverzeichnis mit XAML deklarieren.</span><span class="sxs-lookup"><span data-stu-id="58899-110">The following shows how you declare a custom resource dictionary using XAML.</span></span>
  
 [!code-xaml[HOWTOResourceDictionaries#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 <span data-ttu-id="58899-111">Kompletter Ressourcenverzeichnisse mithilfe von <xref:System.Windows.Application.Resources%2A> ermöglicht es Ihnen, die für den Anwendungsbereich Designs für Anwendungsbereiche, die jeweils von einem einzigen Ressourcenverzeichnis gekapselt ist.</span><span class="sxs-lookup"><span data-stu-id="58899-111">Swapping entire resource dictionaries using <xref:System.Windows.Application.Resources%2A> allows you to support application-scope themes, where each theme is encapsulated by a single resource dictionary.</span></span> <span data-ttu-id="58899-112">Im folgenden Beispiel wird das Festlegen der <xref:System.Windows.ResourceDictionary> veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="58899-112">The following example shows how to set the <xref:System.Windows.ResourceDictionary>.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 <span data-ttu-id="58899-113">Das folgende Beispiel zeigt, wie Sie für den Anwendungsbereich-Ressourcen aus dem Ressourcenverzeichnis verfügbar gemacht werden, indem abrufen können <xref:System.Windows.Application.Resources%2A> in XAML.</span><span class="sxs-lookup"><span data-stu-id="58899-113">The following shows how you can get application-scope resources from the resource dictionary exposed by <xref:System.Windows.Application.Resources%2A> in XAML.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 <span data-ttu-id="58899-114">Im Folgenden wird gezeigt, wie Sie die Ressourcen auch in Code abrufen können.</span><span class="sxs-lookup"><span data-stu-id="58899-114">The following shows how you can also get the resources in code.</span></span>  
  
 [!code-csharp[HOWTOResourceDictionaries#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 <span data-ttu-id="58899-115">Es gibt zwei Überlegungen, die bei der Verwendung <xref:System.Windows.Application.Resources%2A>.</span><span class="sxs-lookup"><span data-stu-id="58899-115">There are two considerations to make when using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="58899-116">Zuerst wird das Wörterbuch *Schlüssel* ist ein Objekt, aus, sodass Sie genau die gleiche Objektinstanz beim Festlegen und Abrufen eines Eigenschaftswerts verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="58899-116">First, the dictionary *key* is an object, so you must use exactly the same object instance when both setting and getting a property value.</span></span> <span data-ttu-id="58899-117">(Beachten Sie, dass beim Verwenden einer Zeichenfolge beim Schlüssel die Groß-/Kleinschreibung beachtet wird.) Anderen ist der *Wert* ist ein Objekt, aus, sodass Sie den Wert in den gewünschten Typ zu konvertieren, wenn einen Eigenschaftswert abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="58899-117">(Note that the key is case-sensitive when using a string.) Second, the dictionary *value* is an object, so you will have to convert the value to the desired type when getting a property value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58899-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58899-118">See also</span></span>

- <xref:System.Windows.ResourceDictionary>
- <xref:System.Windows.Application.Resources%2A>
- [<span data-ttu-id="58899-119">XAML-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="58899-119">XAML Resources</span></span>](../advanced/xaml-resources.md)
- [<span data-ttu-id="58899-120">Zusammengeführte Ressourcenverzeichnisse</span><span class="sxs-lookup"><span data-stu-id="58899-120">Merged Resource Dictionaries</span></span>](../advanced/merged-resource-dictionaries.md)
