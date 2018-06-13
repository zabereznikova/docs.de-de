---
title: Architektur der BindingSource-Komponente
ms.date: 03/30/2017
helpviewer_keywords:
- BindingSource component [Windows Forms], architecture
- Windows Forms, data binding
- BindingSource component [Windows Forms], about BindingSource component
- data binding [Windows Forms], BindingSource component
ms.assetid: 7bc69c90-8a11-48b1-9336-3adab5b41591
ms.openlocfilehash: b0334bd7a0bc5ff46c43fd7ee549422d98c35efe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529259"
---
# <a name="bindingsource-component-architecture"></a>Architektur der BindingSource-Komponente
Mit der <xref:System.Windows.Forms.BindingSource> Komponente, können Sie alle Windows Forms-Steuerelemente universell an Datenquellen binden.  
  
 Die <xref:System.Windows.Forms.BindingSource> Komponente vereinfacht das Binden von Steuerelementen an eine Datenquelle und bietet die folgenden Vorteile gegenüber der herkömmlichen Datenbindung:  
  
-   Eine Entwurfszeit-Bindung an Geschäftsobjekte ermöglicht.  
  
-   Kapselt <xref:System.Windows.Forms.CurrencyManager> Funktionalität und macht <xref:System.Windows.Forms.CurrencyManager> Ereignisse zur Entwurfszeit.  
  
-   Vereinfacht die Erstellung einer Liste, die unterstützt die <xref:System.ComponentModel.IBindingList> Schnittstelle durch die Bereitstellung von Liste änderungsbenachrichtigung für Datenquellen, die Liste keine systemeigene Unterstützung änderungsbenachrichtigungen.  
  
-   Bietet einen Erweiterungspunkt für die <xref:System.ComponentModel.IBindingList.AddNew%2A?displayProperty=nameWithType> Methode.  
  
-   Bietet eine Dereferenzierungsebene zwischen Datenquelle und das Steuerelement an. Dieser Umweg ist wichtig, wenn die Datenquelle zur Laufzeit ändern kann.  
  
-   Interagiert mit anderen datenbezogenen Windows Forms-Steuerelemente, insbesondere die <xref:System.Windows.Forms.BindingNavigator> und <xref:System.Windows.Forms.DataGridView> Steuerelemente.  
  
 Aus diesen Gründen die <xref:System.Windows.Forms.BindingSource> Komponente ist die bevorzugte Methode zum Binden von Windows Forms-Steuerelemente an Datenquellen.  
  
## <a name="bindingsource-features"></a>BindingSource-Funktionen  
 Die <xref:System.Windows.Forms.BindingSource> Komponente bietet verschiedene Funktionen für das Binden von Steuerelementen an Daten. Mit diesen Features können Sie die meisten Datenbindungsszenarien mit fast keine Codierung ihrerseits implementieren.  
  
 Die <xref:System.Windows.Forms.BindingSource> Komponente erreicht dies durch eine konsistente Schnittstelle für den Zugriff auf viele verschiedene Arten von Datenquellen bereit. Dies bedeutet, dass Sie dasselbe Verfahren für die Bindung an einen beliebigen Typ verwenden. Sie können z. B. Anfügen der <xref:System.Windows.Forms.BindingSource.DataSource%2A> Eigenschaft, um eine <xref:System.Data.DataSet> oder ein Geschäftsobjekt und in beiden Fällen verwenden Sie den gleichen Satz von Eigenschaften, Methoden und Ereignisse zum Bearbeiten der Datenquelle.  
  
 Die konsistente Schnittstelle bereitgestellt, die durch die <xref:System.Windows.Forms.BindingSource> Komponente erheblich vereinfacht das Binden von Daten an Steuerelemente. Für Datenquellen-Typen, die bereitstellen änderungsbenachrichtigungen der <xref:System.Windows.Forms.BindingSource> Komponente kommuniziert automatisch Änderungen zwischen dem Steuerelement und der Datenquelle. Für Datenquellen-Typen, die keine änderungsbenachrichtigung bereitstellen, werden Ereignisse bereitgestellt, mit denen Sie die Benachrichtigungen auslösen können. Die folgende Liste enthält die unterstützten Funktionen der <xref:System.Windows.Forms.BindingSource> Komponente:  
  
-   Möglichkeit zur Dereferenzierung.  
  
-   Currency-Verwaltung.  
  
