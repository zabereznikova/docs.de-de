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
ms.openlocfilehash: 6c4470b33977408fa4429d187dafd76241d0d9d9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="interfaces-related-to-data-binding"></a>Auf Datenbindung bezogene Schnittstellen
Mit [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] können Sie viele verschiedene Datenstrukturen entsprechend den Bindungsanforderungen der Anwendung und der Daten erstellen, mit denen Sie arbeiten. Möglicherweise möchten Sie eigene Klassen erstellen, die Daten in Windows Forms bereitstellen oder verwenden. Diese Objekte können ein unterschiedliches Maß an Funktionalität und Komplexität bieten, von der Basisdatenbindung bis hin zur Bereitstellung der Unterstützung während der Entwurfszeit, Überprüfung von Fehlern, Benachrichtigung oder sogar Unterstützung für eine strukturierte Zurücksetzung der an den Daten selbst vorgenommenen Änderungen.  
  
## <a name="consumers-of-data-binding-interfaces"></a>Consumer von Datenbindungsschnittstellen  
 In den folgenden Abschnitten werden zwei Gruppen von Benutzeroberflächenobjekten beschrieben. Die erste Gruppe sind die Schnittstellen, die von Datenquellenautoren für Datenquellen implementiert werden. Diese Schnittstellen sollen von Datenquellenconsumern genutzt werden, die in den meisten Fällen Windows Forms-Steuerelemente oder Komponenten sind. Die zweite Gruppe bilden die Schnittstellen, die für die Verwendung durch Komponentenautoren vorgesehen sind. Komponentenautoren verwenden diese Schnittstellen, wenn sie eine Komponente erstellen, die die vom Windows Forms-Datenbindungsmodul zu nutzende Datenbindung unterstützt. Sie können diese Schnittstellen in Klassen im Zusammenhang mit dem Formular implementieren, um die Datenbindung zu aktivieren. Jeder Fall stellt eine Klasse dar, die eine Schnittstelle implementiert, die die Interaktion mit Daten ermöglicht. Visual Studio rapid Application Development, (RAD) Datenentwurfstools nutzen bereits zu dieser Funktionalität.  
  
### <a name="interfaces-for-implementation-by-data-source-authors"></a>Schnittstellen für die Implementierung von Datenquellenautoren  
 Die folgenden Schnittstellen sollen von Windows Forms-Steuerelementen genutzt werden:  
  
-   <xref:System.Collections.IList>-Schnittstelle  
  
     Eine Klasse, implementiert die <xref:System.Collections.IList> Schnittstelle ist möglicherweise ein <xref:System.Array>, <xref:System.Collections.ArrayList>, oder <xref:System.Collections.CollectionBase>. Hierbei handelt es sich um indizierte Listen von Elementen des Typs <xref:System.Object>. Diese Listen müssen homogene Typen enthalten, da das erste Element des Index den Typ bestimmt. <xref:System.Collections.IList> wäre für die Bindung nur zur Laufzeit verfügbar.  
  
    > [!NOTE]
    >  Wenn Sie eine Liste von Geschäftsobjekten für die Bindung mit Windows Forms erstellen möchten, sollten Sie mit der <xref:System.ComponentModel.BindingList%601>. Die <xref:System.ComponentModel.BindingList%601> ist eine erweiterbare-Klasse, die primären für bidirektionale Windows Forms-Datenbindung erforderlichen Schnittstellen implementiert.  
  
