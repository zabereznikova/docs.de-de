---
title: Architektur der BindingSource-Komponente
ms.date: 03/30/2017
helpviewer_keywords:
- BindingSource component [Windows Forms], architecture
- Windows Forms, data binding
- BindingSource component [Windows Forms], about BindingSource component
- data binding [Windows Forms], BindingSource component
ms.assetid: 7bc69c90-8a11-48b1-9336-3adab5b41591
ms.openlocfilehash: 54a23ba899ceb05701fe3580aefbb723c6b3f0fd
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364416"
---
# <a name="bindingsource-component-architecture"></a>Architektur der BindingSource-Komponente
Mit der <xref:System.Windows.Forms.BindingSource> -Komponente können Sie universell alle Windows Forms-Steuerelemente an Datenquellen binden.  
  
 Die <xref:System.Windows.Forms.BindingSource> Komponente vereinfacht das Binden von Steuerelementen an eine Datenquelle und bietet gegenüber herkömmlichen Daten Bindungen die folgenden Vorteile:  
  
- Aktiviert die Entwurfszeit Bindung an Geschäftsobjekte.  
  
- Kapselt <xref:System.Windows.Forms.CurrencyManager> Funktionen <xref:System.Windows.Forms.CurrencyManager> und macht Ereignisse zur Entwurfszeit verfügbar.  
  
- Vereinfacht das Erstellen einer Liste, die <xref:System.ComponentModel.IBindingList> die-Schnittstelle unterstützt, indem Listen Änderungs Benachrichtigungen für Datenquellen bereitgestellt werden, die keine systemeigene Unterstützung für Listen Änderungs Benachrichtigungen  
  
- Stellt einen Erweiterbarkeits Punkt für die <xref:System.ComponentModel.IBindingList.AddNew%2A?displayProperty=nameWithType> -Methode bereit.  
  
- Stellt eine Dereferenzierungsebene zwischen der Datenquelle und dem-Steuerelement bereit. Diese Dereferenzierung ist wichtig, wenn sich die Datenquelle zur Laufzeit ändern kann.  
  
- Interagiert mit anderen datenbezogenen Windows Forms Steuerelementen, insbesondere dem <xref:System.Windows.Forms.BindingNavigator> und den <xref:System.Windows.Forms.DataGridView> -Steuerelementen.  
  
 Aus diesen Gründen ist die <xref:System.Windows.Forms.BindingSource> -Komponente die bevorzugte Methode, um Ihre Windows Forms-Steuerelemente an Datenquellen zu binden.  
  
## <a name="bindingsource-features"></a>BindingSource-Funktionen  
 Die <xref:System.Windows.Forms.BindingSource> Komponente stellt mehrere Funktionen zum Binden von Steuerelementen an Daten bereit. Mit diesen Features können Sie die meisten Daten Bindungs Szenarios implementieren, bei denen fast keine Codierung für Sie durchzuführen ist.  
  
 Die <xref:System.Windows.Forms.BindingSource> Komponente erreicht dies durch die Bereitstellung einer konsistenten Schnittstelle für den Zugriff auf viele verschiedene Arten von Datenquellen. Dies bedeutet, dass Sie dieselbe Prozedur für die Bindung an einen beliebigen Typ verwenden. Beispielsweise können Sie die <xref:System.Windows.Forms.BindingSource.DataSource%2A> -Eigenschaft an einen <xref:System.Data.DataSet> oder an ein Geschäftsobjekt anfügen. in beiden Fällen verwenden Sie denselben Satz von Eigenschaften, Methoden und Ereignissen, um die Datenquelle zu bearbeiten.  
  
 Die konsistente Schnittstelle, die <xref:System.Windows.Forms.BindingSource> von der Komponente bereitgestellt wird, vereinfacht das Binden von Daten an Steuerelemente erheblich. Bei Datenquellen Typen, die Änderungs Benachrichtigungen bereitstellen, <xref:System.Windows.Forms.BindingSource> kommuniziert die Komponente automatisch mit Änderungen zwischen dem Steuerelement und der Datenquelle. Für Datenquellen Typen, die keine Änderungs Benachrichtigung bereitstellen, werden Ereignisse bereitgestellt, mit denen Sie Änderungs Benachrichtigungen durchführen können. In der folgenden Liste sind die von der <xref:System.Windows.Forms.BindingSource> -Komponente unterstützten Funktionen aufgeführt:  
  
- Dereferenzierung.  
  
- Währungsverwaltung.  
  
- Datenquelle als Liste.  
  
