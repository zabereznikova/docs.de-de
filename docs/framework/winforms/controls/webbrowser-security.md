---
title: WebBrowser-Sicherheit
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: b25cabca050d06dbfe97c563eb56622d1f21be54
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095254"
---
# <a name="webbrowser-security"></a>WebBrowser-Sicherheit
Das <xref:System.Windows.Forms.WebBrowser>-Steuerelement ist nur für vollständige Vertrauenswürdigkeit konzipiert. Der im-Steuerelement angezeigte HTML-Inhalt kann von externen Webservern stammen und kann nicht verwalteten Code in Form von Skripts oder websteuer Elementen enthalten. Wenn Sie in dieser Situation das <xref:System.Windows.Forms.WebBrowser>-Steuerelement verwenden, ist das Steuerelement nicht weniger sicher als Internet Explorer, aber das verwaltete <xref:System.Windows.Forms.WebBrowser> Steuerelement verhindert nicht, dass dieser nicht verwaltete Code ausgeführt wird.  
  
 Weitere Informationen zu Sicherheitsproblemen im Zusammenhang mit dem zugrunde liegenden ActiveX-`WebBrowser` Steuerelement finden Sie unter [Webbrowser-Steuer](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))Element.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.WebBrowser>
- [Übersicht über das WebBrowser-Steuerelement](webbrowser-control-overview.md)
- [WebBrowser-Steuerelement](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))
