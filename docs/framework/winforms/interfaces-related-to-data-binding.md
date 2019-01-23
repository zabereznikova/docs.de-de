---
title: Auf Datenbindung bezogene Schnittstellen
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], data-binding interfaces
- INotifyPropertyChanged interface
- IBindingListView interface
- IList interface [Windows Forms], Windows Forms data binding
- IBindingList interface [Windows Forms], Windows Forms data binding
- interfaces [Windows Forms], Windows Forms data binding
- IEditableObject interface [Windows Forms], Windows Forms data binding
- data binding [Windows Forms], interfaces
- IDataErrorInfo interface [Windows Forms], Windows Forms data binding
ms.assetid: 14e49a2e-3e46-47ca-b491-70d546333277
ms.openlocfilehash: 5a83198a665563c3d283cac042c9fec95c60f8e2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547130"
---
# <a name="interfaces-related-to-data-binding"></a>Auf Datenbindung bezogene Schnittstellen
Mit [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] können Sie viele verschiedene Datenstrukturen entsprechend den Bindungsanforderungen der Anwendung und der Daten erstellen, mit denen Sie arbeiten. Möglicherweise möchten Sie eigene Klassen erstellen, die Daten in Windows Forms bereitstellen oder verwenden. Diese Objekte können ein unterschiedliches Maß an Funktionalität und Komplexität bieten, von der Basisdatenbindung bis hin zur Bereitstellung der Unterstützung während der Entwurfszeit, Überprüfung von Fehlern, Benachrichtigung oder sogar Unterstützung für eine strukturierte Zurücksetzung der an den Daten selbst vorgenommenen Änderungen.  
  
## <a name="consumers-of-data-binding-interfaces"></a>Consumer von Datenbindungsschnittstellen  
 In den folgenden Abschnitten werden zwei Gruppen von Benutzeroberflächenobjekten beschrieben. Die erste Gruppe sind die Schnittstellen, die von Datenquellenautoren für Datenquellen implementiert werden. Diese Schnittstellen sollen von Datenquellenconsumern genutzt werden, die in den meisten Fällen Windows Forms-Steuerelemente oder Komponenten sind. Die zweite Gruppe bilden die Schnittstellen, die für die Verwendung durch Komponentenautoren vorgesehen sind. Komponentenautoren verwenden diese Schnittstellen, wenn sie eine Komponente erstellen, die die von der Windows Forms-Datenbindungs-Engine zu nutzende Datenbindung unterstützt. Sie können diese Schnittstellen in Klassen im Zusammenhang mit dem Formular implementieren, um die Datenbindung zu aktivieren. Jeder Fall stellt eine Klasse dar, die eine Schnittstelle implementiert, die die Interaktion mit Daten ermöglicht. Visual Studio rapid Application Development (RAD)-Datenentwurfstools nutzen bereits die Vorteile dieser Funktionen.  
  
### <a name="interfaces-for-implementation-by-data-source-authors"></a>Schnittstellen für die Implementierung von Datenquellenautoren  
 Die folgenden Schnittstellen sollen von Windows Forms-Steuerelementen genutzt werden:  
  
-   <xref:System.Collections.IList>-Schnittstelle  
  
     Eine Klasse, implementiert die <xref:System.Collections.IList> Schnittstelle ist möglicherweise ein <xref:System.Array>, <xref:System.Collections.ArrayList>, oder <xref:System.Collections.CollectionBase>. Dies sind indizierte Listen von Elementen vom Typ <xref:System.Object>. Diese Listen müssen homogene Typen enthalten, da das erste Element des Index den Typ bestimmt. <xref:System.Collections.IList> wäre für die Bindung nur zur Laufzeit verfügbar.  
  
    > [!NOTE]
    >  Wenn Sie eine Liste von Geschäftsobjekten für die Bindung mit Windows Forms erstellen möchten, sollten Sie mit der <xref:System.ComponentModel.BindingList%601>. Die <xref:System.ComponentModel.BindingList%601> ist eine erweiterbare-Klasse, die die primären Schnittstellen für bidirektionale Windows Forms-Datenbindung implementiert.  
  
