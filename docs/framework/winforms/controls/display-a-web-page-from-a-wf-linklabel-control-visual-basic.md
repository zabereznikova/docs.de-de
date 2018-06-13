---
title: 'Gewusst wie: Anzeigen einer Webseite über ein LinkLabel-Steuerelement in Windows Forms (Visual Basic)'
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
ms.openlocfilehash: a9964c8d333ea87dd995ec9111acc1a8ac1e79b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524182"
---
# <a name="how-to-display-a-web-page-from-a-windows-forms-linklabel-control-visual-basic"></a><span data-ttu-id="5ba52-102">Gewusst wie: Anzeigen einer Webseite über ein LinkLabel-Steuerelement in Windows Forms (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ba52-102">How to: Display a Web Page from a Windows Forms LinkLabel Control (Visual Basic)</span></span>
<span data-ttu-id="5ba52-103">Dieses Beispiel zeigt eine Webseite im Standardbrowser, klickt ein Benutzer einer Windows Forms <xref:System.Windows.Forms.LinkLabel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5ba52-103">This example displays a Web page in the default browser when a user clicks a Windows Forms <xref:System.Windows.Forms.LinkLabel> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ba52-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5ba52-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="5ba52-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="5ba52-105">Compiling the Code</span></span>  
 <span data-ttu-id="5ba52-106">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="5ba52-106">This example requires:</span></span>  
  
-   <span data-ttu-id="5ba52-107">Ein Windows Form mit dem Namen `Form1`.</span><span class="sxs-lookup"><span data-stu-id="5ba52-107">A Windows Form named `Form1`.</span></span>  
  
-   <span data-ttu-id="5ba52-108">Ein <xref:System.Windows.Forms.LinkLabel>-Steuerelement namens `LinkLabel1`.</span><span class="sxs-lookup"><span data-stu-id="5ba52-108">A <xref:System.Windows.Forms.LinkLabel> control named `LinkLabel1`.</span></span>  
  
-   <span data-ttu-id="5ba52-109">Eine aktive Internetverbindung.</span><span class="sxs-lookup"><span data-stu-id="5ba52-109">An active Internet connection.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="5ba52-110">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="5ba52-110">.NET Framework Security</span></span>  
 <span data-ttu-id="5ba52-111">Der Aufruf der <xref:System.Diagnostics.Process.Start%2A> Methode erfordert volle Vertrauenswürdigkeit.</span><span class="sxs-lookup"><span data-stu-id="5ba52-111">The call to the <xref:System.Diagnostics.Process.Start%2A> method requires full trust.</span></span> <span data-ttu-id="5ba52-112">Weitere Informationen finden Sie unter <xref:System.Security.SecurityException>.</span><span class="sxs-lookup"><span data-stu-id="5ba52-112">For more information, see <xref:System.Security.SecurityException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ba52-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ba52-113">See Also</span></span>  
 <xref:System.Windows.Forms.LinkLabel>  
 [<span data-ttu-id="5ba52-114">LinkLabel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5ba52-114">LinkLabel Control</span></span>](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)