-   Die Datenquelle als Liste.  
  
-   <xref:System.Windows.Forms.BindingSource> als ein <xref:System.ComponentModel.IBindingList>.  
  
-   Benutzerdefinierte Elementvorlagen erstellen.  
  
-   Transaktionale Element erstellen.  
  
-   <xref:System.Collections.IEnumerable> unterstützt.  
  
-   Zur Entwurfszeit Unterstützung.  
  
-   Statische <xref:System.Windows.Forms.ListBindingHelper> Methoden.  
  
-   Sortieren und Filtern mit der <xref:System.ComponentModel.IBindingListView> Schnittstelle.  
  
-   Integration mit <xref:System.Windows.Forms.BindingNavigator>.  
  
### <a name="indirection"></a>Dereferenzierung  
 Die <xref:System.Windows.Forms.BindingSource> Komponente bereitstellen eine Dereferenzierungsebene zwischen einem Steuerelement und einer Datenquelle. Anstelle ein Steuerelements direkt an eine Datenquelle binden, binden Sie das Steuerelement eine <xref:System.Windows.Forms.BindingSource>, und fügen Sie die Datenquelle, die <xref:System.Windows.Forms.BindingSource> Komponente <xref:System.Windows.Forms.BindingSource.DataSource%2A> Eigenschaft.  
  
 Dieses Maß an Dereferenzierung können Sie die Datenquelle ändern, ohne die steuerelementbindung zurückzusetzen. Dies bietet Ihnen die folgenden Funktionen:  
  
-   Sie können Anfügen der <xref:System.Windows.Forms.BindingSource> mit verschiedenen Datenquellen und das aktuelle Steuerelement Bindungen beibehalten.  
  
-   Sie können Elemente in der Datenquelle ändern und gebundene Steuerelemente zu benachrichtigen. Weitere Informationen finden Sie unter [Vorgehensweise: widerspiegeln von Datenquellenaktualisierungen in einem Windows Forms-Steuerelement mit der BindingSource-Komponente](../../../../docs/framework/winforms/controls/reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md).  
  
-   Sie können zum Binden einer <xref:System.Type> anstelle eines Objekts im Arbeitsspeicher. Weitere Informationen finden Sie unter [Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md). Sie können dann auf ein Objekt zur Laufzeit binden.  
  
### <a name="currency-management"></a>Währungsverwaltung  
 Die <xref:System.Windows.Forms.BindingSource> -Komponente implementiert die <xref:System.Windows.Forms.ICurrencyManagerProvider> Schnittstelle währungsverwaltung für Sie zu behandeln. Mit der <xref:System.Windows.Forms.ICurrencyManagerProvider> -Schnittstelle, Sie können auch Zugriff auf die Currency-Manager für eine <xref:System.Windows.Forms.BindingSource>, zusätzlich zu den Currency-Manager für eine andere <xref:System.Windows.Forms.BindingSource> gebunden, die auf den gleichen <xref:System.Windows.Forms.BindingSource.DataMember%2A>.  
  
 Die <xref:System.Windows.Forms.BindingSource> Komponente kapselt <xref:System.Windows.Forms.CurrencyManager> Funktionalität und macht die am häufigsten verwendeten <xref:System.Windows.Forms.CurrencyManager> Eigenschaften und Ereignisse. In der folgenden Tabelle werden einige der Elemente im Zusammenhang mit währungsverwaltung beschrieben.  
  
 <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A>-Eigenschaft  
 Ruft den zugeordneten Currency-Manager die <xref:System.Windows.Forms.BindingSource>.  
  
 <xref:System.Windows.Forms.ICurrencyManagerProvider.GetRelatedCurrencyManager%2A>-Methode  
 Wenn derzeit ein anderer wird <xref:System.Windows.Forms.BindingSource> an den angegebenen Datenmember gebunden ist, ruft seine Currency Manager ab.  
  
 <xref:System.Windows.Forms.BindingSource.Current%2A>-Eigenschaft  
 Ruft das aktuelle Element der Datenquelle ab.  
  
 <xref:System.Windows.Forms.BindingSource.Position%2A>-Eigenschaft  
 Ruft die aktuelle Position in der zugrunde liegenden Liste ab oder legt diese fest.  
  
 <xref:System.Windows.Forms.BindingSource.EndEdit%2A>-Methode  
 Wendet anstehende Änderungen auf die zugrunde liegende Datenquelle an.  
  
 <xref:System.Windows.Forms.BindingSource.CancelEdit%2A>-Methode  
 Bricht den aktuellen Bearbeitungsvorgang ab.  
  
