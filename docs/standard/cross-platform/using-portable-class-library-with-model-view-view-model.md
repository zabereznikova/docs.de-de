---
title: Verwenden der portablen Klassenbibliothek mit Model-View-View Model
ms.date: 07/18/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Portable Class Library [.NET Framework], and MVVM
- MVVM, and Portable Class Library
ms.assetid: 41a0b9f8-15a2-431a-bc35-e310b2953b03
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4a477b9d204be0bc9a4c438bccb1379ecc7abf53
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664324"
---
# <a name="using-portable-class-library-with-model-view-view-model"></a><span data-ttu-id="8c400-102">Verwenden der portablen Klassenbibliothek mit Model-View-View Model</span><span class="sxs-lookup"><span data-stu-id="8c400-102">Using Portable Class Library with Model-View-View Model</span></span>
<span data-ttu-id="8c400-103">Sie können .NET Framework [Portable Class Library](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) das Model-View-View Model (MVVM)-Muster implementieren, und geben Sie die Assemblys auf mehreren Plattformen frei.</span><span class="sxs-lookup"><span data-stu-id="8c400-103">You can use the .NET Framework [Portable Class Library](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) to implement the Model-View-View Model (MVVM) pattern and share assemblies across multiple platforms.</span></span>

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 <span data-ttu-id="8c400-104">MVVM ist ein Anwendungsmuster, die die Benutzeroberfläche von der zugrunde liegende Geschäftslogik isoliert.</span><span class="sxs-lookup"><span data-stu-id="8c400-104">MVVM is an application pattern that isolates the user interface from the underlying business logic.</span></span> <span data-ttu-id="8c400-105">Sie können die Modell und Ansicht Modellklassen in implementieren eine [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] -Projekt in Visual Studio 2012, und erstellen Sie Ansichten, die für verschiedene Plattformen angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="8c400-105">You can implement the model and view model classes in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project in Visual Studio 2012, and then create views that are customized for different platforms.</span></span> <span data-ttu-id="8c400-106">Dieser Ansatz ermöglicht Ihnen das Schreiben von Daten von Modell und Geschäftslogik nur einmal und verwenden, die von .NET Framework, Silverlight, Windows Phone-code und [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] -apps, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="8c400-106">This approach enables you to write the data model and business logic only once, and use that code from .NET Framework, Silverlight, Windows Phone, and [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps, as shown in the following illustration.</span></span>

 <span data-ttu-id="8c400-107">![Portable mit MMM-Diagramm](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")</span><span class="sxs-lookup"><span data-stu-id="8c400-107">![Portable with MVVM diagram](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")</span></span>

 <span data-ttu-id="8c400-108">Dieses Thema bietet allgemeine Informationen über das MVVM-Muster nicht.</span><span class="sxs-lookup"><span data-stu-id="8c400-108">This topic does not provide general information about the MVVM pattern.</span></span> <span data-ttu-id="8c400-109">Es enthält nur Informationen zur Verwendung von [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] zum Implementieren von MVVM.</span><span class="sxs-lookup"><span data-stu-id="8c400-109">It only provides information about how to use [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] to implement MVVM.</span></span> <span data-ttu-id="8c400-110">Weitere Informationen zu MVVM finden Sie unter den [MVVM Schnellstart verwenden die Prism Library 5.0 für WPF](https://docs.microsoft.com/previous-versions/msp-n-p/gg430857(v=pandp.40)).</span><span class="sxs-lookup"><span data-stu-id="8c400-110">For more information about MVVM, see the [MVVM Quickstart Using the Prism Library 5.0 for WPF](https://docs.microsoft.com/previous-versions/msp-n-p/gg430857(v=pandp.40)).</span></span>

## <a name="classes-that-support-mvvm"></a><span data-ttu-id="8c400-111">Klassen, die MVVM unterstützen.</span><span class="sxs-lookup"><span data-stu-id="8c400-111">Classes That Support MVVM</span></span>
 <span data-ttu-id="8c400-112">Wenn Sie das Ziel der [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight oder Windows Phone 7.5 für Ihre [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] -Projekt die folgenden Klassen sind für die Implementierung des MVVM-Musters verfügbar:</span><span class="sxs-lookup"><span data-stu-id="8c400-112">When you target the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight, or Windows Phone 7.5 for your [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project, the following classes are available for implementing the MVVM pattern:</span></span>

- <span data-ttu-id="8c400-113"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="8c400-113"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="8c400-114"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="8c400-114"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="8c400-115"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="8c400-115"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="8c400-116"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="8c400-116"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="8c400-117"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="8c400-117"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="8c400-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="8c400-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="8c400-119"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="8c400-119"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="8c400-120"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="8c400-120"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="8c400-121"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="8c400-121"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="8c400-122"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="8c400-122"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="8c400-123">Alle Klassen in der <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> Namespace</span><span class="sxs-lookup"><span data-stu-id="8c400-123">All classes in the <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> namespace</span></span>

## <a name="implementing-mvvm"></a><span data-ttu-id="8c400-124">Implementierung von MVVM</span><span class="sxs-lookup"><span data-stu-id="8c400-124">Implementing MVVM</span></span>
 <span data-ttu-id="8c400-125">Zum Implementieren von MVVM normalerweise erstellen Sie sowohl das Modell und das Ansichtsmodell in einem [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] Projekt, da eine [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] Projekt kann nicht auf ein nicht portables Projekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="8c400-125">To implement MVVM, you typically create both the model and the view model in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project, because a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project cannot reference a non-portable project.</span></span> <span data-ttu-id="8c400-126">Das Modell und das Ansichtsmodell kann im selben Projekt oder in separaten Projekten.</span><span class="sxs-lookup"><span data-stu-id="8c400-126">The model and view model can be in the same project or in separate projects.</span></span> <span data-ttu-id="8c400-127">Wenn Sie separate Projekte verwenden, fügen Sie einen Verweis aus dem Projekt der Modelle anzeigen, auf das Modellprojekt.</span><span class="sxs-lookup"><span data-stu-id="8c400-127">If you use separate projects, add a reference from the view model project to the model project.</span></span>

 <span data-ttu-id="8c400-128">Nachdem Sie das Modell zu kompilieren und modellprojekte anzeigen, verweisen Sie auf diese Assemblys in der app, die die Sicht enthält.</span><span class="sxs-lookup"><span data-stu-id="8c400-128">After you compile the model and view model projects, you reference those assemblies in the app that contains the view.</span></span> <span data-ttu-id="8c400-129">Wenn die Ansicht nur mit dem Ansichtsmodell interagiert, müssen Sie sich nur auf die Assembly verweisen, die das Ansichtsmodell enthält.</span><span class="sxs-lookup"><span data-stu-id="8c400-129">If the view interacts only with the view model, you only have to reference the assembly that contains the view model.</span></span>

### <a name="model"></a><span data-ttu-id="8c400-130">Modell</span><span class="sxs-lookup"><span data-stu-id="8c400-130">Model</span></span>
 <span data-ttu-id="8c400-131">Das folgende Beispiel zeigt eine vereinfachte Model-Klasse, die im befinden könnte eine [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] Projekt.</span><span class="sxs-lookup"><span data-stu-id="8c400-131">The following example shows a simplified model class that could reside in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]

 <span data-ttu-id="8c400-132">Das folgende Beispiel zeigt eine einfache Möglichkeit zum Füllen, abrufen und aktualisieren Sie die Daten in einem [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] Projekt.</span><span class="sxs-lookup"><span data-stu-id="8c400-132">The following example shows a simple way to populate, retrieve, and update the data in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project.</span></span> <span data-ttu-id="8c400-133">In einer echten app würden Sie die Daten aus einer Quelle, z. B. einen Windows Communication Foundation (WCF)-Dienst abrufen.</span><span class="sxs-lookup"><span data-stu-id="8c400-133">In a real app, you would retrieve the data from a source such as a Windows Communication Foundation (WCF) service.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]

### <a name="view-model"></a><span data-ttu-id="8c400-134">Anzeigen des Modells</span><span class="sxs-lookup"><span data-stu-id="8c400-134">View Model</span></span>
 <span data-ttu-id="8c400-135">Eine Basisklasse für anzeigemodelle wird häufig hinzugefügt, bei der Implementierung des MVVM-Musters.</span><span class="sxs-lookup"><span data-stu-id="8c400-135">A base class for view models is frequently added when implementing the MVVM pattern.</span></span> <span data-ttu-id="8c400-136">Das folgende Beispiel zeigt eine Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="8c400-136">The following example shows a base class.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]

 <span data-ttu-id="8c400-137">Eine Implementierung der <xref:System.Windows.Input.ICommand> Schnittstelle wird häufig verwendet, mit dem MVVM-Muster.</span><span class="sxs-lookup"><span data-stu-id="8c400-137">An implementation of the <xref:System.Windows.Input.ICommand> interface is frequently used with the MVVM pattern.</span></span> <span data-ttu-id="8c400-138">Im folgenden Beispiel wird eine Implementierung der <xref:System.Windows.Input.ICommand>-Schnittstelle veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8c400-138">The following example shows an implementation of the <xref:System.Windows.Input.ICommand> interface.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]

 <span data-ttu-id="8c400-139">Das folgende Beispiel zeigt eine vereinfachte Ansicht-Modell.</span><span class="sxs-lookup"><span data-stu-id="8c400-139">The following example shows a simplified view model.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a><span data-ttu-id="8c400-140">Ansicht</span><span class="sxs-lookup"><span data-stu-id="8c400-140">View</span></span>  
 <span data-ttu-id="8c400-141">Aus einem [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] app [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] -app, Silverlight-basierten Anwendung oder Windows Phone 7.5-app, können Sie die Assembly mit dem Modell und Ansicht-modellprojekte verweisen.</span><span class="sxs-lookup"><span data-stu-id="8c400-141">From a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] app, [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, Silverlight-based app, or Windows Phone 7.5 app, you can reference the assembly that contains the model and view model projects.</span></span>  <span data-ttu-id="8c400-142">Anschließend erstellen Sie eine Ansicht, die Interaktion mit dem Ansichtsmodell.</span><span class="sxs-lookup"><span data-stu-id="8c400-142">You then create a view that interacts with the view model.</span></span> <span data-ttu-id="8c400-143">Das folgende Beispiel zeigt eine vereinfachte Windows Presentation Foundation (WPF)-app, die abgerufen und aktualisiert die Daten aus dem Anzeigemodell.</span><span class="sxs-lookup"><span data-stu-id="8c400-143">The following example shows a simplified Windows Presentation Foundation (WPF) app that retrieves and updates data from the view model.</span></span> <span data-ttu-id="8c400-144">Sie können ähnliche Ansichten erstellen, in Silverlight, Windows Phone, oder [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span><span class="sxs-lookup"><span data-stu-id="8c400-144">You could create similar views in Silverlight, Windows Phone, or [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a><span data-ttu-id="8c400-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c400-145">See also</span></span>

- [<span data-ttu-id="8c400-146">Portable Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="8c400-146">Portable Class Library</span></span>](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)
