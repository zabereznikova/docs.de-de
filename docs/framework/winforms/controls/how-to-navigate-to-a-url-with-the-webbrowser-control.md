---
title: "Gewusst wie: Navigieren zu einem URL mit dem WebBrowser-Steuerelement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WebBrowser.Navigate"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Beispiele [Windows Forms], WebBrowser-Steuerelement"
  - "URLs, Navigieren zu"
  - "WebBrowser-Steuerelement [Windows Forms], Beispiele"
  - "WebBrowser-Steuerelement [Windows Forms], Navigieren zu URLs"
ms.assetid: b3ec38cb-f509-4d0b-bd79-9f3611259c62
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Navigieren zu einem URL mit dem WebBrowser-Steuerelement
Im folgenden Codebeispiel wird veranschaulicht, wie mit dem <xref:System.Windows.Forms.WebBrowser>\-Steuerelement zu einer bestimmten URL navigiert wird.  
  
 Verwenden Sie das <xref:System.Windows.Forms.WebBrowser.DocumentCompleted>\-Ereignis, um zu ermitteln, wann das neue Dokument vollständig geladen ist.  Eine Beispiel dieses Ereignisses finden Sie unter [Gewusst wie: Drucken mit einem WebBrowser\-Steuerelement](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md).  
  
## Beispiel  
  
```vb  
Me.webBrowser1.Navigate("http://www.microsoft.com")  
```  
  
```csharp  
this.webBrowser1.Navigate("http://www.microsoft.com");  
```  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Ein <xref:System.Windows.Forms.WebBrowser>\-Steuerelement mit dem Namen `webBrowser1`.  
  
-   Verweise auf die `System`\-Assembly und die `System.Windows.Forms`\-Assembly.  
  
## Siehe auch  
 <xref:System.Windows.Forms.WebBrowser>   
 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=fullName>   
 <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=fullName>   
 <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=fullName>   
 [WebBrowser\-Steuerelement](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)   
 [Gewusst wie: Drucken mit einem WebBrowser\-Steuerelement](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)