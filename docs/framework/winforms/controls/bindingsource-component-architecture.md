---
title: "Architektur der BindingSource-Komponente | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "BindingSource-Komponente [Windows Forms], Informationen über die BindingSource-Komponente"
  - "BindingSource-Komponente, Architektur"
  - "Datenbindung, BindingSource-Komponente"
  - "Windows Forms, Datenbindung"
ms.assetid: 7bc69c90-8a11-48b1-9336-3adab5b41591
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# Architektur der BindingSource-Komponente
Mit der <xref:System.Windows.Forms.BindingSource>\-Komponente können Sie alle Windows Forms\-Steuerelemente universell an Datenquellen binden.  
  
 Die <xref:System.Windows.Forms.BindingSource>\-Komponente vereinfacht das Binden von Steuerelementen an eine Datenquelle und bietet gegenüber der herkömmlichen Datenbindung die folgenden Vorteile:  
  
-   Das Binden an Geschäftsobjekte zur Entwurfszeit wird ermöglicht.  
  
-   Die <xref:System.Windows.Forms.CurrencyManager>\-Funktion wird gekapselt und <xref:System.Windows.Forms.CurrencyManager>\-Ereignisse werden zur Entwurfszeit verfügbar gemacht.  
  
-   Das Erstellen einer Liste, die die <xref:System.ComponentModel.IBindingList>\-Schnittstelle unterstützt, wird erleichtert, indem Listenänderungsbenachrichtigungen für Datenquellen bereitgestellt werden, die keine systemeigenen Listenänderungsbenachrichtigungen unterstützen.  
  
-   Ein Erweiterungspunkt für die <xref:System.ComponentModel.IBindingList.AddNew%2A?displayProperty=fullName>\-Methode wird bereitgestellt.  
  
-   Eine Dereferenzierungsebene zwischen Datenquelle und Steuerelement wird bereitgestellt.  Diese Dereferenzierung ist wichtig, wenn sich die Datenquelle zur Laufzeit ändern kann.  
  
-   Arbeitet mit anderen datenbezogenen Windows Forms\-Steuerelementen zusammen, insbesondere mit <xref:System.Windows.Forms.BindingNavigator> und <xref:System.Windows.Forms.DataGridView>.  
  
 Aus diesen Gründen ist die <xref:System.Windows.Forms.BindingSource>\-Komponente die bevorzugte Methode, die Windows Forms\-Steuerelemente an Datenquellen zu binden.  
  
## BindingSource\-Features  
 Die <xref:System.Windows.Forms.BindingSource>\-Komponente stellt eine Reihe von Features zum Binden von Steuerelementen an Daten bereit.  Mit diesen Features können Sie die meisten Datenbindungsszenarien mit einem sehr geringen Codierungsaufwand implementieren.  
  
 Die <xref:System.Windows.Forms.BindingSource>\-Komponente stellt zu diesem Zweck eine konsistente Schnittstelle für den Zugriff auf viele verschiedene Arten von Datenquellen bereit.  Dies bedeutet, dass Sie die gleiche Prozedur verwenden wie für das Binden an einen beliebigen Typ.  Beispielsweise können Sie die <xref:System.Windows.Forms.BindingSource.DataSource%2A>\-Eigenschaft an ein <xref:System.Data.DataSet> oder ein Geschäftsobjekt binden und in beiden Fällen die Datenquelle mithilfe der gleichen Eigenschaften, Methoden und Ereignisse bearbeiten.  
  
 Die konsistente Schnittstelle, die von der <xref:System.Windows.Forms.BindingSource>\-Komponente bereitgestellt wird, vereinfacht das Binden von Daten an Steuerelemente erheblich.  Für Datenquellentypen, die Änderungsbenachrichtigungen bereitstellen, übermittelt die <xref:System.Windows.Forms.BindingSource>\-Komponente automatisch Änderungen zwischen dem Steuerelement und der Datenquelle.  Für Datenquellentypen, die keine Änderungsbenachrichtigungen unterstützen, werden Ereignisse bereitgestellt, mit denen Sie Änderungsbenachrichtigungen auslösen können.  Die folgende Liste zeigt die von der <xref:System.Windows.Forms.BindingSource>\-Komponente unterstützten Features:  
  
-   Dereferenzierung.  
  
-   Währungsverwaltung.  
  
-   Datenquelle als Liste.  
  
-   <xref:System.Windows.Forms.BindingSource> als <xref:System.ComponentModel.IBindingList>.  
  
