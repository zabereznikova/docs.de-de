---
title: 'Vorgehensweise: Festlegen der Breite eines Fensters von einer Seite'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- width of windows [WPF], setting from a page
- windows [WPF], setting width from a page
- pages [WPF], setting window width from
ms.assetid: 31601c92-7889-472a-b07e-bf675ad21c92
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7354a6c3f1b913494da9ad45181a0c7741a1cfa2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a>Vorgehensweise: Festlegen der Breite eines Fensters von einer Seite
In diesem Beispiel wird veranschaulicht, wie die Breite des Fensters aus Festlegen einer <xref:System.Windows.Controls.Page>.  
  
## <a name="example"></a>Beispiel  
 Ein <xref:System.Windows.Controls.Page> kann durch Festlegen der Breite der entsprechende Hostfenster festgelegt <xref:System.Windows.Controls.Page.WindowWidth%2A>. Diese Eigenschaft ermöglicht die <xref:System.Windows.Controls.Page> keine explizite Kenntnisse in den Typ des Fensters aufweisen, die diese hostet.  
  
> [!NOTE]
>  Die Breite des Fensters festzulegende <xref:System.Windows.Controls.Page.WindowWidth%2A>ein <xref:System.Windows.Controls.Page> muss das untergeordnete Element eines Fensters.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
