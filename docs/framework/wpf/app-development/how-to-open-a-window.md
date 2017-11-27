---
title: "Vorgehensweise: Öffnen Sie ein Fenster"
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
- windows [WPF], opening
- opening windows [WPF]
ms.assetid: 6b91b2bb-fda7-491d-a72e-139dd630a5b0
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6eec13ec1bac864376fcdf5417cc4be68f16dd46
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-open-a-window"></a><span data-ttu-id="1fbda-102">Vorgehensweise: Öffnen Sie ein Fenster</span><span class="sxs-lookup"><span data-stu-id="1fbda-102">How to: Open a Window</span></span>
<span data-ttu-id="1fbda-103">In diesem Beispiel wird gezeigt, wie ein Fenster geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="1fbda-103">This example shows how to open a window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fbda-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1fbda-104">Example</span></span>  
 <span data-ttu-id="1fbda-105">Ein Fenster wird geöffnet, durch die Instanziierung <xref:System.Windows.Window> und Aufrufen der <xref:System.Windows.Window.Show%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="1fbda-105">A window is opened by instantiating <xref:System.Windows.Window> and calling the <xref:System.Windows.Window.Show%2A> method.</span></span> <span data-ttu-id="1fbda-106"><xref:System.Windows.Window.Show%2A>Öffnet ein Fenster und kehrt sofort zurück, ohne zu warten, für das neue Fenster zu schließen.</span><span class="sxs-lookup"><span data-stu-id="1fbda-106"><xref:System.Windows.Window.Show%2A> opens a window and returns immediately without waiting for the new window to close.</span></span> <span data-ttu-id="1fbda-107">Diese Art von Fenster ist auch bekannt als ein *nicht modalen* Fenster, und schränkt keine Benutzereingaben.</span><span class="sxs-lookup"><span data-stu-id="1fbda-107">This type of window is also known as a *modeless* window, and doesn't restrict user input.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewWindowCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewwindowcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewWindowCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewwindowcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="1fbda-108">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="1fbda-108">.NET Framework Security</span></span>  
 <span data-ttu-id="1fbda-109">Instanziieren <xref:System.Windows.Window> erfordert die Berechtigung zum Aufruf von unsicheren systemeigener Methoden (siehe <xref:System.Windows.Window.%23ctor%2A>).</span><span class="sxs-lookup"><span data-stu-id="1fbda-109">Instantiating <xref:System.Windows.Window> requires permission to call unsafe native methods (see <xref:System.Windows.Window.%23ctor%2A>).</span></span>
