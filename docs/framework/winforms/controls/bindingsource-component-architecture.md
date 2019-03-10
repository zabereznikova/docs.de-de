---
title: Architektur der BindingSource-Komponente
ms.date: 03/30/2017
helpviewer_keywords:
- BindingSource component [Windows Forms], architecture
- Windows Forms, data binding
- BindingSource component [Windows Forms], about BindingSource component
- data binding [Windows Forms], BindingSource component
ms.assetid: 7bc69c90-8a11-48b1-9336-3adab5b41591
ms.openlocfilehash: 9348d44697b2c617481b55242faa83ab517e6226
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707819"
---
# <a name="bindingsource-component-architecture"></a>Architektur der BindingSource-Komponente
Mit der <xref:System.Windows.Forms.BindingSource> Komponente ist, können Sie generell alle Windows Forms-Steuerelemente an Datenquellen binden.  
  
 Die <xref:System.Windows.Forms.BindingSource> Komponente vereinfacht das Binden von Steuerelementen an eine Datenquelle, und bietet die folgenden Vorteile gegenüber herkömmlichen Datenbindung:  
  
-   Ermöglicht die Entwurfszeit-Bindung an Geschäftsobjekte.  
  
-   Kapselt <xref:System.Windows.Forms.CurrencyManager> Funktionalität und macht <xref:System.Windows.Forms.CurrencyManager> Ereignisse zur Entwurfszeit.  
  
-   Vereinfacht das Erstellen einer Liste, die unterstützt die <xref:System.ComponentModel.IBindingList> -Schnittstelle durch die Bereitstellung von änderungsbenachrichtigungen für die Liste für änderungsbenachrichtigungen für Datenquellen, die Liste nicht nativ unterstützen.  
  
-   Stellt einen Erweiterungspunkt für die <xref:System.ComponentModel.IBindingList.AddNew%2A?displayProperty=nameWithType> Methode.  
  
-   Bietet eine Dereferenzierungsebene zwischen der Datenquelle und das Steuerelement an. Diese Dereferenzierung ist wichtig, bei die Datenquelle zur Laufzeit ändern kann.  
  
-   Interagiert mit anderen datenbezogenen Windows Forms-Steuerelementen, insbesondere die <xref:System.Windows.Forms.BindingNavigator> und <xref:System.Windows.Forms.DataGridView> Steuerelemente.  
  
 Aus diesen Gründen den <xref:System.Windows.Forms.BindingSource> Komponente ist die bevorzugte Methode für die Windows Forms-Steuerelemente an Datenquellen binden.  
  
## <a name="bindingsource-features"></a>BindingSource-Funktionen  
 Die <xref:System.Windows.Forms.BindingSource> Komponente bietet verschiedene Funktionen zum Binden von Steuerelementen an Daten. Mit diesen Features können Sie die meisten Datenbindungsszenarien fast ohne Codierung ihrerseits implementieren.  
  
 Die <xref:System.Windows.Forms.BindingSource> Komponente erreicht dies durch die Bereitstellung einer einheitliche Schnittstelle für den Zugriff auf viele verschiedene Arten von Datenquellen. Dies bedeutet, dass Sie das gleiche Verfahren für die Bindung an einen beliebigen Typ verwenden. Sie können z. B. Anfügen der <xref:System.Windows.Forms.BindingSource.DataSource%2A> Eigenschaft, um eine <xref:System.Data.DataSet> oder ein Geschäftsobjekt und in beiden Fällen können Sie den gleichen Satz von Eigenschaften, Methoden und Ereignisse um die Datenquelle zu bearbeiten.  
  
 Die konsistente Schnittstelle bereitgestellt werden, indem die <xref:System.Windows.Forms.BindingSource> Komponente deutlich vereinfacht das Binden von Daten an Steuerelemente. Für Datenquellen-Typen, die änderungsbenachrichtigungen, die <xref:System.Windows.Forms.BindingSource> Komponente kommuniziert automatisch Änderungen zwischen dem Steuerelement und die Datenquelle. Für Datenquellen-Typen, die keine änderungsbenachrichtigungen bereitstellen, sind die Ereignisse bereitgestellt, mit denen Sie die Benachrichtigungen auslösen können. Die folgende Liste enthält die Funktionen, die von unterstützt die <xref:System.Windows.Forms.BindingSource> Komponente:  
  
-   Dereferenzierung.  
  
-   Currency-Verwaltung.  
  
-   Die Datenquelle als Liste.  
  
