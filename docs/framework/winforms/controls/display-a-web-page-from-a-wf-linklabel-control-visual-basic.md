---
title: Webseite aus dem LinkLabel-Steuerelement anzeigen (Visual Basic)
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- LinkLabel1_LinkClicked
helpviewer_keywords:
- examples [Windows Forms], LinkLabel control
- Web pages [Windows Forms], displaying
- linking [Windows Forms], to Web pages from forms
- Windows Forms, linking to Web pages
- LinkLabel control [Windows Forms], examples
ms.assetid: 477a7398-5971-4de3-b24c-f49f32bdb28a
ms.openlocfilehash: 75373d55b7bc5ef11e39d5b9546996cb1c4f6f7c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745926"
---
# <a name="how-to-display-a-web-page-from-a-windows-forms-linklabel-control-visual-basic"></a>Gewusst wie: Anzeigen einer Webseite über ein LinkLabel-Steuerelement in Windows Forms (Visual Basic)
In diesem Beispiel wird eine Webseite im Standardbrowser angezeigt, wenn ein Benutzer auf eine Windows Forms <xref:System.Windows.Forms.LinkLabel>-Steuerelement klickt.  
  
## <a name="example"></a>Beispiel  
  
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
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Dieses Beispiel erfordert Folgendes:  
  
- Ein Windows-Formular mit dem Namen `Form1`.  
  
- Ein <xref:System.Windows.Forms.LinkLabel>-Steuerelement namens `LinkLabel1`.  
  
- Eine aktive Internet Verbindung.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Der-<xref:System.Diagnostics.Process.Start%2A> Methode erfordert volle Vertrauenswürdigkeit. Weitere Informationen finden Sie unter <xref:System.Security.SecurityException>.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.LinkLabel>
- [LinkLabel-Steuerelement](linklabel-control-windows-forms.md)
