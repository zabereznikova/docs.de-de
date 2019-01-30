---
title: 'Vorgehensweise: Beibehalten und Wiederherstellen von Eigenschaften für den Anwendungsbereich über mehrere Anwendungssitzungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application-scope properties [WPF], persisting
- persisting application-scope properties [WPF]
- properties [WPF], persisting
- restoring application-scope properties [WPF]
- properties [WPF], restoring
- application-scope properties [WPF], restoring
ms.assetid: 55d5904a-f444-4eb5-abd3-6bc74dd14226
ms.openlocfilehash: c64b13717a427bf7ad8f9cab0a450162ad0c6cde
ms.sourcegitcommit: e39d93d358974b9ed4541cedf4e25c0101015c3c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2019
ms.locfileid: "55204699"
---
# <a name="how-to-persist-and-restore-application-scope-properties-across-application-sessions"></a>Vorgehensweise: Beibehalten und Wiederherstellen von Eigenschaften für den Anwendungsbereich über mehrere Anwendungssitzungen
Dieses Beispiel zeigt, wie Sie anwendungsspezifische Eigenschaften beibehalten werden, wenn eine Anwendung beendet wird und wie Sie zum Wiederherstellen starten Sie anwendungsspezifische Eigenschaften, wenn eine Anwendung weiter ist.  
  
## <a name="example"></a>Beispiel  
 Die Anwendung beibehalten von Anwendungsbereichseigenschaften auf und stellt diese aus isoliertem Speicher wieder her. Isolierte Speicherung ist eine geschützte Speicherbereich, der von Anwendungen ohne Zugriffsberechtigungen für die Datei sicher verwendet werden kann.  Die *"App.xaml"* -Datei definiert die `App_Startup` Methode als Ereignishandler für die <xref:System.Windows.Application.Startup?displayProperty=nameWithType> Ereignis und die `App_Exit` Methode als Ereignishandler für die <xref:System.Windows.Application.Exit?displayProperty=nameWithType> Ereignis, wie in der hervorgehobenen Zeilen im ersten Beispiel gezeigt. Das zweite Beispiel zeigt einen Teil der *"App.Xaml.cs"* und *"App.Xaml.vb"* Dateien, die der Code für markiert die `App_Startup` -Methode, die anwendungsspezifische Eigenschaften und die stelltwiederher`App_Exit` -Methode, die Eigenschaften für den Anwendungsbereich speichert.
 
  
 [!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=17-55)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistrestoreappscopepropertiescodebehind1)]
 