-   <xref:System.Windows.Forms.BindingSource> als ein <xref:System.ComponentModel.IBindingList>.  
  
-   Benutzerdefinierte Erstellung.  
  
-   Transaktionale elementerstellung.  
  
-   <xref:System.Collections.IEnumerable> unterstützt.  
  
-   Während der Entwurfszeit-Unterstützung.  
  
-   Statische <xref:System.Windows.Forms.ListBindingHelper> Methoden.  
  
-   Sortieren und Filtern mit der <xref:System.ComponentModel.IBindingListView> Schnittstelle.  
  
-   Integration mit <xref:System.Windows.Forms.BindingNavigator>.  
  
### <a name="indirection"></a>Dereferenzierung  
 Die <xref:System.Windows.Forms.BindingSource> Komponente stellt eine Dereferenzierungsebene zwischen einer Datenquelle und eines Steuerelements bereit. Anstelle ein Steuerelements direkt an eine Datenquelle binden, binden Sie das Steuerelement, das eine <xref:System.Windows.Forms.BindingSource>, und fügen Sie die Datenquelle, die <xref:System.Windows.Forms.BindingSource> Komponente <xref:System.Windows.Forms.BindingSource.DataSource%2A> Eigenschaft.  
  
 Mit diesem Maß an Dereferenzierung können Sie die Datenquelle ändern, ohne ein Zurücksetzen der steuerelementbindung. Dies bietet Ihnen die folgenden Funktionen:  
  
-   Sie können Anfügen der <xref:System.Windows.Forms.BindingSource> mit verschiedenen Datenquellen und behalten Sie die aktuellen Steuerelement-Bindungen.  
  
-   Sie können ändern, Elemente in der Datenquelle und gebundene Steuerelementen zu benachrichtigen. Weitere Informationen finden Sie unter [Vorgehensweise: Datenquellenaktualisierungen in einem Windows Forms-Steuerelement mit der BindingSource-Komponente](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md).  
  
-   Sie können zum Binden einer <xref:System.Type> anstelle eines Objekts im Arbeitsspeicher. Weitere Informationen finden Sie unter [Vorgehensweise: Binden ein Windows Forms-Steuerelements an einen Typ](how-to-bind-a-windows-forms-control-to-a-type.md). Sie können dann zur Laufzeit auf ein Objekt binden.  
  
### <a name="currency-management"></a>Currency-Verwaltung  
 Die <xref:System.Windows.Forms.BindingSource> Komponente implementiert die <xref:System.Windows.Forms.ICurrencyManagerProvider> Schnittstelle, währungsverwaltung für Sie zu behandeln. Mit der <xref:System.Windows.Forms.ICurrencyManagerProvider> -Schnittstelle, Sie können auch Zugriff auf den währungs-Manager für eine <xref:System.Windows.Forms.BindingSource>, zusätzlich zu den währungs-Manager für eine andere <xref:System.Windows.Forms.BindingSource> gebunden, auf die gleiche <xref:System.Windows.Forms.BindingSource.DataMember%2A>.  
  
 Die <xref:System.Windows.Forms.BindingSource> Komponente kapselt <xref:System.Windows.Forms.CurrencyManager> Funktionen und stellt die am häufigsten verwendeten <xref:System.Windows.Forms.CurrencyManager> Eigenschaften und Ereignisse. In der folgende Tabelle werden einige der Elemente im Zusammenhang mit währungsverwaltung beschrieben.  
  
 <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A> -Eigenschaft  
 Ruft die datensatzzeigerverwaltung ab zugeordneten der <xref:System.Windows.Forms.BindingSource>.  
  
 <xref:System.Windows.Forms.ICurrencyManagerProvider.GetRelatedCurrencyManager%2A>-Methode  
 Wenn andere <xref:System.Windows.Forms.BindingSource> an den angegebenen Datenmember gebundenen, ruft die datensatzzeigerverwaltung ab.  
  
 <xref:System.Windows.Forms.BindingSource.Current%2A> -Eigenschaft  
 Ruft das aktuelle Element der Datenquelle ab.  
  
 <xref:System.Windows.Forms.BindingSource.Position%2A>-Eigenschaft  
 Ruft die aktuelle Position in der zugrunde liegenden Liste ab oder legt diese fest.  
  
 <xref:System.Windows.Forms.BindingSource.EndEdit%2A>-Methode  
 Wendet anstehende Änderungen auf die zugrunde liegende Datenquelle an.  
  
 <xref:System.Windows.Forms.BindingSource.CancelEdit%2A>-Methode  
 Bricht den aktuellen Bearbeitungsvorgang ab.  
  
