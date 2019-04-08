---
title: Übersicht über die BindingSource-Komponente
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, data binding
- controls [Windows Forms], binding to data
- BindingSource component [Windows Forms], about BindingSource component
- data binding [Windows Forms], BindingSource component
ms.assetid: be838caf-fcb0-4b68-827f-58b2c04b747f
ms.openlocfilehash: 2237ba71487afc132f9164243a664b277397ccfa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098636"
---
# <a name="bindingsource-component-overview"></a>Übersicht über die BindingSource-Komponente
Die <xref:System.Windows.Forms.BindingSource>-Komponente vereinfacht den Bindungsvorgang von Steuerelementen an eine zugrunde liegende Datenquelle. Die <xref:System.Windows.Forms.BindingSource>-Komponente fungiert als Kanal sowie als Datenquelle für andere Steuerelemente, an die eine Bindung erfolgen soll. Sie stellt eine Abstraktion der Datenverbindung Ihres Formulars bereit, während Befehle an die zugrunde liegende Liste der Daten übergeben werden. Außerdem können Sie Daten direkt hinzufügen. Die Komponente selbst fungiert daher als Datenquelle.  
  
## <a name="bindingsource-component-as-an-intermediary"></a>„BindingSource“-Komponente als Zwischenelement  
 Die <xref:System.Windows.Forms.BindingSource>-Komponente fungiert als Datenquelle für einige oder alle Steuerelemente im Formular. In Visual Studio die <xref:System.Windows.Forms.BindingSource> gebunden werden kann, auf ein Steuerelement von der `DataBindings` Eigenschaft, die über die **Eigenschaften** Fenster. Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Binden von Windows Forms-Steuerelementen mithilfe der BindingSource-Komponente, die mithilfe des Designers](bind-wf-controls-with-the-bindingsource.md).  
  
 Sie können die <xref:System.Windows.Forms.BindingSource>-Komponente an einfache Datenquellen (etwa eine einzelne Eigenschaft eines Objekts oder eine Basisauflistung wie <xref:System.Collections.ArrayList>) und komplexe Datenquellen (etwa eine Datenbanktabelle) binden. Die <xref:System.Windows.Forms.BindingSource>-Komponente fungiert als Zwischenelement, das Bindungs- und Währungsverwaltungsdienste bereitstellt. Sie können eine <xref:System.Windows.Forms.BindingSource>-Komponente zur Entwurfszeit oder zur Laufzeit an eine komplexe Datenquelle durch Festlegen der Eigenschaften <xref:System.Windows.Forms.BindingSource.DataSource%2A> und <xref:System.Windows.Forms.BindingSource.DataMember%2A> an die Datenbank bzw. die Tabelle binden. Die folgende Abbildung zeigt, wie sich die <xref:System.Windows.Forms.BindingSource>-Komponente in die vorhandene Datenbindungsarchitektur einfügt.  
  
 ![Bindungsquelle und Datenbindungsarchitektur](./media/net-bindsrcdatabindarch.gif "NET_BindSrcDataBindArch")  
  
> [!NOTE]
>  Zur Entwurfszeit erstellen einige Aktionen (z. B. das Ziehen einer Datenbanktabelle aus einem Datenfenster in ein leeres Formular) die <xref:System.Windows.Forms.BindingSource>-Komponente, binden diese an die zugrunde liegenden Datenquelle und fügen datenkompatible Steuerelemente in einem Vorgang hinzu. Siehe auch [Binden von Windows Forms-Steuerelementen an Daten in Visual Studio](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio).  
  
## <a name="bindingsource-component-as-a-data-source"></a>BindingSource-Komponente als Datenquelle  
 Wenn Sie damit beginnen, der <xref:System.Windows.Forms.BindingSource>-Komponente Elemente hinzuzufügen, ohne zunächst eine Liste anzugeben, an die die Bindung erfolgen soll, agiert die Komponente wie eine Listendatenquelle und akzeptiert diese hinzugefügten Elemente.  
  
 Außerdem können Sie Code schreiben, um benutzerdefinierte "AddNew"-Funktionalität mithilfe des Ereignisses <xref:System.Windows.Forms.BindingSource.AddingNew> bereitzustellen, das ausgelöst wird, wenn die Methode <xref:System.Windows.Forms.BindingSource.AddNew%2A> aufgerufen wird, bevor das Element der Liste hinzugefügt wird. Weitere Informationen finden Sie unter [Architektur der BindingSource-Komponente](bindingsource-component-architecture.md).  
  