-   Benutzerdefinierte Elementerstellung.  
  
-   Transaktionale Elementerstellung.  
  
-   <xref:System.Collections.IEnumerable>\-Unterstützung.  
  
-   Unterstützung zur Entwurfszeit.  
  
-   Statische <xref:System.Windows.Forms.ListBindingHelper>\-Methoden.  
  
-   Sortieren und Filtern mit der <xref:System.ComponentModel.IBindingListView>\-Schnittstelle.  
  
-   Integration in <xref:System.Windows.Forms.BindingNavigator>.  
  
### Dereferenzierung  
 Die <xref:System.Windows.Forms.BindingSource>\-Komponente stellt zwischen einem Steuerelement und einer Datenquelle eine Dereferenzierungsebene bereit.  Anstatt ein Steuerelement direkt an eine Datenquelle zu binden, binden Sie es an eine <xref:System.Windows.Forms.BindingSource> und ordnen die Datenquelle der <xref:System.Windows.Forms.BindingSource.DataSource%2A>\-Eigenschaft der <xref:System.Windows.Forms.BindingSource>\-Komponente zu.  
  
 Mit dieser Dereferenzierungsebene können Sie die Datenquelle ändern, ohne die Steuerelementbindung zurückzusetzen.  Dadurch haben Sie folgende Möglichkeiten:  
  
-   Sie können die <xref:System.Windows.Forms.BindingSource> anderen Datenquellen zuordnen und die aktuellen Steuerelementbindungen beibehalten.  
  
-   Sie können Elemente in der Datenquelle ändern und gebundene Steuerelemente benachrichtigen.  Weitere Informationen hierzu finden Sie unter [Gewusst wie: Kennzeichnen von Datenquellenaktualisierungen in einem Windows Forms\-Steuerelement mithilfe der BindingSource](../../../../docs/framework/winforms/controls/reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md).  
  
-   Sie können statt an ein Objekt im Arbeitsspeicher an einen <xref:System.Type> binden.  Weitere Informationen hierzu finden Sie unter [Gewusst wie: Binden eines Windows Forms\-Steuerelements an einen Typ](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md).  Anschließend können Sie zur Laufzeit an ein Objekt binden.  
  
### Währungsverwaltung  
 Die <xref:System.Windows.Forms.BindingSource>\-Komponente implementiert die <xref:System.Windows.Forms.ICurrencyManagerProvider>\-Schnittstelle zur automatischen Behandlung der Währungsverwaltung.  Zusätzlich können Sie mit der <xref:System.Windows.Forms.ICurrencyManagerProvider>\-Schnittstelle neben dem Währungs\-Manager für eine <xref:System.Windows.Forms.BindingSource> auf den Währungs\-Manager für eine weitere <xref:System.Windows.Forms.BindingSource> zugreifen, die an denselben <xref:System.Windows.Forms.BindingSource.DataMember%2A> gebunden ist.  
  
 Die <xref:System.Windows.Forms.BindingSource>\-Komponente kapselt die <xref:System.Windows.Forms.CurrencyManager>\-Funktion und macht die gängigsten <xref:System.Windows.Forms.CurrencyManager>\-Eigenschaften und \-Ereignisse verfügbar.  In der folgenden Tabelle werden einige Member beschrieben, die zur Währungsverwaltung gehören.  
  
 <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A>\-Eigenschaft  
 Ruft den Währungs\-Manager ab, der der <xref:System.Windows.Forms.BindingSource> zugeordnet ist.  
  
 <xref:System.Windows.Forms.ICurrencyManagerProvider.GetRelatedCurrencyManager%2A>\-Methode  
 Wenn eine weitere <xref:System.Windows.Forms.BindingSource> an den angegebenen Datenmember gebunden ist, wird der zugehörige Währungs\-Manager abgerufen.  
  
 <xref:System.Windows.Forms.BindingSource.Current%2A>\-Eigenschaft  
 Ruft das aktuelle Element der Datenquelle ab.  
  
 <xref:System.Windows.Forms.BindingSource.Position%2A>\-Eigenschaft  
 Ruft die aktuelle Position in der zugrunde liegenden Liste ab bzw. legt diese fest.  
  
 <xref:System.Windows.Forms.BindingSource.EndEdit%2A>\-Methode  
 Wendet anstehende Änderungen auf die zugrunde liegende Datenquelle an.  
  
 <xref:System.Windows.Forms.BindingSource.CancelEdit%2A>\-Methode  
 Bricht den aktuellen Bearbeitungsvorgang ab.  
  