### <a name="data-source-as-a-list"></a>Die Datenquelle als eine Liste  
 Die <xref:System.Windows.Forms.BindingSource> Komponente implementiert die <xref:System.ComponentModel.IBindingListView> und <xref:System.ComponentModel.ITypedList> Schnittstellen. Mit dieser Implementierung können Sie mithilfe der <xref:System.Windows.Forms.BindingSource> Komponente selbst als Datenquelle, ohne einen externen Speicher.  
  
 Wenn die <xref:System.Windows.Forms.BindingSource> Komponente mit einer Datenquelle verbunden ist, macht die Datenquelle als eine Liste.  
  
 Die <xref:System.Windows.Forms.BindingSource.DataSource%2A> Eigenschaft kann auf mehrere Datenquellen festgelegt werden. Dazu gehören Typen, Objekte und Listen von Typen. Die resultierende Datenquelle wird als Liste verfügbar gemacht werden. Die folgende Tabelle zeigt einige allgemeine Datenquellen und die resultierende Liste Auswertung.  
  
|DataSource-Eigenschaft|Listenergebnisse|  
|-------------------------|------------------|  
|Ein NULL-Verweis (`Nothing` in Visual Basic).|Ein leeres <xref:System.ComponentModel.IBindingList> von Objekten. Hinzufügen eines Elements wird die Liste in den Typ des hinzugefügten Elements.|  
|Ein null-Verweis (`Nothing` in Visual Basic) mit <xref:System.Windows.Forms.BindingSource.DataMember%2A> festlegen|Nicht unterstützt. löst <xref:System.ArgumentException>.|  
|Nicht-List-Typ oder ein Objekt vom Typ "T"|Ein leeres <xref:System.ComponentModel.IBindingList> vom Typ "T".|  
|Array-Instanz|Ein <xref:System.ComponentModel.IBindingList> , die die Elemente des Arrays enthält.|  
|<xref:System.Collections.IEnumerable> Instanz|Ein <xref:System.ComponentModel.IBindingList> , enthält die <xref:System.Collections.IEnumerable> Elemente|  
|Liste der Instanz, die mit Typ "T"|Ein <xref:System.ComponentModel.IBindingList> Instanz, die Typ "T" enthält.|  
  
 Darüber hinaus <xref:System.Windows.Forms.BindingSource.DataSource%2A> kann in andere Listentypen festgelegt werden, z. B. <xref:System.ComponentModel.IListSource> und <xref:System.ComponentModel.ITypedList>, und die <xref:System.Windows.Forms.BindingSource> entsprechend behandelt. In diesem Fall sollte der Typ, der in der Liste enthalten ist, einen Standardkonstruktor verfügen.  
  
### <a name="bindingsource-as-an-ibindinglist"></a>BindingSource als IBindingList  
 Die <xref:System.Windows.Forms.BindingSource> Komponente stellt Member bereit, zum Zugreifen auf und Bearbeiten der zugrunde liegenden Daten als ein <xref:System.ComponentModel.IBindingList>. In der folgende Tabelle werden einige dieser Member beschrieben.  
  
|Member|Beschreibung|  
|------------|-----------------|  
|<xref:System.Windows.Forms.BindingSource.List%2A> -Eigenschaft|Ruft die Liste ab, die von der Auswertung ergibt die <xref:System.Windows.Forms.BindingSource.DataSource%2A> oder <xref:System.Windows.Forms.BindingSource.DataMember%2A> Eigenschaften.|  
|<xref:System.Windows.Forms.BindingSource.AddNew%2A>-Methode|Fügt der zugrunde liegenden Liste ein neues Element hinzu. Gilt für Datenquellen, implementieren die <xref:System.ComponentModel.IBindingList> Schnittstelle und Hinzufügen von Elementen ermöglichen (d. h. die <xref:System.Windows.Forms.BindingSource.AllowNew%2A> -Eigenschaftensatz auf `true`).|  
  