## <a name="navigation"></a>Navigation  
 Für Benutzer, die in den Daten eines Formulars navigieren müssen, ermöglicht die <xref:System.Windows.Forms.BindingNavigator>-Komponente das Navigieren und Bearbeiten von Daten in Kombination mit einer <xref:System.Windows.Forms.BindingSource>-Komponente. Weitere Informationen finden Sie unter [BindingNavigator-Steuerelement](bindingnavigator-control-windows-forms.md).  
  
## <a name="data-manipulation"></a>Datenbearbeitung  
 Die <xref:System.Windows.Forms.BindingSource> fungiert als ein <xref:System.Windows.Forms.CurrencyManager> für alle Bindungen und kann daher Zugriff auf Währungs- und Positionsinformationen hinsichtlich der Datenquelle bereitstellen. Die folgende Tabelle enthält die Elemente, die die <xref:System.Windows.Forms.BindingSource>-Komponente für den Zugriff auf die und das Bearbeiten der zugrunde liegenden Daten bereitstellt.  
  
|Member|Beschreibung|  
|------------|-----------------|  
|<xref:System.Windows.Forms.BindingSource.Current%2A> property|Ruft das aktuelle Element der Datenquelle ab.|  
|<xref:System.Windows.Forms.BindingSource.Position%2A> property|Ruft die aktuelle Position in der zugrunde liegenden Liste ab oder legt diese fest.|  
|<xref:System.Windows.Forms.BindingSource.List%2A> property|Ruft die Liste ab, die die Auswertung der Auswertung <xref:System.Windows.Forms.BindingSource.DataSource%2A> und <xref:System.Windows.Forms.BindingSource.DataMember%2A> darstellt. Wenn <xref:System.Windows.Forms.BindingSource.DataMember%2A> nicht festgelegt ist, wird die durch <xref:System.Windows.Forms.BindingSource.DataSource%2A> angegebene Liste zurückgegeben.|  
|<xref:System.Windows.Forms.BindingSource.Insert%2A> Methode|Fügt ein Element am angegebenen Index in die Liste ein.|  
|<xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A> Methode|Entfernt das aktuelle Element aus der Liste.|  
|<xref:System.Windows.Forms.BindingSource.EndEdit%2A> Methode|Wendet anstehende Änderungen auf die zugrunde liegende Datenquelle an.|  
|<xref:System.Windows.Forms.BindingSource.CancelEdit%2A> Methode|Bricht den aktuellen Bearbeitungsvorgang ab.|  
|<xref:System.Windows.Forms.BindingSource.AddNew%2A> Methode|Fügt der zugrunde liegenden Liste ein neues Element hinzu. Wenn die Datenquelle <xref:System.ComponentModel.IBindingList> implementiert und ein Element aus dem <xref:System.Windows.Forms.BindingSource.AddingNew>-Ereignis zurückgibt, wird dieses Element hinzugefügt. Andernfalls wird die Anforderung an die Methode <xref:System.ComponentModel.IBindingList.AddNew%2A> der Liste übergeben. Wenn die zugrunde liegende Liste keine <xref:System.ComponentModel.IBindingList> ist, wird das Element automatisch über seinen öffentlichen Standardkonstruktor erstellt.|  
  
## <a name="sorting-and-filtering"></a>Sortieren und Filtern  
 In der Regel sollten Sie mit einer sortierten oder gefilterten Sicht der Datenquelle arbeiten. Die folgende Tabelle zeigt die Elemente, die die <xref:System.Windows.Forms.BindingSource>-Komponentendatenquelle bereitstellt.  
  
|Member|Beschreibung|  
|------------|-----------------|  
|<xref:System.Windows.Forms.BindingSource.Sort%2A> property|Wenn die Datenquelle eine <xref:System.ComponentModel.IBindingList> ist, wird ein Spaltenname abgerufen oder festgelegt, der für das Sortieren und für Informationen zur Sortierreihenfolge verwendet wird. Wenn die Datenquelle eine <xref:System.ComponentModel.IBindingListView> ist und erweiterte Sortierung unterstützt, werden mehrere Spaltennamen abgerufen, die für das Sortieren und für Informationen zur Sortierreihenfolge verwendet werden.|  
|<xref:System.Windows.Forms.BindingSource.Filter%2A> property|Wenn die Datenquelle eine <xref:System.ComponentModel.IBindingListView> ist, wird der Ausdruck abgerufen, der zum Filtern der anzuzeigenden Zeilen verwendet wird, oder dieser Ausdruck wird festgelegt.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [Architektur der BindingSource-Komponente](bindingsource-component-architecture.md)
- [BindingSource-Komponente](bindingsource-component.md)
- [BindingNavigator-Steuerelement](bindingnavigator-control-windows-forms.md)
- [Datenbindung in Web Forms](../windows-forms-data-binding.md)
- [Steuerelemente für Windows Forms](controls-to-use-on-windows-forms.md)