- <xref:System.Windows.Forms.BindingSource><xref:System.ComponentModel.IBindingList>als.  
  
- Erstellen eines benutzerdefinierten Elements.  
  
- Transaktions Element Erstellung.  
  
- <xref:System.Collections.IEnumerable>Förder.  
  
- Unterstützung für die Entwurfszeit.  
  
- Statische <xref:System.Windows.Forms.ListBindingHelper> Methoden.  
  
- Sortieren und Filtern mit der <xref:System.ComponentModel.IBindingListView> -Schnittstelle.  
  
- Integration in <xref:System.Windows.Forms.BindingNavigator>.  
  
### <a name="indirection"></a>Dereferenzierung  
 Die <xref:System.Windows.Forms.BindingSource> Komponente stellt eine Dereferenzierungsebene zwischen einem Steuerelement und einer Datenquelle bereit. Anstatt ein Steuerelement direkt an eine Datenquelle zu binden, binden Sie das Steuerelement <xref:System.Windows.Forms.BindingSource>an eine und fügen die Datenquelle an die <xref:System.Windows.Forms.BindingSource> - <xref:System.Windows.Forms.BindingSource.DataSource%2A> Eigenschaft der Komponente an.  
  
 Bei dieser Dereferenzierung können Sie die Datenquelle ohne Zurücksetzen der Steuerelement Bindung ändern. Dadurch haben Sie die folgenden Möglichkeiten:  
  
- Sie können das <xref:System.Windows.Forms.BindingSource> an verschiedene Datenquellen anfügen, während Sie die aktuellen Steuerelement Bindungen beibehalten.  
  
- Sie können Elemente in der Datenquelle ändern und gebundene Steuerelemente benachrichtigen. Weitere Informationen finden Sie unter [Vorgehensweise: Datenquellen Aktualisierungen in einem Windows Forms-Steuerelement mit der BindingSource](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)widerspiegeln.  
  
- Sie können eine Bindung zu <xref:System.Type> einem anstelle eines Objekts im Arbeitsspeicher herstellen. Weitere Informationen finden Sie unter [Vorgehensweise: Binden eines Windows Forms-Steuer Elements an](how-to-bind-a-windows-forms-control-to-a-type.md)einen Typ. Anschließend können Sie zur Laufzeit eine Bindung an ein Objekt herstellen.  
  
### <a name="currency-management"></a>Währungsverwaltung  
 Die <xref:System.Windows.Forms.BindingSource> -Komponente implementiert <xref:System.Windows.Forms.ICurrencyManagerProvider> die-Schnittstelle, um die Währungsverwaltung für Sie zu verarbeiten. Mit der <xref:System.Windows.Forms.ICurrencyManagerProvider> -Schnittstelle können Sie auch auf den Currency Manager für einen <xref:System.Windows.Forms.BindingSource>zugreifen, zusätzlich zum Currency Manager für einen anderen <xref:System.Windows.Forms.BindingSource> , der an denselben <xref:System.Windows.Forms.BindingSource.DataMember%2A>gebunden ist.  
  
 Die <xref:System.Windows.Forms.BindingSource> Komponente kapselt <xref:System.Windows.Forms.CurrencyManager> Funktionen <xref:System.Windows.Forms.CurrencyManager> und macht die gängigsten Eigenschaften und Ereignisse verfügbar. In der folgenden Tabelle werden einige der Mitglieder im Zusammenhang mit der Währungsverwaltung beschrieben.  
  
 <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A> -Eigenschaft  
 Ruft den Currency Manager ab, der <xref:System.Windows.Forms.BindingSource>dem zugeordnet ist.  
  
 <xref:System.Windows.Forms.ICurrencyManagerProvider.GetRelatedCurrencyManager%2A>-Methode  
 Wenn eine andere <xref:System.Windows.Forms.BindingSource> an den angegebenen Datenmember gebunden ist, wird der zugehörige Currency Manager abgerufen.  
  
 <xref:System.Windows.Forms.BindingSource.Current%2A> -Eigenschaft  
 Ruft das aktuelle Element der Datenquelle ab.  
  
 <xref:System.Windows.Forms.BindingSource.Position%2A> -Eigenschaft  
 Ruft die aktuelle Position in der zugrunde liegenden Liste ab oder legt diese fest.  
  
 <xref:System.Windows.Forms.BindingSource.EndEdit%2A>-Methode  
 Wendet anstehende Änderungen auf die zugrunde liegende Datenquelle an.  
  
 <xref:System.Windows.Forms.BindingSource.CancelEdit%2A>-Methode  
 Bricht den aktuellen Bearbeitungsvorgang ab.  
  
