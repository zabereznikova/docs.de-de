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
ms.openlocfilehash: 9f102b584d2ed0b5a9d2bbb0e7ce3f7871ec40b2
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046368"
---
# <a name="interfaces-related-to-data-binding"></a>Auf Datenbindung bezogene Schnittstellen

Mit ADO.net können Sie viele verschiedene Datenstrukturen erstellen, die den Bindungs Anforderungen Ihrer Anwendung und der Daten entsprechen, mit denen Sie arbeiten. Möglicherweise möchten Sie eigene Klassen erstellen, die Daten in Windows Forms bereitstellen oder verwenden. Diese Objekte können ein unterschiedliches Maß an Funktionalität und Komplexität bieten, von der Basisdatenbindung bis hin zur Bereitstellung der Unterstützung während der Entwurfszeit, Überprüfung von Fehlern, Benachrichtigung oder sogar Unterstützung für eine strukturierte Zurücksetzung der an den Daten selbst vorgenommenen Änderungen.

## <a name="consumers-of-data-binding-interfaces"></a>Consumer von Datenbindungsschnittstellen

In den folgenden Abschnitten werden zwei Gruppen von Benutzeroberflächenobjekten beschrieben. Die erste Gruppe sind die Schnittstellen, die von Datenquellenautoren für Datenquellen implementiert werden. Diese Schnittstellen sollen von Datenquellenconsumern genutzt werden, die in den meisten Fällen Windows Forms-Steuerelemente oder Komponenten sind. Die zweite Gruppe bilden die Schnittstellen, die für die Verwendung durch Komponentenautoren vorgesehen sind. Komponentenautoren verwenden diese Schnittstellen, wenn sie eine Komponente erstellen, die die von der Windows Forms-Datenbindungs-Engine zu nutzende Datenbindung unterstützt. Sie können diese Schnittstellen in Klassen im Zusammenhang mit dem Formular implementieren, um die Datenbindung zu aktivieren. Jeder Fall stellt eine Klasse dar, die eine Schnittstelle implementiert, die die Interaktion mit Daten ermöglicht. Die Tools für die Entwicklung von Daten in Visual Studio (Rapid Application Development, Rad) nutzen diese Funktionen bereits.

### <a name="interfaces-for-implementation-by-data-source-authors"></a>Schnittstellen für die Implementierung von Datenquellenautoren

Die folgenden Schnittstellen sollen von Windows Forms-Steuerelementen genutzt werden:

- <xref:System.Collections.IList>berfläche

  Eine Klasse, die die <xref:System.Collections.IList> -Schnittstelle implementiert <xref:System.Array>, <xref:System.Collections.ArrayList>kann, <xref:System.Collections.CollectionBase>oder sein. Dabei handelt es sich um indizierte Listen <xref:System.Object>von Elementen des Typs. Diese Listen müssen homogene Typen enthalten, da das erste Element des Index den Typ bestimmt. <xref:System.Collections.IList>steht nur zur Laufzeit für die Bindung zur Verfügung.

  > [!NOTE]
  > Wenn Sie eine Liste von Geschäftsobjekten für die Bindung mit Windows Forms erstellen möchten, sollten Sie die Verwendung des <xref:System.ComponentModel.BindingList%601>-Objekts in Erwägung gezogen. <xref:System.ComponentModel.BindingList%601> Ist eine erweiterbare Klasse, die die primären Schnittstellen implementiert, die für die bidirektionale Windows Forms Datenbindung erforderlich sind.

