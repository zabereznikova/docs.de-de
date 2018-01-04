---
title: WebBrowser-Sicherheit
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3985fc9916b3e95e650502ef1f8dc301363b1f90
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="webbrowser-security"></a>WebBrowser-Sicherheit
Die <xref:System.Windows.Forms.WebBrowser> Steuerelement soll nur vollständige Vertrauenswürdigkeit verwendet. Der HTML-Inhalt, der im Steuerelement angezeigte kann von externen Webservern stammen und darf nicht verwalteten Code in Form von Skripts oder Websteuerelementen enthalten. Bei Verwendung der <xref:System.Windows.Forms.WebBrowser> Steuerelement in diesem Fall kann das Steuerelement ist nicht unsicherer als Internet Explorer, aber die verwaltete werden würde <xref:System.Windows.Forms.WebBrowser> Steuerelement verhindert nicht solcher nicht verwalteten Code ausgeführt wird.  
  
 Weitere Informationen zu Sicherheitsproblemen im Zusammenhang mit der zugrunde liegenden ActiveX `WebBrowser` steuern, finden Sie unter [WebBrowser-Steuerelement](http://go.microsoft.com/fwlink/?LinkId=198812).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.WebBrowser>  
 [Übersicht über das WebBrowser-Steuerelement](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 [WebBrowser-Steuerelement](http://go.microsoft.com/fwlink/?LinkId=198812)