-   <xref:System.ComponentModel.IBindingList>-Schnittstelle  
  
     Eine Klasse, implementiert die <xref:System.ComponentModel.IBindingList> Schnittstelle bietet eine viel höhere Datenbindungsfunktion. Diese Implementierung bietet Ihnen die grundlegenden Sortierfunktionen und Änderungsbenachrichtigung für Änderungen der Listenelemente (z.B. wenn das Feld Adresse des dritten Elements in einer Liste von Kunden geändert wurde) und für Änderungen der Liste selbst (z.B. wenn die Anzahl der Elemente in der Liste erhöht oder verringert wird). Änderungsbenachrichtigungen sind wichtig, wenn mehrere Steuerelemente an dieselben Daten gebunden und Datenänderungen in einem der Steuerelemente vorgenommen werden sollen, die an die anderen gebundenen Steuerelemente weitergegeben werden sollen.  
  
    > [!NOTE]
    >  Änderungsbenachrichtigung aktiviert ist, für die <xref:System.ComponentModel.IBindingList> Schnittstelle, über die <xref:System.ComponentModel.IBindingList.SupportsChangeNotification%2A> Eigenschaft die, wenn `true`, löst eine <xref:System.ComponentModel.IBindingList.ListChanged> Ereignis, geändert, der angibt, der Liste geändert oder ein Element in der Liste.  
  
     Die Art der Änderung wird beschrieben, indem Sie die <xref:System.ComponentModel.ListChangedType> Eigenschaft von der <xref:System.ComponentModel.ListChangedEventArgs> Parameter. Wenn das Datenmodell aktualisiert wird, werden daher alle abhängigen Ansichten, wie z.B. andere Steuerelemente, die an die gleiche Datenquelle gebunden sind, ebenfalls aktualisiert. In der Liste enthaltenen Objekte müssen Sie allerdings um die Liste zu benachrichtigen, wenn sie ändern, sodass die Liste auslösen kann die <xref:System.ComponentModel.IBindingList.ListChanged> Ereignis.  
  
    > [!NOTE]
    >  Die <xref:System.ComponentModel.BindingList%601> enthält generische Implementierung der <xref:System.ComponentModel.IBindingList> Schnittstelle.  
  
-   <xref:System.ComponentModel.IBindingListView>-Schnittstelle  
  
     Eine Klasse, die implementiert die <xref:System.ComponentModel.IBindingListView> Schnittstelle bietet alle Funktionen der Implementierung <xref:System.ComponentModel.IBindingList>, ebenso wie Filterung und erweiterte Sortierung. Diese Implementierung bietet zeichenfolgenbasierte Filterung und die mehrspaltige Sortierung mit Eigenschaftendeskriptor-Richtungspaaren.  
  
-   <xref:System.ComponentModel.IEditableObject>-Schnittstelle  
  
     Eine Klasse, implementiert die <xref:System.ComponentModel.IEditableObject> Schnittstelle einem Objekt Gelegenheit zu steuern, wann Änderungen an diesem Objekt dauerhaft gemacht werden. Diese Implementierung entspricht Sie der <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, und <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> -Methoden, die Ihnen ermöglichen, mit dem Objekt vorgenommenen Änderungen ein Rollback auszuführen. Es folgt eine kurze Erläuterung der Funktionsweise der <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, und <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> Methoden und deren Funktionsweise in Verbindung stehen, um ein Rollback für mögliche Änderungen an den Daten zu aktivieren:  
  
    -   Die <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> -Methode signalisiert den Beginn der Bearbeitung eines Objekts. Ein Objekt, das diese Schnittstelle implementiert, müssen alle Updates nach dem Speichern der <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> Methodenaufruf so, dass die Updates können verworfen werden Wenn die <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> -Methode aufgerufen wird. Sie können in Windows Forms-Datenbindung Aufrufen <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> mehrmals bearbeiten Sie innerhalb des Bereichs einer einzelnen Transaktion (z. B. <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>). Implementierungen von <xref:System.ComponentModel.IEditableObject> sollten nachverfolgen, ob <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> bereits aufgerufen wurde und ignoriert nachfolgende Aufrufe <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>. Da diese Methode mehrmals aufgerufen werden kann, ist es wichtig, dass nachfolgende Aufrufe zerstörerisch sind; d. h. nachfolgende <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> Aufrufe können nicht zerstört werden die Updates, die vorgenommen wurden, oder ändern die Daten, die gespeichert wurde auf dem ersten <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> aufrufen.  
  
    -   Die <xref:System.ComponentModel.IEditableObject.EndEdit%2A> Methode legt alle Änderungen seit <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> wurde in der zugrunde liegenden Objekt aufgerufen, wenn das Objekt derzeit im Bearbeitungsmodus befindet.  
  
    -   Die <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> -Methode verwirft alle Änderungen an das Objekt.  
  
     Weitere Informationen darüber, wie die <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, und <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> Methoden arbeiten, finden Sie unter [Daten wieder in der Datenbank speichern](/visualstudio/data-tools/save-data-back-to-the-database).  
  
     Dieses Konzept transaktionale Data-Funktionalität wird verwendet, durch die <xref:System.Windows.Forms.DataGridView> Steuerelement.  
  
