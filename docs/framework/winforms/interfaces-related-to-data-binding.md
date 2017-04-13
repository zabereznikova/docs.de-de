---
title: "Auf Datenbindung bezogene Schnittstellen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Daten [Windows Forms], Datenbindungsschnittstellen"
  - "Datenbindung, Schnittstellen"
  - "IBindingList-Schnittstelle, Windows Forms-Datenbindung"
  - "IBindingListView-Schnittstelle"
  - "IDataErrorInfo-Schnittstelle, Windows Forms-Datenbindung"
  - "IEditableObject-Schnittstelle, Windows Forms-Datenbindung"
  - "IList-Schnittstelle, Windows Forms-Datenbindung"
  - "INotifyPropertyChanged-Schnittstelle"
  - "Schnittstellen, Windows Forms-Datenbindung"
ms.assetid: 14e49a2e-3e46-47ca-b491-70d546333277
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# Auf Datenbindung bezogene Schnittstellen
Mit [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] können Sie viele verschiedene Datenstrukturen erstellen, um den Bindungsanforderungen der Anwendung sowie der Daten, mit denen Sie arbeiten, gerecht zu werden.  Möglicherweise möchten Sie eigene Klassen erstellen, die Daten in Windows Forms bereitstellen oder konsumieren.  Diese Objekte können unterschiedliche Funktionalitäts\- und Komplexitätsstufen bieten. Dazu gehören z. B. die einfache Datenbindung, die Bereitstellung von Unterstützung zur Entwurfszeit, die Fehlerprüfung, die Änderungsbenachrichtigung und sogar die Unterstützung eines strukturierten Rollbacks der an den Daten selbst vorgenommenen Änderungen.  
  
## Consumer von Datenbindungsschnittstellen  
 In den folgenden Abschnitten werden zwei Gruppen von Schnittstellenobjekten beschrieben.  In der ersten Gruppe sind Schnittstellen aufgeführt, die von Datenquellenautoren für Datenquellen implementiert werden.  Diese Schnittstellen sollen von Datenquellenconsumern konsumiert werden, bei denen es sich in den meisten Fällen um Windows Forms\-Steuerelemente oder \-Komponenten handelt.  In der zweiten Gruppe sind Schnittstellen aufgelistet, die für die Verwendung durch Komponentenautoren vorgesehen sind.  Komponentenautoren verwenden diese Schnittstellen zum Erstellen von Komponenten, die die Datenbindung unterstützen, die vom Windows Forms\-Datenbindungsmodul konsumiert werden soll.  Sie können diese Schnittstellen innerhalb der mit dem Formular verknüpften Klassen implementieren, um die Datenbindung zu ermöglichen. Dabei entsteht immer eine Klasse, durch die eine Schnittstelle implementiert wird, die die Interaktion mit Daten ermöglicht.  Die Datenentwurfstools zur schnellen Anwendungsentwicklung \(RAD, Rapid Application Development\) von [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] nutzen bereits die Vorteile dieser Funktionen.  
  
### Schnittstellen für die Implementierung durch Datenquellenautoren  
 Die folgenden Schnittstellen sind für die Konsumierung durch Windows Forms\-Steuerelemente vorgesehen:  
  
-   <xref:System.Collections.IList>\-Schnittstelle  
  
     Eine Klasse, die die <xref:System.Collections.IList>\-Schnittstelle implementiert, könnte eine der Klassen <xref:System.Array>, <xref:System.Collections.ArrayList> oder <xref:System.Collections.CollectionBase> sein.  Dies sind indizierte Listen mit Elementen des Typs <xref:System.Object>.  Diese Listen müssen homogene Typen enthalten, da der Typ durch das erste Element des Indexes festgelegt wird.  <xref:System.Collections.IList> ist nur für die Bindung zur Laufzeit verfügbar.  
  
    > [!NOTE]
    >  Wenn Sie eine Liste von Geschäftsobjekten für die Bindung mit Windows Forms erstellen möchten, sollten Sie die Verwendung von <xref:System.ComponentModel.BindingList%601> in Betracht ziehen.  <xref:System.ComponentModel.BindingList%601> ist eine erweiterbare Klasse, durch die die primären Schnittstellen implementiert werden, die für die bidirektionale Datenbindung von Windows Forms erforderlich sind.  
  
