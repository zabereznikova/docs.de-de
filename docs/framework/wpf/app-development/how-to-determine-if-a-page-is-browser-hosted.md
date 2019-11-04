---
title: 'Gewusst wie: bestimmen, ob eine Seite Browser gehostet ist'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosted pages in browser [WPF]
- pages [WPF], hosted in browser
ms.assetid: 737e0f26-8371-49b4-9579-70879e51e1aa
ms.openlocfilehash: c4cb1065807d16c1d1f5a95c8ac9c9cbe5a0fdab
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424689"
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a>Gewusst wie: bestimmen, ob eine Seite Browser gehostet ist
In diesem Beispiel wird veranschaulicht, wie ermittelt wird, ob ein <xref:System.Windows.Controls.Page> in einem Browser gehostet wird.  
  
## <a name="example"></a>Beispiel  
 Eine <xref:System.Windows.Controls.Page> kann Host agnostisch sein und daher in verschiedene Arten von Hosts geladen werden, einschließlich einer <xref:System.Windows.Controls.Frame>, eines <xref:System.Windows.Navigation.NavigationWindow>oder eines Browsers. Dies kann vorkommen, wenn eine Bibliotheksassembly vorhanden ist, die eine oder mehrere Seiten enthält und auf die von mehreren eigenständigen und durch suchbaren (XBAP) Host Anwendungen verwiesen wird.  
  
 Im folgenden Beispiel wird veranschaulicht, wie <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> verwendet wird, um zu bestimmen, ob ein <xref:System.Windows.Controls.Page> in einem Browser gehostet wird.  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