### <a name="custom-item-creation"></a>Benutzerdefinierte Erstellung  
 Sie können behandeln die <xref:System.Windows.Forms.BindingSource.AddingNew> Ereignis, um Ihre eigene Logik zum-Erstellung bereitzustellen. Die <xref:System.Windows.Forms.BindingSource.AddingNew> Ereignis tritt auf, bevor ein neues Objekt hinzugefügt wird die <xref:System.Windows.Forms.BindingSource>. Dieses Ereignis wird ausgelöst, nachdem die <xref:System.Windows.Forms.BindingSource.AddNew%2A> Methode wird aufgerufen, aber bevor der zugrunde liegenden Liste das neue Element hinzugefügt wird. Dieses Ereignis wird behandelt, können Sie benutzerdefinierte Elementerstellungsverhalten bereitstellen, ohne eine Ableitung von der <xref:System.Windows.Forms.BindingSource> Klasse. Weitere Informationen finden Sie unter [Vorgehensweise: Anpassen der Hinzufügung mithilfe der BindingSource von Windows Forms](how-to-customize-item-addition-with-the-windows-forms-bindingsource.md).  
  
### <a name="transactional-item-creation"></a>Transaktionale Erstellung  
 Die <xref:System.Windows.Forms.BindingSource> Komponente implementiert die <xref:System.ComponentModel.ICancelAddNew> -Schnittstelle, die transaktionale Erstellung aktiviert. Nachdem ein neues Element vorläufig erstellt wird, indem Sie über einen Aufruf an <xref:System.Windows.Forms.BindingSource.AddNew%2A>, zusätzlich kann ein Commit oder Rollback auf folgende Weise:  
  
-   Die <xref:System.ComponentModel.ICancelAddNew.EndNew%2A> -Methode wird explizit einen commit für die ausstehende Hinzufügung.  
  
-   Einen anderen Vorgang Auflistung, z. B. eine Einfügung, Entfernung oder verschieben, wird implizit die ausstehende Hinzufügung commit.  
  
-   Die <xref:System.ComponentModel.ICancelAddNew.CancelNew%2A> Methode Rollback ausstehende hinzufügen, wenn die Methode noch kein Commit ausgeführt wurde.  
  
### <a name="ienumerable-support"></a>IEnumerable-Unterstützung  
 Die <xref:System.Windows.Forms.BindingSource> ermöglicht Binden von Steuerelementen an <xref:System.Collections.IEnumerable> -Datenquellen. Mit dieser Komponente können Sie an Binden einer Datenquelle wie z. B. eine <xref:System.Data.SqlClient.SqlDataReader?displayProperty=nameWithType>.  
  
 Bei der ein <xref:System.Collections.IEnumerable> Datenquelle zugewiesen ist die <xref:System.Windows.Forms.BindingSource> -Komponente, die <xref:System.Windows.Forms.BindingSource> erstellt eine <xref:System.ComponentModel.IBindingList> und fügt den Inhalt der der <xref:System.Collections.IEnumerable> -Datenquelle, um die Liste.  
  
### <a name="design-time-support"></a>Entwurfszeitunterstützung  
 Einige Objekttypen können nicht zur Entwurfszeit, z. B. Objekte, die von einer Formularbereichsfactory-Klasse erstellt oder von einem Webdienst zurückgegebenen Objekte erstellt werden. In einigen Fällen möglicherweise, die Steuerelemente zur Entwurfszeit auf diese Typen zu binden, obwohl kein Objekt vorhanden ist, im Arbeitsspeicher, der Ihre Steuerelemente gebunden werden können. Müssen möglicherweise, z. B. die Spaltenüberschriften der Bezeichnung eine <xref:System.Windows.Forms.DataGridView> Steuerelement mit den Namen der öffentlichen Eigenschaften des benutzerdefinierten Typs.  
  
 Zur Unterstützung dieses Szenarios die <xref:System.Windows.Forms.BindingSource> Komponente unterstützt die Bindung an eine <xref:System.Type>. Wenn Sie zuweisen eine <xref:System.Type> auf die <xref:System.Windows.Forms.BindingSource.DataSource%2A> -Eigenschaft, die <xref:System.Windows.Forms.BindingSource> Komponente erstellt ein leeres <xref:System.ComponentModel.BindingList%601> von <xref:System.Type> Elemente. Alle Steuerelemente, die Sie sich anschließend an die <xref:System.Windows.Forms.BindingSource> Komponente werden Warnungen ausgegeben, um das Vorhandensein der Eigenschaften oder im Schema des Typs zur Entwurfszeit oder zur Laufzeit. Weitere Informationen finden Sie unter [Vorgehensweise: Binden ein Windows Forms-Steuerelements an einen Typ](how-to-bind-a-windows-forms-control-to-a-type.md).  
  