### Datenquelle als Liste  
 Die <xref:System.Windows.Forms.BindingSource>\-Komponente implementiert die <xref:System.ComponentModel.IBindingListView>\-Schnittstelle und die <xref:System.ComponentModel.ITypedList>\-Schnittstelle.  Mit dieser Implementierung können Sie die <xref:System.Windows.Forms.BindingSource>\-Komponente selbst als Datenquelle verwenden, ohne einen externen Speicher.  
  
 Wenn die <xref:System.Windows.Forms.BindingSource>\-Komponente einer Datenquelle zugeordnet ist, macht sie die Datenquelle als Liste verfügbar.  
  
 Die <xref:System.Windows.Forms.BindingSource.DataSource%2A>\-Eigenschaft kann auf mehrere Datenquellen festgelegt werden.  Hierzu gehören Typen, Objekte und Typenlisten.  Die sich ergebende Datenquelle wird als Liste verfügbar gemacht.  In der folgenden Tabelle werden einige gängige Datenquellen und die daraus resultierende Listenauswertung angezeigt.  
  
|DataSource\-Eigenschaft|Listenergebnis|  
|-----------------------------|--------------------|  
|Ein Nullverweis \(`Nothing` in Visual Basic\)|Eine leere <xref:System.ComponentModel.IBindingList> der Objekte.  Durch das Hinzufügen eines Elements wird die Liste auf den Typ des hinzugefügten Elements festgelegt.|  
|Ein Nullverweis \(`Nothing` in Visual Basic\) mit festgelegtem <xref:System.Windows.Forms.BindingSource.DataMember%2A>|Nicht unterstützt; löst <xref:System.ArgumentException> aus.|  
|Kein Listentyp oder Objekt vom Typ "T"|Eine leere <xref:System.ComponentModel.IBindingList> vom Typ "T".|  
|Arrayinstanz|Eine <xref:System.ComponentModel.IBindingList>, die die Arrayelemente enthält.|  
|<xref:System.Collections.IEnumerable>\-Instanz|Eine <xref:System.ComponentModel.IBindingList>, die die <xref:System.Collections.IEnumerable>\-Elemente enthält|  
|Listeninstanz, die den Typ "T" enthält|Eine <xref:System.ComponentModel.IBindingList>\-Instanz, die den Typ "T" enthält.|  
  
 Darüber hinaus kann <xref:System.Windows.Forms.BindingSource.DataSource%2A> auf andere Listentypen wie <xref:System.ComponentModel.IListSource> und <xref:System.ComponentModel.ITypedList> festgelegt werden. Diese werden von <xref:System.Windows.Forms.BindingSource> korrekt behandelt.  Der in der Liste enthaltene Typ sollte in diesem Fall über einen Standardkonstruktor verfügen.  
  
### BindingSource als IBindingList  
 Die <xref:System.Windows.Forms.BindingSource>\-Komponente stellt Member zum Aufrufen und Bearbeiten der zugrunde liegenden Daten als <xref:System.ComponentModel.IBindingList> bereit.  In der folgenden Tabelle werden einige dieser Member beschrieben.  
  
|Member|Beschreibung|  
|------------|------------------|  
|<xref:System.Windows.Forms.BindingSource.List%2A>\-Eigenschaft|Ruft die Liste ab, die sich aus der Auswertung der <xref:System.Windows.Forms.BindingSource.DataSource%2A>\-Eigenschaft oder der <xref:System.Windows.Forms.BindingSource.DataMember%2A>\-Eigenschaft ergibt.|  
|<xref:System.Windows.Forms.BindingSource.AddNew%2A>\-Methode|Fügt der zugrunde liegenden Liste ein neues Element hinzu.  Gilt für Datenquellen, die die <xref:System.ComponentModel.IBindingList>\-Schnittstelle implementieren und das Hinzufügen von Elementen ermöglichen \(d. h., die <xref:System.Windows.Forms.BindingSource.AllowNew%2A>\-Eigenschaft ist auf `true` festgelegt\).|  
  
