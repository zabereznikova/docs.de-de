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
ms.openlocfilehash: 85fb12028687578b76e0f16061deb9b9a4de70e3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121965"
---
# <a name="how-to-print-a-windows-form"></a><span data-ttu-id="37794-102">Vorgehensweise: Drucken in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="37794-102">How to: Print a Windows Form</span></span>
<span data-ttu-id="37794-103">Im Rahmen des Entwicklungsprozesses sollten Sie in der Regel eine Kopie Ihres Windows-Formulars drucken.</span><span class="sxs-lookup"><span data-stu-id="37794-103">As part of the development process, you typically will want to print a copy of your Windows Form.</span></span> <span data-ttu-id="37794-104">Im folgenden Codebeispiel wird veranschaulicht, wie so drucken Sie eine Kopie des aktuellen Formulars mithilfe der <xref:System.Drawing.Graphics.CopyFromScreen%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="37794-104">The following code example shows how to print a copy of the current form by using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37794-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="37794-105">Example</span></span>  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="37794-106">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="37794-106">Compiling the Code</span></span>  
 <span data-ttu-id="37794-107">Dies ist ein vollständiges Codebeispiel, das enthält eine `Main` Methode.</span><span class="sxs-lookup"><span data-stu-id="37794-107">This is a complete code example that contains a `Main` method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="37794-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="37794-108">Robust Programming</span></span>  
 <span data-ttu-id="37794-109">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="37794-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="37794-110">Sie haben keine Berechtigung zum Zugriff auf den Drucker.</span><span class="sxs-lookup"><span data-stu-id="37794-110">You do not have permission to access the printer.</span></span>  
  
-   <span data-ttu-id="37794-111">Es ist kein Drucker installiert.</span><span class="sxs-lookup"><span data-stu-id="37794-111">There is no printer installed.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="37794-112">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="37794-112">.NET Framework Security</span></span>  
 <span data-ttu-id="37794-113">Um dieses Codebeispiel ausführen, benötigen Sie die Berechtigung zum Zugriff auf den Drucker, die, den Sie mit Ihrem Computer zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="37794-113">In order to run this code example, you must have permission to access the printer you use with your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37794-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37794-114">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="37794-115">Vorgehensweise: Darstellen von Bildern mit GDI+</span><span class="sxs-lookup"><span data-stu-id="37794-115">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
- [<span data-ttu-id="37794-116">Vorgehensweise: Drucken von Grafiken in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="37794-116">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)
