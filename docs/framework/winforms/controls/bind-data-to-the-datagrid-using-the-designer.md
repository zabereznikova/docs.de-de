---
title: 'Vorgehensweise: Binden von Daten an das DataGridView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, binding to a data source
- data sources [Windows Forms], binding to Windows Forms controls
- DataGridView control [Windows Forms], data binding
ms.assetid: f4f46009-cec2-441b-8668-6b5af057558b
ms.openlocfilehash: 8c90366111957f27a6bd86035013eba00426f46b
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718505"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control-using-the-designer"></a>Vorgehensweise: Binden von Daten an das DataGridView-Steuerelement in Windows Forms mithilfe des Designers
Sie können den Designer verwenden, die Verbindung eine <xref:System.Windows.Forms.DataGridView> Steuerelement mit Datenquellen, die verschiedenen Varianten, einschließlich Datenbanken, Geschäftsobjekte oder Webdienste. Wenn Sie mit einer Datenquelle mithilfe des Designers das Steuerelement binden, das Steuerelement automatisch an gebunden ist eine <xref:System.Windows.Forms.BindingSource> Komponente, die die Datenquelle darstellt. Darüber hinaus werden automatisch Spalten im Steuerelement erstellt, damit sie den Schemainformationen der Datenquelle entsprechen.  
  
 Nachdem die Spalten erzeugt wurden, können Sie sie Ihren Bedürfnissen entsprechend ändern. Sie können z.B. Spalten entfernen oder ausblenden, die für Sie nicht interessant sind, die Spalten neu anordnen oder die Typen der Spalten ändern. Weitere Informationen zum Modifizieren von Spalten finden Sie in den Themen im Abschnitt „Siehe auch“.  
  
 Sie können auch mehrere binden <xref:System.Windows.Forms.DataGridView> -Steuerelemente an zugehörige Tabellen zum Erstellen von Master/Detail-Beziehungen. In dieser Konfiguration zeigt ein Steuerelement eine übergeordnete Tabelle und ein anderes Steuerelement nur die Reihen einer untergeordneten Tabelle an, die sich auf die aktuelle Reihe in der übergeordneten Tabelle beziehen. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von verknüpften Daten in einer Windows Forms-Anwendung](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120)).  
  
 Das folgende Verfahren benötigt eine **Windows-Anwendung** -Projekt mit einem Formular, enthält eine <xref:System.Windows.Forms.DataGridView> -Steuerelement oder zwei Steuerelemente für eine Master/Detail-Beziehung. Informationen zum Starten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-bind-the-control-to-a-data-source"></a>So binden Sie das Steuerelement an eine Datenquelle  
  
1.  Klicken Sie auf die Smarttag-Glyphe (![Smarttag-Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) in der Ecke oben rechts von der <xref:System.Windows.Forms.DataGridView> Steuerelement.  
  
2.  Klicken Sie auf den Dropdownpfeil für die Option **Datenquelle auswählen**.  
  
3.  Klicken Sie auf **Projektdatenquelle hinzufügen**, wenn Ihr Projekt noch nicht über eine Datenquelle verfügt, und befolgen Sie die Schritte des Assistenten.  
  
     Weitere Informationen finden Sie unter [Assistent zum Konfigurieren von Datenquellen](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/w4dd7z6t(v=vs.120)). Die neue Datenquelle wird im Dropdownfenster **Datenquelle auswählen** angezeigt. Wenn Ihre neue Datenquelle nur einen Member enthält, z.B. eine einzelne Datenbanktabelle, bindet das Steuerelement automatisch an diesen Member. Setzen Sie andernfalls den Vorgang mit dem nächsten Schritt fort.  
  
4.  Erweitern Sie die Knoten **Weitere Datenquellen** und **Projektdatenquellen**, wenn Sie noch nicht erweitert sind, und wählen Sie die Datenquelle aus, an die Sie das Steuerelement binden wollen.  
  
5.  Wenn Sie die Datenquelle mehr als ein Element enthält, z. B. Wenn Sie haben eine <xref:System.Data.DataSet?displayProperty=nameWithType> , die mehrere Tabellen enthält, erweitern Sie die Datenquelle, und wählen Sie dann den bestimmten Member zum Binden an.  
  
6.  Erstellen Sie eine Master/Detail-Beziehung in der **Datenquelle auswählen** Dropdownfenster für eine Sekunde <xref:System.Windows.Forms.DataGridView> steuern, erweitern Sie die <xref:System.Windows.Forms.BindingSource> für die übergeordnete Tabelle erstellt, und wählen Sie dann die zugehörige untergeordnete Tabelle aus der Liste angezeigt.  
  
    > [!NOTE]
    >  Wenn Ihr Projekt bereits über eine Datenquelle verfügt, können Sie auch das Fenster **Datenquellen** verwenden, um ein Datenformular zu erstellen. Weitere Informationen finden Sie unter [Datenquellenfenster](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120)).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridView.DataMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- [Vorgehensweise: Verbinden Sie mit Daten in einer Datenbank](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120))
- [Vorgehensweise: Hinzufügen und Entfernen von Spalten in der DataGridView-Steuerelement in Windows Forms mithilfe des Designers](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Vorgehensweise: Ändern der Reihenfolge der Spalten in der DataGridView-Steuerelement in Windows Forms mithilfe des Designers](change-the-order-of-columns-in-the-datagrid-using-the-designer.md)
- [Vorgehensweise: Ändern des Typs einer DataGridView-Spalte in Windows Forms mithilfe des Designers](change-the-type-of-a-wf-datagridview-column-using-the-designer.md)
- [Vorgehensweise: Einfrieren von Spalten in der DataGridView-Steuerelement in Windows Forms mithilfe des Designers](freeze-columns-in-the-datagrid-using-the-designer.md)
- [Vorgehensweise: Ausblenden von Spalten in der DataGridView-Steuerelement in Windows Forms mithilfe des Designers](hide-columns-in-the-datagrid-using-the-designer.md)
- [Vorgehensweise: Stellen Sie Spalten aus, in das DataGridView-Steuerelement in Windows Forms mithilfe des Designers schreibgeschützt](make-columns-read-only-in-the-datagrid-using-the-designer.md)
- [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md)
- [Datenquellenfenster](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))
- [Vorgehensweise: Zeigen Sie verknüpfter Daten in einer Windows Forms-Anwendung an](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120))
