---
title: "Gewusst wie: Anzeigen einer Webseite &#252;ber ein LinkLabel-Steuerelement in Windows Forms (Visual&#160;Basic) | Microsoft Docs"
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
  - "LinkLabel1_LinkClicked"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Beispiele [Windows Forms], LinkLabel-Steuerelement"
  - "Verknüpfen, Mit Webseiten aus Formularen"
  - "LinkLabel-Steuerelement [Windows Forms], Beispiele"
  - "Webseiten, Anzeigen"
  - "Windows Forms, Verknüpfen mit Webseiten"
ms.assetid: 477a7398-5971-4de3-b24c-f49f32bdb28a
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Anzeigen einer Webseite &#252;ber ein LinkLabel-Steuerelement in Windows Forms (Visual&#160;Basic)
In diesem Beispiel wird eine Webseite im Standardbrowser angezeigt, wenn der Benutzer auf das <xref:System.Windows.Forms.LinkLabel>\-Steuerelement in Windows Forms klickt.  
  
## Beispiel  
  
```vb  
Private Sub Form1_Load(ByVal sender As System.Object, ByVal e _  
As System.EventArgs) Handles MyBase.Load  
    LinkLabel1.Text = "Click here to get more info."  
    LinkLabel1.Links.Add(6, 4, "www.microsoft.com")  
End Sub  
Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, ByVal _  
e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) Handles _  
LinkLabel1.LinkClicked  
    System.Diagnostics.Process.Start(e.Link.LinkData.ToString())  
End Sub  
```  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Ein Windows Form mit dem Namen `Form1`.  
  
-   Ein <xref:System.Windows.Forms.LinkLabel>\-Steuerelement mit dem Namen `LinkLabel1`.  
  
-   Eine aktive Internetverbindung muss vorhanden sein.  
  
## .NET Framework-Sicherheit  
 Der Aufruf der <xref:System.Diagnostics.Process.Start%2A>\-Methode erfordert volle Vertrauenswürdigkeit.  Weitere Informationen finden Sie unter <xref:System.Security.SecurityException>.  
  
## Siehe auch  
 <xref:System.Windows.Forms.LinkLabel>   
 [LinkLabel\-Steuerelement](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)