---
title: 'Vorgehensweise: Behandeln von Tastatureingaben auf Formularebene'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboard input [Windows Forms], at form level
- Windows Forms, handling keyboard input
- keyboards [Windows Forms], form-level input
ms.assetid: d7f8b390-dc91-42d2-ae0f-2ffa388127ad
ms.openlocfilehash: 8e346c5b69c507307d459f6246e26a6a96bb9e24
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64591299"
---
# <a name="how-to-handle-keyboard-input-at-the-form-level"></a>Vorgehensweise: Behandeln von Tastatureingaben auf Formularebene
Windows Forms bieten die Möglichkeit, Tastatureingaben auf Formularebene zu behandeln, bevor die Eingaben an ein Steuerelement weitergegeben werden. In diesem Thema wird gezeigt, wie Sie diese Aufgabe ausführen.  
  
### <a name="to-handle-a-keyboard-message-at-the-form-level"></a>So behandeln Sie eine Tastatureingabe auf Formularebene  
  
- Behandeln Sie das Ereignis <xref:System.Windows.Forms.Control.KeyPress> oder <xref:System.Windows.Forms.Control.KeyDown> im Startformular, und legen Sie die <xref:System.Windows.Forms.Form.KeyPreview%2A>-Eigenschaft des Formulars auf `true` fest, damit Tastatureingaben vom Formular empfangen werden, bevor sie an irgendeines der Steuerelemente auf dem Formular weitergegeben werden. Im folgenden Codebeispiel wird das <xref:System.Windows.Forms.Control.KeyPress>-Ereignis behandelt, indem alle Zahlentasten erkannt und "1", "4" und "7" verarbeitet werden.  
  
     [!code-cpp[System.Windows.Forms.KeyboardInputForm#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/cpp/form1.cpp#10)]
     [!code-csharp[System.Windows.Forms.KeyboardInputForm#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/CS/form1.cs#10)]
     [!code-vb[System.Windows.Forms.KeyboardInputForm#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/VB/form1.vb#10)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel ist die vollständige Anwendung für das vorstehende Codebeispiel. Die Anwendung enthält ein <xref:System.Windows.Forms.TextBox> sowie mehrere andere Steuerelemente, die es Ihnen ermöglichen, den Fokus aus dem <xref:System.Windows.Forms.TextBox> zu verschieben. Das <xref:System.Windows.Forms.Control.KeyPress>-Ereignis der Haupt-<xref:System.Windows.Forms.Form> verarbeitet "1", "4" und "7", und das <xref:System.Windows.Forms.Control.KeyPress>-Ereignis des <xref:System.Windows.Forms.TextBox> verarbeitet "2", "5" und "8", während die restlichen Tasten angezeigt werden. Vergleichen Sie die Ausgabe von <xref:System.Windows.Forms.MessageBox>, wenn Sie eine Zahlentaste drücken, während das <xref:System.Windows.Forms.TextBox> den Fokus besitzt, mit der Ausgabe von <xref:System.Windows.Forms.MessageBox>, wenn sie eine Zahlentaste drücken, während eines der andere Steuerelemente den Fokus besitzt.  
  
 [!code-cpp[System.Windows.Forms.KeyBoardInputForm#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.KeyBoardInputForm#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.KeyBoardInputForm#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.  

## <a name="see-also"></a>Siehe auch

- [Tastatureingaben in einer Windows Forms-Anwendung](keyboard-input-in-a-windows-forms-application.md)
