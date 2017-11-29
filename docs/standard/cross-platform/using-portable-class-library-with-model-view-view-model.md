---
title: Verwenden der portablen Klassenbibliothek mit Model-View-View Model
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Portable Class Library [.NET Framework], and MVVM
- MVVM, and Portable Class Library
ms.assetid: 41a0b9f8-15a2-431a-bc35-e310b2953b03
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e39a8df5c8aee05414e778f15a29bbeda8dba930
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="using-portable-class-library-with-model-view-view-model"></a><span data-ttu-id="fddde-102">Verwenden der portablen Klassenbibliothek mit Model-View-View Model</span><span class="sxs-lookup"><span data-stu-id="fddde-102">Using Portable Class Library with Model-View-View Model</span></span>
<span data-ttu-id="fddde-103">Sie können .NET Framework [Portable Class Library](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) der Model-View-View Model (MVVM)-Muster implementiert wird und Assemblys von mehreren Plattformen gemeinsam genutzt.</span><span class="sxs-lookup"><span data-stu-id="fddde-103">You can use the .NET Framework [Portable Class Library](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) to implement the Model-View-View Model (MVVM) pattern and share assemblies across multiple platforms.</span></span>  
  
 <span data-ttu-id="fddde-104">MVVM ist ein Anwendungsmuster, die die Benutzeroberfläche von der zugrunde liegenden Geschäftslogik isoliert.</span><span class="sxs-lookup"><span data-stu-id="fddde-104">MVVM is an application pattern that isolates the user interface from the underlying business logic.</span></span> <span data-ttu-id="fddde-105">Sie können das Modell und Ansicht Modellklassen in implementieren eine [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] Projekt [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], und erstellen Sie Ansichten, die für unterschiedliche Plattformen angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="fddde-105">You can implement the model and view model classes in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], and then create views that are customized for different platforms.</span></span> <span data-ttu-id="fddde-106">Dieser Ansatz ermöglicht es Ihnen, die Daten schreiben Modell und Geschäftslogik nur einmal und verwenden, die von .NET Framework, Silverlight, Windows Phone-code und [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="fddde-106">This approach enables you to write the data model and business logic only once, and use that code from .NET Framework, Silverlight, Windows Phone, and [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps, as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="fddde-107">![Portable mit MMM-Diagramm](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")</span><span class="sxs-lookup"><span data-stu-id="fddde-107">![Portable with MVVM diagram](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")</span></span>  
  
 <span data-ttu-id="fddde-108">Dieses Thema stellt allgemeine Informationen über das MVVM-Muster nicht bereit.</span><span class="sxs-lookup"><span data-stu-id="fddde-108">This topic does not provide general information about the MVVM pattern.</span></span> <span data-ttu-id="fddde-109">Es enthält nur Informationen zur Verwendung von [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] MVVM implementieren.</span><span class="sxs-lookup"><span data-stu-id="fddde-109">It only provides information about how to use [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] to implement MVVM.</span></span> <span data-ttu-id="fddde-110">Weitere Informationen zu MVVM, finden Sie unter der [MVVM Schnellstart](http://go.microsoft.com/fwlink/?LinkId=234934).</span><span class="sxs-lookup"><span data-stu-id="fddde-110">For more information about MVVM, see the [MVVM Quickstart](http://go.microsoft.com/fwlink/?LinkId=234934).</span></span>  
  
## <a name="classes-that-support-mvvm"></a><span data-ttu-id="fddde-111">Klassen, die MVVM unterstützen</span><span class="sxs-lookup"><span data-stu-id="fddde-111">Classes That Support MVVM</span></span>  
 <span data-ttu-id="fddde-112">Wenn Sie das Ziel der [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight oder Windows Phone 7.5 für Ihre [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] -Projekt die folgenden Klassen zum Implementieren des Musters MVVM verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="fddde-112">When you target the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight, or Windows Phone 7.5 for your [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project, the following classes are available for implementing the MVVM pattern:</span></span>  
  
-   <span data-ttu-id="fddde-113"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="fddde-113"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="fddde-114"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="fddde-114"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="fddde-115"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="fddde-115"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="fddde-116"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="fddde-116"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="fddde-117"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="fddde-117"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="fddde-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="fddde-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="fddde-119"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="fddde-119"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="fddde-120"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="fddde-120"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="fddde-121"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="fddde-121"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="fddde-122"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="fddde-122"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="fddde-123">Alle Klassen in der <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> Namespace</span><span class="sxs-lookup"><span data-stu-id="fddde-123">All classes in the <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> namespace</span></span>  
  
## <a name="implementing-mvvm"></a><span data-ttu-id="fddde-124">Implementieren von MVVM</span><span class="sxs-lookup"><span data-stu-id="fddde-124">Implementing MVVM</span></span>  
 <span data-ttu-id="fddde-125">Um MVVM zu implementieren, Sie erstellen in der Regel das Modell und die Ansichtsmodell in einem [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] Projekt, da ein [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] Projekt kann nicht auf ein Projekt nicht portabel verweisen.</span><span class="sxs-lookup"><span data-stu-id="fddde-125">To implement MVVM, you typically create both the model and the view model in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project, because a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project cannot reference a non-portable project.</span></span> <span data-ttu-id="fddde-126">Das Modell und die Ansichtsmodell im selben Projekt oder in separaten Projekten möglich.</span><span class="sxs-lookup"><span data-stu-id="fddde-126">The model and view model can be in the same project or in separate projects.</span></span> <span data-ttu-id="fddde-127">Wenn Sie separate Projekte verwenden, fügen Sie einen Verweis aus der Sicht Modellprojekt am Modellprojekt.</span><span class="sxs-lookup"><span data-stu-id="fddde-127">If you use separate projects, add a reference from the view model project to the model project.</span></span>  
  
 <span data-ttu-id="fddde-128">Nachdem Sie das Modell zu kompilieren und Modellprojekten anzeigen, verweisen Sie diese Assemblys in der app, die die Sicht enthält.</span><span class="sxs-lookup"><span data-stu-id="fddde-128">After you compile the model and view model projects, you reference those assemblies in the app that contains the view.</span></span> <span data-ttu-id="fddde-129">Wenn die Ansicht nur das Ansichtsmodell interagiert, müssen Sie sich nur auf die Assembly verweisen, die das Ansichtsmodell enthält.</span><span class="sxs-lookup"><span data-stu-id="fddde-129">If the view interacts only with the view model, you only have to reference the assembly that contains the view model.</span></span>  
  
### <a name="model"></a><span data-ttu-id="fddde-130">Modell</span><span class="sxs-lookup"><span data-stu-id="fddde-130">Model</span></span>  
 <span data-ttu-id="fddde-131">Das folgende Beispiel zeigt eine vereinfachtes Modell-Klasse, die im befinden könnte ein [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] Projekt.</span><span class="sxs-lookup"><span data-stu-id="fddde-131">The following example shows a simplified model class that could reside in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]  
  
 <span data-ttu-id="fddde-132">Das folgende Beispiel zeigt eine einfache Möglichkeit zum Auffüllen, abrufen und aktualisieren Sie die Daten in einem [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] Projekt.</span><span class="sxs-lookup"><span data-stu-id="fddde-132">The following example shows a simple way to populate, retrieve, and update the data in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project.</span></span> <span data-ttu-id="fddde-133">In eine wirkliche app wäre die Daten aus einer Quelle, z. B. einen Windows Communication Foundation (WCF)-Dienst abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="fddde-133">In a real app, you would retrieve the data from a source such as a Windows Communication Foundation (WCF) service.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]  
  
### <a name="view-model"></a><span data-ttu-id="fddde-134">Anzeigen des Modells</span><span class="sxs-lookup"><span data-stu-id="fddde-134">View Model</span></span>  
 <span data-ttu-id="fddde-135">Eine Basisklasse für Modelle anzeigen wird häufig hinzugefügt werden, wenn das MVVM-Muster implementieren.</span><span class="sxs-lookup"><span data-stu-id="fddde-135">A base class for view models is frequently added when implementing the MVVM pattern.</span></span> <span data-ttu-id="fddde-136">Das folgende Beispiel zeigt eine Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="fddde-136">The following example shows a base class.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]  
  
 <span data-ttu-id="fddde-137">Eine Implementierung der <xref:System.Windows.Input.ICommand> Schnittstelle wird häufig verwendet, mit dem MVVM-Muster.</span><span class="sxs-lookup"><span data-stu-id="fddde-137">An implementation of the <xref:System.Windows.Input.ICommand> interface is frequently used with the MVVM pattern.</span></span> <span data-ttu-id="fddde-138">Im folgenden Beispiel wird eine Implementierung der <xref:System.Windows.Input.ICommand>-Schnittstelle veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="fddde-138">The following example shows an implementation of the <xref:System.Windows.Input.ICommand> interface.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]  
  
 <span data-ttu-id="fddde-139">Das folgende Beispiel zeigt eine vereinfachte Ansicht-Modell.</span><span class="sxs-lookup"><span data-stu-id="fddde-139">The following example shows a simplified view model.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a><span data-ttu-id="fddde-140">Ansicht</span><span class="sxs-lookup"><span data-stu-id="fddde-140">View</span></span>  
 <span data-ttu-id="fddde-141">Aus einem [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] app [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, Silverlight-basierten Anwendung oder Windows Phone 7.5 app, können Sie die Assembly, die das Modell und Ansicht Modellprojekten enthält verweisen.</span><span class="sxs-lookup"><span data-stu-id="fddde-141">From a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] app, [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, Silverlight-based app, or Windows Phone 7.5 app, you can reference the assembly that contains the model and view model projects.</span></span>  <span data-ttu-id="fddde-142">Anschließend erstellen Sie eine Sicht, die Interaktion mit dem Modell anzeigen.</span><span class="sxs-lookup"><span data-stu-id="fddde-142">You then create a view that interacts with the view model.</span></span> <span data-ttu-id="fddde-143">Das folgende Beispiel zeigt eine vereinfachte Windows Presentation Foundation (WPF)-app, die abgerufen und aktualisiert die Daten aus dem Modell anzeigen.</span><span class="sxs-lookup"><span data-stu-id="fddde-143">The following example shows a simplified Windows Presentation Foundation (WPF) app that retrieves and updates data from the view model.</span></span> <span data-ttu-id="fddde-144">Sie können ähnliche Ansichten erstellen, in Silverlight, Windows Phone-oder [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span><span class="sxs-lookup"><span data-stu-id="fddde-144">You could create similar views in Silverlight, Windows Phone, or [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a><span data-ttu-id="fddde-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fddde-145">See Also</span></span>  
 [<span data-ttu-id="fddde-146">Portable Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="fddde-146">Portable Class Library</span></span>](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)
