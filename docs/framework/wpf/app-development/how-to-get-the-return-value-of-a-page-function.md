---
title: "Gewusst wie: Abrufen des Rückgabewerts einer Seitenfunktion"
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
- functions [WPF], getting return values of
- page functions [WPF], getting return values of
- return values of page functions [WPF]
- getting [WPF], return values of page functions
ms.assetid: 75470af6-256c-4c46-87e7-705080723a1c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 86c767de0b05563a91ee624c24f530c61d582f47
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-get-the-return-value-of-a-page-function"></a>Gewusst wie: Abrufen des Rückgabewerts einer Seitenfunktion
In diesem Beispiel wird gezeigt, wie das Ergebnis, das von einer Seitenfunktion zurückgegeben wird, abgerufen wird.  
  
## <a name="example"></a>Beispiel  
 Zum Abrufen des Ergebnisses, das von einer Seitenfunktion zurückgegeben wird, müssen Sie behandeln <xref:System.Windows.Navigation.PageFunction%601.Return> der Seite "-Funktion, die Sie aufrufen.  
  
 [!code-xaml[HOWTOPageFunctionSnippets#CallAPageFunctionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml#callapagefunctionxaml)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#GetPageFunctionResultCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#getpagefunctionresultcodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#GetPageFunctionResultCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#getpagefunctionresultcodebehind)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Navigation.PageFunction%601>
