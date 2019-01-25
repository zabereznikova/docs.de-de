---
title: 'Vorgehensweise: Bestimmen Sie, ob eine Seite im Browser gehostet wird'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosted pages in browser [WPF]
- pages [WPF], hosted in browser
ms.assetid: 737e0f26-8371-49b4-9579-70879e51e1aa
ms.openlocfilehash: aa2aa36e4f887c4fa02314f7834e2a46268c8ff9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661294"
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a><span data-ttu-id="06b12-102">Vorgehensweise: Bestimmen Sie, ob eine Seite im Browser gehostet wird</span><span class="sxs-lookup"><span data-stu-id="06b12-102">How to: Determine If a Page is Browser Hosted</span></span>
<span data-ttu-id="06b12-103">In diesem Beispiel wird veranschaulicht, wie Sie bestimmen, ob eine <xref:System.Windows.Controls.Page> in einem Browser gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="06b12-103">This example demonstrates how to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06b12-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="06b12-104">Example</span></span>  
 <span data-ttu-id="06b12-105">Ein <xref:System.Windows.Controls.Page> kann hostunabhängig und, folglich geladen werden, in verschiedene Arten von Hosts, einschließlich einer <xref:System.Windows.Controls.Frame>, ein <xref:System.Windows.Navigation.NavigationWindow>, oder einen Browser.</span><span class="sxs-lookup"><span data-stu-id="06b12-105">A <xref:System.Windows.Controls.Page> can be host agnostic and, consequently, can be loaded into several different types of hosts, including a <xref:System.Windows.Controls.Frame>, a <xref:System.Windows.Navigation.NavigationWindow>, or a browser.</span></span> <span data-ttu-id="06b12-106">Dies kann auftreten, wenn man eine Bibliotheksassembly, die eine oder mehrere Seiten enthält, und befindet sich auf die verwiesen wird durch mehrere eigenständige und durchsucht werden kann ([!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]) Anwendungen hosten.</span><span class="sxs-lookup"><span data-stu-id="06b12-106">This can happen when you have a library assembly that contains one or more pages, and which is referenced by multiple standalone and browsable ([!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]) host applications.</span></span>  
  
 <span data-ttu-id="06b12-107">Im folgenden Beispiel wird veranschaulicht, wie <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> zu entscheiden, ob eine <xref:System.Windows.Controls.Page> in einem Browser gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="06b12-107">The following example demonstrates how to use <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a><span data-ttu-id="06b12-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06b12-108">See also</span></span>
- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