### <a name="data-source-as-a-list"></a>Datenquelle als Liste  
 Die <xref:System.Windows.Forms.BindingSource> -Komponente implementiert <xref:System.ComponentModel.IBindingListView> die <xref:System.ComponentModel.ITypedList> -und-Schnittstellen. Mit dieser Implementierung können Sie die <xref:System.Windows.Forms.BindingSource> Komponente selbst als Datenquelle ohne externen Speicher verwenden.  
  
 Wenn die <xref:System.Windows.Forms.BindingSource> Komponente an eine Datenquelle angefügt ist, wird die Datenquelle als Liste verfügbar gemacht.  
  
 Die <xref:System.Windows.Forms.BindingSource.DataSource%2A> -Eigenschaft kann auf mehrere Datenquellen festgelegt werden. Dazu zählen Typen, Objekte und Listen von Typen. Die resultierende Datenquelle wird als Liste verfügbar gemacht. In der folgenden Tabelle sind einige der allgemeinen Datenquellen und die resultierende Listen Auswertung aufgeführt.  
  
|DataSource-Eigenschaft|Ergebnisse auflisten|  
|-------------------------|------------------|  
|Ein NULL-Verweis (`Nothing` in Visual Basic).|Ein leeres <xref:System.ComponentModel.IBindingList> von-Objekten. Durch das Hinzufügen eines Elements wird die Liste auf den Typ des hinzugefügten Elements festgelegt.|  
|Ein NULL-Verweis`Nothing` (in Visual Basic) <xref:System.Windows.Forms.BindingSource.DataMember%2A> mit Set|Nicht unterstützt. löst <xref:System.ArgumentException>aus.|  
|Non-List-Typ oder-Objekt vom Typ "T"|Ein leeres <xref:System.ComponentModel.IBindingList> vom Typ "T".|  
|Array Instanz|Ein <xref:System.ComponentModel.IBindingList> , das die Array Elemente enthält.|  
|<xref:System.Collections.IEnumerable>lichen|Eine <xref:System.ComponentModel.IBindingList> , die <xref:System.Collections.IEnumerable> die Elemente enthält.|  
|Listen Instanz mit dem Typ "T"|Eine <xref:System.ComponentModel.IBindingList> -Instanz, die den Typ "T" enthält.|  
  
 Außerdem kann auf andere Listen Typen, <xref:System.ComponentModel.IListSource> z. b. und <xref:System.ComponentModel.ITypedList>, festgelegt werden <xref:System.Windows.Forms.BindingSource> , und der verarbeitet sie entsprechend. <xref:System.Windows.Forms.BindingSource.DataSource%2A> In diesem Fall sollte der in der Liste enthaltene Typ über einen Parameter losen Konstruktor verfügen.  
  
### <a name="bindingsource-as-an-ibindinglist"></a>BindingSource als IBindingList  
 Die <xref:System.Windows.Forms.BindingSource> Komponente stellt Member für den Zugriff auf und die Bearbeitung der zugrunde <xref:System.ComponentModel.IBindingList>liegenden Daten als dar. In der folgenden Tabelle werden einige dieser Member beschrieben.  
  
|Member|Beschreibung|  
|------------|-----------------|  
|<xref:System.Windows.Forms.BindingSource.List%2A> -Eigenschaft|Ruft die Liste ab, die sich aus der Auswertung <xref:System.Windows.Forms.BindingSource.DataSource%2A> der <xref:System.Windows.Forms.BindingSource.DataMember%2A> -Eigenschaft oder der-Eigenschaft ergibt.|  
|<xref:System.Windows.Forms.BindingSource.AddNew%2A>-Methode|Fügt der zugrunde liegenden Liste ein neues Element hinzu. Gilt für Datenquellen, die die <xref:System.ComponentModel.IBindingList> -Schnittstelle implementieren und das Hinzufügen von Elementen <xref:System.Windows.Forms.BindingSource.AllowNew%2A> zulassen (das heißt `true`, die-Eigenschaft ist auf festgelegt).|  
  
