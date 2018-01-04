---
title: 'Gewusst wie: Binden von Daten an das DataGridView-Steuerelement in Windows Forms mithilfe des Designers'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, binding to a data source
- data sources [Windows Forms], binding to Windows Forms controls
- DataGridView control [Windows Forms], data binding
ms.assetid: f4f46009-cec2-441b-8668-6b5af057558b
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a31b407360467f37c2e60b1a3f4f4c72e80e13a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control-using-the-designer"></a>Gewusst wie: Binden von Daten an das DataGridView-Steuerelement in Windows Forms mithilfe des Designers
Können Sie die Verbindung den Designer einen <xref:System.Windows.Forms.DataGridView> Steuerelement Datenquellen verschiedenster, z. B. Datenbanken, Geschäftsobjekte oder Webdienste. Wenn Sie das Steuerelement mit einer Datenquelle mithilfe des Designers binden, wird das Steuerelement automatisch an gebunden eine <xref:System.Windows.Forms.BindingSource> Komponente, die die Datenquelle darstellt. Darüber hinaus werden automatisch Spalten im Steuerelement erstellt, damit sie den Schemainformationen der Datenquelle entsprechen.  
  
 Nachdem die Spalten erzeugt wurden, können Sie sie Ihren Bedürfnissen entsprechend ändern. Sie können z.B. Spalten entfernen oder ausblenden, die für Sie nicht interessant sind, die Spalten neu anordnen oder die Typen der Spalten ändern. Weitere Informationen zum Modifizieren von Spalten finden Sie in den Themen im Abschnitt „Siehe auch“.  
  
 Sie können auch mehrere binden <xref:System.Windows.Forms.DataGridView> Steuerelemente zu verknüpften Tabellen Master/Detail-Beziehung zu erstellen. In dieser Konfiguration zeigt ein Steuerelement eine übergeordnete Tabelle und ein anderes Steuerelement nur die Reihen einer untergeordneten Tabelle an, die sich auf die aktuelle Reihe in der übergeordneten Tabelle beziehen. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von verknüpften Daten in einer Windows Forms-Anwendung](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd).  
  
 Das folgende Verfahren erfordert eine **Windows-Anwendung** -Projekts mit einem Formular, enthält eine <xref:System.Windows.Forms.DataGridView> zwei Steuerelemente für eine Master/Detail-Beziehung. Informationen zum Starten eines solchen Projekts finden Sie unter [How to: Create a Windows Application Project (Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts)](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Vorgehensweise: Hinzufügen von Steuerelementen für Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-bind-the-control-to-a-data-source"></a>So binden Sie das Steuerelement an eine Datenquelle  
  
1.  Klicken Sie auf das Smarttag-Symbol (![Smart Tag-Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) in der oberen rechten Ecke des der <xref:System.Windows.Forms.DataGridView> Steuerelement.  
  
2.  Klicken Sie auf den Dropdownpfeil für die Option **Datenquelle auswählen**.  
  
3.  Klicken Sie auf **Projektdatenquelle hinzufügen**, wenn Ihr Projekt noch nicht über eine Datenquelle verfügt, und befolgen Sie die Schritte des Assistenten.  
  
     Weitere Informationen finden Sie unter [Assistent zum Konfigurieren von Datenquellen](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f). Die neue Datenquelle wird im Dropdownfenster **Datenquelle auswählen** angezeigt. Wenn Ihre neue Datenquelle nur einen Member enthält, z.B. eine einzelne Datenbanktabelle, bindet das Steuerelement automatisch an diesen Member. Setzen Sie andernfalls den Vorgang mit dem nächsten Schritt fort.  
  
4.  Erweitern Sie die Knoten **Weitere Datenquellen** und **Projektdatenquellen**, wenn Sie noch nicht erweitert sind, und wählen Sie die Datenquelle aus, an die Sie das Steuerelement binden wollen.  
  
5.  Wenn die Datenquelle mehrere Member enthält, z. B. Wenn Sie haben eine <xref:System.Data.DataSet?displayProperty=nameWithType> , die mehrere Tabellen enthält, erweitern Sie die Datenquelle, und wählen Sie dann auf das ein bestimmte Element zum Binden an.  
  
6.  So erstellen eine Master/Detail-Beziehung in der **Datenquelle auswählen** Dropdown-Fenster für eine zweite <xref:System.Windows.Forms.DataGridView> steuern, erweitern Sie die <xref:System.Windows.Forms.BindingSource> für die übergeordnete Tabelle erstellt, und wählen Sie dann die zugehörige untergeordnete Tabelle aus der Liste angezeigt.  
  
    > [!NOTE]
    >  Wenn Ihr Projekt bereits über eine Datenquelle verfügt, können Sie auch das Fenster **Datenquellen** verwenden, um ein Datenformular zu erstellen. Weitere Informationen finden Sie unter [Datenquellenfenster](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.DataGridView.DataMember%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 [Gewusst wie: Herstellen einer Verbindung zu Daten in einer Datenbank](http://msdn.microsoft.com/library/6c56e54e-8834-4297-85aa-cc1a443ba556)  
 [Vorgehensweise: Hinzufügen und Entfernen von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 [Vorgehensweise: Ändern der Reihenfolge von Spalten des DataGridView-Steuerelements in Windows Forms mithilfe des Designers](../../../../docs/framework/winforms/controls/change-the-order-of-columns-in-the-datagrid-using-the-designer.md)  
 [Vorgehensweise: Ändern des Typs einer DataGridView-Spalte in Windows Forms mithilfe des Designers](../../../../docs/framework/winforms/controls/change-the-type-of-a-wf-datagridview-column-using-the-designer.md)  
 [Vorgehensweise: Fixieren von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers](../../../../docs/framework/winforms/controls/freeze-columns-in-the-datagrid-using-the-designer.md)  
 [Vorgehensweise: Ausblenden von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers](../../../../docs/framework/winforms/controls/hide-columns-in-the-datagrid-using-the-designer.md)  
 [Vorgehensweise: Festlegen von schreibgeschützten Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers](../../../../docs/framework/winforms/controls/make-columns-read-only-in-the-datagrid-using-the-designer.md)  
 [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [Datenquellenfenster](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)  
 [Gewusst wie: Anzeigen von verknüpften Daten in einer Windows Forms-Anwendung](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)