- <xref:System.ComponentModel.IBindingList>berfläche

  Eine Klasse, die die <xref:System.ComponentModel.IBindingList> -Schnittstelle implementiert, bietet ein viel höheres Maß an Daten Bindungs Funktionalität. Diese Implementierung bietet Ihnen die grundlegenden Sortierfunktionen und Änderungsbenachrichtigung für Änderungen der Listenelemente (z.B. wenn das Feld Adresse des dritten Elements in einer Liste von Kunden geändert wurde) und für Änderungen der Liste selbst (z.B. wenn die Anzahl der Elemente in der Liste erhöht oder verringert wird). Änderungsbenachrichtigungen sind wichtig, wenn mehrere Steuerelemente an dieselben Daten gebunden und Datenänderungen in einem der Steuerelemente vorgenommen werden sollen, die an die anderen gebundenen Steuerelemente weitergegeben werden sollen.

  > [!NOTE]
  > Die Änderungs Benachrichtigung wird für die <xref:System.ComponentModel.IBindingList> -Schnittstelle <xref:System.ComponentModel.IBindingList.SupportsChangeNotification%2A> durch die-Eigenschaft `true`aktiviert, die <xref:System.ComponentModel.IBindingList.ListChanged> , wenn, ein-Ereignis auslöst, das angibt, dass die Liste geändert oder ein Element in der Liste geändert wurde.

  Der Typ der Änderung wird von der <xref:System.ComponentModel.ListChangedType> -Eigenschaft <xref:System.ComponentModel.ListChangedEventArgs> des-Parameters beschrieben. Wenn das Datenmodell aktualisiert wird, werden daher alle abhängigen Ansichten, wie z.B. andere Steuerelemente, die an die gleiche Datenquelle gebunden sind, ebenfalls aktualisiert. In der Liste enthaltene Objekte müssen die Liste jedoch Benachrichtigen, wenn Sie sich ändern, sodass die Liste das <xref:System.ComponentModel.IBindingList.ListChanged> Ereignis ausgeben kann.

  > [!NOTE]
  > Stellt eine generische Implementierung <xref:System.ComponentModel.IBindingList> der-Schnittstelle bereit. <xref:System.ComponentModel.BindingList%601>

- <xref:System.ComponentModel.IBindingListView>berfläche

  Eine Klasse, die die <xref:System.ComponentModel.IBindingListView> -Schnittstelle implementiert, bietet alle Funktionen einer <xref:System.ComponentModel.IBindingList>Implementierung von sowie Filter und erweiterte Sortierfunktionen. Diese Implementierung bietet zeichenfolgenbasierte Filterung und die mehrspaltige Sortierung mit Eigenschaftendeskriptor-Richtungspaaren.

- <xref:System.ComponentModel.IEditableObject>berfläche

  Eine Klasse, die die <xref:System.ComponentModel.IEditableObject> -Schnittstelle implementiert, ermöglicht einem Objekt, zu steuern, wann Änderungen an diesem Objekt dauerhaft gemacht werden. Diese Implementierung bietet Ihnen die <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>Methoden <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, und <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> , mit denen Sie die an dem Objekt vorgenommenen Änderungen zurücksetzen können. Im folgenden finden Sie eine kurze Erläuterung der Funktionsweise <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>der <xref:System.ComponentModel.IEditableObject.EndEdit%2A>Methoden, <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> und und deren Funktionsweise in Verbindung mit einander, um ein mögliches Rollback der an den Daten vorgenommenen Änderungen zu ermöglichen:

  - Die <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> -Methode signalisiert den Anfang einer Bearbeitung für ein-Objekt. Ein Objekt, das diese Schnittstelle implementiert, muss alle Updates nach dem <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> Methodenaufruf so speichern, dass die Aktualisierungen verworfen werden können, wenn die <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> -Methode aufgerufen wird. In Daten Bindungs Windows Forms können Sie mehrmals innerhalb <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> des Gültigkeits Bereichs einer einzelnen Bearbeitungs Transaktion ( <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>z <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>. b.,, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>) aufgerufen werden. Implementierungen von <xref:System.ComponentModel.IEditableObject> sollten nachverfolgen, ob <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> bereits aufgerufen wurde, <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>und nachfolgende Aufrufe von ignorieren. Da diese Methode mehrmals aufgerufen werden kann, ist es wichtig, dass nachfolgende Aufrufe an diese nicht destruktiv sind. Das heißt, dass <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> nachfolgende Aufrufe die Updates, die durchgeführt wurden, nicht zerstören oder die beim ersten <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> Aufruf gespeicherten Daten geändert haben.

  - Die <xref:System.ComponentModel.IEditableObject.EndEdit%2A> -Methode überträgt alle Änderungen <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> seit dem Aufruf in das zugrunde liegende-Objekt, wenn sich das Objekt derzeit im Bearbeitungsmodus befindet.

  - Die <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> -Methode verwirft alle an dem-Objekt vorgenommenen Änderungen.

  Weitere Informationen zur Funktionsweise der <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>Methoden <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, und <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> finden [Sie unter Speichern von Daten in der Datenbank](/visualstudio/data-tools/save-data-back-to-the-database).

  Dieses Transaktions Konzept der Daten Funktionalität wird vom <xref:System.Windows.Forms.DataGridView> -Steuerelement verwendet.

