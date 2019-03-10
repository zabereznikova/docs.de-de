---
title: 'Vorgehensweise: Ordnen Sie ein ContextMenuStrip zu einem Steuerelement zu'
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
ms.openlocfilehash: 4b61da8dc9f36e0a80807547e2049ef512c94747
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718335"
---
# <a name="how-to-associate-a-contextmenustrip-with-a-control"></a>Vorgehensweise: Ordnen Sie ein ContextMenuStrip zu einem Steuerelement zu
Nachdem Sie Ihre Steuerelemente und Kontextmenüs erstellt haben, verwenden Sie die folgenden Verfahren, um ein bestimmtes Kontextmenü anzuzeigen, wenn der Benutzer mit der rechten Maustaste auf das Steuerelement klickt. In diesen Verfahren wird eine <xref:System.Windows.Forms.ContextMenuStrip>-Instanz einem Windows Form-Objekt und einem <xref:System.Windows.Forms.ToolStrip>-Steuerelement zugeordnet.  
  
### <a name="to-associate-a-contextmenustrip-with-a-windows-form"></a>So ordnen Sie eine ContextMenuStrip-Instanz einem Windows Form-Objekt zu  
  
1.  Legen Sie die <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>-Eigenschaft auf den Namen der zugeordneten <xref:System.Windows.Forms.ContextMenuStrip>-Instanz fest.  
  
### <a name="to-associate-a-contextmenustrip-with-a-toolstrip-control"></a>So ordnen Sie eine ContextMenuStrip-Instanz einem ToolStrip-Steuerelement zu  
  
1.  Legen Sie die <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>-Eigenschaft des Steuerelements auf den Namen der zugeordneten <xref:System.Windows.Forms.ContextMenuStrip>-Instanz fest.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel werden ein Windows Form-Objekt und ein <xref:System.Windows.Forms.ToolStrip>-Steuerelement erstellt, und beiden wird jeweils ein anderes <xref:System.Windows.Forms.ContextMenuStrip>-Steuerelement zugeordnet.  
  
 [!code-csharp[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>
- <xref:System.Windows.Forms.ToolStrip>
- [Vorgehensweise: Hinzufügen von Menüelementen zu einem ContextMenuStrip](how-to-add-menu-items-to-a-contextmenustrip.md)
- [ContextMenuStrip-Steuerelement](contextmenustrip-control.md)
