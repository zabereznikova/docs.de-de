---
title: 'Vorgehensweise: Auslösen von Änderungsbenachrichtigungen mithilfe der BindingSource und der INotifyPropertyChanged-Schnittstelle'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- change notifications [Windows Forms], raising
- BindingSource component [Windows Forms], and IPropertyChange
- data sources [Windows Forms], detecting changes
- examples [Windows Forms], BindingSource component
- change notifications
- INotifyPropertyChanged interface [Windows Forms], using with BindingSource
- BindingSource component [Windows Forms], examples
ms.assetid: 7fa2cf51-c09f-4375-adf0-e36c5617f099
ms.openlocfilehash: b3ac3982905bf3d84c9cc570d901d95ca14cc92e
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/22/2019
ms.locfileid: "56664067"
---
# <a name="how-to-raise-change-notifications-using-a-bindingsource-and-the-inotifypropertychanged-interface"></a>Vorgehensweise: Auslösen von Änderungsbenachrichtigungen mithilfe der BindingSource und der INotifyPropertyChanged-Schnittstelle
Die <xref:System.Windows.Forms.BindingSource>-Komponente erkennt automatisch Änderungen in einer Datenquelle, wenn der in der Datenquelle enthaltene Typ die <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle implementiert und <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged>-Ereignisse auslöst, sobald ein Eigenschaftswert geändert wird. Dies ist nützlich, da an die <xref:System.Windows.Forms.BindingSource> gebundene Steuerelemente automatisch aktualisiert werden, wenn sich die Datenquellenwerte ändern.  
  
> [!NOTE]
>  Wenn die Datenquelle <xref:System.ComponentModel.INotifyPropertyChanged> implementiert, sollten Sie beim Durchführen asynchroner Operationen keine Änderungen an der Datenquelle in einem Hintergrundthread vornehmen. Lesen Sie die Daten stattdessen in einem Hintergrundthread, und führen Sie sie in einer Liste auf dem UI-Thread zusammen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht eine einfache Implementierung der <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle. Darüber hinaus wird gezeigt, wie <xref:System.Windows.Forms.BindingSource> automatisch eine Datenquellenänderung an ein gebundenes Steuerelement übergibt, wenn <xref:System.Windows.Forms.BindingSource> an eine Liste des <xref:System.ComponentModel.INotifyPropertyChanged>-Typs gebunden ist.   
  
 Wenn Sie das `CallerMemberName`-Attribut verwenden, müssen Aufrufe der `NotifyPropertyChanged`-Methode den Eigenschaftennamen nicht als Zeichenfolgenargument angeben. Weitere Informationen finden Sie unter [Caller Information (C#)](../../../csharp/programming-guide/concepts/caller-information.md) oder [Aufruferinformationen (Visual Basic)](../../../visual-basic/programming-guide/concepts/caller-information.md).  
  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen. Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Kompilieren und Ausführen einer vollständigen Windows Forms-Codebeispiels mit Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb129228(v=vs.100)).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.ComponentModel.INotifyPropertyChanged>
- [BindingSource-Komponente](../../../../docs/framework/winforms/controls/bindingsource-component.md)
- [Vorgehensweise: Auslösen von Änderungsbenachrichtigungen mithilfe der BindingSource ResetItem-Methode](../../../../docs/framework/winforms/controls/how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)
