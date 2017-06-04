---
title: "Windows&#160;Forms und nicht verwaltete Anwendungen | Microsoft Docs"
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
  - "ActiveX-Steuerelemente [Windows Forms]"
  - "COM [Windows Forms]"
  - "COM-Interop, Windows Forms"
  - "Windows Forms, Interop"
  - "Windows Forms, Nicht verwaltet"
ms.assetid: 81bc100c-fa49-4614-85a6-0f7ab59eac8a
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Windows&#160;Forms und nicht verwaltete Anwendungen
Windows Forms\-Anwendungen und\-Steuerelemente können mit einigen Einschränkungen mit nicht verwalteten Anwendungen zusammenarbeiten.  In den folgenden Abschnitten werden die von Windows Forms\-Anwendungen und \-Steuerelementen unterstützten und nicht unterstützten Szenarien und Konfigurationen beschrieben.  
  
## In diesem Abschnitt  
 [Übersicht über Windows Forms und nicht verwaltete Anwendungen](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications-overview.md)  
 Bietet allgemeine Informationen zur Verwendung und Implementierung von Windows Forms\-Steuerelementen, die in nicht verwalteten Anwendungen verwendet werden können.  
  
 [Gewusst wie: Unterstützen von COM\-Interop durch Anzeigen eines Windows Forms mit der ShowDialog\-Methode](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md)  
 Enthält ein Codebeispiel für die Verwendung der <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=fullName>\-Methode zum Ausführen eines Windows Forms in einer nicht verwalteten Anwendung.  
  
 [Gewusst wie: Unterstützen von COM\-Interop durch das Anzeigen einzelner Windows Forms in einem eigenen Thread](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 Enthält ein Codebeispiel für die Ausführung eines Windows Forms in einem eigenen Thread.  
  
 Siehe auch [Exemplarische Vorgehensweise: Unterstützen von COM\-Interop durch Anzeigen jedes Windows Forms in einem eigenen Thread](http://msdn.microsoft.com/library/ms233639\(v=vs.110\)).  
  
## Referenz  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=fullName>  
 Wird zum Erstellen eines separaten Threads für ein Windows Form verwendet.  
  
 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=fullName>  
 Startet eine Nachrichtenschleife für einen Thread.  
  
 <xref:System.Windows.Forms.Control.Invoke%2A>  
 Marshallt Aufrufe von einer nicht verwalteten Anwendung für ein Formular.  
  
## Verwandte Abschnitte  
 [Exposing .NET Framework Components to COM](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 Bietet allgemeine Informationen zur Verwendung von .NET Framework\-Typen in nicht verwalteten Anwendungen.