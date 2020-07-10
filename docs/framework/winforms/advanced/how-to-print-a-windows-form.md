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
# <a name="how-to-print-a-windows-form"></a>Vorgehensweise: Drucken in Windows Forms
Im Rahmen des Entwicklungsprozesses möchten Sie in der Regel eine Kopie Ihres Windows Forms drucken. Im folgenden Codebeispiel wird gezeigt, wie eine Kopie des aktuellen Formulars mit der-Methode gedruckt wird <xref:System.Drawing.Graphics.CopyFromScreen%2A> .  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
- Sie haben keine Berechtigung für den Zugriff auf den Drucker.  
  
- Es ist kein Drucker installiert.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Um dieses Codebeispiel ausführen zu können, müssen Sie über die Berechtigung verfügen, auf den Drucker zuzugreifen, den Sie mit Ihrem Computer verwenden.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Drawing.Printing.PrintDocument>
- [Vorgehensweise: Darstellen von Bildern mit GDI+](how-to-render-images-with-gdi.md)
- [How to: Drucken von Grafiken in Windows Forms](how-to-print-graphics-in-windows-forms.md)