-   <xref:System.ComponentModel.ICancelAddNew>-Schnittstelle  
  
     Eine Klasse, implementiert die <xref:System.ComponentModel.ICancelAddNew> Schnittstelle in der Regel implementiert die <xref:System.ComponentModel.IBindingList> Schnittstelle und ermöglicht Ihnen, ein Rollback Zusatz versucht, die Datenquelle mit der <xref:System.ComponentModel.IBindingList.AddNew%2A> Methode. Wenn die Datenquelle implementiert die <xref:System.ComponentModel.IBindingList> -Schnittstelle, Sie sollten außerdem haben sie implementieren die <xref:System.ComponentModel.ICancelAddNew> Schnittstelle.  
  
-   <xref:System.ComponentModel.IDataErrorInfo>-Schnittstelle  
  
     Eine Klasse, implementiert die <xref:System.ComponentModel.IDataErrorInfo> Schnittstelle ermöglicht es Objekten, die benutzerdefinierten Fehlerinformationen datengebundene Steuerelemente zu bieten:  
  
    -   Die <xref:System.ComponentModel.IDataErrorInfo.Error%2A> Eigenschaft gibt die allgemeine Fehlermeldungstext zurück (z. B. "Fehler").  
  
    -   Die <xref:System.ComponentModel.IDataErrorInfo.Item%2A> Eigenschaft gibt eine Zeichenfolge mit der Fehlermeldung zurück, aus der Spalte (z. B. "der Wert in der `State` Spalte ist ungültig").  
  
-   <xref:System.Collections.IEnumerable>-Schnittstelle  
  
     Eine Klasse, implementiert die <xref:System.Collections.IEnumerable> Schnittstelle in der Regel durch belegt [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]. Windows Forms-Unterstützung für diese Schnittstelle ist nur verfügbar, bis die <xref:System.Windows.Forms.BindingSource> Komponente.  
  
    > [!NOTE]
    >  Die <xref:System.Windows.Forms.BindingSource> Komponente kopiert alle <xref:System.Collections.IEnumerable> Elemente in einer separaten Liste Bindungszwecken.  
  
-   <xref:System.ComponentModel.ITypedList>-Schnittstelle  
  
     Eine Auflistungsklasse, implementiert die <xref:System.ComponentModel.ITypedList> Schnittstelle bietet die Möglichkeit zur Steuerung der Reihenfolge und den Satz von Eigenschaften, die für das gebundene Steuerelement verfügbar gemacht.  
  
    > [!NOTE]
    >  Beim Implementieren der <xref:System.ComponentModel.ITypedList.GetItemProperties%2A> -Methode, und die <xref:System.ComponentModel.PropertyDescriptor> Array ist nicht null, ist des letzten Eintrags im Array der Eigenschaftendeskriptor, der die List-Eigenschaft beschreibt, die eine andere Liste der Elemente ist.  
  