- <xref:System.ComponentModel.ICancelAddNew>berfläche

  Eine Klasse, die die <xref:System.ComponentModel.ICancelAddNew> -Schnittstelle implementiert <xref:System.ComponentModel.IBindingList> , Implementiert in der Regel die-Schnittstelle und ermöglicht es Ihnen, eine Addition <xref:System.ComponentModel.IBindingList.AddNew%2A> für die Datenquelle mit der-Methode zurückzusetzen. Wenn die Datenquelle die <xref:System.ComponentModel.IBindingList> -Schnittstelle implementiert, sollte Sie auch die <xref:System.ComponentModel.ICancelAddNew> -Schnittstelle implementieren.

- <xref:System.ComponentModel.IDataErrorInfo>berfläche

  Eine Klasse, die die <xref:System.ComponentModel.IDataErrorInfo> -Schnittstelle implementiert, ermöglicht es Objekten, gebundenen Steuerelementen benutzerdefinierte Fehlerinformationen bereitzustellen:

  - Die <xref:System.ComponentModel.IDataErrorInfo.Error%2A> -Eigenschaft gibt den allgemeinen Fehlermeldungs Text zurück (z. b. "ein Fehler ist aufgetreten").

  - Die <xref:System.ComponentModel.IDataErrorInfo.Item%2A> -Eigenschaft gibt eine Zeichenfolge mit der angegebenen Fehlermeldung aus der Spalte zurück (z. b. " `State` der Wert in der Spalte ist ungültig").

- <xref:System.Collections.IEnumerable>berfläche

  Eine Klasse, die die <xref:System.Collections.IEnumerable> -Schnittstelle implementiert, wird in der Regel von ASP.net genutzt. Windows Forms Unterstützung für diese Schnittstelle ist nur über die <xref:System.Windows.Forms.BindingSource> -Komponente verfügbar.

  > [!NOTE]
  > Die <xref:System.Windows.Forms.BindingSource> Komponente kopiert alle <xref:System.Collections.IEnumerable> Elemente zu Bindungs Zwecken in eine separate Liste.

- <xref:System.ComponentModel.ITypedList>berfläche

  Eine Auflistungs Klasse, <xref:System.ComponentModel.ITypedList> die die-Schnittstelle implementiert, bietet die Möglichkeit, die Reihenfolge und den Satz von Eigenschaften zu steuern, die für das gebundene Steuerelement

  > [!NOTE]
  > Wenn Sie die <xref:System.ComponentModel.ITypedList.GetItemProperties%2A> -Methode implementieren und das <xref:System.ComponentModel.PropertyDescriptor> Array nicht NULL ist, ist der letzte Eintrag im Array der Eigenschaften Deskriptor, der die Listen Eigenschaft beschreibt, bei der es sich um eine weitere Liste von Elementen handelt.