### <a name="data-source-as-a-list"></a>Die Datenquelle als Liste  
 Die <xref:System.Windows.Forms.BindingSource> -Komponente implementiert die <xref:System.ComponentModel.IBindingListView> und <xref:System.ComponentModel.ITypedList> Schnittstellen. Mit dieser Implementierung können Sie mithilfe der <xref:System.Windows.Forms.BindingSource> Komponente selbst als Datenquelle, ohne einen externen Speicher.  
  
 Wenn die <xref:System.Windows.Forms.BindingSource> Komponente mit einer Datenquelle verbunden ist, macht die Datenquelle als Liste.  
  
 Die <xref:System.Windows.Forms.BindingSource.DataSource%2A> Eigenschaft kann auf mehrere Datenquellen festgelegt werden. Dazu gehören Typen, Objekte und Listen von Typen. Die resultierende Datenquelle wird als Liste verfügbar gemacht werden. Die folgende Tabelle zeigt einige der allgemeinen Datenquellen und die resultierende Liste Auswertung.  
  
|DataSource-Eigenschaft|Listenergebnissen|  
|-------------------------|------------------|  
|Ein NULL-Verweis (`Nothing` in Visual Basic).|Ein leeres <xref:System.ComponentModel.IBindingList> von Objekten. Hinzufügen eines Elements wird die Liste in den Typ des hinzugefügten Elements.|  
|Ein null-Verweis (`Nothing` in Visual Basic) mit <xref:System.Windows.Forms.BindingSource.DataMember%2A> festlegen|Nicht unterstützt. löst <xref:System.ArgumentException>.|  
|Nicht-Listentyp oder Objekt vom Typ "T"|Ein leeres <xref:System.ComponentModel.IBindingList> vom Typ "T".|  
|Array-Instanz|Ein <xref:System.ComponentModel.IBindingList> , enthält die Elemente des Arrays.|  
|<xref:System.Collections.IEnumerable> Instanz|Ein <xref:System.ComponentModel.IBindingList> , enthält die <xref:System.Collections.IEnumerable> Elemente|  
|Liste der Instanz, die mit Typ "T"|Ein <xref:System.ComponentModel.IBindingList> Instanz, die Typ "T" enthält.|  
  
 Darüber hinaus <xref:System.Windows.Forms.BindingSource.DataSource%2A> kann auf andere Listentypen festgelegt werden, z. B. <xref:System.ComponentModel.IListSource> und <xref:System.ComponentModel.ITypedList>, und die <xref:System.Windows.Forms.BindingSource> entsprechend behandelt wird. In diesem Fall sollte der Typ, der in der Liste enthalten ist einen Standardkonstruktor verfügen.  
  
### <a name="bindingsource-as-an-ibindinglist"></a>BindingSource-Komponente als IBindingList  
 Die <xref:System.Windows.Forms.BindingSource> Komponente bereitgestellt werden Member zum Zugreifen auf und Bearbeiten der zugrunde liegenden Daten als ein <xref:System.ComponentModel.IBindingList>. In der folgenden Tabelle werden einige dieser Member beschrieben.  
  
|Member|Beschreibung|  
|------------|-----------------|  
|<xref:System.Windows.Forms.BindingSource.List%2A>-Eigenschaft|Ruft die Liste ab, die aus der Auswertung ergibt die <xref:System.Windows.Forms.BindingSource.DataSource%2A> oder <xref:System.Windows.Forms.BindingSource.DataMember%2A> Eigenschaften.|  
|<xref:System.Windows.Forms.BindingSource.AddNew%2A>-Methode|Fügt der zugrunde liegenden Liste ein neues Element hinzu. Gilt für Datenquellen, implementieren die <xref:System.ComponentModel.IBindingList> Schnittstelle und Hinzufügen von Elementen ermöglichen (d. h. die <xref:System.Windows.Forms.BindingSource.AllowNew%2A> -Eigenschaftensatz auf `true`).|  
  