-   <xref:System.ComponentModel.IBindingList>\-Schnittstelle  
  
     Eine Klasse, die die <xref:System.ComponentModel.IBindingList>\-Schnittstelle implementiert, verfügt über weitaus umfassendere Datenbindungsfunktionen.  Durch diese Implementierung stehen Ihnen für den Fall einer Änderung der Listenelemente \(z. B. wenn sich das Feld Adresse für das dritte Element der Kundenliste ändert\) oder einer Änderung der Liste \(z. B. wenn sich die Anzahl der Elemente in der Liste erhöht oder verringert\) grundlegende Sortierfunktionen und die Änderungsbenachrichtigung zur Verfügung.  Die Änderungsbenachrichtigung ist wichtig, wenn mehrere Steuerelemente an dieselben Daten gebunden werden sollen, und falls Sie Datenänderungen, die in einem der Steuerelemente vorgenommen wurden, an die anderen gebundenen Steuerelemente weitergeben möchten.  
  
    > [!NOTE]
    >  Die Änderungsbenachrichtigung für die <xref:System.ComponentModel.IBindingList>\-Schnittstelle wird über die <xref:System.ComponentModel.IBindingList.SupportsChangeNotification%2A>\-Eigenschaft aktiviert. Wenn diese `true` ist, wird ein <xref:System.ComponentModel.IBindingList.ListChanged>\-Ereignis ausgelöst, das angibt, dass sich die Liste oder ein Listenelement geändert hat.  
  
     Die Art der Änderung wird mithilfe der <xref:System.ComponentModel.ListChangedType>\-Eigenschaft des <xref:System.ComponentModel.ListChangedEventArgs>\-Parameters beschrieben.  Sobald das Datenmodell aktualisiert wird, werden folglich auch alle abhängigen Ansichten aktualisiert, z. B. andere, an dieselbe Datenquelle gebundene Steuerelemente.  Die Objekte in der Liste müssen bei einer Änderung die Liste allerdings benachrichtigen, damit diese das <xref:System.ComponentModel.IBindingList.ListChanged>\-Ereignis auslösen kann.  
  
    > [!NOTE]
    >  Die <xref:System.ComponentModel.BindingList%601>\-Klasse stellt eine generische Implementierung der <xref:System.ComponentModel.IBindingList>\-Schnittstelle bereit.  
  
-   <xref:System.ComponentModel.IBindingListView>\-Schnittstelle  
  
     Eine Klasse, die die <xref:System.ComponentModel.IBindingListView>\-Schnittstelle implementiert, stellt sämtliche Funktionen einer Implementierung von <xref:System.ComponentModel.IBindingList> und zusätzlich Funktionen für die Filterung und erweiterte Sortierung bereit.  Diese Implementierung ermöglicht die zeichenfolgenbasierte Filterung und mehrspaltige Sortierung auf der Grundlage einer Kombination aus Eigenschaftendeskriptor und Sortierrichtung.  
  
