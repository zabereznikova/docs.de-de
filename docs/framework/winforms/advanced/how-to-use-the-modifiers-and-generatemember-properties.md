---
title: 'Gewusst wie: Verwenden von Modifizierern und GenerateMember-Eigenschaften'
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
f1_keywords:
- Designer_GenerateMember
- Designer_Modifiers
helpviewer_keywords:
- base forms
- inheritance [Windows Forms], forms
- inherited forms [Windows Forms], Windows Forms
- inherited forms
- form inheritance
- Windows Forms, inheritance
ms.assetid: 3381a5e4-e1a3-44e2-a765-a0b758937b85
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f524bab55527bf9d3c744cb6f50d1df1fc9a2302
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a>Gewusst wie: Verwenden von Modifizierern und GenerateMember-Eigenschaften
Wenn Sie eine Komponente in einem Windows Form platzieren, werden zwei Eigenschaften von der entwurfsumgebung bereitgestellt: `GenerateMember` und `Modifiers`. Die `GenerateMember` Eigenschaft gibt an, wann eine Membervariable für eine Komponente von Windows Forms-Designer generiert. Die `Modifiers` Eigenschaft ist für den Zugriffsmodifizierer auf diese Membervariable zugewiesen. Wenn der Wert von der `GenerateMember` Eigenschaft ist `false`, den Wert des der `Modifiers` Eigenschaft hat keine Auswirkungen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-specify-whether-a-component-is-a-member-of-the-form"></a>Um anzugeben, ob eine Komponente des Formulars angehört  
  
1.  Öffnen Sie in Windows Forms-Designer das Formular aus.  
  
2.  Öffnen der **Toolbox**, und platzieren Sie auf dem Formular drei <xref:System.Windows.Forms.Button> Steuerelemente.  
  
3.  Legen Sie die `GenerateMember` und `Modifiers` Eigenschaften für die einzelnen <xref:System.Windows.Forms.Button> Steuerelement entsprechend der folgenden Tabelle.  
  
    |Schaltflächenname|GenerateMember-Wert|Modifizierer Wert|  
    |-----------------|--------------------------|---------------------|  
    |`button1`|`true`|`private`|  
    |`button2`|`true`|`protected`|  
    |`button3`|`false`|Keine Änderung|  
  
4.  Erstellen Sie die Projektmappe.  
  
5.  Klicken Sie im **Projektmappen-Explorer** auf die Schaltfläche **Alle Dateien anzeigen**.  
  
6.  Öffnen Sie die **Form1** Knoten, und klicken Sie in der **Code-Editor**öffnen die **Form1.Designer.vb** oder **Form1.Designer.cs** Datei. Diese Datei enthält den Code ausgegeben, die für Windows Forms-Designer.  
  
7.  Suchen Sie die Deklarationen für die drei Schaltflächen. Das folgende Codebeispiel zeigt die Unterschiede, die gemäß der `GenerateMember` und `Modifiers` Eigenschaften.  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]  
  
> [!NOTE]
>  Windows Forms-Designer weist standardmäßig den `private` (`Friend` in Visual Basic) Modifizierer Containersteuerelementen wie <xref:System.Windows.Forms.Panel>. Wenn Ihre Basis <xref:System.Windows.Forms.UserControl> oder <xref:System.Windows.Forms.Form> ist ein Container-Steuerelement akzeptiert keine neuen untergeordneten Elemente in geerbte Steuerelemente und Formulare. Die Lösung besteht darin, den Modifizierer des Steuerelements basiscontainerobjekts ändern `protected` oder `public`.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Button>  
 [Visuelle Vererbung in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)  
 [Exemplarische Vorgehensweise: Demonstrieren der visuellen Vererbung](../../../../docs/framework/winforms/advanced/walkthrough-demonstrating-visual-inheritance.md)  
 [Vorgehensweise: Erben von Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)
