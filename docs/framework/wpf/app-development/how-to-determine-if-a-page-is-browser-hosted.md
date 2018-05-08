---
title: 'Vorgehensweise: bestimmen, ob eine Seite im Browser gehostet wird'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosted pages in browser [WPF]
- pages [WPF], hosted in browser
ms.assetid: 737e0f26-8371-49b4-9579-70879e51e1aa
ms.openlocfilehash: 6eb83429cb4f9dac5f3561b41997d24bcaa2c62f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a>Vorgehensweise: bestimmen, ob eine Seite im Browser gehostet wird
In diesem Beispiel wird veranschaulicht, wie ermittelt werden, ob eine <xref:System.Windows.Controls.Page> in einem Browser gehostet wird.  
  
## <a name="example"></a>Beispiel  
 Ein <xref:System.Windows.Controls.Page> kann hostunabhängig und können daher in verschiedene Typen von Hosts, einschließlich geladen werden eine <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Navigation.NavigationWindow>, oder einen Browser. Dies kann auftreten, wenn einer oder mehreren Seiten enthält, und die verwiesen wird, indem Sie mehrere eigenständige und durchsucht werden kann, haben eine Bibliotheksassembly ([!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]) Anwendungen hosten.  
  
 Im folgenden Beispiel wird veranschaulicht, wie <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> zum bestimmen, ob eine <xref:System.Windows.Controls.Page> in einem Browser gehostet wird.  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Frame>  
 <xref:System.Windows.Controls.Page>