-   <xref:System.ComponentModel.IEditableObject>\-Schnittstelle  
  
     Über eine Klasse, die die <xref:System.ComponentModel.IEditableObject>\-Schnittstelle implementiert, können Objekte steuern, wann an ihnen vorgenommene Änderungen permanent werden.  Durch diese Implementierung stehen Ihnen die Methoden <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A> und <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> zur Verfügung, mit deren Hilfe Sie ein Rollback der am Objekt vorgenommenen Änderungen ausführen können.  Im Folgenden finden Sie eine kurze Erläuterung zur Funktionsweise der Methoden <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A> und <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> sowie zum Zusammenwirken dieser Methoden, um ein Rollback der an den Daten vorgenommenen Änderungen zu ermöglichen:  
  
    -   Die <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>\-Methode signalisiert den Beginn der Bearbeitung eines Objekts.  Objekte, die diese Schnittstelle implementieren, müssen alle nach Aufrufen der <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>\-Methode erfolgten Updates so speichern, dass diese bei Aufrufen der <xref:System.ComponentModel.IEditableObject.CancelEdit%2A>\-Methode verworfen werden können.  Bei der Datenbindung in Windows Forms können Sie <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> innerhalb des Gültigkeitsbereichs einer einzelnen Edit\-Transaktion \(z. B. <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>\) mehrfach aufrufen.  Implementierungen von <xref:System.ComponentModel.IEditableObject> sollten nachverfolgen, ob <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> bereits aufgerufen wurde, und alle nachfolgenden Aufrufe an <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> ignorieren.  Da diese Methode mehrmals aufgerufen werden kann, muss gewährleistet sein, dass bei allen weiteren Versuchen, die Methode aufzurufen, kein Schaden entsteht, d. h., dass die vorgenommenen Updates bei nachfolgenden <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>\-Aufrufen nicht beschädigt oder die beim ersten Aufruf von <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> gespeicherten Daten nicht geändert werden.  
  
    -   Die <xref:System.ComponentModel.IEditableObject.EndEdit%2A>\-Methode verschiebt die seit dem Aufruf von <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> für das zugrunde liegende Objekt vorgenommenen Änderungen, wenn sich das Objekt im Bearbeitungsmodus befindet.  
  
    -   Die <xref:System.ComponentModel.IEditableObject.CancelEdit%2A>\-Methode verwirft alle am Objekt vorgenommenen Änderungen.  
  
     Weitere Informationen zur Funktionsweise der Methoden <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A> und <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> finden Sie unter [Speichern von Daten in Datasets](../Topic/Save%20data%20back%20to%20the%20database.md).  
  
     Dieser Transaktionsaspekt der Datenfunktionen wird vom <xref:System.Windows.Forms.DataGridView>\-Steuerelement verwendet.  
  
-   <xref:System.ComponentModel.ICancelAddNew>\-Schnittstelle  
  
     Von einer Klasse, die die <xref:System.ComponentModel.ICancelAddNew>\-Schnittstelle implementiert, wird normalerweise auch die <xref:System.ComponentModel.IBindingList>\-Schnittstelle implementiert. Sie ermöglicht es Ihnen, mit der <xref:System.ComponentModel.IBindingList.AddNew%2A>\-Methode an der Datenquelle vorgenommene Änderungen zurückzusetzen.  Wenn die Datenquelle die <xref:System.ComponentModel.IBindingList>\-Schnittstelle implementiert, sollte sie auch die <xref:System.ComponentModel.ICancelAddNew>\-Schnittstelle implementieren.  
  
-   <xref:System.ComponentModel.IDataErrorInfo>\-Schnittstelle  
  
     Eine Klasse, die die <xref:System.ComponentModel.IDataErrorInfo>\-Schnittstelle implementiert, ermöglicht es Objekten, gebundenen Steuerelementen benutzerdefinierte Fehlerinformationen zur Verfügung zu stellen:  
  
    -   Die <xref:System.ComponentModel.IDataErrorInfo.Error%2A>\-Eigenschaft gibt allgemeinen Fehlermeldungstext zurück \(z. B. "Ein Fehler ist aufgetreten"\).  
  
    -   Die <xref:System.ComponentModel.IDataErrorInfo.Item%2A>\-Eigenschaft gibt eine Zeichenfolge mit der spezifischen Fehlermeldung aus der Spalte zurück \(z. B. "Der Wert in der Spalte `State`  ist ungültig"\).  
  
-   <xref:System.Collections.IEnumerable>\-Schnittstelle  
  
     Eine Klasse, die die <xref:System.Collections.IEnumerable>\-Schnittstelle implementiert, wird normalerweise von [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] konsumiert.  Windows Forms\-Unterstützung für diese Schnittstelle ist nur über die <xref:System.Windows.Forms.BindingSource>\-Komponente verfügbar.  
  
    > [!NOTE]
    >  Die <xref:System.Windows.Forms.BindingSource>\-Komponente kopiert alle <xref:System.Collections.IEnumerable>\-Elemente zu Bindungszwecken in eine separate Liste.  
  
-   <xref:System.ComponentModel.ITypedList>\-Schnittstelle  
  
     Über eine Auflistungsklasse, die die <xref:System.ComponentModel.ITypedList>\-Schnittstelle implementiert, können die Reihenfolge und die für das gebundene Steuerelement verfügbar gemachte Gruppe von Eigenschaften gesteuert werden.  
  
    > [!NOTE]
    >  Wenn Sie die <xref:System.ComponentModel.ITypedList.GetItemProperties%2A>\-Methode implementieren und das <xref:System.ComponentModel.PropertyDescriptor>\-Array nicht NULL ist, entspricht der letzte Eintrag im Array dem Eigenschaftendeskriptor, durch den die List\-Eigenschaft beschrieben wird, die wiederum eine andere Elementliste darstellt.  
  