### Benutzerdefinierte Elementerstellung  
 Sie können das <xref:System.Windows.Forms.BindingSource.AddingNew>\-Ereignis behandeln, um ihre eigene Elementerstellungslogik bereitzustellen.  Das <xref:System.Windows.Forms.BindingSource.AddingNew>\-Ereignis tritt auf, bevor der <xref:System.Windows.Forms.BindingSource> ein neues Objekt hinzugefügt wird.  Dieses Ereignis wird ausgelöst, nachdem die <xref:System.Windows.Forms.BindingSource.AddNew%2A>\-Methode aufgerufen wurde, jedoch bevor das neue Element der zugrunde liegenden Liste hinzugefügt wird.  Indem Sie dieses Ereignis behandeln, können Sie benutzerdefiniertes Elementerstellungsverhalten bereitstellen, ohne von der <xref:System.Windows.Forms.BindingSource>\-Klasse abzuleiten.  Weitere Informationen hierzu finden Sie unter [Gewusst wie: Anpassen der Hinzufügung von Elementen mithilfe der BindingSource von Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-item-addition-with-the-windows-forms-bindingsource.md).  
  
### Transaktionale Elementerstellung  
 Die <xref:System.Windows.Forms.BindingSource>\-Komponente implementiert die <xref:System.ComponentModel.ICancelAddNew>\-Schnittstelle, die eine transaktionale Elementerstellung ermöglicht.  Nachdem ein neues Element durch einen Aufruf von <xref:System.Windows.Forms.BindingSource.AddNew%2A> vorläufig erstellt wurde, kann für diese Hinzufügung auf folgende Weise ein Commit oder Rollback ausgeführt werden:  
  
-   Die <xref:System.ComponentModel.ICancelAddNew.EndNew%2A>\-Methode führt explizit einen Commit für die anstehende Hinzufügung aus.  
  
-   Wenn eine andere Auflistungsoperation ausgeführt wird, z. B. Einfügen, Löschen oder Verschieben, wird für die anstehende Hinzufügung ein indirekter Commit ausgeführt.  
  
-   Die <xref:System.ComponentModel.ICancelAddNew.CancelNew%2A>\-Methode führt einen Rollback für die ausstehende Hinzufügung aus, sofern für die Methode noch kein Commit ausgeführt wurde.  
  
### IEnumerable\-Unterstützung  
 Die <xref:System.Windows.Forms.BindingSource>\-Komponente ermöglicht das Binden von Steuerelementen an <xref:System.Collections.IEnumerable>\-Datenquellen.  Mit dieser Komponente können Sie an eine Datenquelle wie <xref:System.Data.SqlClient.SqlDataReader?displayProperty=fullName> binden.  
  
 Wenn eine <xref:System.Collections.IEnumerable>\-Datenquelle der <xref:System.Windows.Forms.BindingSource>\-Komponente zugeordnet ist, erstellt die <xref:System.Windows.Forms.BindingSource> eine <xref:System.ComponentModel.IBindingList> und fügt den Inhalt der <xref:System.Collections.IEnumerable>\-Datenquelle zur Liste hinzu.  
  
### Unterstützung zur Entwurfszeit  
 Einige Objekttypen können zur Entwurfszeit nicht erstellt werden, z. B. Objekte, die aus einer Factoryklasse erstellt oder von einem Webdienst zurückgegeben werden.  Gegebenenfalls müssen Sie die Steuerelemente zur Entwurfszeit an diese Typen binden, auch wenn sich im Arbeitsspeicher kein Objekt befindet, an das die Steuerelemente gebunden werden können.  Beispielsweise müssen Sie die Spaltenheader eines <xref:System.Windows.Forms.DataGridView>\-Steuerelements mit den Namen der öffentlichen Eigenschaften des benutzerdefinierten Typs bezeichnen.  
  
 Um dieses Szenario zu unterstützen, wird von der <xref:System.Windows.Forms.BindingSource>\-Komponente das Binden an einen <xref:System.Type> unterstützt.  Wenn Sie der <xref:System.Windows.Forms.BindingSource.DataSource%2A>\-Eigenschaft einen <xref:System.Type> zuordnen, erstellt die <xref:System.Windows.Forms.BindingSource>\-Komponente eine leere <xref:System.ComponentModel.BindingList%601> von <xref:System.Type>\-Elementen.  Für alle Steuerelemente, die Sie nachfolgend an die <xref:System.Windows.Forms.BindingSource>\-Komponente binden, werden zur Entwurfszeit oder zur Laufzeit Warnungen über das Vorhandensein der Eigenschaften oder des Schemas für den Typ ausgegeben.  Weitere Informationen hierzu finden Sie unter [Gewusst wie: Binden eines Windows Forms\-Steuerelements an einen Typ](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md).  
  
