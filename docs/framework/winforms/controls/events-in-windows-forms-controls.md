---
title: "Ereignisse in Windows&#160;Forms-Steuerelementen | Microsoft Docs"
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
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Ereignisübersicht (mit Code)"
  - "Ereignisse [Windows Forms], Benutzerdefinierte Steuerelemente (mithilfe von Code)"
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Ereignisse in Windows&#160;Forms-Steuerelementen
Ein Windows Forms\-Steuerelement erbt mehr als sechzig Ereignisse von <xref:System.Windows.Forms.Control?displayProperty=fullName>.  Hierzu gehören das <xref:System.Windows.Forms.Control.Paint>\-Ereignis, durch das ein Steuerelement gezeichnet wird, Ereignisse im Zusammenhang mit der Anzeige eines Fensters, z. B. das <xref:System.Windows.Forms.Control.Resize>\-Ereignis und das <xref:System.Windows.Forms.Control.Layout>\-Ereignis, sowie Maus\- und Tastaturereignisse auf niedriger Ebene.  Einige systemnahe Ereignisse werden von <xref:System.Windows.Forms.Control> in semantische Ereignisse umgewandelt, z. B. <xref:System.Windows.Forms.Control.Click> und <xref:System.Windows.Forms.Control.DoubleClick>.  Ausführliche Informationen über geerbte Ereignisse finden Sie unter <xref:System.Windows.Forms.Control>.  
  
 Wenn das benutzerdefinierte Steuerelement geerbte Ereignisfunktionen überschreiben soll, überschreiben Sie die geerbte `On`*EventName*\-Methode, anstatt einen Delegaten anzufügen.  Wenn Sie mit dem Ereignismodell in .NET Framework nicht vertraut sind, finden Sie dazu weitere Informationen unter [Raising Events from a Component](../Topic/Raising%20Events%20from%20a%20Component.md).  
  
## Siehe auch  
 [Überschreiben der OnPaint\-Methode](../../../../docs/framework/winforms/controls/overriding-the-onpaint-method.md)   
 [Behandeln von Benutzereingaben](../../../../docs/framework/winforms/controls/handling-user-input.md)   
 [Definieren eines Ereignisses](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)   
 [Ereignisse](../../../../docs/standard/events/index.md)