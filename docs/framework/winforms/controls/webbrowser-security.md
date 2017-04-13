---
title: "WebBrowser-Sicherheit | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Sicherheit [Windows Forms], WebBrowser-Steuerelement"
  - "WebBrowser-Steuerelement [Windows Forms], Sicherheit"
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# WebBrowser-Sicherheit
Das <xref:System.Windows.Forms.WebBrowser>\-Steuerelement kann nur unter voller Vertrauenswürdigkeit arbeiten.  Die HTML\-Inhalte, die in dem Steuerelement angezeigt werden, können von externen Webservern stammen und enthalten unter Umständen nicht verwalteten Code in Form von Skripts oder Websteuerelementen.  Die Verwendung des <xref:System.Windows.Forms.WebBrowser>\-Steuerelements in einer solchen Situation ist zwar ebenso sicher wie die Verwendung von Internet Explorer, das verwaltete <xref:System.Windows.Forms.WebBrowser>\-Steuerelement verhindert jedoch nicht, dass der nicht verwaltete Code ausgeführt wird.  
  
 Weitere Informationen zu Sicherheitsproblemen in Bezug auf das zugrunde liegende ActiveX\- `WebBrowser`\-Steuerelement finden Sie unter [WebBrowser\-Steuerelement](http://go.microsoft.com/fwlink/?LinkId=198812).  
  
## Siehe auch  
 <xref:System.Windows.Forms.WebBrowser>   
 [Übersicht über das WebBrowser\-Steuerelement](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)   
 [WebBrowser\-Steuerelement](http://go.microsoft.com/fwlink/?LinkId=198812)