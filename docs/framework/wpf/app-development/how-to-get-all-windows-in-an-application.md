---
title: 'Vorgehensweise: Abrufen aller Fenster in einer Anwendung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- window objects [WPF], getting
ms.assetid: f120f06e-993b-4a97-9657-af0d1986981f
ms.openlocfilehash: 34316f0c6f81b960a8e00131a30b9a237b9ca938
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947770"
---
# <a name="how-to-get-all-windows-in-an-application"></a>Vorgehensweise: Abrufen aller Fenster in einer Anwendung
In diesem Beispiel wird gezeigt, wie zum Abrufen aller <xref:System.Windows.Window> Objekte in einer Anwendung.  
  
## <a name="example"></a>Beispiel  
 Jede instanziiert <xref:System.Windows.Window> Objekt, ob sichtbar oder nicht, wird automatisch hinzugefügt, um eine Auflistung der Verweise auf Fenster, die von verwaltet wird <xref:System.Windows.Application>, und vom verfügbar gemachten <xref:System.Windows.Application.Windows%2A>.  
  
 Sie können auflisten <xref:System.Windows.Application.Windows%2A> zum Abrufen aller instanziierten Fenster, die mit dem folgenden Code:  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetAllWindows](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/CustomWindow.xaml.cs#getallwindows)]
 [!code-vb[HOWTOWindowManagementSnippets#GetAllWindows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/customwindow.xaml.vb#getallwindows)]
