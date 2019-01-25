---
title: 'Vorgehensweise: Drucken eines Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- printing a form
- printing [Windows Forms], printing a form
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
ms.openlocfilehash: 5e672f40797a90111daefed0be74c941d4cc37b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628135"
---
# <a name="how-to-print-a-windows-form"></a><span data-ttu-id="756b0-102">Vorgehensweise: Drucken eines Windows Form</span><span class="sxs-lookup"><span data-stu-id="756b0-102">How to: Print a Windows Form</span></span>
<span data-ttu-id="756b0-103">Im Rahmen des Entwicklungsprozesses sollten Sie in der Regel eine Kopie Ihres Windows-Formulars drucken.</span><span class="sxs-lookup"><span data-stu-id="756b0-103">As part of the development process, you typically will want to print a copy of your Windows Form.</span></span> <span data-ttu-id="756b0-104">Im folgenden Codebeispiel wird veranschaulicht, wie so drucken Sie eine Kopie des aktuellen Formulars mithilfe der <xref:System.Drawing.Graphics.CopyFromScreen%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="756b0-104">The following code example shows how to print a copy of the current form by using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="756b0-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="756b0-105">Example</span></span>  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="756b0-106">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="756b0-106">Compiling the Code</span></span>  
 <span data-ttu-id="756b0-107">Dies ist ein vollständiges Codebeispiel, das enthält eine `Main` Methode.</span><span class="sxs-lookup"><span data-stu-id="756b0-107">This is a complete code example that contains a `Main` method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="756b0-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="756b0-108">Robust Programming</span></span>  
 <span data-ttu-id="756b0-109">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="756b0-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="756b0-110">Sie haben keine Berechtigung zum Zugriff auf den Drucker.</span><span class="sxs-lookup"><span data-stu-id="756b0-110">You do not have permission to access the printer.</span></span>  
  
-   <span data-ttu-id="756b0-111">Es ist kein Drucker installiert.</span><span class="sxs-lookup"><span data-stu-id="756b0-111">There is no printer installed.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="756b0-112">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="756b0-112">.NET Framework Security</span></span>  
 <span data-ttu-id="756b0-113">Um dieses Codebeispiel ausführen, benötigen Sie die Berechtigung zum Zugriff auf den Drucker, die, den Sie mit Ihrem Computer zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="756b0-113">In order to run this code example, you must have permission to access the printer you use with your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="756b0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="756b0-114">See also</span></span>
- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="756b0-115">Vorgehensweise: Darstellen von Bildern mit GDI +</span><span class="sxs-lookup"><span data-stu-id="756b0-115">How to: Render Images with GDI+</span></span>](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)
- [<span data-ttu-id="756b0-116">Vorgehensweise: Drucken von Grafiken in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="756b0-116">How to: Print Graphics in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)
