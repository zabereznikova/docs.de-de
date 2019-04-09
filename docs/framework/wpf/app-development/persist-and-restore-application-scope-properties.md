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
ms.openlocfilehash: 99b04060d4e7c14313655010dc4fbd5ce1c90487
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134952"
---
# <a name="how-to-persist-and-restore-application-scope-properties-across-application-sessions"></a><span data-ttu-id="28ac0-102">Vorgehensweise: Beibehalten und Wiederherstellen von Eigenschaften für den Anwendungsbereich über mehrere Anwendungssitzungen</span><span class="sxs-lookup"><span data-stu-id="28ac0-102">How to: Persist and Restore Application-Scope Properties Across Application Sessions</span></span>
<span data-ttu-id="28ac0-103">Dieses Beispiel zeigt, wie Sie anwendungsspezifische Eigenschaften beibehalten werden, wenn eine Anwendung beendet wird und wie Sie zum Wiederherstellen starten Sie anwendungsspezifische Eigenschaften, wenn eine Anwendung weiter ist.</span><span class="sxs-lookup"><span data-stu-id="28ac0-103">This example shows how to persist application-scope properties when an application shuts down, and how to restore application-scope properties when an application is next launch.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28ac0-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="28ac0-104">Example</span></span>  
 <span data-ttu-id="28ac0-105">Die Anwendung beibehalten von Anwendungsbereichseigenschaften auf und stellt diese aus isoliertem Speicher wieder her.</span><span class="sxs-lookup"><span data-stu-id="28ac0-105">The application persists application-scope properties to, and restores them from, isolated storage.</span></span> <span data-ttu-id="28ac0-106">Isolierte Speicherung ist eine geschützte Speicherbereich, der von Anwendungen ohne Zugriffsberechtigungen für die Datei sicher verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="28ac0-106">Isolated storage is a protected storage area that can safely be used by applications without file access permission.</span></span>  <span data-ttu-id="28ac0-107">Die *"App.xaml"* -Datei definiert die `App_Startup` Methode als Ereignishandler für die <xref:System.Windows.Application.Startup?displayProperty=nameWithType> Ereignis und die `App_Exit` Methode als Ereignishandler für die <xref:System.Windows.Application.Exit?displayProperty=nameWithType> Ereignis, wie in der hervorgehobenen Zeilen im ersten Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="28ac0-107">The *App.xaml* file defines the `App_Startup` method as the handler for the <xref:System.Windows.Application.Startup?displayProperty=nameWithType> event, and the `App_Exit` method as the handler for the  <xref:System.Windows.Application.Exit?displayProperty=nameWithType> event, as shown in the highlighted lines of the first example.</span></span> <span data-ttu-id="28ac0-108">Das zweite Beispiel zeigt einen Teil der *"App.Xaml.cs"* und *"App.Xaml.vb"* Dateien, die der Code für markiert die `App_Startup` -Methode, die anwendungsspezifische Eigenschaften und die stelltwiederher`App_Exit` -Methode, die Eigenschaften für den Anwendungsbereich speichert.</span><span class="sxs-lookup"><span data-stu-id="28ac0-108">The second example shows a portion of the *App.xaml.cs* and *App.xaml.vb* files that highlights the code for the `App_Startup` method, which restores application-scope properties, and the `App_Exit` method, which saves application-scope properties.</span></span>

 [!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=17-55)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistrestoreappscopepropertiescodebehind1)]
