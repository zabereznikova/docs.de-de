---
title: 'Vorgehensweise: Festlegen des Titels eines Fensters einer Seite'
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting title from a page
- title of window [WPF], setting from a page
- pages [WPF], setting window title from
ms.assetid: fecf0d19-3eb6-4f8c-a44f-ff1b6f2b34b3
ms.openlocfilehash: 55444de6c61107979307b94910ba944e7001cf9e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054002"
---
# <a name="how-to-set-the-title-of-a-window-from-a-page"></a><span data-ttu-id="88d97-102">Vorgehensweise: Festlegen des Titels eines Fensters einer Seite</span><span class="sxs-lookup"><span data-stu-id="88d97-102">How to: Set the Title of a Window from a Page</span></span>
<span data-ttu-id="88d97-103">Dieses Beispiel veranschaulicht die legen Sie des Titels des Fensters in der ein <xref:System.Windows.Controls.Page> gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="88d97-103">This example shows how to set the title of the window in which a <xref:System.Windows.Controls.Page> is hosted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88d97-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="88d97-104">Example</span></span>  
 <span data-ttu-id="88d97-105">Eine Seite kann ändern Sie den Titel des Fensters, das sie durch Festlegen von hostet die <xref:System.Windows.Controls.Page.WindowTitle%2A> -Eigenschaft wie folgt:</span><span class="sxs-lookup"><span data-stu-id="88d97-105">A page can change the title of the window that is hosting it by setting the <xref:System.Windows.Controls.Page.WindowTitle%2A> property, like so:</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowTitleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowTitlePage.xaml#setpagewindowtitlexaml)]  
  
> [!NOTE]
>  <span data-ttu-id="88d97-106">Festlegen der <xref:System.Windows.Controls.Page.Title%2A> Eigenschaft einer Seite ändert sich nicht auf den Wert der der Titel des Fensters.</span><span class="sxs-lookup"><span data-stu-id="88d97-106">Setting the <xref:System.Windows.Controls.Page.Title%2A> property of a page does not change the value of the window title.</span></span> <span data-ttu-id="88d97-107">Stattdessen <xref:System.Windows.Controls.Page.Title%2A> gibt Sie den Namen eines Eintrags für die Seite im Navigationsverlauf.</span><span class="sxs-lookup"><span data-stu-id="88d97-107">Instead, <xref:System.Windows.Controls.Page.Title%2A> specifies the name of a page entry in navigation history.</span></span>
