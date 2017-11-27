---
title: "Gewusst wie: Ausführen eines Vorgangs im Hintergrund"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c07d2e5dfb89827f00a03d3c361ccc1417cdeeeb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-run-an-operation-in-the-background"></a>Gewusst wie: Ausführen eines Vorgangs im Hintergrund
Gibt es einen Vorgang, der bis zu seinem Abschluss eine lange Zeit in Anspruch nimmt, und Sie möchten keine Verzögerungen in der Benutzeroberfläche verursachen, können Sie die <xref:System.ComponentModel.BackgroundWorker>-Klasse dazu verwenden, den Vorgang über einen anderen Thread auszuführen.  
  
 Im folgenden Codebeispiel wird gezeigt, wie ein zeitaufwändiger Vorgang im Hintergrund ausgeführt wird. Das Formular verfügt über die Schaltflächen **Start** und **Abbrechen**. Klicken Sie auf die Schaltfläche **Start**, um einen asynchronen Vorgang auszuführen. Klicken Sie auf die Schaltfläche **Abbrechen**, um einen aktiven asynchronen Vorgang anzuhalten. Das Ergebnis jedes Vorgangs wird in einem <xref:System.Windows.Forms.MessageBox>-Steuerelement angezeigt.  
  
 In [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] wird diese Aufgabe umfassend unterstützt.  
  
 Siehe auch [Exemplarische Vorgehensweise: Ausführen eines Vorgangs im Hintergrund](http://msdn.microsoft.com/library/ms233672\(v=vs.110\)).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.ComponentModel.BackgroundWorker.Example#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.Example#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Erstellen über die Befehlszeile mit „csc.exe“](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch: [Vorgehensweise: Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ComponentModel.BackgroundWorker>  
 <xref:System.ComponentModel.DoWorkEventArgs>  
 [Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 [BackgroundWorker-Komponente](../../../../docs/framework/winforms/controls/backgroundworker-component.md)