-   <xref:System.ComponentModel.ICustomTypeDescriptor>-Schnittstelle  
  
     Eine Klasse, implementiert die <xref:System.ComponentModel.ICustomTypeDescriptor> Schnittstelle bietet dynamische Informationen über sich selbst. Diese Schnittstelle ähnelt <xref:System.ComponentModel.ITypedList> wird jedoch für Objekte, sondern Listen verwendet. Diese Schnittstelle wird verwendet, indem <xref:System.Data.DataRowView> , das Schema der zugrunde liegenden Zeilen zu projizieren. Eine einfache Implementierung der <xref:System.ComponentModel.ICustomTypeDescriptor> wird bereitgestellt, indem Sie die <xref:System.ComponentModel.CustomTypeDescriptor> Klasse.  
  
    > [!NOTE]
    >  Zur Unterstützung der Bindung zur Entwurfszeit Typen implementiert, <xref:System.ComponentModel.ICustomTypeDescriptor>, der Typ muss auch implementieren <xref:System.ComponentModel.IComponent> und als eine Instanz im Formular vorhanden ist.  
  
-   <xref:System.ComponentModel.IListSource>-Schnittstelle  
  
     Eine Klasse, implementiert die <xref:System.ComponentModel.IListSource> Schnittstelle ermöglicht listenbasierte Bindung für nicht-List-Objekte. Die <xref:System.ComponentModel.IListSource.GetList%2A> Methode <xref:System.ComponentModel.IListSource> wird verwendet, um eine bindbare Liste von einem Objekt zurückzugeben, die nicht von erbt <xref:System.Collections.IList>. <xref:System.ComponentModel.IListSource> wird verwendet, durch die <xref:System.Data.DataSet> Klasse.  
  
-   <xref:System.ComponentModel.IRaiseItemChangedEvents>-Schnittstelle  
  
     Eine Klasse, implementiert die <xref:System.ComponentModel.IRaiseItemChangedEvents> Schnittstelle ist eine bindbare Liste, die implementiert außerdem die <xref:System.ComponentModel.IBindingList> Schnittstelle. Diese Schnittstelle wird verwendet, um anzugeben, ob Ihr Typ löst <xref:System.ComponentModel.IBindingList.ListChanged> Ereignisse des Typs <xref:System.ComponentModel.ListChangedType.ItemChanged> über seine <xref:System.ComponentModel.IRaiseItemChangedEvents.RaisesItemChangedEvents%2A> Eigenschaft.  
  
    > [!NOTE]
    >  Implementieren Sie die <xref:System.ComponentModel.IRaiseItemChangedEvents> Wenn Ihre Datenquelle die Eigenschaft, die zuvor beschriebenen Konvertierung enthält und damit interagieren ist die <xref:System.Windows.Forms.BindingSource> Komponente. Andernfalls die <xref:System.Windows.Forms.BindingSource> führt auch die Eigenschaft, um die Konvertierung zu Leistungseinbußen.  
  
-   <xref:System.ComponentModel.ISupportInitialize>-Schnittstelle  
  
     Eine Komponente, implementiert die <xref:System.ComponentModel.ISupportInitialize> Schnittstelle nutzt die Vorteile von Batchoptimierungen für das Festlegen von Eigenschaften und Co-abhängige Eigenschaften zu initialisieren. Die <xref:System.ComponentModel.ISupportInitialize> enthält zwei Methoden:  
  
    -   <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> signalisiert, dass die objektinitialisierung beginnt.  
  
    -   <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> signalisiert, dass es sich bei die objektinitialisierung beendet wird.  
  
-   <xref:System.ComponentModel.ISupportInitializeNotification>-Schnittstelle  
  
     Eine Komponente, implementiert die <xref:System.ComponentModel.ISupportInitializeNotification> Schnittstelle auch implementiert die <xref:System.ComponentModel.ISupportInitialize> Schnittstelle. Diese Schnittstelle bietet die Möglichkeit, anderen benachrichtigen <xref:System.ComponentModel.ISupportInitialize> Komponenten, dass die Initialisierung abgeschlossen ist. Die <xref:System.ComponentModel.ISupportInitializeNotification> Schnittstelle enthält zwei Elemente:  
  
    -   <xref:System.ComponentModel.ISupportInitializeNotification.IsInitialized%2A> Gibt eine `boolean` Wert, der angibt, ob die Komponente initialisiert wird.  
  
    -   <xref:System.ComponentModel.ISupportInitializeNotification.Initialized> Tritt auf, wenn <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> aufgerufen wird.  
  