### <a name="custom-item-creation"></a>Benutzerdefiniertes Element erstellen  
 Sie können behandeln die <xref:System.Windows.Forms.BindingSource.AddingNew> Ereignis, um Ihre eigene Logik zum Erstellen von Element bereitzustellen. Die <xref:System.Windows.Forms.BindingSource.AddingNew> Ereignis tritt auf, bevor ein neues Objekt hinzugefügt wird die <xref:System.Windows.Forms.BindingSource>. Dieses Ereignis wird ausgelöst, nachdem die <xref:System.Windows.Forms.BindingSource.AddNew%2A> Methode wird aufgerufen, aber bevor der zugrunde liegenden Liste das neue Element hinzugefügt wird. Sie können benutzerdefinierte Elementvorlagen Erstellungsverhalten durch die Behandlung dieses Ereignisses, bereitstellen, ohne eine Ableitung von der <xref:System.Windows.Forms.BindingSource> Klasse. Weitere Informationen finden Sie unter [wie: Anpassen der Hinzufügung mit der BindingSource in Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-item-addition-with-the-windows-forms-bindingsource.md).  
  
### <a name="transactional-item-creation"></a>Transaktionale Element erstellen  
 Die <xref:System.Windows.Forms.BindingSource> -Komponente implementiert die <xref:System.ComponentModel.ICancelAddNew> -Schnittstelle, die transaktionale Element erstellen kann. Nachdem ein neues Element vorläufig erstellt wurde, mithilfe eines Aufrufs an <xref:System.Windows.Forms.BindingSource.AddNew%2A>, die Addition kann ein Commit oder Rollback auf folgende Weise:  
  
-   Die <xref:System.ComponentModel.ICancelAddNew.EndNew%2A> Methode führt explizit ein commit für die ausstehende Hinzufügung.  
  
-   Ausführen einer anderen Auflistung-Vorgangs, z. B. eine Einfügung, entfernen oder verschieben, führt die ausstehende Hinzufügung implizit commit aus.  
  
-   Die <xref:System.ComponentModel.ICancelAddNew.CancelNew%2A> Methode Rollback ausstehende hinzufügen, wenn die Methode noch kein Commit ausgeführt wurde.  
  
### <a name="ienumerable-support"></a>IEnumerable-Unterstützung  
 Die <xref:System.Windows.Forms.BindingSource> -Komponente ermöglicht das Binden von Steuerelementen an <xref:System.Collections.IEnumerable> Datenquellen. Mit dieser Komponente Sie können Binden an eine Datenquelle wie z. B. eine <xref:System.Data.SqlClient.SqlDataReader?displayProperty=nameWithType>.  
  
 Wenn ein <xref:System.Collections.IEnumerable> Datenquelle zugewiesen ist die <xref:System.Windows.Forms.BindingSource> Komponente, die <xref:System.Windows.Forms.BindingSource> erstellt ein <xref:System.ComponentModel.IBindingList> und fügt die Inhalte der der <xref:System.Collections.IEnumerable> -Datenquelle, um die Liste.  
  
### <a name="design-time-support"></a>Unterstützung während der Entwurfszeit  
 Einige Objekttypen können zur Entwurfszeit, z. B. Objekte, die aus einer Factoryklasse erstellt oder von einem Webdienst zurückgegebenen Objekte erstellt werden. In einigen Fällen möglicherweise die Steuerelemente auf diese Typen zur Entwurfszeit zu binden, obwohl es wurde kein Objekt im Arbeitsspeicher, die an die die Steuerelemente gebunden werden können. Z. B. möglicherweise die Spaltenüberschriften der Beschriftung einer <xref:System.Windows.Forms.DataGridView> Steuerelement mit den Namen der öffentlichen Eigenschaften des benutzerdefinierten Typs.  
  
 Zur Unterstützung dieses Szenarios die <xref:System.Windows.Forms.BindingSource> Komponente unterstützt die Bindung an eine <xref:System.Type>. Wenn Sie Zuweisen einer <xref:System.Type> auf die <xref:System.Windows.Forms.BindingSource.DataSource%2A> -Eigenschaft, die <xref:System.Windows.Forms.BindingSource> Komponente erstellt ein leeres <xref:System.ComponentModel.BindingList%601> von <xref:System.Type> Elemente. Alle Steuerelemente, die Sie anschließend zum Binden der <xref:System.Windows.Forms.BindingSource> Komponente benachrichtigt wird das Vorhandensein der Eigenschaften oder dem Schema des Typs zur Entwurfszeit oder zur Laufzeit. Weitere Informationen finden Sie unter [Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md).  
  
