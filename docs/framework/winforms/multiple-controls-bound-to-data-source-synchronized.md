---
title: 'Vorgehensweise: Sicherstellen, dass mehrere Steuerelemente, die an die gleiche Datenquelle gebunden sind, synchronisiert bleiben'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], binding multiple
- controls [Windows Forms], synchronizing with data source
ms.assetid: c2f0ecc6-11e6-4c2c-a1ca-0759630c451e
ms.openlocfilehash: 8f7e59720420a845fa195b8c0fb078a8699a9bc3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170338"
---
# <a name="how-to-ensure-multiple-controls-bound-to-the-same-data-source-remain-synchronized"></a>Vorgehensweise: Sicherstellen, dass mehrere Steuerelemente, die an die gleiche Datenquelle gebunden sind, synchronisiert bleiben
Wenn bei der Arbeit mit Datenbindung in Windows Forms sind mehrere Steuerelemente an die gleiche Datenquelle gebunden. In einigen Fällen kann es erforderlich sein einige zusätzliche Schritte durchführen, um sicherzustellen, dass die gebundenen Eigenschaften der Steuerelemente mit miteinander und mit der Datenquelle synchronisiert bleiben. Diese Schritte sind in zwei Situationen erforderlich:  
  
-   Wenn die Datenquelle keine implementiert <xref:System.ComponentModel.IBindingList>, und generieren Sie aus diesem Grund <xref:System.ComponentModel.IBindingList.ListChanged> Ereignisse des Typs <xref:System.ComponentModel.ListChangedType.ItemChanged>.  
  
-   Wenn die Datenquelle implementiert <xref:System.ComponentModel.IEditableObject>.  
  
 Im ersten Fall können Sie eine <xref:System.Windows.Forms.BindingSource> auf die Datenquelle an Steuerelemente binden. In letzterem Fall verwenden Sie eine <xref:System.Windows.Forms.BindingSource> und behandeln die <xref:System.Windows.Forms.BindingSource.BindingComplete> Ereignis, und rufen <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> für das zugeordnete <xref:System.Windows.Forms.BindingManagerBase>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie drei Steuerelemente gebunden – zwei Textfeld-Steuerelemente und ein <xref:System.Windows.Forms.DataGridView> Steuerelement – an derselben Spalte in einer <xref:System.Data.DataSet> mithilfe einer <xref:System.Windows.Forms.BindingSource> Komponente. In diesem Beispiel wird veranschaulicht, wie Sie behandelt die <xref:System.Windows.Forms.BindingSource.BindingComplete> Ereignis und stellen Sie sicher, dass wenn der Textwert des einem Textfeld geändert wird, das zusätzliche Textfeld und die <xref:System.Windows.Forms.DataGridView> Steuerelement mit dem richtigen Wert aktualisiert werden.  
  
 Im Beispiel wird eine <xref:System.Windows.Forms.BindingSource> der Datenquelle und die Steuerelemente gebunden. Alternativ können Sie die Steuerelemente direkt an die Datenquelle zu binden und Abrufen der <xref:System.Windows.Forms.BindingManagerBase> für die Bindung von des Formulars <xref:System.Windows.Forms.Control.BindingContext%2A> und verarbeiten dann die <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> -Ereignis für die <xref:System.Windows.Forms.BindingManagerBase>. Ein Beispiel dazu, der Hilfeseite finden Sie Informationen zu den <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> Ereignis <xref:System.Windows.Forms.BindingManagerBase>.  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleControls#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleControls#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-   Dieses Codebeispiel erfordert  
  
-   Verweise auf die Assemblys <xref:System>, <xref:System.Windows.Forms> und <xref:System.Drawing>.  
  
-   Ein Formular mit den <xref:System.Windows.Forms.Form.Load> Ereignis als behandelt und einem Aufruf an die `InitializeControlsAndDataSource` -Methode in der im Beispiel des Formulars <xref:System.Windows.Forms.Form.Load> -Ereignishandler.  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Freigeben von gebundenen Daten in Formularen mithilfe der BindingSource-Komponente](./controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)
- [Änderungsbenachrichtigung in der Windows Forms-Datenbindung](change-notification-in-windows-forms-data-binding.md)
- [Auf Datenbindung bezogene Schnittstellen](interfaces-related-to-data-binding.md)
- [Windows Forms-Datenbindung](windows-forms-data-binding.md)
