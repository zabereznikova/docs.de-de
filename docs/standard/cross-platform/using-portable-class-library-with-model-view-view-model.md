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
ms.openlocfilehash: ff34b295ba443088115d470d8ade0c986ac1d856
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288848"
---
# <a name="using-portable-class-library-with-model-view-view-model"></a><span data-ttu-id="6d282-102">Verwenden der portablen Klassenbibliothek mit Model-View-View Model</span><span class="sxs-lookup"><span data-stu-id="6d282-102">Using Portable Class Library with Model-View-View Model</span></span>
<span data-ttu-id="6d282-103">Mithilfe der .NET Framework [portablen Klassenbibliothek](cross-platform-development-with-the-portable-class-library.md) können Sie das Model-View-View Model (MVVM)-Muster implementieren und Assemblys auf mehreren Plattformen freigeben.</span><span class="sxs-lookup"><span data-stu-id="6d282-103">You can use the .NET Framework [Portable Class Library](cross-platform-development-with-the-portable-class-library.md) to implement the Model-View-View Model (MVVM) pattern and share assemblies across multiple platforms.</span></span>

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 <span data-ttu-id="6d282-104">MVVM ist ein Anwendungs Muster, das die Benutzeroberfläche von der zugrunde liegenden Geschäftslogik isoliert.</span><span class="sxs-lookup"><span data-stu-id="6d282-104">MVVM is an application pattern that isolates the user interface from the underlying business logic.</span></span> <span data-ttu-id="6d282-105">Sie können das Modell und die Modellklassen in einem Projekt für eine portable Klassenbibliothek in Visual Studio 2012 implementieren und dann Sichten erstellen, die für unterschiedliche Plattformen angepasst sind.</span><span class="sxs-lookup"><span data-stu-id="6d282-105">You can implement the model and view model classes in a Portable Class Library project in Visual Studio 2012, and then create views that are customized for different platforms.</span></span> <span data-ttu-id="6d282-106">Mit diesem Ansatz können Sie das Datenmodell und die Geschäftslogik nur einmal schreiben und diesen Code aus .NET Framework-, Silverlight-, Windows Phone-und Windows 8. x Store-Apps verwenden, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6d282-106">This approach enables you to write the data model and business logic only once, and use that code from .NET Framework, Silverlight, Windows Phone, and Windows 8.x Store apps, as shown in the following illustration.</span></span>

 ![Zeigt die portable Klassenbibliothek mit MVVM, die Assemblys plattformübergreifend freigibt.](./media/using-portable-class-library-with-model-view-view-model/mvvm-share-assemblies-across-platforms.png)

 <span data-ttu-id="6d282-108">In diesem Thema werden keine allgemeinen Informationen zum MVVM-Muster bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="6d282-108">This topic does not provide general information about the MVVM pattern.</span></span> <span data-ttu-id="6d282-109">Sie enthält nur Informationen zur Verwendung der portablen Klassenbibliothek zum Implementieren von MVVM.</span><span class="sxs-lookup"><span data-stu-id="6d282-109">It only provides information about how to use Portable Class Library to implement MVVM.</span></span> <span data-ttu-id="6d282-110">Weitere Informationen zu MVVM finden [Sie unter MVVM-Schnellstart mit der Prism-Bibliothek 5,0 für WPF](https://docs.microsoft.com/previous-versions/msp-n-p/gg430857(v=pandp.40)).</span><span class="sxs-lookup"><span data-stu-id="6d282-110">For more information about MVVM, see the [MVVM Quickstart Using the Prism Library 5.0 for WPF](https://docs.microsoft.com/previous-versions/msp-n-p/gg430857(v=pandp.40)).</span></span>

## <a name="classes-that-support-mvvm"></a><span data-ttu-id="6d282-111">Klassen, die MVVM unterstützen</span><span class="sxs-lookup"><span data-stu-id="6d282-111">Classes That Support MVVM</span></span>
 <span data-ttu-id="6d282-112">Wenn Sie die .NET Framework 4,5, .net für Windows 8. x Store-Apps, Silverlight oder Windows Phone 7,5 für das Projekt der portablen Klassenbibliothek als Ziel angeben, sind die folgenden Klassen für die Implementierung des MVVM-Musters verfügbar:</span><span class="sxs-lookup"><span data-stu-id="6d282-112">When you target the .NET Framework 4.5, .NET for Windows 8.x Store apps, Silverlight, or Windows Phone 7.5 for your Portable Class Library project, the following classes are available for implementing the MVVM pattern:</span></span>

- <span data-ttu-id="6d282-113"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="6d282-113"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="6d282-114"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="6d282-114"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="6d282-115"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="6d282-115"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="6d282-116"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="6d282-116"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="6d282-117"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="6d282-117"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="6d282-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="6d282-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="6d282-119"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="6d282-119"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="6d282-120"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="6d282-120"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="6d282-121"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="6d282-121"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="6d282-122"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType>-Klasse</span><span class="sxs-lookup"><span data-stu-id="6d282-122"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="6d282-123">Alle Klassen im- <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> Namespace</span><span class="sxs-lookup"><span data-stu-id="6d282-123">All classes in the <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> namespace</span></span>

## <a name="implementing-mvvm"></a><span data-ttu-id="6d282-124">Implementieren von MVVM</span><span class="sxs-lookup"><span data-stu-id="6d282-124">Implementing MVVM</span></span>
 <span data-ttu-id="6d282-125">Zum Implementieren von MVVM erstellen Sie in der Regel sowohl das Modell als auch das Ansichts Modell in einem Projekt für eine portable Klassenbibliothek, da ein Projekt für eine portable Klassenbibliothek nicht auf ein nicht Portables Projekt verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="6d282-125">To implement MVVM, you typically create both the model and the view model in a Portable Class Library project, because a Portable Class Library project cannot reference a non-portable project.</span></span> <span data-ttu-id="6d282-126">Das Modell und das Ansichts Modell können sich im selben Projekt oder in separaten Projekten befinden.</span><span class="sxs-lookup"><span data-stu-id="6d282-126">The model and view model can be in the same project or in separate projects.</span></span> <span data-ttu-id="6d282-127">Wenn Sie separate Projekte verwenden, fügen Sie dem Modellprojekt einen Verweis aus dem Ansichts Modellprojekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="6d282-127">If you use separate projects, add a reference from the view model project to the model project.</span></span>

 <span data-ttu-id="6d282-128">Nachdem Sie das Modell kompiliert und Modellprojekte angezeigt haben, verweisen Sie in der APP, die die Sicht enthält, auf diese Assemblys.</span><span class="sxs-lookup"><span data-stu-id="6d282-128">After you compile the model and view model projects, you reference those assemblies in the app that contains the view.</span></span> <span data-ttu-id="6d282-129">Wenn die Sicht nur mit dem Ansichts Modell interagiert, müssen Sie nur auf die Assembly verweisen, die das Ansichts Modell enthält.</span><span class="sxs-lookup"><span data-stu-id="6d282-129">If the view interacts only with the view model, you only have to reference the assembly that contains the view model.</span></span>

### <a name="model"></a><span data-ttu-id="6d282-130">Modell</span><span class="sxs-lookup"><span data-stu-id="6d282-130">Model</span></span>
 <span data-ttu-id="6d282-131">Das folgende Beispiel zeigt eine vereinfachte Modell Klasse, die sich in einem Projekt für eine portable Klassenbibliothek befinden könnte.</span><span class="sxs-lookup"><span data-stu-id="6d282-131">The following example shows a simplified model class that could reside in a Portable Class Library project.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]

 <span data-ttu-id="6d282-132">Das folgende Beispiel zeigt eine einfache Möglichkeit zum Auffüllen, abrufen und Aktualisieren der Daten in einem Projekt für eine portable Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="6d282-132">The following example shows a simple way to populate, retrieve, and update the data in a Portable Class Library project.</span></span> <span data-ttu-id="6d282-133">In einer echten APP würden Sie die Daten von einer Quelle, z. b. einem Windows Communication Foundation (WCF)-Dienst, abrufen.</span><span class="sxs-lookup"><span data-stu-id="6d282-133">In a real app, you would retrieve the data from a source such as a Windows Communication Foundation (WCF) service.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]

