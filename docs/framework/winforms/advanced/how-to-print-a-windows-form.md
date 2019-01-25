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
# <a name="how-to-print-a-windows-form"></a>Vorgehensweise: Drucken eines Windows Form
Im Rahmen des Entwicklungsprozesses sollten Sie in der Regel eine Kopie Ihres Windows-Formulars drucken. Im folgenden Codebeispiel wird veranschaulicht, wie so drucken Sie eine Kopie des aktuellen Formulars mithilfe der <xref:System.Drawing.Graphics.CopyFromScreen%2A> Methode.  
  
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
 Um dieses Codebeispiel ausführen, benötigen Sie die Berechtigung zum Zugriff auf den Drucker, die, den Sie mit Ihrem Computer zu verwenden.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Drawing.Printing.PrintDocument>
- [Vorgehensweise: Darstellen von Bildern mit GDI +](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)
- [Vorgehensweise: Drucken von Grafiken in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)
