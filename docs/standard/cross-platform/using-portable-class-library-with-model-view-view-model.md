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
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cc12a90025a1862fc6c588fe4425f3f8341da313
ms.sourcegitcommit: 91691981897cf8451033cb01071d8f5d94017f97
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2018
---
# <a name="using-portable-class-library-with-model-view-view-model"></a>Verwenden der portablen Klassenbibliothek mit Model-View-View Model
Sie können .NET Framework [Portable Class Library](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) der Model-View-View Model (MVVM)-Muster implementiert wird und Assemblys von mehreren Plattformen gemeinsam genutzt.  
  
 MVVM ist ein Anwendungsmuster, die die Benutzeroberfläche von der zugrunde liegenden Geschäftslogik isoliert. Sie können das Modell und Ansicht Modellklassen in implementieren eine [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] Projekt [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], und erstellen Sie Ansichten, die für unterschiedliche Plattformen angepasst werden. Dieser Ansatz ermöglicht es Ihnen, die Daten schreiben Modell und Geschäftslogik nur einmal und verwenden, die von .NET Framework, Silverlight, Windows Phone-code und [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps, wie in der folgenden Abbildung dargestellt.  
  
 ![Portable mit MMM-Diagramm](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")  
  
 Dieses Thema stellt allgemeine Informationen über das MVVM-Muster nicht bereit. Es enthält nur Informationen zur Verwendung von [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] MVVM implementieren. Weitere Informationen zu MVVM, finden Sie unter der [MVVM Schnellstart](https://msdn.microsoft.com/library/gg430869(v=PandP.40).aspx).  
  
## <a name="classes-that-support-mvvm"></a>Klassen, die MVVM unterstützen  
 Wenn Sie das Ziel der [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight oder Windows Phone 7.5 für Ihre [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] -Projekt die folgenden Klassen zum Implementieren des Musters MVVM verfügbar sind:  
  
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
  
## <a name="implementing-mvvm"></a>Implementieren von MVVM  
 Um MVVM zu implementieren, Sie erstellen in der Regel das Modell und die Ansichtsmodell in einem [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] Projekt, da ein [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] Projekt kann nicht auf ein Projekt nicht portabel verweisen. Das Modell und die Ansichtsmodell im selben Projekt oder in separaten Projekten möglich. Wenn Sie separate Projekte verwenden, fügen Sie einen Verweis aus der Sicht Modellprojekt am Modellprojekt.  
  
 Nachdem Sie das Modell zu kompilieren und Modellprojekten anzeigen, verweisen Sie diese Assemblys in der app, die die Sicht enthält. Wenn die Ansicht nur das Ansichtsmodell interagiert, müssen Sie sich nur auf die Assembly verweisen, die das Ansichtsmodell enthält.  
  
### <a name="model"></a>Modell  
 Das folgende Beispiel zeigt eine vereinfachtes Modell-Klasse, die im befinden könnte ein [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] Projekt.  
  
 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]  
  
 Das folgende Beispiel zeigt eine einfache Möglichkeit zum Auffüllen, abrufen und aktualisieren Sie die Daten in einem [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] Projekt. In eine wirkliche app wäre die Daten aus einer Quelle, z. B. einen Windows Communication Foundation (WCF)-Dienst abgerufen werden.  
  
 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]  
  
### <a name="view-model"></a>Anzeigen des Modells  
 Eine Basisklasse für Modelle anzeigen wird häufig hinzugefügt werden, wenn das MVVM-Muster implementieren. Das folgende Beispiel zeigt eine Basisklasse.  
  
 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]  
  
 Eine Implementierung der <xref:System.Windows.Input.ICommand> Schnittstelle wird häufig verwendet, mit dem MVVM-Muster. Im folgenden Beispiel wird eine Implementierung der <xref:System.Windows.Input.ICommand>-Schnittstelle veranschaulicht.  
  
 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]  
  
 Das folgende Beispiel zeigt eine vereinfachte Ansicht-Modell.  
  
 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a>Ansicht  
 Aus einem [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] app [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, Silverlight-basierten Anwendung oder Windows Phone 7.5 app, können Sie die Assembly, die das Modell und Ansicht Modellprojekten enthält verweisen.  Anschließend erstellen Sie eine Sicht, die Interaktion mit dem Modell anzeigen. Das folgende Beispiel zeigt eine vereinfachte Windows Presentation Foundation (WPF)-app, die abgerufen und aktualisiert die Daten aus dem Modell anzeigen. Sie können ähnliche Ansichten erstellen, in Silverlight, Windows Phone-oder [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a>Siehe auch  
 [Portable Klassenbibliothek](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)
