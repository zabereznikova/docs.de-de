---
title: 'Vorgehensweise: Öffnen eines Fensters'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows [WPF], opening
- opening windows [WPF]
ms.assetid: 6b91b2bb-fda7-491d-a72e-139dd630a5b0
ms.openlocfilehash: 9ce7ffb3f46dd869fda7893745b531bd02d18ee1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947679"
---
# <a name="how-to-open-a-window"></a><span data-ttu-id="c004c-102">Vorgehensweise: Öffnen eines Fensters</span><span class="sxs-lookup"><span data-stu-id="c004c-102">How to: Open a Window</span></span>
<span data-ttu-id="c004c-103">Dieses Beispiel zeigt, wie Sie ein Fenster zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c004c-103">This example shows how to open a window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c004c-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c004c-104">Example</span></span>  
 <span data-ttu-id="c004c-105">Ein Fenster wird geöffnet, durch die Instanziierung <xref:System.Windows.Window> und das Aufrufen der <xref:System.Windows.Window.Show%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="c004c-105">A window is opened by instantiating <xref:System.Windows.Window> and calling the <xref:System.Windows.Window.Show%2A> method.</span></span> <span data-ttu-id="c004c-106"><xref:System.Windows.Window.Show%2A> Öffnet ein Fenster und kehrt sofort zurück, ohne zu warten, für das neue Fenster zu schließen.</span><span class="sxs-lookup"><span data-stu-id="c004c-106"><xref:System.Windows.Window.Show%2A> opens a window and returns immediately without waiting for the new window to close.</span></span> <span data-ttu-id="c004c-107">Diese Art von Fenster wird auch bezeichnet als eine *nicht modale* Fenster, und schränkt keine Benutzereingaben.</span><span class="sxs-lookup"><span data-stu-id="c004c-107">This type of window is also known as a *modeless* window, and doesn't restrict user input.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewwindowcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewwindowcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="c004c-108">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c004c-108">.NET Framework Security</span></span>  
 <span data-ttu-id="c004c-109">Instanziieren von <xref:System.Windows.Window> erfordert die Berechtigung auf unsafe native Methoden aufzurufen (finden Sie unter <xref:System.Windows.Window.%23ctor%2A>).</span><span class="sxs-lookup"><span data-stu-id="c004c-109">Instantiating <xref:System.Windows.Window> requires permission to call unsafe native methods (see <xref:System.Windows.Window.%23ctor%2A>).</span></span>