- <xref:System.ComponentModel.ICustomTypeDescriptor>berfläche

  Eine Klasse, die die <xref:System.ComponentModel.ICustomTypeDescriptor> -Schnittstelle implementiert, stellt dynamische Informationen über sich selbst bereit. Diese Schnittstelle ähnelt, <xref:System.ComponentModel.ITypedList> wird jedoch anstelle von Listen für-Objekte verwendet. Diese Schnittstelle wird von <xref:System.Data.DataRowView> verwendet, um das Schema der zugrunde liegenden Zeilen zu projizieren. Eine einfache Implementierung von <xref:System.ComponentModel.ICustomTypeDescriptor> wird von der <xref:System.ComponentModel.CustomTypeDescriptor> -Klasse bereitgestellt.

  > [!NOTE]
  > Zur Unterstützung der Entwurfszeit Bindung an Typen, <xref:System.ComponentModel.ICustomTypeDescriptor>die implementieren, muss der Typ <xref:System.ComponentModel.IComponent> auch implementieren und als-Instanz im Formular vorhanden sein.

- <xref:System.ComponentModel.IListSource>berfläche

  Eine Klasse, die die <xref:System.ComponentModel.IListSource> -Schnittstelle implementiert, ermöglicht eine Listen basierte Bindung für nicht-Listen Objekte. Die <xref:System.ComponentModel.IListSource.GetList%2A> -Methode <xref:System.ComponentModel.IListSource> von wird verwendet, um eine bindbare Liste von einem Objekt zurückzugeben, das <xref:System.Collections.IList>nicht von erbt. <xref:System.ComponentModel.IListSource>wird von der <xref:System.Data.DataSet> -Klasse verwendet.

- <xref:System.ComponentModel.IRaiseItemChangedEvents>berfläche

  Eine Klasse, die die <xref:System.ComponentModel.IRaiseItemChangedEvents> -Schnittstelle implementiert, ist eine bindbare Liste <xref:System.ComponentModel.IBindingList> , die auch die-Schnittstelle implementiert. Diese Schnittstelle wird verwendet, um anzugeben, ob <xref:System.ComponentModel.IBindingList.ListChanged> der Typ durch <xref:System.ComponentModel.ListChangedType.ItemChanged> die <xref:System.ComponentModel.IRaiseItemChangedEvents.RaisesItemChangedEvents%2A> -Eigenschaft Ereignisse vom Typ auslöst.

  > [!NOTE]
  > Sie sollten die <xref:System.ComponentModel.IRaiseItemChangedEvents> implementieren, wenn Ihre Datenquelle die-Eigenschaft bereitstellt, um die zuvor beschriebene Ereignis Konvertierung aufzulisten <xref:System.Windows.Forms.BindingSource> und mit der-Komponente zu interagieren. Andernfalls führt der <xref:System.Windows.Forms.BindingSource> auch die-Eigenschaft zum Auflisten der Ereignis Konvertierung aus, was zu einer langsameren Leistung führt.

- <xref:System.ComponentModel.ISupportInitialize>berfläche

  Eine Komponente, die die <xref:System.ComponentModel.ISupportInitialize> -Schnittstelle implementiert, nutzt die Vorteile von Batch Optimierungen zum Festlegen von Eigenschaften und zum Initialisieren von Co-abhängigen Eigenschaften. Der <xref:System.ComponentModel.ISupportInitialize> enthält zwei Methoden:

  - <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A>signalisiert, dass die Objekt Initialisierung gestartet wird.

  - <xref:System.ComponentModel.ISupportInitialize.EndInit%2A>signalisiert, dass die Objekt Initialisierung abgeschlossen ist.

- <xref:System.ComponentModel.ISupportInitializeNotification>berfläche

  Eine Komponente, die die <xref:System.ComponentModel.ISupportInitializeNotification> Schnittstelle implementiert, <xref:System.ComponentModel.ISupportInitialize> implementiert auch die-Schnittstelle. Mit dieser Schnittstelle können Sie andere <xref:System.ComponentModel.ISupportInitialize> Komponenten Benachrichtigen, dass die Initialisierung beendet ist. Die <xref:System.ComponentModel.ISupportInitializeNotification> -Schnittstelle enthält zwei Member:

  - <xref:System.ComponentModel.ISupportInitializeNotification.IsInitialized%2A>Gibt einen `boolean` Wert zurück, der angibt, ob die Komponente initialisiert ist.

  - <xref:System.ComponentModel.ISupportInitializeNotification.Initialized>Tritt auf <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> , wenn aufgerufen wird.

