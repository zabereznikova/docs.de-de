---
title: WebBrowser-Sicherheit
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: 730d8f692a44a06ea142bb870bbd961d5983c785
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534611"
---
# <a name="webbrowser-security"></a>WebBrowser-Sicherheit
Die <xref:System.Windows.Forms.WebBrowser> Steuerelement soll nur vollständige Vertrauenswürdigkeit verwendet. Der HTML-Inhalt, der im Steuerelement angezeigte kann von externen Webservern stammen und darf nicht verwalteten Code in Form von Skripts oder Websteuerelementen enthalten. Bei Verwendung der <xref:System.Windows.Forms.WebBrowser> Steuerelement in diesem Fall kann das Steuerelement ist nicht unsicherer als Internet Explorer, aber die verwaltete werden würde <xref:System.Windows.Forms.WebBrowser> Steuerelement verhindert nicht solcher nicht verwalteten Code ausgeführt wird.  
  
 Weitere Informationen zu Sicherheitsproblemen im Zusammenhang mit der zugrunde liegenden ActiveX `WebBrowser` steuern, finden Sie unter [WebBrowser-Steuerelement](http://go.microsoft.com/fwlink/?LinkId=198812).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.WebBrowser>  
 [Übersicht über das WebBrowser-Steuerelement](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 [WebBrowser-Steuerelement](http://go.microsoft.com/fwlink/?LinkId=198812)
