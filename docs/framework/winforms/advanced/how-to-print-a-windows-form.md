---
title: 'Gewusst wie: Drucken eines Windows Form'
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
ms.openlocfilehash: 42940654a0754ac3616ca7983af07d20607f480f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522268"
---
# <a name="how-to-print-a-windows-form"></a>Gewusst wie: Drucken eines Windows Form
Als Teil des Entwicklungsprozesses sollten Sie in der Regel eine Kopie der Windows Form zu drucken. Im folgenden Codebeispiel wird veranschaulicht, wie auf eine Kopie des aktuellen Formulars gedruckt werden, indem Sie mit der <xref:System.Drawing.Graphics.CopyFromScreen%2A> Methode.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Dies ist ein vollständiges Codebeispiel, das enthält eine `Main` Methode.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Sie haben keine Berechtigung zum Zugriff auf den Drucker.  
  
-   Es ist kein Drucker installiert.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Um dieses Codebeispiel ausführen zu können, benötigen Sie die Berechtigung zum Zugriff auf den Drucker, die mit dem Computer verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Printing.PrintDocument>  
 [Gewusst wie: Darstellen von Bildern mit GDI+](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)  
 [Vorgehensweise: Drucken von Grafiken in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)