-   <xref:System.ComponentModel.IBindingList>-Schnittstelle  
  
     Eine Klasse, implementiert die <xref:System.ComponentModel.IBindingList> Schnittstelle bietet eine viel höhere Datenbindungsfunktionen. Diese Implementierung bietet Ihnen die grundlegenden Sortierfunktionen und Änderungsbenachrichtigung für Änderungen der Listenelemente (z.B. wenn das Feld Adresse des dritten Elements in einer Liste von Kunden geändert wurde) und für Änderungen der Liste selbst (z.B. wenn die Anzahl der Elemente in der Liste erhöht oder verringert wird). Änderungsbenachrichtigungen sind wichtig, wenn mehrere Steuerelemente an dieselben Daten gebunden und Datenänderungen in einem der Steuerelemente vorgenommen werden sollen, die an die anderen gebundenen Steuerelemente weitergegeben werden sollen.  
  
    > [!NOTE]
    >  Für die änderungsbenachrichtigung aktiviert ist die <xref:System.ComponentModel.IBindingList> Schnittstelle, über die <xref:System.ComponentModel.IBindingList.SupportsChangeNotification%2A> Eigenschaft die, wenn `true`, löst eine <xref:System.ComponentModel.IBindingList.ListChanged> Ereignis, geändert, der angibt, die Liste, die geändert oder ein Element in der Liste.  
  
     Der Typ der Änderung von beschrieben wird die <xref:System.ComponentModel.ListChangedType> Eigenschaft der <xref:System.ComponentModel.ListChangedEventArgs> Parameter. Wenn das Datenmodell aktualisiert wird, werden daher alle abhängigen Ansichten, wie z.B. andere Steuerelemente, die an die gleiche Datenquelle gebunden sind, ebenfalls aktualisiert. In der Liste enthaltene Objekte müssen jedoch auf die Liste zu benachrichtigen, wenn sie ändern, sodass die Liste auslösen kann die <xref:System.ComponentModel.IBindingList.ListChanged> Ereignis.  
  
    > [!NOTE]
    >  Die <xref:System.ComponentModel.BindingList%601> stellt eine generische Implementierung von der <xref:System.ComponentModel.IBindingList> Schnittstelle.  
  
-   <xref:System.ComponentModel.IBindingListView>-Schnittstelle  
  
     Eine Klasse, implementiert die <xref:System.ComponentModel.IBindingListView> Schnittstelle bietet alle Funktionen für die Implementierung von <xref:System.ComponentModel.IBindingList>, sowie Filterung und erweiterte Sortierung. Diese Implementierung bietet zeichenfolgenbasierte Filterung und die mehrspaltige Sortierung mit Eigenschaftendeskriptor-Richtungspaaren.  
  
-   <xref:System.ComponentModel.IEditableObject>-Schnittstelle  
  
     Eine Klasse, implementiert die <xref:System.ComponentModel.IEditableObject> Schnittstelle ermöglicht es, ein Objekt zu steuern, wann Änderungen an diesem Objekt festgelegt werden. Diese Implementierung bietet Ihnen die <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, und <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> Methoden, die Ihnen ermöglichen, Rollback von Änderungen auf das Objekt. Es folgt eine kurze Erläuterung der Funktionsweise der <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, und <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> Methoden und deren Funktionsweise in Verbindung miteinander, um das Zurücksetzen von Änderungen an den Daten zu aktivieren:  
  
    -   Die <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> -Methode signalisiert den Start der Bearbeitung eines Objekts. Ein Objekt, das diese Schnittstelle implementiert, müssen alle Updates nach dem Speichern der <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> Methodenaufruf so, dass die Updates verworfen werden können Wenn die <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> Methode wird aufgerufen. Sie können in Windows Forms-Datenbindung Aufrufen <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> mehrmals innerhalb des Bereichs einer einzelnen Bearbeitungstransaktion (z. B. <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>). Implementierungen von <xref:System.ComponentModel.IEditableObject> sollten nachverfolgen, ob <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> bereits aufgerufen wurde, und ignorieren Sie nachfolgende Aufrufe von <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>. Da diese Methode mehrmals aufgerufen werden kann, ist es wichtig, dass nachfolgende Aufrufe nicht destruktiv sind; d. h. nachfolgende <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> Aufrufe können nicht zerstört werden die Updates, die vorgenommen wurden, oder ändern Sie die Daten, die gespeichert wurde auf dem ersten <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> aufrufen.  
  
    -   Die <xref:System.ComponentModel.IEditableObject.EndEdit%2A> -Methode überträgt alle Änderungen seit <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> wurde in der zugrunde liegenden Objekt aufgerufen, wenn das Objekt gerade im Bearbeitungsmodus befindet.  
  
    -   Die <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> -Methode verwirft alle Änderungen, die auf das Objekt.  
  
     Weitere Informationen zur Funktionsweise des <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, und <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> Methoden funktionieren, finden Sie unter [Rückspeichern von Daten in der Datenbank](/visualstudio/data-tools/save-data-back-to-the-database).  
  
     Dieser Transaktionsaspekt der Datenfunktionen wird verwendet, durch die <xref:System.Windows.Forms.DataGridView> Steuerelement.  
  
