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
ms.openlocfilehash: d2f07e471d4f0173f768b0d2a463d756b5be0682
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2018
ms.locfileid: "46472603"
---
# <a name="using-portable-class-library-with-model-view-view-model"></a>Verwenden der portablen Klassenbibliothek mit Model-View-View Model
Sie können .NET Framework [Portable Class Library](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) das Model-View-View Model (MVVM)-Muster implementieren, und geben Sie die Assemblys auf mehreren Plattformen frei.  

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 MVVM ist ein Anwendungsmuster, die die Benutzeroberfläche von der zugrunde liegende Geschäftslogik isoliert. Sie können die Modell und Ansicht Modellklassen in implementieren eine [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] Projekt [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], und erstellen Sie Ansichten, die für verschiedene Plattformen angepasst werden. Dieser Ansatz ermöglicht Ihnen das Schreiben von Daten von Modell und Geschäftslogik nur einmal und verwenden, die von .NET Framework, Silverlight, Windows Phone-code und [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] -apps, wie in der folgenden Abbildung dargestellt.  
  
 ![Portable mit MMM-Diagramm](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")  
  
 Dieses Thema bietet allgemeine Informationen über das MVVM-Muster nicht. Es enthält nur Informationen zur Verwendung von [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] zum Implementieren von MVVM. Weitere Informationen zu MVVM finden Sie unter den [MVVM Schnellstart](https://msdn.microsoft.com/library/gg430869(v=PandP.40).aspx).  
  
## <a name="classes-that-support-mvvm"></a>Klassen, die MVVM unterstützen.  
 Wenn Sie das Ziel der [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight oder Windows Phone 7.5 für Ihre [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] -Projekt die folgenden Klassen sind für die Implementierung des MVVM-Musters verfügbar:  
  
-   <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType>-Klasse  
  
-   <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType>-Klasse  
  
-   <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType>-Klasse  
  
-   <xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType>-Klasse  
  
-   <xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType>-Klasse  
  
-   <xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType>-Klasse  
  
-   <xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType>-Klasse  
  
-   <xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType>-Klasse  
  
-   <xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType>-Klasse  
  
-   <xref:System.Windows.Input.ICommand?displayProperty=nameWithType>-Klasse  
  
-   Alle Klassen in der <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> Namespace  
  
## <a name="implementing-mvvm"></a>Implementierung von MVVM  
 Zum Implementieren von MVVM normalerweise erstellen Sie sowohl das Modell und das Ansichtsmodell in einem [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] Projekt, da eine [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] Projekt kann nicht auf ein nicht portables Projekt verweisen. Das Modell und das Ansichtsmodell kann im selben Projekt oder in separaten Projekten. Wenn Sie separate Projekte verwenden, fügen Sie einen Verweis aus dem Projekt der Modelle anzeigen, auf das Modellprojekt.  
  
 Nachdem Sie das Modell zu kompilieren und modellprojekte anzeigen, verweisen Sie auf diese Assemblys in der app, die die Sicht enthält. Wenn die Ansicht nur mit dem Ansichtsmodell interagiert, müssen Sie sich nur auf die Assembly verweisen, die das Ansichtsmodell enthält.  
  
### <a name="model"></a>Modell  
 Das folgende Beispiel zeigt eine vereinfachte Model-Klasse, die im befinden könnte eine [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] Projekt.  
  
 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]  
  
 Das folgende Beispiel zeigt eine einfache Möglichkeit zum Füllen, abrufen und aktualisieren Sie die Daten in einem [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] Projekt. In einer echten app würden Sie die Daten aus einer Quelle, z. B. einen Windows Communication Foundation (WCF)-Dienst abrufen.  
  
 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]  
  
### <a name="view-model"></a>Anzeigen des Modells  
 Eine Basisklasse für anzeigemodelle wird häufig hinzugefügt, bei der Implementierung des MVVM-Musters. Das folgende Beispiel zeigt eine Basisklasse.  
  
 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]  
  
 Eine Implementierung der <xref:System.Windows.Input.ICommand> Schnittstelle wird häufig verwendet, mit dem MVVM-Muster. Im folgenden Beispiel wird eine Implementierung der <xref:System.Windows.Input.ICommand>-Schnittstelle veranschaulicht.  
  
 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]  
  
 Das folgende Beispiel zeigt eine vereinfachte Ansicht-Modell.  
  
 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a>Ansicht  
 Aus einem [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] app [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] -app, Silverlight-basierten Anwendung oder Windows Phone 7.5-app, können Sie die Assembly mit dem Modell und Ansicht-modellprojekte verweisen.  Anschließend erstellen Sie eine Ansicht, die Interaktion mit dem Ansichtsmodell. Das folgende Beispiel zeigt eine vereinfachte Windows Presentation Foundation (WPF)-app, die abgerufen und aktualisiert die Daten aus dem Anzeigemodell. Sie können ähnliche Ansichten erstellen, in Silverlight, Windows Phone, oder [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a>Siehe auch

- [Portable Klassenbibliothek](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)
