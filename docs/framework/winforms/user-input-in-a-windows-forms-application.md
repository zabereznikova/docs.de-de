---
title: "Benutzereingabe in einer Windows Forms-Anwendung | Microsoft Docs"
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
  - "Windows Forms, Benutzereingabe"
ms.assetid: 9d61fa96-70f7-4754-885a-49a4a6316bdb
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Benutzereingabe in einer Windows Forms-Anwendung
In Windows Forms werden Benutzereingaben in Form von Windows\-Meldungen an Anwendungen gesendet.  Diese Meldungen werden von einer Reihe überschreibbarer Methoden auf Anwendungs\-, Formular\- und Steuerelementebene verarbeitet.  Wenn diese Methoden Maus\- und Tastaturmeldungen empfangen, lösen sie Ereignisse aus, die behandelt werden können, um Informationen über die Maus\- bzw. Tastatureingabe zu erhalten.  In vielen Fällen können in Windows Forms\-Anwendungen alle Benutzereingaben lediglich durch Behandeln dieser Ereignisse verarbeitet werden.  In anderen Fällen muss eine Anwendung möglicherweise eine der Methoden, die die Meldungen verarbeiten, überschreiben, um eine bestimmte Meldung abzufangen, bevor sie von der Anwendung, dem Formular oder dem Steuerelement empfangen wird.  
  
## Maus\- und Tastaturereignisse  
 Alle Windows Forms\-Steuerelemente erben eine Reihe von Ereignissen, die im Zusammenhang mit Maus\- und Tastatureingaben stehen.  Ein Steuerelement kann beispielsweise das <xref:System.Windows.Forms.Control.KeyPress>\-Ereignis behandeln, um den Zeichencode einer gedrückten Taste zu bestimmen. Ebenso kann ein Steuerelement das <xref:System.Windows.Forms.Control.MouseClick>\-Ereignis behandeln, um die Position eines Mausklicks zu bestimmen.  Weitere Informationen über die Maus\- und Tastaturereignisse finden Sie unter [Verwenden von Tastaturereignissen](../../../docs/framework/winforms/using-keyboard-events.md) und [Mausereignisse in Windows Forms](../../../docs/framework/winforms/mouse-events-in-windows-forms.md).  
  
## Methoden, die Benutzereingabemeldungen verarbeiten  
 Formulare und Steuerelemente haben Zugriff auf die <xref:System.Windows.Forms.IMessageFilter>\-Schnittstelle sowie eine Reihe von überschreibbaren Methoden, die Windows\-Meldungen an unterschiedlichen Stellen in der Meldungswarteschlange verarbeiten.  Diese Methoden verfügen alle über einen <xref:System.Windows.Forms.Message>\-Parameter, der die systemnahen Details von Windows\-Meldungen kapselt.  Sie können diese Methoden implementieren oder überschreiben, um die Meldung zu überprüfen und sie anschließend entweder selbst verwenden oder an den nächsten Consumer in der Meldungswarteschlange übergeben.  Die folgende Tabelle enthält die Methoden, mit denen alle Windows\-Meldungen in Windows Forms verarbeitet werden.  
  
|Methode|Hinweise|  
|-------------|--------------|  
|<xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A>|Diese Methode fängt in die Warteschlange eingereihte \(bzw. bereitgestellte\) Windows\-Meldungen auf Anwendungsebene ab.|  
|<xref:System.Windows.Forms.Control.PreProcessMessage%2A>|Diese Methode fängt Windows\-Meldungen auf Formular\- und Steuerelementebene ab, bevor sie verarbeitet wurden.|  
|<xref:System.Windows.Forms.Control.WndProc%2A>|Diese Methode verarbeitet Windows\-Meldungen auf Formular\- und Steuerelementebene.|  
|<xref:System.Windows.Forms.Control.DefWndProc%2A>|Diese Methode führt die Standardverarbeitung von Windows\-Meldungen auf Formular\- und Steuerelementebene aus.  Dabei wird die minimale Funktionalität eines Fensters bereitgestellt.|  
|<xref:System.Windows.Forms.Control.OnNotifyMessage%2A>|Diese Methode fängt Meldungen auf Formular\- und Steuerelementebene ab, nachdem sie verarbeitet wurden.  Damit diese Methode aufgerufen werden kann, muss das <xref:System.Windows.Forms.ControlStyles>\-Stilbit festgelegt werden.|  
  
 Tastatur\- und Mausmeldungen werden zudem durch zusätzliche überschreibbare Methoden verarbeitet, die speziell für diese Arten von Meldungen verwendet werden.  Weitere Informationen finden Sie unter [Funktionsweise von Tastatureingaben](../../../docs/framework/winforms/how-keyboard-input-works.md) und [Funktionsweise von Mauseingaben in Windows Forms](../../../docs/framework/winforms/how-mouse-input-works-in-windows-forms.md).  
  
## Siehe auch  
 [Benutzereingaben in Windows Forms](../../../docs/framework/winforms/user-input-in-windows-forms.md)   
 [Tastatureingaben in einer Windows Forms\-Anwendung](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)   
 [Mauseingabe in einer Windows Forms\-Anwendung](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)