-   <xref:System.ComponentModel.ICancelAddNew>-Schnittstelle  
  
     Eine Klasse, implementiert die <xref:System.ComponentModel.ICancelAddNew> -Schnittstelle implementiert, in der Regel die <xref:System.ComponentModel.IBindingList> Schnittstelle und ermöglicht es Ihnen, einen Zusatz zu der Datenquelle mit Rollback der <xref:System.ComponentModel.IBindingList.AddNew%2A> Methode. Wenn die Datenquelle implementiert die <xref:System.ComponentModel.IBindingList> -Schnittstelle, Sie sollten auch haben sie implementieren die <xref:System.ComponentModel.ICancelAddNew> Schnittstelle.  
  
-   <xref:System.ComponentModel.IDataErrorInfo>-Schnittstelle  
  
     Eine Klasse, implementiert die <xref:System.ComponentModel.IDataErrorInfo> Schnittstelle ermöglicht es Objekten, benutzerdefinierte Fehlerinformationen zu gebundenen Steuerelementen anzubieten:  
  
    -   Die <xref:System.ComponentModel.IDataErrorInfo.Error%2A> -Eigenschaft gibt allgemeinen Fehlermeldungstext zurück (z. B. "Fehler").  
  
    -   Die <xref:System.ComponentModel.IDataErrorInfo.Item%2A> Eigenschaft eine Zeichenfolge mit der spezifischen Fehlermeldung zurück, aus der Spalte (z. B. "den Wert in der `State` Spalte ist ungültig.").  
  
-   <xref:System.Collections.IEnumerable>-Schnittstelle  
  
     Eine Klasse, implementiert die <xref:System.Collections.IEnumerable> Schnittstelle wird durch die in der Regel verbraucht [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]. Windows Forms-Unterstützung für diese Schnittstelle ist nur verfügbar, über die <xref:System.Windows.Forms.BindingSource> Komponente.  
  
    > [!NOTE]
    >  Die <xref:System.Windows.Forms.BindingSource> -Komponente kopiert alle <xref:System.Collections.IEnumerable> Elemente in eine separate Liste für eine Bindung herangezogen.  
  
-   <xref:System.ComponentModel.ITypedList>-Schnittstelle  
  
     Eine Auflistungsklasse, die implementiert die <xref:System.ComponentModel.ITypedList> Schnittstelle bietet die Möglichkeit zur Steuerung der Reihenfolge und den Satz von Eigenschaften, die für das gebundene Steuerelement verfügbar gemacht.  
  
    > [!NOTE]
    >  Bei der Implementierung der <xref:System.ComponentModel.ITypedList.GetItemProperties%2A> -Methode, und die <xref:System.ComponentModel.PropertyDescriptor> Array nicht null ist, werden des letzten Eintrags im Array der Eigenschaftendeskriptor, der die Listeneigenschaft beschreibt, die eine andere Liste von Elementen ist.  
  