-   <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle  
  
     Eine Klasse, die diese Schnittstelle implementiert, ist ein Typ, der ein Ereignis auslöst, wenn sich einer der Eigenschaftswerte ändert. Diese Schnittstelle soll das Muster ersetzen, dass für jede Eigenschaft eines Steuerelements ein Änderungsereignis vorhanden ist. Bei der Verwendung in einer <xref:System.ComponentModel.BindingList%601>, sollte ein Geschäftsobjekt implementieren die <xref:System.ComponentModel.INotifyPropertyChanged> -Schnittstelle\`1 konvertiert <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> Ereignisse <xref:System.ComponentModel.BindingList%601.ListChanged> Ereignisse des Typs <xref:System.ComponentModel.ListChangedType.ItemChanged>.  
  
    > [!NOTE]
    >  Für Change Benachrichtigung in einer Bindung zwischen einem gebundenen Client und einem auftreten Datenquellentyp die gebundene Datenquelle sollten entweder implementieren die <xref:System.ComponentModel.INotifyPropertyChanged> -Schnittstelle (bevorzugt fest), oder Sie können bereitstellen *PropertyName* `Changed` Ereignisse für den Typ gebunden, aber Sie sollten nicht beide Methoden.  
  
### <a name="interfaces-for-implementation-by-component-authors"></a>Schnittstellen für die Implementierung von Komponentenautoren  
 Die folgenden Schnittstellen sind für die Nutzung durch das Windows Forms-Datenbindungsmodul ausgelegt:  
  
-   <xref:System.Windows.Forms.IBindableComponent>-Schnittstelle  
  
     Eine Klasse, die diese Schnittstelle implementiert, ist eine Nichtsteuerungskomponente, die die Datenbindung unterstützt. Diese Klasse gibt die datenbindungen und Bindungskontext verwendet der Komponente durch die <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> und <xref:System.Windows.Forms.IBindableComponent.BindingContext%2A> Eigenschaften dieser Schnittstelle.  
  
    > [!NOTE]
    >  Falls die Komponente erbt <xref:System.Windows.Forms.Control>, Sie müssen nicht zum Implementieren der <xref:System.Windows.Forms.IBindableComponent> Schnittstelle.  
  
-   <xref:System.Windows.Forms.ICurrencyManagerProvider>-Schnittstelle  
  
     Eine Klasse, implementiert die <xref:System.Windows.Forms.ICurrencyManagerProvider> Schnittstelle ist eine Komponente, die einen eigenen bietet <xref:System.Windows.Forms.CurrencyManager> zum Verwalten der Bindungen, die diese bestimmte Komponente zugeordnet. Zugriff auf die benutzerdefinierte <xref:System.Windows.Forms.CurrencyManager> wird bereitgestellt, indem Sie die <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A> Eigenschaft.  
  
    > [!NOTE]
    >  Eine Klasse, die von erben <xref:System.Windows.Forms.Control> verwaltet Bindungen automatisch über seine <xref:System.Windows.Forms.Control.BindingContext%2A> -Eigenschaft, die dies der Fall ist Fälle, in denen Sie implementieren müssen, die <xref:System.Windows.Forms.ICurrencyManagerProvider> treten relativ selten ein.  
  
## <a name="see-also"></a>Siehe auch  
 [Datenbindung und Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [Vorgehensweise: Erstellen eines einfach gebundenen Steuerelements in einem Windows Form](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)  
 [Windows Forms-Datenbindung](../../../docs/framework/winforms/windows-forms-data-binding.md)
