---
title: "Gewusst wie: Abrufen des R&#252;ckgabewerts einer Seitenfunktion | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Funktionen, Abrufen von Rückgabewerten von"
  - "Abrufen, Rückgabewerte für Seitenfunktionen"
  - "Seitenfunktionen, Abrufen von Rückgabewerten von"
  - "Rückgabewerte für Seitenfunktionen"
ms.assetid: 75470af6-256c-4c46-87e7-705080723a1c
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Abrufen des R&#252;ckgabewerts einer Seitenfunktion
In diesem Beispiel wird gezeigt, wie das Ergebnis, das von einer Seitenfunktion zurückgegeben wird, abgerufen wird.  
  
## Beispiel  
 Um das Ergebnis abzurufen, das von einer Seitenfunktion zurückgegeben wird, müssen Sie das <xref:System.Windows.Navigation.PageFunction%601.Return>\-Element der aufgerufenen Seitenfunktion verarbeiten.  
  
 [!code-xml[HOWTOPageFunctionSnippets#CallAPageFunctionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml#callapagefunctionxaml)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#GetPageFunctionResultCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#getpagefunctionresultcodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#GetPageFunctionResultCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#getpagefunctionresultcodebehind)]  
  
## Siehe auch  
 <xref:System.Windows.Navigation.PageFunction%601>