---
title: 'Vorgehensweise: Bestimmen, ob eine Seite im Browser gehostet wird'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosted pages in browser [WPF]
- pages [WPF], hosted in browser
ms.assetid: 737e0f26-8371-49b4-9579-70879e51e1aa
ms.openlocfilehash: d154de2f885101d1bd0c4613dfb1604be8acbe6a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107145"
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a>Vorgehensweise: Bestimmen, ob eine Seite im Browser gehostet wird
In diesem Beispiel wird veranschaulicht, wie Sie bestimmen, ob eine <xref:System.Windows.Controls.Page> in einem Browser gehostet wird.  
  
## <a name="example"></a>Beispiel  
 Ein <xref:System.Windows.Controls.Page> kann hostunabhängig und, folglich geladen werden, in verschiedene Arten von Hosts, einschließlich einer <xref:System.Windows.Controls.Frame>, ein <xref:System.Windows.Navigation.NavigationWindow>, oder einen Browser. Dies kann auftreten, wenn man eine Bibliotheksassembly, die eine oder mehrere Seiten enthält, und befindet sich auf die verwiesen wird durch mehrere eigenständige und durchsucht werden kann ([!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]) Anwendungen hosten.  
  
 Im folgenden Beispiel wird veranschaulicht, wie <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> zu entscheiden, ob eine <xref:System.Windows.Controls.Page> in einem Browser gehostet wird.  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