- <xref:System.ComponentModel.INotifyPropertyChanged>berfläche

  Eine Klasse, die diese Schnittstelle implementiert, ist ein Typ, der ein Ereignis auslöst, wenn sich einer der Eigenschaftswerte ändert. Diese Schnittstelle soll das Muster ersetzen, dass für jede Eigenschaft eines Steuerelements ein Änderungsereignis vorhanden ist. Wenn ein Geschäftsobjekt <xref:System.ComponentModel.BindingList%601>in einem verwendet wird, sollte die <xref:System.ComponentModel.INotifyPropertyChanged> -Schnittstelle implementiert werden,\`und die BindingList <xref:System.ComponentModel.BindingList%601.ListChanged> 1 konvertiert <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> Ereignisse <xref:System.ComponentModel.ListChangedType.ItemChanged>in Ereignisse vom Typ.

  > [!NOTE]
  > Damit die Änderungs Benachrichtigung in einer Bindung zwischen einem gebundenen Client und einer Datenquelle auftritt, muss der gebundene Daten Quellentyp entweder die <xref:System.ComponentModel.INotifyPropertyChanged> -Schnittstelle implementieren (bevorzugt), oder Sie können *propertyName* `Changed` -Ereignisse für den gebundenen Typ bereitstellen. Sie sollten jedoch nicht beides tun.

### <a name="interfaces-for-implementation-by-component-authors"></a>Schnittstellen für die Implementierung von Komponentenautoren

Die folgenden Schnittstellen sind für die Nutzung durch die Windows Forms-Datenbindungs-Engine ausgelegt:

- <xref:System.Windows.Forms.IBindableComponent>berfläche

  Eine Klasse, die diese Schnittstelle implementiert, ist eine Nichtsteuerungskomponente, die die Datenbindung unterstützt. Diese Klasse gibt die Daten Bindungen und den Bindungs Kontext der Komponente über die <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> - <xref:System.Windows.Forms.IBindableComponent.BindingContext%2A> Eigenschaft und die-Eigenschaft dieser Schnittstelle zurück.

  > [!NOTE]
  > Wenn die Komponente von <xref:System.Windows.Forms.Control>erbt, müssen Sie die <xref:System.Windows.Forms.IBindableComponent> -Schnittstelle nicht implementieren.

- <xref:System.Windows.Forms.ICurrencyManagerProvider>berfläche

  Eine Klasse, die die <xref:System.Windows.Forms.ICurrencyManagerProvider> -Schnittstelle implementiert, ist eine Komponente <xref:System.Windows.Forms.CurrencyManager> , die eine eigene bereitstellt, um die dieser speziellen Komponente zugeordneten Bindungen zu verwalten. Der Zugriff auf die <xref:System.Windows.Forms.CurrencyManager> benutzerdefinierte wird von <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A> der-Eigenschaft bereitgestellt.

  > [!NOTE]
  > Eine Klasse, die von <xref:System.Windows.Forms.Control> erbt, verwaltet Bindungen automatisch über Ihre <xref:System.Windows.Forms.Control.BindingContext%2A> -Eigenschaft. daher <xref:System.Windows.Forms.ICurrencyManagerProvider> sind Fälle, in denen Sie implementieren müssen, relativ selten.

## <a name="see-also"></a>Siehe auch

- [Datenbindung und Windows Forms](data-binding-and-windows-forms.md)
- [Vorgehensweise: Erstellen eines einfach gebundenen Steuer Elements in einem Windows Form](how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [Windows Forms-Datenbindung](windows-forms-data-binding.md)
