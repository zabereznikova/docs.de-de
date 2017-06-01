---
title: "Verwenden der portablen Klassenbibliothek mit Model-View-View Model | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Portable Klassenbibliothek [.NET Framework] und MVVM"
  - "MVVM und portable Klassenbibliothek"
ms.assetid: 41a0b9f8-15a2-431a-bc35-e310b2953b03
caps.latest.revision: 17
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 17
---
# Verwenden der portablen Klassenbibliothek mit Model-View-View Model
Sie können .NET Framework [Portable Klassenbibliothek](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) verwenden, um das Muster MVVM \(Model\-View\-View Model \(MVVM\) zu implementieren und Assemblys auf mehreren Plattformen freigegeben.  
  
 MVVM ist ein Anwendungsmuster, das die Benutzeroberfläche von der zugrunde liegenden Geschäftslogik isoliert.  Sie können die Modell\- und Ansichtsmodellklassen in einem [!INCLUDE[net_portable](../../../includes/net-portable-md.md)][!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]\- Projekt implementieren und dann Ansichten erstellen, die für unterschiedliche Plattformen angepasst sind.  Dieser Ansatz ermöglicht Ihnen, das Datenmodell und die Geschäftslogik nur einmal schreiben und verwendet diesen Code in .NET Framework, von Silverlight, Windows Phone und [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] \- Apps, wie in der folgenden Abbildung gezeigt.  
  
 ![Übertragbar mit MMM&#45;Diagramm](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")  
  
 Dieses Thema bietet keine allgemeinen Informationen über das MVVM\-Muster.  Es enthält nur Informationen darüber, wie [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] zum Implementieren von MVVM verwendet wird.  Weitere Informationen über MVVM, finden Sie unter [MVVM Schnellstart](http://go.microsoft.com/fwlink/?LinkId=234934) in der MSDN Library.  
  
## Klassen, die MVVM unterstützen  
 Wenn die Zielplattform des [!INCLUDE[net_portable](../../../includes/net-portable-md.md)]\-Projekts, [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], .[!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight oder Windows Phone 7.5 ist, sind die folgenden Klassen zum Implementieren des MVVM\-Musters verfügbar:  
  
-   <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=fullName>\-Klasse  
  
-   <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=fullName>\-Klasse  
  
-   <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=fullName>\-Klasse  
  
-   <xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=fullName>\-Klasse  
  
-   <xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=fullName>\-Klasse  
  
-   <xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=fullName>\-Klasse  
  
-   <xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=fullName>\-Klasse  
  
-   <xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=fullName>\-Klasse  
  
-   <xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=fullName>\-Klasse  
  
-   <xref:System.Windows.Input.ICommand?displayProperty=fullName>\-Klasse  
  
-   Alle Klassen im <xref:System.ComponentModel.DataAnnotations?displayProperty=fullName>\-Namespace  
  
## Implementieren von MVVM  
 Zum Implementieren von MVVM erstellen Sie in der Regel das Modell und das Ansichtsmodell in einem [!INCLUDE[net_portable](../../../includes/net-portable-md.md)]\-Projekt, da ein [!INCLUDE[net_portable](../../../includes/net-portable-md.md)]\-Projekt nur auf portable Projekte verweisen kann.  Das Modell und das Ansichtsmodell können sich im gleichen Projekt oder in verschiedenen Projekten befinden.  Wenn Sie verschiedene Projekte verwenden, fügen Sie einen Verweis vom Ansichtsmodellprojekt zum Modellprojekt hinzu.  
  
 Nachdem Sie das Modellprojekt und das Ansichtsmodellprojekt kompiliert haben, verweisen Sie in der App, in der sich die Ansicht befindet, auf die entsprechenden Assemblys.  Wenn die Ansicht nur mit dem Ansichtsmodell interagiert, müssen Sie nur auf die Assembly verweisen, die das Ansichtsmodell enthält.  
  
### Modell  
 Im folgenden Beispiel wird eine vereinfachte Modellklasse gezeigt, die sich in einem [!INCLUDE[net_portable](../../../includes/net-portable-md.md)]\-Projekt befinden kann.  
  
 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]  
  
 Das folgende Beispiel zeigt eine einfache Möglichkeit zum Füllen, Abrufen und Aktualisieren der Daten in einem [!INCLUDE[net_portable](../../../includes/net-portable-md.md)]\-Projekt.  In einer realen App rufen Sie die Daten aus einer Quelle wie einem Windows Communication Foundation \(WCF\)\-Dienst ab.  
  
 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]  
  
### Ansichtsmodell  
 Beim Implementieren des MVVM\-Musters wird häufig eine Basisklasse für Ansichtsmodelle hinzugefügt.  Das folgende Beispiel zeigt eine Basisklasse.  
  
 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]  
  
 Mit dem MVVM\-Muster wird häufig eine Implementierung der <xref:System.Windows.Input.ICommand>\-Schnittstelle verwendet.  Im folgenden Beispiel wird eine Implementierung der <xref:System.Windows.Input.ICommand>\-Schnittstelle veranschaulicht.  
  
 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]  
  
 Im folgenden Beispiel wird ein vereinfachtes Ansichtsmodell gezeigt.  
  
 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### Ansicht  
 Sie können von einer [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]\-App, einer App im [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], einer Silverlight\-App oder Windows Phone 7.5\-App auf die Assembly verweisen, die das Modellprojekt und das Ansichtsmodellprojekt enthält.  Anschließend erstellen Sie eine Ansicht, die mit dem Ansichtsmodell interagiert.  Im folgenden Beispiel wird eine vereinfachte WPF \(Windows Presentation Foundation\)\-App gezeigt, die Daten aus dem Ansichtsmodell abfragt und aktualisiert.  Sie können in Silverlight\-Apps, Windows Phone\-Apps oder Apps im [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] ähnliche Ansichten erstellen.  
  
 [!code-xml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## Siehe auch  
 [Portable Klassenbibliothek](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)