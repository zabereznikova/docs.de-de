---
title: 'Gewusst wie: Sicherstellen, dass mehrere Steuerelemente, die an die gleiche Datenquelle gebunden sind, synchronisiert bleiben'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], binding multiple
- controls [Windows Forms], synchronizing with data source
ms.assetid: c2f0ecc6-11e6-4c2c-a1ca-0759630c451e
ms.openlocfilehash: 5ab7eebd4f4087502f8709e17dde3f3de448c9aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539539"
---
# <a name="how-to-ensure-multiple-controls-bound-to-the-same-data-source-remain-synchronized"></a>Gewusst wie: Sicherstellen, dass mehrere Steuerelemente, die an die gleiche Datenquelle gebunden sind, synchronisiert bleiben
Häufig bei der Arbeit mit dem Datenbindung in Windows Forms werden mehrere Steuerelemente, die an die gleiche Datenquelle gebunden. In einigen Fällen kann es erforderlich sein, zusätzliche Schritte ausführen, um sicherzustellen, dass die gebundenen Eigenschaften der Steuerelemente untereinander und mit der Datenquelle synchronisiert bleiben. Diese Schritte sind in zwei Situationen notwendig:  
  
-   Wenn die Datenquelle keine implementiert <xref:System.ComponentModel.IBindingList>, und daher generieren <xref:System.ComponentModel.IBindingList.ListChanged> Ereignisse des Typs <xref:System.ComponentModel.ListChangedType.ItemChanged>.  
  
-   Wenn die Datenquelle implementiert <xref:System.ComponentModel.IEditableObject>.  
  
 Im ersten Fall können Sie eine <xref:System.Windows.Forms.BindingSource> die Datenquelle an Steuerelemente binden. In letzterem Fall verwenden Sie eine <xref:System.Windows.Forms.BindingSource> und behandeln die <xref:System.Windows.Forms.BindingSource.BindingComplete> Ereignis, und rufen <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> auf dem zugeordneten <xref:System.Windows.Forms.BindingManagerBase>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie drei Steuerelemente binden – zwei Textfeld Steuerelemente und ein <xref:System.Windows.Forms.DataGridView> Steuerelement – an derselben Spalte in einer <xref:System.Data.DataSet> mithilfe einer <xref:System.Windows.Forms.BindingSource> Komponente. In diesem Beispiel wird veranschaulicht, wie behandelt die <xref:System.Windows.Forms.BindingSource.BindingComplete> Ereignis und sicherstellen, dass, wenn der Textwert, der ein Textfeld geändert wird, wird das zusätzliche Textfeld und die <xref:System.Windows.Forms.DataGridView> Steuerelement mit dem richtigen Wert aktualisiert werden.  
  
 Im Beispiel wird eine <xref:System.Windows.Forms.BindingSource> der Datenquelle und die Steuerelemente binden. Alternativ können Sie die Steuerelemente direkt an die Datenquelle binden und Abrufen der <xref:System.Windows.Forms.BindingManagerBase> für die Bindung aus des Formulars <xref:System.Windows.Forms.Control.BindingContext%2A> und behandeln Sie anschließend die <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> -Ereignis für die <xref:System.Windows.Forms.BindingManagerBase>. Ein Beispiel hierzu finden Sie die Hilfeseite zum der <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> -Ereignis <xref:System.Windows.Forms.BindingManagerBase>.  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-   Dieses Codebeispiel erfordert  
  
-   Verweise auf die Assemblys <xref:System>, <xref:System.Windows.Forms> und <xref:System.Drawing>.  
  
-   Ein Formular mit der <xref:System.Windows.Forms.Form.Load> Ereignis behandelt und einem Aufruf an die `InitializeControlsAndDataSource` -Methode im Beispiel aus des Formulars <xref:System.Windows.Forms.Form.Load> -Ereignishandler.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Freigeben von gebundenen Daten in Formularen mithilfe der BindingSource-Komponente](../../../docs/framework/winforms/controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)  
 [Änderungsbenachrichtigung in der Windows Forms-Datenbindung](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [Auf Datenbindung bezogene Schnittstellen](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)  
 [Windows Forms-Datenbindung](../../../docs/framework/winforms/windows-forms-data-binding.md)
