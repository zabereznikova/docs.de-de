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
ms.openlocfilehash: 80bf88ad048e55a381d034d2a796de6f77f8691c
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714150"
---
# <a name="how-to-print-a-windows-form"></a>Vorgehensweise: Drucken eines Windows Form
Im Rahmen des Entwicklungsprozesses sollten Sie in der Regel eine Kopie Ihres Windows-Formulars drucken. Im folgenden Codebeispiel wird veranschaulicht, wie so drucken Sie eine Kopie des aktuellen Formulars mithilfe der <xref:System.Drawing.Graphics.CopyFromScreen%2A> Methode.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Dies ist ein vollständiges Codebeispiel, das enthält eine `Main` Methode.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Sie haben keine Berechtigung zum Zugriff auf den Drucker.  
  
-   Es ist kein Drucker installiert.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Um dieses Codebeispiel ausführen, benötigen Sie die Berechtigung zum Zugriff auf den Drucker, die, den Sie mit Ihrem Computer zu verwenden.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Drawing.Printing.PrintDocument>
- [Vorgehensweise: Darstellen von Bildern mit GDI +](how-to-render-images-with-gdi.md)
- [Vorgehensweise: Drucken von Grafiken in Windows Forms](how-to-print-graphics-in-windows-forms.md)
