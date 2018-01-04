---
title: "Gewusst wie: Beibehalten und Wiederherstellen von Eigenschaften für den Anwendungsbereich über mehrere Anwendungssitzungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 815efbe0a4adcacddeb4c1a70cc3c1fef21fed05
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-persist-and-restore-application-scope-properties-across-application-sessions"></a><span data-ttu-id="ba5e3-102">Gewusst wie: Beibehalten und Wiederherstellen von Eigenschaften für den Anwendungsbereich über mehrere Anwendungssitzungen</span><span class="sxs-lookup"><span data-stu-id="ba5e3-102">How to: Persist and Restore Application-Scope Properties Across Application Sessions</span></span>
<span data-ttu-id="ba5e3-103">Dieses Beispiel zeigt, wie Sie anwendungsspezifische Eigenschaften persistent zu speichern, wenn eine Anwendung heruntergefahren und zum Wiederherstellen starten Sie anwendungsspezifische Eigenschaften, wenn eine Anwendung weiter.</span><span class="sxs-lookup"><span data-stu-id="ba5e3-103">This example shows how to persist application-scope properties when an application shuts down, and how to restore application-scope properties when an application is next launch.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba5e3-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ba5e3-104">Example</span></span>  
 <span data-ttu-id="ba5e3-105">Die Anwendung anwendungsspezifische Eigenschaften zum beibehalten und Wiederherstellen von isolierten Speicher.</span><span class="sxs-lookup"><span data-stu-id="ba5e3-105">The application persists application-scope properties to, and restores them from, isolated storage.</span></span> <span data-ttu-id="ba5e3-106">Isolierte Speicherung ist eine geschützte Speicherbereich, der von Anwendungen ohne Zugriffsberechtigung für die Datei sicher verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ba5e3-106">Isolated storage is a protected storage area that can safely be used by applications without file access permission.</span></span>  
  
 [!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml#persistrestoreappscopepropertiesxaml1)]  
[!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml#persistrestoreappscopepropertiesxaml2)]  
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs#persistrestoreappscopepropertiescodebehind1)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistrestoreappscopepropertiescodebehind1)]  
[!code-csharp[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs#persistrestoreappscopepropertiescodebehind2)]
[!code-vb[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistrestoreappscopepropertiescodebehind2)]  
[!code-csharp[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs#persistrestoreappscopepropertiescodebehind3)]
[!code-vb[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistrestoreappscopepropertiescodebehind3)]
