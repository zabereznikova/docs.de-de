---
title: 'Gewusst wie: Binden von Windows Forms-Steuerelementen an DBNull-Datenbankwerte'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BindingSource component [Windows Forms], binding to DBNull values
- examples [Windows Forms], BindingSource component
- controls [Windows Forms], binding to DBNull values
ms.assetid: 96494e6f-5f40-4f83-af97-bbd7192c2af8
ms.openlocfilehash: c8c942b872b23bc6ff0a6f254b952189f9e62dbb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530314"
---
# <a name="how-to-bind-windows-forms-controls-to-dbnull-database-values"></a>Gewusst wie: Binden von Windows Forms-Steuerelementen an DBNull-Datenbankwerte
Wenn Sie Windows Forms-Steuerelemente an eine Datenquelle gebunden haben und die Datenquelle einen <xref:System.DBNull>-Wert zurückgibt, können Sie einen entsprechenden Wert ersetzen, ohne Ereignisse behandeln, formatieren oder analysieren zu müssen. Die <xref:System.Windows.Forms.Binding.NullValue%2A>-Eigenschaft konvertiert <xref:System.DBNull> beim Formatieren oder Analysieren der Datenquellenwerte in ein angegebenes Objekt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein <xref:System.DBNull>-Wert in zwei verschiedenen Situationen gebunden wird. In der ersten Situation wird dargestellt, wie <xref:System.Windows.Forms.Binding.NullValue%2A> für eine Zeichenfolgeneigenschaft festgelegt wird, und in der zweiten Situation wird dargestellt, wie <xref:System.Windows.Forms.Binding.NullValue%2A> für eine Bildeigenschaft festgelegt wird.  
  
 [!code-csharp[System.Windows.Forms.BindingDBNull#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingDBNull#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/VB/form1.vb#1)]  
  
 Der Typ der gebundenen Eigenschaft muss mit dem Typ der <xref:System.Windows.Forms.Binding.NullValue%2A>-Eigenschaft übereinstimmen. Andernfalls wird ein Fehler ausgegeben, und es werden keine weiteren <xref:System.Windows.Forms.Binding.NullValue%2A>-Werte verarbeitet . In diesem Fall wird keine Ausnahme ausgelöst.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Siehe auch  
 [BindingSource-Komponente](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [Vorgehensweise: Behandeln von Fehlern und Ausnahmen in Zusammenhang mit der Datenbindung](../../../../docs/framework/winforms/controls/how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)  
 [Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