### Statische ListBindingHelper\-Methoden  
 Die Typen <xref:System.Windows.Forms.BindingContext?displayProperty=fullName>, <xref:System.Windows.Forms.CurrencyManager?displayProperty=fullName> und <xref:System.Windows.Forms.BindingSource> verfügen über eine gemeinsame Logik zum Generieren einer Liste aus einem `DataSource`\/`DataMember`\-Paar.  Diese gemeinsame Logik wird außerdem für Autoren von Steuerelementen und andere Dritte in den folgenden `static`\-Methoden öffentlich verfügbar gemacht:  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListItemProperties%2A>  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetList%2A>.  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListName%2A>  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListItemType%2A>  
  
### Sortieren und Filtern mit der IBindingListView\-Schnittstelle  
 Die <xref:System.Windows.Forms.BindingSource>\-Komponente implementiert die <xref:System.ComponentModel.IBindingListView>\-Schnittstelle, die die <xref:System.ComponentModel.IBindingList>\-Schnittstelle erweitert.  Die <xref:System.ComponentModel.IBindingList> ermöglicht das Sortieren einzelner Spalten, und die <xref:System.ComponentModel.IBindingListView> stellt erweiterte Funktionen zum Sortieren und Filtern bereit.  Mit <xref:System.ComponentModel.IBindingListView> können Sie Elemente in der Datenquelle sortieren und filtern, wenn von der Datenquelle ebenfalls eine dieser Schnittstellen implementiert wird.  Die <xref:System.Windows.Forms.BindingSource>\-Komponente stellt keine Verweisimplementierung dieser Member bereit.  Stattdessen werden Aufrufe zur zugrunde liegenden Liste weitergeleitet.  
  
 In der folgenden Tabelle werden die Eigenschaften beschrieben, die Sie zum Sortieren und Filtern verwenden.  
  
|Member|Beschreibung|  
|------------|------------------|  
|<xref:System.Windows.Forms.BindingSource.Filter%2A>\-Eigenschaft|Wenn die Datenquelle eine <xref:System.ComponentModel.IBindingListView> ist, wird der Ausdruck abgerufen oder festgelegt, der zum Filtern der angezeigten Zeilen verwendet wird.|  
|<xref:System.Windows.Forms.BindingSource.Sort%2A>\-Eigenschaft|Wenn die Datenquelle eine <xref:System.ComponentModel.IBindingList> ist, wird ein Spaltenname abgerufen oder festgelegt, der zum Sortieren sowie für Informationen zur Sortierreihenfolge verwendet wird.<br /><br /> \- oder \-<br /><br /> Wenn es sich bei der Datenquelle um eine <xref:System.ComponentModel.IBindingListView> und erweitertes Sortieren unterstützt wird, werden mit dieser Eigenschaft mehrere Spaltennamen abgerufen, die zum Sortieren und für die Sortierreihenfolge verwendet werden.|  
  
### Integration in BindingNavigator  
 Sie können mithilfe der <xref:System.Windows.Forms.BindingSource>\-Komponente beliebige Windows Forms\-Steuerelemente an eine Datenquelle binden. Das <xref:System.Windows.Forms.BindingNavigator>\-Steuerelement wurde jedoch speziell für die Interaktion mit der <xref:System.Windows.Forms.BindingSource>\-Komponente entworfen.  Das <xref:System.Windows.Forms.BindingNavigator>\-Steuerelement stellt eine Benutzeroberfläche zum Steuern des aktuellen Elements der <xref:System.Windows.Forms.BindingSource>\-Komponente bereit.  Standardmäßig stellt das <xref:System.Windows.Forms.BindingNavigator>\-Steuerelement Schaltflächen bereit, die den Navigationsmethoden auf der <xref:System.Windows.Forms.BindingSource>\-Komponente entsprechen.  Weitere Informationen finden Sie unter [Gewusst wie: Datennavigation mithilfe des DataNavigator\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-navigate-data-with-the-windows-forms-bindingnavigator-control.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.BindingSource>   
 <xref:System.Windows.Forms.BindingNavigator>   
 [Übersicht über die BindingSource\-Komponente](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)   
 [BindingNavigator\-Steuerelement](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)   
 [Datenbindung in Web Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Steuerelemente für Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [Gewusst wie: Binden eines Windows Forms\-Steuerelements an einen Typ](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)   
 [Gewusst wie: Kennzeichnen von Datenquellenaktualisierungen in einem Windows Forms\-Steuerelement mithilfe der BindingSource](../../../../docs/framework/winforms/controls/reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)