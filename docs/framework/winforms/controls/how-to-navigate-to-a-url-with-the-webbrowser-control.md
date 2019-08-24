---
title: 'Vorgehensweise: Navigieren zu einem URL mit dem WebBrowser-Steuerelement'
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
ms.openlocfilehash: b6c1255fa17d91daaa73001fea04f26e73dba0ae
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015825"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a>Vorgehensweise: Navigieren zu einem URL mit dem WebBrowser-Steuerelement
Im folgenden Codebeispiel wird veranschaulicht, wie Sie <xref:System.Windows.Forms.WebBrowser> das-Steuerelement zu einer bestimmten URL navigieren.

 Behandeln Sie das <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> -Ereignis, um zu bestimmen, wann das neue Dokument vollständig geladen wurde. Eine Demonstration dieses Ereignisses finden [Sie unter Gewusst wie: Drucken mit einem Webbrowser-](how-to-print-with-a-webbrowser-control.md)Steuerelement.

## <a name="example"></a>Beispiel

```vb
Me.webBrowser1.Navigate("http://www.microsoft.com")
```

```csharp
this.webBrowser1.Navigate("http://www.microsoft.com");
```

## <a name="compiling-the-code"></a>Kompilieren des Codes
 Für dieses Beispiel benötigen Sie Folgendes:

- Ein <xref:System.Windows.Forms.WebBrowser>-Steuerelement namens `webBrowser1`.

- Verweise auf die Assemblys `System` und `System.Windows.Forms`.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>
- [WebBrowser-Steuerelement](webbrowser-control-windows-forms.md)
- [Vorgehensweise: Drucken mit einem Webbrowser-Steuerelement](how-to-print-with-a-webbrowser-control.md)
