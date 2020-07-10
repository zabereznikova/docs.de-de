---
title: 'Vorgehensweise: Drucken in Windows Forms'
description: Erfahren Sie, wie Sie mithilfe der CopyFromScreen-Methode eine Kopie des aktuellen Windows Forms Programm gesteuert drucken.
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
ms.openlocfilehash: b59ea4b5347903b36a166c4f8ac0d8d7db18635e
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174691"
---
# <a name="how-to-print-a-windows-form"></a><span data-ttu-id="32abe-103">Vorgehensweise: Drucken in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="32abe-103">How to: Print a Windows Form</span></span>
<span data-ttu-id="32abe-104">Im Rahmen des Entwicklungsprozesses möchten Sie in der Regel eine Kopie Ihres Windows Forms drucken.</span><span class="sxs-lookup"><span data-stu-id="32abe-104">As part of the development process, you typically will want to print a copy of your Windows Form.</span></span> <span data-ttu-id="32abe-105">Im folgenden Codebeispiel wird gezeigt, wie eine Kopie des aktuellen Formulars mit der-Methode gedruckt wird <xref:System.Drawing.Graphics.CopyFromScreen%2A> .</span><span class="sxs-lookup"><span data-stu-id="32abe-105">The following code example shows how to print a copy of the current form by using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32abe-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="32abe-106">Example</span></span>  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="32abe-107">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="32abe-107">Robust Programming</span></span>  
 <span data-ttu-id="32abe-108">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="32abe-108">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="32abe-109">Sie haben keine Berechtigung für den Zugriff auf den Drucker.</span><span class="sxs-lookup"><span data-stu-id="32abe-109">You do not have permission to access the printer.</span></span>  
  
- <span data-ttu-id="32abe-110">Es ist kein Drucker installiert.</span><span class="sxs-lookup"><span data-stu-id="32abe-110">There is no printer installed.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="32abe-111">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="32abe-111">.NET Framework Security</span></span>  
 <span data-ttu-id="32abe-112">Um dieses Codebeispiel ausführen zu können, müssen Sie über die Berechtigung verfügen, auf den Drucker zuzugreifen, den Sie mit Ihrem Computer verwenden.</span><span class="sxs-lookup"><span data-stu-id="32abe-112">In order to run this code example, you must have permission to access the printer you use with your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32abe-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="32abe-113">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="32abe-114">Vorgehensweise: Darstellen von Bildern mit GDI+</span><span class="sxs-lookup"><span data-stu-id="32abe-114">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
- [<span data-ttu-id="32abe-115">How to: Drucken von Grafiken in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="32abe-115">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)