### <a name="custom-item-creation"></a>Erstellung benutzerdefinierter Elemente  
 Sie können das <xref:System.Windows.Forms.BindingSource.AddingNew> -Ereignis behandeln, um eine eigene Logik zur Element Erstellung bereitzustellen. Das <xref:System.Windows.Forms.BindingSource.AddingNew> -Ereignis tritt <xref:System.Windows.Forms.BindingSource>auf, bevor ein neues-Objekt hinzugefügt wird. Dieses Ereignis wird ausgelöst, nachdem <xref:System.Windows.Forms.BindingSource.AddNew%2A> die-Methode aufgerufen wurde, aber bevor das neue Element der zugrunde liegenden Liste hinzugefügt wird. Durch die Behandlung dieses Ereignisses können Sie benutzerdefiniertes Element Erstellungs Verhalten bereitstellen <xref:System.Windows.Forms.BindingSource> , ohne von der Klasse abgeleitet zu werden. Weitere Informationen finden Sie unter [Vorgehensweise: Anpassen des Hinzufügens von Elementen mit dem](how-to-customize-item-addition-with-the-windows-forms-bindingsource.md)Windows Forms BindingSource.  
  
### <a name="transactional-item-creation"></a>Transaktions Element Erstellung  
 Die <xref:System.Windows.Forms.BindingSource> -Komponente implementiert <xref:System.ComponentModel.ICancelAddNew> die-Schnittstelle, die das Erstellen von transaktionalen Elementen ermöglicht. Nachdem ein neues Element mithilfe eines Aufrufens <xref:System.Windows.Forms.BindingSource.AddNew%2A>von vorläufig erstellt wurde, kann auf folgende Weise ein Commit oder ein Rollback für die Addition ausgeführt werden:  
  
- Die <xref:System.ComponentModel.ICancelAddNew.EndNew%2A> -Methode führt einen expliziten Commit für die ausstehende Addition aus.  
  
- Durch das Ausführen eines weiteren Auflistungs Vorgangs (z. b. einfügen, entfernen oder verschieben) wird die ausstehende Addition implizit committ.  
  
- Die <xref:System.ComponentModel.ICancelAddNew.CancelNew%2A> Methode führt ein Rollback für die ausstehende Addition aus, wenn für die Methode nicht bereits ein Commit ausgeführt wurde.  
  
### <a name="ienumerable-support"></a>IEnumerable-Unterstützung  
 Die <xref:System.Windows.Forms.BindingSource> -Komponente ermöglicht das Binden <xref:System.Collections.IEnumerable> von Steuerelementen an Datenquellen. Mit dieser Komponente können Sie eine Bindung an eine Datenquelle, z. <xref:System.Data.SqlClient.SqlDataReader?displayProperty=nameWithType>b. eine, herstellen.  
  
 Wenn der <xref:System.Collections.IEnumerable> <xref:System.Windows.Forms.BindingSource> <xref:System.ComponentModel.IBindingList> <xref:System.Collections.IEnumerable> Komponente eine Datenquelle zugewiesen ist, wird von eine erstellt und der Liste der Inhalt der Datenquelle hinzugefügt. <xref:System.Windows.Forms.BindingSource>  
  
### <a name="design-time-support"></a>Entwurfszeit Unterstützung  
 Einige Objekttypen können nicht zur Entwurfszeit erstellt werden, z. b. Objekte, die aus einer Factoryklasse erstellt wurden, oder von einem Webdienst zurückgegebene Objekte. Manchmal müssen Sie Ihre Steuerelemente zur Entwurfszeit an diese Typen binden, auch wenn kein Objekt im Speicher vorhanden ist, an das die Steuerelemente gebunden werden können. Sie können z. b. die Spaltenkopfzeilen eines <xref:System.Windows.Forms.DataGridView> -Steuer Elements mit den Namen der öffentlichen Eigenschaften des benutzerdefinierten Typs bezeichnen.  
  
 Zur Unterstützung dieses Szenarios <xref:System.Windows.Forms.BindingSource> unterstützt die-Komponente <xref:System.Type>die Bindung an. Wenn Sie der <xref:System.Windows.Forms.BindingSource.DataSource%2A> - <xref:System.Type> Eigenschaft ein-Objekt zuweisen <xref:System.Windows.Forms.BindingSource> , erstellt die Komponente <xref:System.ComponentModel.BindingList%601> eine <xref:System.Type> leere von Elementen. Alle Steuerelemente, die Sie anschließend <xref:System.Windows.Forms.BindingSource> an die Komponente binden, werden zur Entwurfszeit oder zur Laufzeit gewarnt, wenn die Eigenschaften oder das Schema Ihres Typs vorhanden sind. Weitere Informationen finden Sie unter [Vorgehensweise: Binden eines Windows Forms-Steuer Elements an](how-to-bind-a-windows-forms-control-to-a-type.md)einen Typ.  
  
