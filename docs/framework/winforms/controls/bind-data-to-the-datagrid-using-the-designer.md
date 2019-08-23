---
title: 'Vorgehensweise: Binden von Daten an das DataGridView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, binding to a data source
- data sources [Windows Forms], binding to Windows Forms controls
- DataGridView control [Windows Forms], data binding
ms.assetid: f4f46009-cec2-441b-8668-6b5af057558b
ms.openlocfilehash: 609878416be26786ce865168c996c78e18b1897f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917877"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control-using-the-designer"></a>Vorgehensweise: Binden von Daten an das DataGridView-Steuerelement in Windows Forms mithilfe des Designers
Sie können den-Designer verwenden, um <xref:System.Windows.Forms.DataGridView> ein-Steuerelement mit Datenquellen verschiedener Variationen, einschließlich Datenbanken, Geschäftsobjekten oder Webdiensten, zu verbinden. Wenn Sie das Steuerelement mithilfe des Designers an eine Datenquelle binden, wird das Steuerelement automatisch an <xref:System.Windows.Forms.BindingSource> eine Komponente gebunden, die die Datenquelle darstellt. Darüber hinaus werden automatisch Spalten im Steuerelement erstellt, damit sie den Schemainformationen der Datenquelle entsprechen.

 Nachdem die Spalten erzeugt wurden, können Sie sie Ihren Bedürfnissen entsprechend ändern. Sie können z.B. Spalten entfernen oder ausblenden, die für Sie nicht interessant sind, die Spalten neu anordnen oder die Typen der Spalten ändern. Weitere Informationen zum Modifizieren von Spalten finden Sie in den Themen im Abschnitt „Siehe auch“.

 Sie können auch mehrere <xref:System.Windows.Forms.DataGridView> Steuerelemente an verknüpfte Tabellen binden, um Master-/Detailbeziehungen zu erstellen. In dieser Konfiguration zeigt ein Steuerelement eine übergeordnete Tabelle und ein anderes Steuerelement nur die Reihen einer untergeordneten Tabelle an, die sich auf die aktuelle Reihe in der übergeordneten Tabelle beziehen. Weitere Informationen finden Sie unter [Vorgehensweise: Zeigen Sie verknüpfte Daten in einer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120))Windows Forms Anwendung an.

 Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, das <xref:System.Windows.Forms.DataGridView> ein-Steuerelement oder zwei-Steuerelemente für eine Master/Detail-Beziehung enthält. Weitere Informationen zum Starten eines solchen Projekts finden [Sie unter Gewusst wie: Erstellen Sie ein Windows Forms-](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Anwendungs [Projekt, und Gewusst wie: Fügen Sie Windows Forms](how-to-add-controls-to-windows-forms.md)Steuerelemente hinzu.

## <a name="to-bind-the-control-to-a-data-source"></a>So binden Sie das Steuerelement an eine Datenquelle

1. Klicken Sie in der oberen rechten <xref:System.Windows.Forms.DataGridView> Ecke des Steuer Elements auf das Smarttagsymbol (![Smarttag-Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")).

2. Klicken Sie auf den Dropdownpfeil für die Option **Datenquelle auswählen**.

3. Klicken Sie auf **Projektdatenquelle hinzufügen**, wenn Ihr Projekt noch nicht über eine Datenquelle verfügt, und befolgen Sie die Schritte des Assistenten.

     Weitere Informationen finden Sie unter [Assistent zum Konfigurieren von Datenquellen](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/w4dd7z6t(v=vs.120)). Die neue Datenquelle wird im Dropdownfenster **Datenquelle auswählen** angezeigt. Wenn Ihre neue Datenquelle nur einen Member enthält, z.B. eine einzelne Datenbanktabelle, bindet das Steuerelement automatisch an diesen Member. Setzen Sie andernfalls den Vorgang mit dem nächsten Schritt fort.

4. Erweitern Sie die Knoten **Weitere Datenquellen** und **Projektdatenquellen**, wenn Sie noch nicht erweitert sind, und wählen Sie die Datenquelle aus, an die Sie das Steuerelement binden wollen.

5. Wenn die Datenquelle mehr als ein Element enthält, z. b. Wenn Sie eine <xref:System.Data.DataSet?displayProperty=nameWithType> erstellt haben, die mehrere Tabellen enthält, erweitern Sie die Datenquelle, und wählen Sie dann den bestimmten Member aus, an den die Bindung erfolgen soll.

6. Zum Erstellen einer Master/Detail-Beziehung erweitern Sie im Dropdown Fenster **Datenquelle auswählen** für ein zweites <xref:System.Windows.Forms.DataGridView> Steuerelement das <xref:System.Windows.Forms.BindingSource> für die übergeordnete Tabelle erstellte, und wählen Sie dann in der angezeigten Liste die zugehörige untergeordnete Tabelle aus.

    > [!NOTE]
    > Wenn Ihr Projekt bereits über eine Datenquelle verfügt, können Sie auch das Fenster **Datenquellen** verwenden, um ein Datenformular zu erstellen. Weitere Informationen finden Sie unter [Datenquellenfenster](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120)).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridView.DataMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- [Vorgehensweise: Herstellen einer Verbindung mit Daten in einer Datenbank](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120))
- [Vorgehensweise: Hinzufügen und Entfernen von Spalten im Windows Forms DataGridView-Steuerelement mithilfe des Designers](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Vorgehensweise: Ändern der Reihenfolge von Spalten im Windows Forms DataGridView-Steuerelement mithilfe des Designers](change-the-order-of-columns-in-the-datagrid-using-the-designer.md)
- [Vorgehensweise: Ändern des Typs einer Windows Forms DataGridView-Spalte mithilfe des Designers](change-the-type-of-a-wf-datagridview-column-using-the-designer.md)
- [Vorgehensweise: Fixieren von Spalten im Windows Forms DataGridView-Steuerelement mithilfe des Designers](freeze-columns-in-the-datagrid-using-the-designer.md)
- [Vorgehensweise: Ausblenden von Spalten im Windows Forms DataGridView-Steuerelement mithilfe des Designers](hide-columns-in-the-datagrid-using-the-designer.md)
- [Vorgehensweise: Festlegen von schreibgeschützten Spalten im Windows Forms DataGridView-Steuerelement mithilfe des Designers](make-columns-read-only-in-the-datagrid-using-the-designer.md)
- [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md)
- [Datenquellen Fenster](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))
- [Vorgehensweise: Anzeigen verwandter Daten in einer Windows Forms Anwendung](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120))