-   <xref:System.ComponentModel.ICustomTypeDescriptor>\-Schnittstelle  
  
     Eine Klasse, die die <xref:System.ComponentModel.ICustomTypeDescriptor>\-Schnittstelle implementiert, stellt dynamische Informationen über sich selbst bereit.  Diese Schnittstelle ist mit <xref:System.ComponentModel.ITypedList> vergleichbar, sie wird jedoch für Objekte und nicht für Listen verwendet.  Diese Schnittstelle wird von <xref:System.Data.DataRowView> verwendet, um das Schema der zugrunde liegenden Zeilen zu projizieren.  Eine einfache Implementierung von <xref:System.ComponentModel.ICustomTypeDescriptor> wird von der <xref:System.ComponentModel.CustomTypeDescriptor>\-Klasse bereitgestellt.  
  
    > [!NOTE]
    >  Um die Bindung an Typen, die <xref:System.ComponentModel.ICustomTypeDescriptor> implementieren, zur Entwurfszeit zu unterstützen, muss der Typ außerdem <xref:System.ComponentModel.IComponent> implementieren und als Instanz im Formular vorhanden sein.  
  
-   <xref:System.ComponentModel.IListSource>\-Schnittstelle  
  
     Durch eine Klasse, die die <xref:System.ComponentModel.IListSource>\-Schnittstelle implementiert, wird die listenbasierte Bindung an Objekte aktiviert, die keine Liste darstellen.  Die <xref:System.ComponentModel.IListSource.GetList%2A>\-Methode von <xref:System.ComponentModel.IListSource> wird verwendet, um eine bindbare Liste von einem Objekt zurückzugeben, das nicht von <xref:System.Collections.IList> erbt.  <xref:System.ComponentModel.IListSource> wird von der <xref:System.Data.DataSet>\-Klasse verwendet.  
  
-   <xref:System.ComponentModel.IRaiseItemChangedEvents>\-Schnittstelle  
  
     Eine Klasse, die die <xref:System.ComponentModel.IRaiseItemChangedEvents>\-Schnittstelle implementiert, ist eine bindbare Liste, die zusätzlich die <xref:System.ComponentModel.IBindingList>\-Schnittstelle implementiert.  Über diese Schnittstelle wird angezeigt, ob der jeweilige Typ <xref:System.ComponentModel.IBindingList.ListChanged>\-Ereignisse des Typs <xref:System.ComponentModel.ListChangedType> auslöst, indem er die zugehörige <xref:System.ComponentModel.IRaiseItemChangedEvents.RaisesItemChangedEvents%2A>\-Eigenschaft verwendet.  
  
    > [!NOTE]
    >  Sie sollten <xref:System.ComponentModel.IRaiseItemChangedEvents> implementieren, wenn die Datenquelle die zuvor beschriebene Eigenschaft\-zu\-Listenereignis\-Konvertierung bereitstellt und mit der <xref:System.Windows.Forms.BindingSource>\-Komponente interagiert.  Andernfalls wird die Eigenschaft\-zu\-Listenereignis\-Konvertierung auch von <xref:System.Windows.Forms.BindingSource> ausgeführt, was die Leistung beeinträchtigt.  
  
-   <xref:System.ComponentModel.ISupportInitialize>\-Schnittstelle  
  
     Eine Komponente, die die <xref:System.ComponentModel.ISupportInitialize>\-Schnittstelle implementiert, nutzt die Vorteile von Batchoptimierungen, um Eigenschaften festzulegen und co\-abhängige Eigenschaften zu initialisieren.  <xref:System.ComponentModel.ISupportInitialize> enthält zwei Methoden:  
  
    -   <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> signalisiert, dass die Objektinitialisierung gestartet wird.  
  
    -   <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> signalisiert, dass die Objektinitialisierung beendet wird.  
  