### <a name="static-listbindinghelper-methods"></a>Statische ListBindingHelper-Methoden  
 Die <xref:System.Windows.Forms.BindingContext?displayProperty=nameWithType>Typen <xref:System.Windows.Forms.CurrencyManager?displayProperty=nameWithType>, `DataSource` und <xref:System.Windows.Forms.BindingSource> haben alle gemeinsame Logik, um eine Liste aus einem / `DataMember` paar zu generieren. Außerdem wird diese gängige Logik öffentlich zur Verwendung durch Autoren von Steuerelementen und anderen Drittanbietern in den folgenden `static` Methoden bereitgestellt:  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetListItemProperties%2A>  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetList%2A>  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetListName%2A>  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetListItemType%2A>  
  
### <a name="sorting-and-filtering-with-the-ibindinglistview-interface"></a>Sortieren und Filtern mit der IBindingListView-Schnittstelle  
 Die <xref:System.Windows.Forms.BindingSource> -Komponente implementiert <xref:System.ComponentModel.IBindingListView> die-Schnittstelle, <xref:System.ComponentModel.IBindingList> die die-Schnittstelle erweitert. Bietet eine Sortierung mit einer einzelnen Spalte <xref:System.ComponentModel.IBindingListView> und bietet erweiterte Sortier-und Filterfunktionen. <xref:System.ComponentModel.IBindingList> Mit <xref:System.ComponentModel.IBindingListView>können Sie Elemente in der Datenquelle sortieren und Filtern, wenn die Datenquelle auch eine dieser Schnittstellen implementiert. Die <xref:System.Windows.Forms.BindingSource> Komponente stellt keine Verweis Implementierung dieser Member bereit. Stattdessen werden Aufrufe an die zugrunde liegende Liste weitergeleitet.  
  
 In der folgenden Tabelle werden die Eigenschaften beschrieben, die Sie zum Sortieren und Filtern verwenden.  
  
|Member|Beschreibung|  
|------------|-----------------|  
|<xref:System.Windows.Forms.BindingSource.Filter%2A> -Eigenschaft|Wenn die Datenquelle eine <xref:System.ComponentModel.IBindingListView> ist, wird der Ausdruck abgerufen, der zum Filtern der anzuzeigenden Zeilen verwendet wird, oder dieser Ausdruck wird festgelegt.|  
|<xref:System.Windows.Forms.BindingSource.Sort%2A> -Eigenschaft|Wenn die Datenquelle eine <xref:System.ComponentModel.IBindingList> ist, wird ein Spaltenname abgerufen oder festgelegt, der für das Sortieren und für Informationen zur Sortierreihenfolge verwendet wird.<br /><br /> -oder-<br /><br /> Wenn die Datenquelle eine ist <xref:System.ComponentModel.IBindingListView> und erweiterte Sortierung unterstützt, werden mehrere Spaltennamen abgerufen, die für Sortierung und Sortierreihenfolge verwendet werden.|  
  
### <a name="integration-with-bindingnavigator"></a>Integration in BindingNavigator  
 Sie können die <xref:System.Windows.Forms.BindingSource> -Komponente verwenden, um beliebige Windows Forms Steuerelemente an eine Datenquelle zu <xref:System.Windows.Forms.BindingNavigator> binden, aber das-Steuerelement ist <xref:System.Windows.Forms.BindingSource> speziell für die Arbeit mit der-Komponente konzipiert. Das <xref:System.Windows.Forms.BindingNavigator> -Steuerelement stellt eine Benutzeroberfläche zum <xref:System.Windows.Forms.BindingSource> Steuern des aktuellen Elements der Komponente bereit. Standardmäßig stellt das <xref:System.Windows.Forms.BindingNavigator> Steuer <xref:System.Windows.Forms.BindingSource> Element Schaltflächen bereit, die den Navigationsmethoden der Komponente entsprechen. Weitere Informationen finden Sie unter [Vorgehensweise: Navigieren Sie mit dem Windows Forms BindingNavigator-](how-to-navigate-data-with-the-windows-forms-bindingnavigator-control.md)Steuerelement zu Daten.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [Übersicht über die BindingSource-Komponente](bindingsource-component-overview.md)
- [BindingNavigator-Steuerelement](bindingnavigator-control-windows-forms.md)
- [Windows Forms-Datenbindung](../windows-forms-data-binding.md)
- [Windows Forms-Steuerelemente](controls-to-use-on-windows-forms.md)
- [Vorgehensweise: Binden eines Windows Forms-Steuer Elements an einen Typ](how-to-bind-a-windows-forms-control-to-a-type.md)
- [Vorgehensweise: Reflektieren von Datenquellen Aktualisierungen in einem Windows Forms-Steuerelement mit der BindingSource](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)