-   <xref:System.ComponentModel.ICustomTypeDescriptor>-Schnittstelle  
  
     Eine Klasse, implementiert die <xref:System.ComponentModel.ICustomTypeDescriptor> Schnittstelle stellt dynamische Informationen über sich selbst bereit. Diese Schnittstelle ähnelt <xref:System.ComponentModel.ITypedList> wird jedoch für Objekte, sondern Listen verwendet. Diese Schnittstelle wird verwendet, indem <xref:System.Data.DataRowView> , das Schema der zugrunde liegenden Zeilen zu projizieren. Eine einfache Implementierung der <xref:System.ComponentModel.ICustomTypeDescriptor> erfolgt über die <xref:System.ComponentModel.CustomTypeDescriptor> Klasse.  
  
    > [!NOTE]
    >  Zur Unterstützung von entwurfszeitbindung an Typen implementiert <xref:System.ComponentModel.ICustomTypeDescriptor>, der Typ muss auch implementieren <xref:System.ComponentModel.IComponent> und als eine Instanz auf dem Formular vorhanden sein.  
  
-   <xref:System.ComponentModel.IListSource>-Schnittstelle  
  
     Eine Klasse, implementiert die <xref:System.ComponentModel.IListSource> Schnittstelle ermöglicht die listenbasierte Bindung auf nichtlistenobjekten. Die <xref:System.ComponentModel.IListSource.GetList%2A> -Methode der <xref:System.ComponentModel.IListSource> wird verwendet, um eine bindbare Liste von einem Objekt zurückzugeben, die nicht von erbt <xref:System.Collections.IList>. <xref:System.ComponentModel.IListSource> wird verwendet, durch die <xref:System.Data.DataSet> Klasse.  
  
-   <xref:System.ComponentModel.IRaiseItemChangedEvents>-Schnittstelle  
  
     Eine Klasse, implementiert die <xref:System.ComponentModel.IRaiseItemChangedEvents> Schnittstelle ist eine bindbare Liste, die auch implementiert die <xref:System.ComponentModel.IBindingList> Schnittstelle. Diese Schnittstelle wird verwendet, um anzugeben, ob Ihr Typ löst <xref:System.ComponentModel.IBindingList.ListChanged> Ereignisse des Typs <xref:System.ComponentModel.ListChangedType.ItemChanged> über seine <xref:System.ComponentModel.IRaiseItemChangedEvents.RaisesItemChangedEvents%2A> Eigenschaft.  
  
    > [!NOTE]
    >  Implementieren Sie die <xref:System.ComponentModel.IRaiseItemChangedEvents> , wenn Sie die Datenquelle die Eigenschaft, die zuvor beschriebene ereigniskonvertierung aufzulisten stellt und damit interagieren ist die <xref:System.Windows.Forms.BindingSource> Komponente. Andernfalls die <xref:System.Windows.Forms.BindingSource> führt auch die Eigenschaft ereigniskonvertierung aufzulisten, was zu Leistungseinbußen.  
  
-   <xref:System.ComponentModel.ISupportInitialize>-Schnittstelle  
  
     Eine Komponente, implementiert die <xref:System.ComponentModel.ISupportInitialize> Schnittstelle nutzt die Vorteile von Batchoptimierungen, um Eigenschaften festzulegen und Eigenschaften zu initialisieren. Die <xref:System.ComponentModel.ISupportInitialize> enthält zwei Methoden:  
  
    -   <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> signalisiert, dass die objektinitialisierung beginnt.  
  
    -   <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> signalisiert, dass die objektinitialisierung beendet wird.  
  
