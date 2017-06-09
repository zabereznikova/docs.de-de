---
title: "Mauserfassung in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Maus, Erfassen"
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Mauserfassung in Windows Forms
Von *Mauserfassung* spricht man, wenn ein Steuerelement sämtliche Mauseingaben steuert.  Wenn ein Steuerelement die Maus erfasst hat, empfängt es Mauseingaben unabhängig davon, ob sich der Zeiger innerhalb seiner Grenzen befindet.  
  
## Festlegen der Mauserfassung  
 In Windows Forms wird die Maus vom Steuerelement erfasst, wenn der Benutzer auf einem Steuerelement eine Maustaste drückt. Sobald der Benutzer die Maustaste loslässt, wird die Maus von dem Steuerelement freigegeben.  
  
 Die <xref:System.Windows.Forms.Control.Capture%2A>\-Eigenschaft der <xref:System.Windows.Forms.Control>\-Klasse gibt an, ob ein Steuerelement die Maus erfasst hat.  Um zu bestimmen, wann ein Steuerelement die Mauserfassung verliert, behandeln Sie das <xref:System.Windows.Forms.Control.MouseCaptureChanged>\-Ereignis.  
  
 Die Maus kann nur im Vordergrundfenster erfasst werden.  Wenn versucht wird, die Maus im Hintergrundfenster zu erfassen, empfängt das Fenster Meldungen nur für Mausereignisse, die stattfinden, wenn sich der Mauszeiger innerhalb des sichtbaren Bereichs des Fensters befindet.  Wenn die Maus im Vordergrundfenster erfasst wurde, kann der Benutzer zudem auf ein anderes Fenster klicken und es so in den Vordergrund bringen.  Wenn die Maus erfasst wird, können keine Tastenkombinationen verwendet werden.  
  
## Siehe auch  
 [Mauseingabe in einer Windows Forms\-Anwendung](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)