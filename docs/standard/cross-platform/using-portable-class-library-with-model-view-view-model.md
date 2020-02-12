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
ms.openlocfilehash: f5312177b9f437d9b5474d38fca80db6fc45245b
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77123674"
---
# <a name="using-portable-class-library-with-model-view-view-model"></a>Verwenden der portablen Klassenbibliothek mit Model-View-View Model
Mithilfe der .NET Framework [portablen Klassenbibliothek](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) können Sie das Model-View-View Model (MVVM)-Muster implementieren und Assemblys auf mehreren Plattformen freigeben.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 MVVM ist ein Anwendungs Muster, das die Benutzeroberfläche von der zugrunde liegenden Geschäftslogik isoliert. Sie können das Modell und die Modellklassen in einem Projekt für eine portable Klassenbibliothek in Visual Studio 2012 implementieren und dann Sichten erstellen, die für unterschiedliche Plattformen angepasst sind. Mit diesem Ansatz können Sie das Datenmodell und die Geschäftslogik nur einmal schreiben und diesen Code aus .NET Framework-, Silverlight-, Windows Phone-und Windows 8. x Store-Apps verwenden, wie in der folgenden Abbildung dargestellt.

 ![Zeigt die portable Klassenbibliothek mit MVVM, die Assemblys plattformübergreifend freigibt.](./media/using-portable-class-library-with-model-view-view-model/mvvm-share-assemblies-across-platforms.png)

 In diesem Thema werden keine allgemeinen Informationen zum MVVM-Muster bereitgestellt. Sie enthält nur Informationen zur Verwendung der portablen Klassenbibliothek zum Implementieren von MVVM. Weitere Informationen zu MVVM finden [Sie unter MVVM-Schnellstart mit der Prism-Bibliothek 5,0 für WPF](https://docs.microsoft.com/previous-versions/msp-n-p/gg430857(v=pandp.40)).

## <a name="classes-that-support-mvvm"></a>Klassen, die MVVM unterstützen
 Wenn Sie die .NET Framework 4,5, .net für Windows 8. x Store-Apps, Silverlight oder Windows Phone 7,5 für das Projekt der portablen Klassenbibliothek als Ziel angeben, sind die folgenden Klassen für die Implementierung des MVVM-Musters verfügbar:

- <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType>-Klasse

- <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType>-Klasse

- <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType>-Klasse

- <xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType>-Klasse

- <xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType>-Klasse

- <xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType>-Klasse

- <xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType>-Klasse

- <xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType>-Klasse

- <xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType>-Klasse

- <xref:System.Windows.Input.ICommand?displayProperty=nameWithType>-Klasse

- Alle Klassen im <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType>-Namespace

## <a name="implementing-mvvm"></a>Implementieren von MVVM
 Zum Implementieren von MVVM erstellen Sie in der Regel sowohl das Modell als auch das Ansichts Modell in einem Projekt für eine portable Klassenbibliothek, da ein Projekt für eine portable Klassenbibliothek nicht auf ein nicht Portables Projekt verweisen kann. Das Modell und das Ansichts Modell können sich im selben Projekt oder in separaten Projekten befinden. Wenn Sie separate Projekte verwenden, fügen Sie dem Modellprojekt einen Verweis aus dem Ansichts Modellprojekt hinzu.

 Nachdem Sie das Modell kompiliert und Modellprojekte angezeigt haben, verweisen Sie in der APP, die die Sicht enthält, auf diese Assemblys. Wenn die Sicht nur mit dem Ansichts Modell interagiert, müssen Sie nur auf die Assembly verweisen, die das Ansichts Modell enthält.

### <a name="model"></a>Modell
 Das folgende Beispiel zeigt eine vereinfachte Modell Klasse, die sich in einem Projekt für eine portable Klassenbibliothek befinden könnte.

 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]

 Das folgende Beispiel zeigt eine einfache Möglichkeit zum Auffüllen, abrufen und Aktualisieren der Daten in einem Projekt für eine portable Klassenbibliothek. In einer echten APP würden Sie die Daten von einer Quelle, z. b. einem Windows Communication Foundation (WCF)-Dienst, abrufen.

 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]

### <a name="view-model"></a>Modell anzeigen
 Eine Basisklasse für Ansichts Modelle wird bei der Implementierung des MVVM-Musters häufig hinzugefügt. Im folgenden Beispiel wird eine Basisklasse veranschaulicht.

 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]

 Eine Implementierung der <xref:System.Windows.Input.ICommand>-Schnittstelle wird häufig mit dem MVVM-Muster verwendet. Im folgenden Beispiel wird eine Implementierung der <xref:System.Windows.Input.ICommand>-Schnittstelle veranschaulicht.

 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]

 Das folgende Beispiel zeigt ein vereinfachtes Ansichts Modell.

 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a>Sicht  
 Aus einer .NET Framework 4,5-APP, einer Windows 8. x Store-App, einer Silverlight-basierten APP oder einer Windows Phone 7,5-App können Sie auf die Assembly verweisen, die die Modell-und Modellprojekte enthält.  Anschließend erstellen Sie eine Ansicht, die mit dem Ansichts Modell interagiert. Das folgende Beispiel zeigt eine vereinfachte Windows Presentation Foundation-app (WPF), mit der Daten aus dem Ansichts Modell abgerufen und aktualisiert werden. Ähnliche Ansichten können Sie in Silverlight-, Windows Phone-oder Windows 8. x Store-Apps erstellen.  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Portable Klassenbibliothek](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)
