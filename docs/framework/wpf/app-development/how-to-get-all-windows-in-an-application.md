---
title: 'Vorgehensweise: Abrufen Sie aller Windows in einer Anwendung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- window objects [WPF], getting
ms.assetid: f120f06e-993b-4a97-9657-af0d1986981f
ms.openlocfilehash: 34316f0c6f81b960a8e00131a30b9a237b9ca938
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378821"
---
# <a name="how-to-get-all-windows-in-an-application"></a>Vorgehensweise: Abrufen Sie aller Windows in einer Anwendung
In diesem Beispiel wird gezeigt, wie zum Abrufen aller <xref:System.Windows.Window> Objekte in einer Anwendung.  
  
## <a name="example"></a>Beispiel  
 Jede instanziiert <xref:System.Windows.Window> Objekt, ob sichtbar oder nicht, wird automatisch hinzugefügt, um eine Auflistung der Verweise auf Fenster, die von verwaltet wird <xref:System.Windows.Application>, und vom verfügbar gemachten <xref:System.Windows.Application.Windows%2A>.  
  
 Sie können auflisten <xref:System.Windows.Application.Windows%2A> zum Abrufen aller instanziierten Fenster, die mit dem folgenden Code:  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetAllWindows](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/CustomWindow.xaml.cs#getallwindows)]
 [!code-vb[HOWTOWindowManagementSnippets#GetAllWindows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/customwindow.xaml.vb#getallwindows)]
