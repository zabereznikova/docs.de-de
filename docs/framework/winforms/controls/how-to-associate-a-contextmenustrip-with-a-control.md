---
title: 'Gewusst wie: Zuordnen eines ContextMenuStrip zu einem Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [Windows Forms], relating
- ContextMenuStrips [Windows Forms], associating with controls
- context menus [Windows Forms], associating with controls
- ContextMenuStrips [Windows Forms], relating
ms.assetid: 6fc40a42-5d69-427f-aa30-0a146193226b
ms.openlocfilehash: 7776a5e5ed6e650aad82f7863a7fa1748006b3bc
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45517723"
---
# <a name="how-to-associate-a-contextmenustrip-with-a-control"></a>Gewusst wie: Zuordnen eines ContextMenuStrip zu einem Steuerelement
Nachdem Sie Ihre Steuerelemente und Kontextmenüs erstellt haben, verwenden Sie die folgenden Verfahren, um ein bestimmtes Kontextmenü anzuzeigen, wenn der Benutzer mit der rechten Maustaste auf das Steuerelement klickt. In diesen Verfahren wird eine <xref:System.Windows.Forms.ContextMenuStrip>-Instanz einem Windows Form-Objekt und einem <xref:System.Windows.Forms.ToolStrip>-Steuerelement zugeordnet.  
  
### <a name="to-associate-a-contextmenustrip-with-a-windows-form"></a>So ordnen Sie eine ContextMenuStrip-Instanz einem Windows Form-Objekt zu  
  
1.  Legen Sie die <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>-Eigenschaft auf den Namen der zugeordneten <xref:System.Windows.Forms.ContextMenuStrip>-Instanz fest.  
  
### <a name="to-associate-a-contextmenustrip-with-a-toolstrip-control"></a>So ordnen Sie eine ContextMenuStrip-Instanz einem ToolStrip-Steuerelement zu  
  
1.  Legen Sie die <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>-Eigenschaft des Steuerelements auf den Namen der zugeordneten <xref:System.Windows.Forms.ContextMenuStrip>-Instanz fest.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel werden ein Windows Form-Objekt und ein <xref:System.Windows.Forms.ToolStrip>-Steuerelement erstellt, und beiden wird jeweils ein anderes <xref:System.Windows.Forms.ContextMenuStrip>-Steuerelement zugeordnet.  
  
 [!code-csharp[System.Windows.Forms.ContextMenuStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ContextMenuStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch: [Vorgehensweise Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>  
 <xref:System.Windows.Forms.ToolStrip>  
 [Vorgehensweise: Hinzufügen von Menüelementen zu einem ContextMenuStrip](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md)  
 [ContextMenuStrip-Steuerelement](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)
