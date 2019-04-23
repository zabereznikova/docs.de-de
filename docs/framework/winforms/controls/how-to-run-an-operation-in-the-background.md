---
title: 'Vorgehensweise: Ausführen eines Vorgangs im Hintergrund'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 5b56e2aa-dc05-444f-930c-2d7b23f9ad5b
ms.openlocfilehash: 5ccbb6e4c09f5417f6c2766824ec7ed9722eed52
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59217990"
---
# <a name="how-to-run-an-operation-in-the-background"></a>Vorgehensweise: Ausführen eines Vorgangs im Hintergrund
Gibt es einen Vorgang, der bis zu seinem Abschluss eine lange Zeit in Anspruch nimmt, und Sie möchten keine Verzögerungen in der Benutzeroberfläche verursachen, können Sie die <xref:System.ComponentModel.BackgroundWorker>-Klasse dazu verwenden, den Vorgang über einen anderen Thread auszuführen.  
  
 Im folgenden Codebeispiel wird gezeigt, wie ein zeitaufwändiger Vorgang im Hintergrund ausgeführt wird. Das Formular verfügt über die Schaltflächen **Start** und **Abbrechen**. Klicken Sie auf die Schaltfläche **Start**, um einen asynchronen Vorgang auszuführen. Klicken Sie auf die Schaltfläche **Abbrechen**, um einen aktiven asynchronen Vorgang anzuhalten. Das Ergebnis jedes Vorgangs wird in einem <xref:System.Windows.Forms.MessageBox>-Steuerelement angezeigt.  
  
 Visual Studio bietet umfassende Unterstützung für diese Aufgabe.  
  
 Siehe auch [Exemplarische Vorgehensweise: Ausführen eines Vorgangs im Hintergrund](walkthrough-running-an-operation-in-the-background.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet](how-to-implement-a-form-that-uses-a-background-operation.md)
- [BackgroundWorker-Komponente](backgroundworker-component.md)
