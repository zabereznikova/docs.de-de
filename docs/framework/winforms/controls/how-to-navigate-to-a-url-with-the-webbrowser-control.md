---
title: 'Vorgehensweise: Navigieren Sie zu einer URL mit dem WebBrowser-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- WebBrowser.Navigate
helpviewer_keywords:
- WebBrowser control [Windows Forms], examples
- URLs [Windows Forms], navigating to
- WebBrowser control [Windows Forms], navigating to URLs
- examples [Windows Forms], WebBrowser control
ms.assetid: b3ec38cb-f509-4d0b-bd79-9f3611259c62
ms.openlocfilehash: 8d592aea972a95a582cc35ecb14227edec5860ce
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707234"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a>Vorgehensweise: Navigieren Sie zu einer URL mit dem WebBrowser-Steuerelement
Im folgenden Codebeispiel wird veranschaulicht, wie zum Navigieren der <xref:System.Windows.Forms.WebBrowser> Steuerelement an eine bestimmte URL.  
  
 Um zu bestimmen, wann das neue Dokument vollständig geladen wurde, behandelt der <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> Ereignis. Eine Demonstration dieses Ereignisses finden Sie unter [Vorgehensweise: Mit einem WebBrowser-Steuerelement Drucken](how-to-print-with-a-webbrowser-control.md).  
  
## <a name="example"></a>Beispiel  
  
```vb  
Me.webBrowser1.Navigate("http://www.microsoft.com")  
```  
  
```csharp  
this.webBrowser1.Navigate("http://www.microsoft.com");  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Windows.Forms.WebBrowser>-Steuerelement namens `webBrowser1`.  
  
-   Verweise auf die Assemblys `System` und `System.Windows.Forms`.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>
- [WebBrowser-Steuerelement](webbrowser-control-windows-forms.md)
- [Vorgehensweise: Drucken Sie mit einem WebBrowser-Steuerelement](how-to-print-with-a-webbrowser-control.md)