### <a name="static-listbindinghelper-methods"></a>Statische ListBindingHelper-Methoden  
 Die <xref:System.Windows.Forms.BindingContext?displayProperty=nameWithType>, <xref:System.Windows.Forms.CurrencyManager?displayProperty=nameWithType>, und <xref:System.Windows.Forms.BindingSource> alle Freigabe gemeinsame Logik zum Generieren einer Liste von Typen eine `DataSource` / `DataMember` Paar. Darüber hinaus diese gemeinsame Logik ist öffentlich verfügbar gemacht werden für die Verwendung von Autoren von Steuerelementen und anderen Drittanbietern in der folgenden `static` Methoden:  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListItemProperties%2A>  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetList%2A>.  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListName%2A>  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListItemType%2A>  
  
### <a name="sorting-and-filtering-with-the-ibindinglistview-interface"></a>Sortieren und Filtern mit der IBindingListView-Schnittstelle  
 Die <xref:System.Windows.Forms.BindingSource> Komponente implementiert die <xref:System.ComponentModel.IBindingListView> -Schnittstelle, die erweitert die <xref:System.ComponentModel.IBindingList> Schnittstelle. Die <xref:System.ComponentModel.IBindingList> bietet einer Spalte sortiert und die <xref:System.ComponentModel.IBindingListView> bietet erweiterte, Sortieren und filtern. Mit <xref:System.ComponentModel.IBindingListView>, können Sie sortieren und Filtern von Elementen in der Datenquelle, wenn die Datenquelle auch implementiert eine dieser Schnittstellen. Die <xref:System.Windows.Forms.BindingSource> Komponente bietet eine referenzimplementierung dieser Member nicht. Stattdessen werden die Aufrufe an die zugrunde liegende Liste weitergeleitet.  
  
 Die folgende Tabelle beschreibt die Eigenschaften, mit denen Sie zum Sortieren und filtern.  
  
|Member|Beschreibung|  
|------------|-----------------|  
|<xref:System.Windows.Forms.BindingSource.Filter%2A> -Eigenschaft|Wenn die Datenquelle eine <xref:System.ComponentModel.IBindingListView> ist, wird der Ausdruck abgerufen, der zum Filtern der anzuzeigenden Zeilen verwendet wird, oder dieser Ausdruck wird festgelegt.|  
|<xref:System.Windows.Forms.BindingSource.Sort%2A> -Eigenschaft|Wenn die Datenquelle eine <xref:System.ComponentModel.IBindingList> ist, wird ein Spaltenname abgerufen oder festgelegt, der für das Sortieren und für Informationen zur Sortierreihenfolge verwendet wird.<br /><br /> - oder - <br /><br /> Wenn die Datenquelle ist eine <xref:System.ComponentModel.IBindingListView> und erweiterte Sortierung unterstützt, werden mehrere Spaltennamen, die für die Sortierung und Sortierreihenfolge verwendet abgerufen|  
  
### <a name="integration-with-bindingnavigator"></a>BindingNavigator-Integration  
 Können Sie die <xref:System.Windows.Forms.BindingSource> -Komponente zum Binden von jedes Windows Forms-Steuerelement an eine Datenquelle, aber die <xref:System.Windows.Forms.BindingNavigator> dient speziell für die Arbeit mit der <xref:System.Windows.Forms.BindingSource> Komponente. Die <xref:System.Windows.Forms.BindingNavigator> Steuerelement stellt eine Benutzeroberfläche bereit, für die Steuerung der <xref:System.Windows.Forms.BindingSource> Komponente des aktuellen Elements. In der Standardeinstellung die <xref:System.Windows.Forms.BindingNavigator> Steuerelement enthält Schaltflächen, die die Navigationsmethoden für entsprechen den <xref:System.Windows.Forms.BindingSource> Komponente. Weitere Informationen finden Sie unter [Vorgehensweise: Datennavigation mithilfe des BindingNavigator-Steuerelements in Windows Forms](how-to-navigate-data-with-the-windows-forms-bindingnavigator-control.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [Übersicht über die BindingSource-Komponente](bindingsource-component-overview.md)
- [BindingNavigator-Steuerelement](bindingnavigator-control-windows-forms.md)
- [Windows Forms-Datenbindung](../windows-forms-data-binding.md)
- [Windows Forms-Steuerelemente](controls-to-use-on-windows-forms.md)
- [Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ](how-to-bind-a-windows-forms-control-to-a-type.md)
- [Vorgehensweise: Datenquellenaktualisierungen Sie in einem Windows Forms-Steuerelement mit der BindingSource-Komponente](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)
