---
title: 'Vorgehensweise: Navigieren zu einem URL mit dem WebBrowser-Steuerelement'
description: Erfahren Sie, wie Sie das Windows Forms WebBrowser. Navigate-Steuerelement verwenden, um zu einer bestimmten URL zu navigieren. Erfahren Sie außerdem, wie Sie bestimmen, wann das neue Dokument geladen wird.
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
ms.openlocfilehash: e6ad360cc73a84ca040869832bb59d354cb78bd5
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325577"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a>Vorgehensweise: Navigieren zu einem URL mit dem WebBrowser-Steuerelement
Im folgenden Codebeispiel wird veranschaulicht, wie Sie das- <xref:System.Windows.Forms.WebBrowser> Steuerelement zu einer bestimmten URL navigieren.

 Behandeln Sie das-Ereignis, um zu bestimmen, wann das neue Dokument vollständig geladen wurde <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> . Eine Demonstration dieses Ereignisses finden Sie unter Gewusst [wie: Drucken mit einem Webbrowser-Steuer](how-to-print-with-a-webbrowser-control.md)Element.

## <a name="example"></a>Beispiel

```vb
Me.webBrowser1.Navigate("https://www.microsoft.com")
```

```csharp
this.webBrowser1.Navigate("https://www.microsoft.com");
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
- [Vorgehensweise: Drucken mit einem WebBrowser-Steuerelement](how-to-print-with-a-webbrowser-control.md)