-   <xref:System.ComponentModel.ISupportInitializeNotification>\-Schnittstelle  
  
     Durch eine Komponente, die die <xref:System.ComponentModel.ISupportInitializeNotification>\-Schnittstelle implementiert, wird auch die <xref:System.ComponentModel.ISupportInitialize>\-Schnittstelle implementiert.  Diese Schnittstelle ermöglicht es Ihnen, andere <xref:System.ComponentModel.ISupportInitialize>\-Komponenten darüber zu benachrichtigen, dass die Initialisierung abgeschlossen wurde.  Die <xref:System.ComponentModel.ISupportInitializeNotification>\-Schnittstelle enthält zwei Member:  
  
    -   <xref:System.ComponentModel.ISupportInitializeNotification.IsInitialized%2A> gibt einen `boolean` Wert zurück, der angibt, ob die Komponente initialisiert wird.  
  
    -   <xref:System.ComponentModel.ISupportInitializeNotification.Initialized> tritt ein, wenn <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> aufgerufen wird.  
  
-   <xref:System.ComponentModel.INotifyPropertyChanged>\-Schnittstelle  
  
     Eine Klasse, die diese Schnittstelle implementiert, ist ein Typ, der ein Ereignis auslöst, wenn sich einer der zugehörigen Eigenschaftswerte ändert.  Durch diese Schnittstelle wird die bisherige Praxis abgelöst, für jede Eigenschaft eines Steuerelements ein Change\-Ereignis bereitzuhalten.  Bei Verwendung in <xref:System.ComponentModel.BindingList%601> sollte ein Geschäftsobjekt die <xref:System.ComponentModel.INotifyPropertyChanged>\-Schnittstelle implementieren. <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged>\-Ereignisse werden von BindingList\`1 in <xref:System.ComponentModel.BindingList%601.ListChanged>\-Ereignisse des Typs <xref:System.ComponentModel.ListChangedType> konvertiert.  
  
    > [!NOTE]
    >  Damit in einer Bindung zwischen einem gebundenen Client und einer Datenquelle eine Änderungsbenachrichtigung stattfindet, sollte der Typ der gebundenen Datenquelle entweder die <xref:System.ComponentModel.INotifyPropertyChanged>\-Schnittstelle implementieren \(empfohlen\), oder Sie stellen *propertyName*`Changed`\-Ereignisse für den gebundenen Typ zur Verfügung. Beide Verfahrensweisen sollten nicht gleichzeitig angewendet werden.  
  
### Schnittstellen für die Implementierung durch Komponentenautoren  
 Die folgenden Schnittstellen sind für die Konsumierung durch das Windows Forms\-Datenbindungsmodul vorgesehen:  
  
-   <xref:System.Windows.Forms.IBindableComponent>\-Schnittstelle  
  
     Eine Klasse, die diese Schnittstelle implementiert, ist eine Komponente, die kein Steuerelement darstellt und die die Datenbindung unterstützt.  Diese Klasse gibt die Datenbindungen und den Bindungskontext der Komponente über die <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A>\-Eigenschaft und die <xref:System.Windows.Forms.IBindableComponent.BindingContext%2A>\-Eigenschaft dieser Schnittstelle zurück.  
  
    > [!NOTE]
    >  Wenn eine Komponente von <xref:System.Windows.Forms.Control> erbt, müssen Sie die <xref:System.Windows.Forms.IBindableComponent>\-Schnittstelle nicht implementieren.  
  
-   <xref:System.Windows.Forms.ICurrencyManagerProvider>\-Schnittstelle  
  
     Eine Klasse, die die <xref:System.Windows.Forms.ICurrencyManagerProvider>\-Schnittstelle implementiert, ist eine Komponente mit eigenem <xref:System.Windows.Forms.CurrencyManager>, um die mit dieser Komponente verknüpften Bindungen zu verwalten.  Der Zugriff auf den benutzerdefinierten <xref:System.Windows.Forms.CurrencyManager> wird über die <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A>\-Eigenschaft bereitgestellt.  
  
    > [!NOTE]
    >  Eine Klasse, die von <xref:System.Windows.Forms.Control> erbt, verwaltet Bindungen automatisch über ihre <xref:System.Windows.Forms.Control.BindingContext%2A>\-Eigenschaft. Deshalb muss <xref:System.Windows.Forms.ICurrencyManagerProvider> nur in seltenen Fällen implementiert werden.  
  
## Siehe auch  
 [Datenbindung und Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)   
 [Gewusst wie: Erstellen eines einfach gebundenen Steuerelements in einem Windows Form](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)   
 [Datenbindung in Web Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)