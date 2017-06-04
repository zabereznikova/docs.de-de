---
title: "Gewusst wie: Unterst&#252;tzen von COM-Interop durch Anzeigen eines Windows Forms mit der ShowDialog-Methode | Microsoft Docs"
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
  - "COM [Windows Forms]"
  - "Windows Forms, nicht verwaltet"
  - "COM-Interop, Aufrufmethoden"
  - "ActiveX-Steuerelemente [Windows Forms], COM-Interop"
  - "ShowDialog-Methode"
  - "Windows Forms, interop"
ms.assetid: 87aac8ad-3c04-43b3-9b0c-d0b00df9ee74
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Unterst&#252;tzen von COM-Interop durch Anzeigen eines Windows Forms mit der ShowDialog-Methode
Sie können Probleme mit der Component Object Model\-Interoperabilität \(COM\) beheben, indem Sie die Windows Form in einer [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Nachrichtenschleife anzeigen, die Sie mit der <xref:System.Windows.Forms.Application.Run%2A?displayProperty=fullName>\-Methode erstellen können.  
  
 Damit ein Formular aus einer COM\-Clientanwendung heraus ordnungsgemäß funktioniert, müssen Sie es in einer Windows Forms\-Nachrichtenschleife ausführen. Hierzu können Sie einen der folgenden Ansätze verwenden:  
  
-   Verwenden Sie die <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=fullName>\-Methode, um die Windows Form anzuzeigen.  
  
-   Zeigen Sie jedes Windows Form in einem separaten Thread an. Weitere Informationen finden Sie unter [Gewusst wie: Unterstützen von COM\-Interop durch das Anzeigen einzelner Windows Forms in einem eigenen Thread](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md).  
  
## Prozedur  
 Die <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=fullName>\-Methode ist möglicherweise die einfachste Möglichkeit, eine Form in einer [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Nachrichtenschleife anzuzeigen, weil es von allen Ansätzen die geringste Codeimplementierung erfordert.  
  
 Die <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=fullName>\-Methode unterbricht die Nachrichtenschleife der nicht verwalteten Anwendung und zeigt die Form als Dialogfeld an. Da die Schleife der Hostanwendung angehalten wurde, erstellt die <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=fullName>\-Methode eine neue [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Nachrichtenschleife zum Verarbeiten der Nachrichten der Form.  
  
 Der Nachteil der <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=fullName>\-Methode ist, dass die Form als modales Dialogfeld geöffnet wird. Dieses Verhalten blockiert solange jede Benutzeroberfläche \(UI\) in der aufrufenden Anwendung, wie die Windows Form geöffnet ist. Wenn der Benutzer die Form schließt, wird die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Nachrichtenschleife geschlossen und die zuvor erstellte Nachrichtenschleife der Anwendung erneut ausgeführt.  
  
 Sie können eine Klassenbibliothek in Windows Forms erstellen, die über eine Methode zum Anzeigen der Form verfügt, und die Klassenbibliothek anschließend für COM\-Interop bauen. Sie können diese DLL\-Datei aus Visual Basic 6.0 oder Microsoft Foundation Classes \(MFC\) verwenden, und Sie können in jeder dieser Umgebungen die <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=fullName>\-Methode aufrufen, um die Form anzuzeigen.  
  
#### So unterstützen Sie COM\-Interop durch Anzeigen einer Windows Form mit der ShowDialog\-Methode  
  
-   Ersetzen Sie in Ihrer [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Komponente alle Aufrufe der <xref:System.Windows.Forms.Form.Show%2A?displayProperty=fullName>\-Methode durch Aufrufe der <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=fullName>\-Methode.  
  
## Siehe auch  
 [Exposing .NET Framework Components to COM](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [Gewusst wie: Unterstützen von COM\-Interop durch das Anzeigen einzelner Windows Forms in einem eigenen Thread](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)   
 [Windows Forms und nicht verwaltete Anwendungen](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md)