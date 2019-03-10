---
title: 'Vorgehensweise: Anzeigen einer Webseite über ein Windows Forms LinkLabel-Steuerelement (Visual Basic)'
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
ms.openlocfilehash: 7e80dba9cd43385be016506ac2a7e887a68dedf2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705228"
---
# <a name="how-to-display-a-web-page-from-a-windows-forms-linklabel-control-visual-basic"></a>Vorgehensweise: Anzeigen einer Webseite über ein Windows Forms LinkLabel-Steuerelement (Visual Basic)
In diesem Beispiel wird eine Webseite im Standardbrowser, klickt ein Benutzer ein Windows Forms <xref:System.Windows.Forms.LinkLabel> Steuerelement.  
  
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
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein Windows-Formular mit dem Namen `Form1`.  
  
-   Ein <xref:System.Windows.Forms.LinkLabel>-Steuerelement namens `LinkLabel1`.  
  
-   Eine aktive Internetverbindung.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Der Aufruf der <xref:System.Diagnostics.Process.Start%2A> Methode erfordert volles Vertrauen. Weitere Informationen finden Sie unter <xref:System.Security.SecurityException>.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.LinkLabel>
- [LinkLabel-Steuerelement](linklabel-control-windows-forms.md)