### <a name="static-listbindinghelper-methods"></a>Statische ListBindingHelper-Methoden  
 Die <xref:System.Windows.Forms.BindingContext?displayProperty=nameWithType>, <xref:System.Windows.Forms.CurrencyManager?displayProperty=nameWithType>, und <xref:System.Windows.Forms.BindingSource> alle Freigabe gemeinsame Logik zum Generieren einer Liste von Typen ein `DataSource` / `DataMember` Paar. Darüber hinaus diese gemeinsame Logik ist öffentlich verfügbar gemacht für die Verwendung von Autoren von Steuerelementen und andere dritte in den folgenden `static` Methoden:  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListItemProperties%2A>  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetList%2A>  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListName%2A>  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListItemType%2A>  
  
### <a name="sorting-and-filtering-with-the-ibindinglistview-interface"></a>Sortieren und Filtern mit der IBindingListView-Schnittstelle  
 Die <xref:System.Windows.Forms.BindingSource> -Komponente implementiert die <xref:System.ComponentModel.IBindingListView> -Schnittstelle, die durch Erweiterung der <xref:System.ComponentModel.IBindingList> Schnittstelle. Die <xref:System.ComponentModel.IBindingList> bietet einzelne Spalte zu sortieren und die <xref:System.ComponentModel.IBindingListView> bietet erweiterte sortieren und filtern. Mit <xref:System.ComponentModel.IBindingListView>, Sortieren und Filtern von Elementen in der Datenquelle, wenn die Datenquelle auch eine dieser Schnittstellen implementiert. Die <xref:System.Windows.Forms.BindingSource> Komponente bietet eine referenzimplementierung diesen Member keine. Stattdessen werden die Aufrufe an die zugrunde liegende Liste weitergeleitet.  
  
 Die folgende Tabelle beschreibt die Eigenschaften, die Sie zum Sortieren und Filtern verwenden.  
  
|Member|Beschreibung|  
|------------|-----------------|  
|<xref:System.Windows.Forms.BindingSource.Filter%2A>-Eigenschaft|Wenn die Datenquelle eine <xref:System.ComponentModel.IBindingListView> ist, wird der Ausdruck abgerufen, der zum Filtern der anzuzeigenden Zeilen verwendet wird, oder dieser Ausdruck wird festgelegt.|  
|<xref:System.Windows.Forms.BindingSource.Sort%2A>-Eigenschaft|Wenn die Datenquelle eine <xref:System.ComponentModel.IBindingList> ist, wird ein Spaltenname abgerufen oder festgelegt, der für das Sortieren und für Informationen zur Sortierreihenfolge verwendet wird.<br /><br /> - oder - <br /><br /> Wenn die Datenquelle ist ein <xref:System.ComponentModel.IBindingListView> und erweiterte Sortierung unterstützt, werden mehrere Spaltennamen, die für die Sortierung und Sortierreihenfolge verwendete abgerufen|  
  
### <a name="integration-with-bindingnavigator"></a>Integration mit BindingNavigator  
 Können Sie die <xref:System.Windows.Forms.BindingSource> -Komponente zum Binden von Windows Forms-Steuerelement mit einer Datenquelle, aber die <xref:System.Windows.Forms.BindingNavigator> Steuerelement ist speziell dazu konzipiert, mit der <xref:System.Windows.Forms.BindingSource> Komponente. Die <xref:System.Windows.Forms.BindingNavigator> Steuerelement bietet eine Benutzeroberfläche zum Steuern der <xref:System.Windows.Forms.BindingSource> Komponente des aktuellen Elements. Wird standardmäßig die <xref:System.Windows.Forms.BindingNavigator> Steuerelement enthält Schaltflächen, die die Navigationsmethoden für entsprechen den <xref:System.Windows.Forms.BindingSource> Komponente. Weitere Informationen finden Sie unter [wie: Navigieren Sie Daten mit BindingNavigator-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-navigate-data-with-the-windows-forms-bindingnavigator-control.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.BindingNavigator>  
 [Übersicht über die BindingSource-Komponente](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)  
 [BindingNavigator-Steuerelement](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)  
 [Windows Forms-Datenbindung](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)  
 [Vorgehensweise: Kennzeichnen von Datenquellenaktualisierungen in einem Windows Forms-Steuerelement mithilfe der BindingSource](../../../../docs/framework/winforms/controls/reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)