### <a name="view-model"></a><span data-ttu-id="6d282-134">Modell anzeigen</span><span class="sxs-lookup"><span data-stu-id="6d282-134">View Model</span></span>
 <span data-ttu-id="6d282-135">Eine Basisklasse für Ansichts Modelle wird bei der Implementierung des MVVM-Musters häufig hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6d282-135">A base class for view models is frequently added when implementing the MVVM pattern.</span></span> <span data-ttu-id="6d282-136">Im folgenden Beispiel wird eine Basisklasse veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6d282-136">The following example shows a base class.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]

 <span data-ttu-id="6d282-137">Eine Implementierung der- <xref:System.Windows.Input.ICommand> Schnittstelle wird häufig mit dem MVVM-Muster verwendet.</span><span class="sxs-lookup"><span data-stu-id="6d282-137">An implementation of the <xref:System.Windows.Input.ICommand> interface is frequently used with the MVVM pattern.</span></span> <span data-ttu-id="6d282-138">Im folgenden Beispiel wird eine Implementierung der <xref:System.Windows.Input.ICommand>-Schnittstelle veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6d282-138">The following example shows an implementation of the <xref:System.Windows.Input.ICommand> interface.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]

 <span data-ttu-id="6d282-139">Das folgende Beispiel zeigt ein vereinfachtes Ansichts Modell.</span><span class="sxs-lookup"><span data-stu-id="6d282-139">The following example shows a simplified view model.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a><span data-ttu-id="6d282-140">Ansicht</span><span class="sxs-lookup"><span data-stu-id="6d282-140">View</span></span>  
 <span data-ttu-id="6d282-141">Aus einer .NET Framework 4,5-APP, einer Windows 8. x Store-App, einer Silverlight-basierten APP oder einer Windows Phone 7,5-App können Sie auf die Assembly verweisen, die die Modell-und Modellprojekte enthält.</span><span class="sxs-lookup"><span data-stu-id="6d282-141">From a .NET Framework 4.5 app, Windows 8.x Store app, Silverlight-based app, or Windows Phone 7.5 app, you can reference the assembly that contains the model and view model projects.</span></span>  <span data-ttu-id="6d282-142">Anschließend erstellen Sie eine Ansicht, die mit dem Ansichts Modell interagiert.</span><span class="sxs-lookup"><span data-stu-id="6d282-142">You then create a view that interacts with the view model.</span></span> <span data-ttu-id="6d282-143">Das folgende Beispiel zeigt eine vereinfachte Windows Presentation Foundation-app (WPF), mit der Daten aus dem Ansichts Modell abgerufen und aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="6d282-143">The following example shows a simplified Windows Presentation Foundation (WPF) app that retrieves and updates data from the view model.</span></span> <span data-ttu-id="6d282-144">Ähnliche Ansichten können Sie in Silverlight-, Windows Phone-oder Windows 8. x Store-Apps erstellen.</span><span class="sxs-lookup"><span data-stu-id="6d282-144">You could create similar views in Silverlight, Windows Phone, or Windows 8.x Store apps.</span></span>  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a><span data-ttu-id="6d282-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d282-145">See also</span></span>

- [<span data-ttu-id="6d282-146">Portable Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="6d282-146">Portable Class Library</span></span>](cross-platform-development-with-the-portable-class-library.md)