-   <xref:System.ComponentModel.ISupportInitializeNotification>-Schnittstelle  
  
     Eine Komponente, implementiert die <xref:System.ComponentModel.ISupportInitializeNotification> -Schnittstelle auch implementiert die <xref:System.ComponentModel.ISupportInitialize> Schnittstelle. Diese Schnittstelle ermöglicht es Ihnen, die für Benachrichtigungen <xref:System.ComponentModel.ISupportInitialize> Komponenten, dass die Initialisierung abgeschlossen ist. Die <xref:System.ComponentModel.ISupportInitializeNotification> -Schnittstelle enthält zwei Elemente:  
  
    -   <xref:System.ComponentModel.ISupportInitializeNotification.IsInitialized%2A> Gibt eine `boolean` Wert, der angibt, ob die Komponente initialisiert wurde.  
  
    -   <xref:System.ComponentModel.ISupportInitializeNotification.Initialized> Tritt auf, wenn <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> aufgerufen wird.  
  
-   <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle  
  
     Eine Klasse, die diese Schnittstelle implementiert, ist ein Typ, der ein Ereignis auslöst, wenn sich einer der Eigenschaftswerte ändert. Diese Schnittstelle soll das Muster ersetzen, dass für jede Eigenschaft eines Steuerelements ein Änderungsereignis vorhanden ist. Bei der Verwendung in einer <xref:System.ComponentModel.BindingList%601>, sollte ein Geschäftsobjekt, das Implementieren der <xref:System.ComponentModel.INotifyPropertyChanged> -Schnittstelle und die BindingList\`1 konvertiert <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> Ereignisse <xref:System.ComponentModel.BindingList%601.ListChanged> Ereignisse des Typs <xref:System.ComponentModel.ListChangedType.ItemChanged>.  
  
    > [!NOTE]
    >  Änderung Benachrichtigung in der eine Bindung zwischen einem gebundenen Client und einer Datenquelle auftreten Quelle den Typ der gebundenen Datenquelle sollten entweder implementieren die <xref:System.ComponentModel.INotifyPropertyChanged> -Schnittstelle (bevorzugt) oder bieten *PropertyName* `Changed` Ereignisse für den Typ gebunden, aber Sie sollten nicht beide Methoden verwenden.  
  
### <a name="interfaces-for-implementation-by-component-authors"></a>Schnittstellen für die Implementierung von Komponentenautoren  
 Die folgenden Schnittstellen sind für die Nutzung durch die Windows Forms-Datenbindungs-Engine ausgelegt:  
  
-   <xref:System.Windows.Forms.IBindableComponent>-Schnittstelle  
  
     Eine Klasse, die diese Schnittstelle implementiert, ist eine Nichtsteuerungskomponente, die die Datenbindung unterstützt. Diese Klasse gibt die datenbindungen und den Bindungskontext der Komponente über die <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> und <xref:System.Windows.Forms.IBindableComponent.BindingContext%2A> Eigenschaften dieser Schnittstelle.  
  
    > [!NOTE]
    >  Wenn Ihre Komponente erbt <xref:System.Windows.Forms.Control>, Sie müssen nicht zum Implementieren der <xref:System.Windows.Forms.IBindableComponent> Schnittstelle.  
  
-   <xref:System.Windows.Forms.ICurrencyManagerProvider>-Schnittstelle  
  
     Eine Klasse, implementiert die <xref:System.Windows.Forms.ICurrencyManagerProvider> Schnittstelle ist eine Komponente, die ein eigenes <xref:System.Windows.Forms.CurrencyManager> , die mit dieser bestimmten Komponente verknüpften Bindungen zu verwalten. Zugriff auf den benutzerdefinierten <xref:System.Windows.Forms.CurrencyManager> erfolgt über die <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A> Eigenschaft.  
  
    > [!NOTE]
    >  Eine Klasse, die von erbt <xref:System.Windows.Forms.Control> verwaltet die Bindungen automatisch über die <xref:System.Windows.Forms.Control.BindingContext%2A> -Eigenschaft, also Fälle, in dem Sie implementieren müssen, die <xref:System.Windows.Forms.ICurrencyManagerProvider> sind ziemlich selten.  
  
## <a name="see-also"></a>Siehe auch
- [Datenbindung und Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
- [Vorgehensweise: Erstellen eines einfach gebundenen Steuerelements in Windows Forms](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [Windows Forms-Datenbindung](../../../docs/framework/winforms/windows-forms-data-binding.md)
