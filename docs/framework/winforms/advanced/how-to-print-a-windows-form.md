---
title: 'Vorgehensweise: Drucken in Windows Forms'
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
ms.openlocfilehash: cd10e0a43ff37b921dc8e024d7a6a51fafbb0400
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591852"
---
# <a name="how-to-print-a-windows-form"></a><span data-ttu-id="08fc4-102">Vorgehensweise: Drucken in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="08fc4-102">How to: Print a Windows Form</span></span>
<span data-ttu-id="08fc4-103">Im Rahmen des Entwicklungsprozesses sollten Sie in der Regel eine Kopie Ihres Windows-Formulars drucken.</span><span class="sxs-lookup"><span data-stu-id="08fc4-103">As part of the development process, you typically will want to print a copy of your Windows Form.</span></span> <span data-ttu-id="08fc4-104">Im folgenden Codebeispiel wird veranschaulicht, wie so drucken Sie eine Kopie des aktuellen Formulars mithilfe der <xref:System.Drawing.Graphics.CopyFromScreen%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="08fc4-104">The following code example shows how to print a copy of the current form by using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08fc4-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="08fc4-105">Example</span></span>  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="08fc4-106">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="08fc4-106">Robust Programming</span></span>  
 <span data-ttu-id="08fc4-107">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="08fc4-107">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="08fc4-108">Sie haben keine Berechtigung zum Zugriff auf den Drucker.</span><span class="sxs-lookup"><span data-stu-id="08fc4-108">You do not have permission to access the printer.</span></span>  
  
- <span data-ttu-id="08fc4-109">Es ist kein Drucker installiert.</span><span class="sxs-lookup"><span data-stu-id="08fc4-109">There is no printer installed.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="08fc4-110">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="08fc4-110">.NET Framework Security</span></span>  
 <span data-ttu-id="08fc4-111">Um dieses Codebeispiel ausführen, benötigen Sie die Berechtigung zum Zugriff auf den Drucker, die, den Sie mit Ihrem Computer zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="08fc4-111">In order to run this code example, you must have permission to access the printer you use with your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08fc4-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08fc4-112">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="08fc4-113">Vorgehensweise: Darstellen von Bildern mit GDI +</span><span class="sxs-lookup"><span data-stu-id="08fc4-113">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
- [<span data-ttu-id="08fc4-114">Vorgehensweise: Drucken von Grafiken in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="08fc4-114">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)
