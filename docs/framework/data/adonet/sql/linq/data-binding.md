---
title: Datenbindung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cbec8b02-a1e8-4ae8-a83b-bb5190413ac5
ms.openlocfilehash: 79a14e787b4fe1aa1b16ad661b11a43b12bdd718
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70247380"
---
# <a name="data-binding"></a>Datenbindung

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]unterstützt die Bindung an allgemeine Steuerelemente, z.b. Raster Steuerelemente. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Definiert insbesondere die grundlegenden Muster für das Binden an ein Datenraster und das Verarbeiten der Master-Detail-Bindung, sowohl im Hinblick auf die Anzeige als auch auf das aktualisieren.

## <a name="underlying-principle"></a>Zugrunde liegendes Prinzip

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]übersetzt [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] Abfragen in SQL für die Ausführung in einer Datenbank. Die Ergebnisse sind `IEnumerable` mit strikter Typbindung. Da es sich hierbei um gewöhnliche Common Language Runtime (CLR)-Objekte handelt, lassen sich die Ergebnisse mithilfe von gewöhnlicher Objektdatenbindung darstellen. Andererseits erfordern Änderungsoperationen (Einfügungen, Aktualisieren, Löschen) zusätzliche Schritte.

## <a name="operation"></a>Vorgang

Die implizite Bindung an Windows Forms-Steuerelemente erfolgt durch Implementierung von <xref:System.ComponentModel.IListSource>. Generische <xref:System.Data.Linq.Table%601> Datenquellen (`Table<T>` in C# oder `Table(Of T)` in Visual Basic) und generische `DataQuery` wurden aktualisiert, um zu <xref:System.ComponentModel.IListSource>implementieren. Datenbindungs-Engines der Benutzeroberfläche (UI) (Windows Forms und Windows Presentation Foundation) prüfen, ob ihre Datenquelle <xref:System.ComponentModel.IListSource> implementiert. Daher wird durch das Schreiben einer direkten Zuneigung einer Abfrage in eine Datenquelle eines-Steuer Elements implizit [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die Sammlungs Generierung aufgerufen, wie im folgenden Beispiel gezeigt:

[!code-csharp[DLinqDataBinding#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDataBinding/cs/Program.cs#1)]
[!code-vb[DLinqDataBinding#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDataBinding/vb/Module1.vb#1)]

Das Gleiche geschieht bei Windows Presentation Foundation:

[!code-csharp[DLinqDataBinding#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDataBinding/cs/Program.cs#2)]
[!code-vb[DLinqDataBinding#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDataBinding/vb/Module1.vb#2)]

Auflistungsgenerierungen werden von generischem <xref:System.Data.Linq.Table%601> und generischem `DataQuery` in <xref:System.ComponentModel.IListSource.GetList%2A> implementiert.

## <a name="ilistsource-implementation"></a>IListSource-Implementierung

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]implementiert <xref:System.ComponentModel.IListSource> an zwei Orten:

- Die Datenquelle ist eine <xref:System.Data.Linq.Table%601>: [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] durchsucht die Tabelle, um eine `DataBindingList` Auflistung aufzufüllen, die einen Verweis auf die Tabelle beibehält.

- Die Datenquelle ist eine <xref:System.Linq.IQueryable%601>. Es existieren zwei Szenarien:

  - Wenn [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die zugrunde liegende <xref:System.Data.Linq.Table%601> von der <xref:System.Linq.IQueryable%601>sucht, lässt die Quelle die Edition zu, und die Situation entspricht der im ersten Aufzählungs Punkt.

  - Wenn [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die zugrunde liegende <xref:System.Data.Linq.Table%601>nicht finden kann, lässt die Quelle keine `groupby`Edition zu (z. b.). [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]durchsucht die Abfrage, um eine generische `SortableBindingList`auszufüllen, bei der es <xref:System.ComponentModel.BindingList%601> sich um eine einfache handelt, die die Sortierfunktion für T-Entitäten für eine bestimmte Eigenschaft implementiert.

## <a name="specialized-collections"></a>Spezialisierte Auflistungen

Bei vielen zuvor in diesem Dokument beschriebenen Funktionen wurde <xref:System.ComponentModel.BindingList%601> auf abweichende Klassen spezialisiert. Diese Klassen sind generische `SortableBindingList` und generische `DataBindingList`. Beide werden als intern deklariert.

### <a name="generic-sortablebindinglist"></a>Generische SortableBindingList

Diese Klasse erbt von <xref:System.ComponentModel.BindingList%601> und ist eine durchsuchbare Version von <xref:System.ComponentModel.BindingList%601>. Die Sortierung ist eine Lösung im Arbeitsspeicher, die niemals einen Kontakt zur Datenbank herstellt. <xref:System.ComponentModel.BindingList%601> implementiert <xref:System.ComponentModel.IBindingList>, unterstützt jedoch standardmäßig keine Sortierung. Implementiert jedoch mit virtuellen Kern Methoden. <xref:System.ComponentModel.BindingList%601> <xref:System.ComponentModel.IBindingList> Sie können diese Methoden leicht überschreiben. Die generische `SortableBindingList` überschreibt <xref:System.ComponentModel.BindingList%601.SupportsSortingCore%2A>, <xref:System.ComponentModel.BindingList%601.SortPropertyCore%2A>, <xref:System.ComponentModel.BindingList%601.SortDirectionCore%2A> und <xref:System.ComponentModel.BindingList%601.ApplySortCore%2A>. `ApplySortCore` wird von <xref:System.ComponentModel.IBindingList.ApplySort%2A> aufgerufen und sortiert die Liste der T-Elemente einer gegebenen Eigenschaft.

Wenn die Eigenschaft nicht zu T gehört, wird eine Ausnahme ausgelöst.

Um die Sortierung zu [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erreichen, erstellt `SortableBindingList.PropertyComparer` eine generische Klasse, die von <xref:System.Collections.Generic.Comparer%601.System%23Collections%23IComparer%23Compare%2A> der generischen Klasse erbt und einen Standard Vergleich für einen angegebenen `PropertyDescriptor`Typ T, eine und eine Richtung implementiert. Diese Klasse erstellt dynamisch einen `Comparer` von T, bei dem T der `PropertyType` des `PropertyDescriptor` ist. Dann wird der Standardvergleich vom statischen generischen `Comparer` abgerufen. Eine Standardinstanz wird durch Reflektion erzeugt.

Eine generische `SortableBindingList` ist auch die Basisklasse für `DataBindingList`. Eine generische `SortableBindingList` bietet zwei virtuelle Methoden zum Unterbrechen oder Fortsetzen der Verfolgung des Hinzufügens/Entfernens von Elementen. Diese beiden Methoden lassen sich für Basisfunktionen wie Sortierung verwenden, werden jedoch tatsächlich von höheren Klassen wie der generischen `DataBindingList` implementiert.

### <a name="generic-databindinglist"></a>Generische DataBindingList

Diese Klasse erbt von der generischen `SortableBindingLIst`. Die generische `DataBindingList` behält einen Verweis auf die zugrunde liegende generische `Table` der generischen `IQueryable` bei, die für das erste Füllen der Auflistung verwendet wurde. Die generische `DatabindingList` fügt die Verfolgung für das Hinzufügen/Entfernen von Elementen hinzu, indem Sie `InsertItem`() und `RemoveItem`() überschreiben. Außerdem wird die abstrakte Funktion zur Unterbrechung/Wiederaufnahme der Verfolgung implementiert, um eine bedingte Verfolgung zu ermöglichen. Mit dieser Funktion nutzt die generische `DataBindingList` die Vorteile der polymorphen Verwendung der Verfolgungsfunktion für übergeordnete Klassen.

## <a name="binding-to-entitysets"></a>Binden an EntitySets

Eine Bindung an `EntitySet` ist ein Sonderfall, da `EntitySet` bereits eine Auflistung ist, die <xref:System.ComponentModel.IBindingList> implementiert. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]Fügt die Unterstützung für Sortierung<xref:System.ComponentModel.ICancelAddNew>und Abbruch () hinzu. Eine `EntitySet`-Klasse verwendet eine interne Liste, um Entitäten zu speichern. Diese Liste ist eine Auflistung auf niedriger Ebene, die auf einem generischen Array, der generischen `ItemList`-Klasse, basiert.

### <a name="adding-a-sorting-feature"></a>Hinzufügen einer Sortierungsfunktion

Arrays bieten eine Sortiermethode (`Array.Sort()`), die Sie zusammen mit einem `Comparer` von T verwenden können. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verwendet die weiter oben in diesem Thema beschriebene generische `SortableBindingList.PropertyComparer`-Klasse, um diesen `Comparer` für die Eigenschaft und die Sortierrichtung zu erhalten. Eine `ApplySort`-Methode wird der generischen `ItemList` hinzugefügt, um diese Funktion aufzurufen.

Auf der `EntitySet`-Seite müssen Sie jetzt die Sortierungsunterstützung deklarieren:

- <xref:System.ComponentModel.IBindingList.SupportsSorting%2A> gibt `true` zurück.

- <xref:System.ComponentModel.IBindingList.ApplySort%2A> ruft `entities.ApplySort()` und dann `OnListChanged()` auf.

- Die <xref:System.ComponentModel.IBindingList.SortDirection%2A>-Eigenschaft und die <xref:System.ComponentModel.IBindingList.SortProperty%2A>-Eigenschaft zeigen die aktuelle Sortierungsdefinition, die in lokalen Membern gespeichert wird.

Wenn Sie eine System. Windows. Forms. BindingSource verwenden und eine EntitySet\<TEntity-> an die System. Windows. Forms. BindingSource. DataSource binden, müssen Sie EntitySet\<TEntity > aufrufen. GetNewBindingList zum Aktualisieren von BindingSource. List.

Wenn Sie eine System. Windows. Forms. BindingSource-Eigenschaft verwenden und die BindingSource. DataMember-Eigenschaft festlegen und BindingSource. DataSource auf eine Klasse mit dem Namen in BindingSource. DataMember festlegen, die die EntitySet\<TEntity-> verfügbar macht, der EntitySet\<TEntity-> muss nicht aufgerufen werden. GetNewBindingList zum Aktualisieren der BindingSource. List, aber Sie verlieren die Sortierfunktion.

## <a name="caching"></a>Zwischenspeicherung

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Abfragen <xref:System.ComponentModel.IListSource.GetList%2A>implementieren. Trifft die Windows Forms-BindingSource-Klasse auf diese Schnittstelle, wird GetList() für eine Verbindung dreimal aufgerufen. Um diese Situation zu umgehen, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] implementiert einen Cache pro Instanz, um zu speichern, und gibt immer dieselbe generierte Sammlung zurück.

## <a name="cancellation"></a>Abbruch

<xref:System.ComponentModel.IBindingList> definiert eine <xref:System.ComponentModel.IBindingList.AddNew%2A>-Methode, die von Steuerelementen genutzt wird, um ein neues Element aus einer Bindungsauflistung zu erstellen. Das `DataGridView`-Steuerelement zeigt diese Funktion sehr gut, wenn die letzte sichtbare Zeile ein Sternchen in der Überschrift enthält. Das Sternchen zeigt an, dass Sie ein neues Element hinzufügen können.

Zusätzlich zu dieser Funktion kann eine Auflistung auch <xref:System.ComponentModel.ICancelAddNew> implementieren. Mit dieser Funktion können Steuerelemente den Vorgang abbrechen oder validieren, ob das neu bearbeitete Element validiert wurde oder nicht.

<xref:System.ComponentModel.ICancelAddNew> wird in allen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Auflistungen mit Datenbindung implementiert (generische `SortableBindingList` und generischer `EntitySet`). In beiden Implementierungen verhält sich der Code wie folgt:

- Lässt das Einfügen und Entfernen von Elementen in die bzw. aus der Auflistung zu.

- Verfolgt keine Änderungen, solange die Benutzeroberfläche keinen Commit für die Bearbeitung ausführt.

- Verfolgt keine Änderungen, so lange die Bearbeitung abgebrochen wird (<xref:System.ComponentModel.ICancelAddNew.CancelNew%2A>).

- Ermöglicht die Verfolgung, wenn die Bearbeitung aktiviert wurde (<xref:System.ComponentModel.ICancelAddNew.EndNew%2A>).

- Sorgt für das normale Verhalten der Auflistung, wenn das neue Element nicht aus <xref:System.ComponentModel.IBindingList.AddNew%2A> stammt.

## <a name="troubleshooting"></a>Problembehandlung

Dieser Abschnitt erläutert verschiedene Elemente, die Sie bei der Fehlerbehebung von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Datenbindungsanwendungen unterstützen können.

- Sie müssen Eigenschaften verwenden. Die ausschließliche Verwendung von Feldern genügt nicht. Windows Forms erfordert diese Verwendung.

- Standardmäßig `image`werden die Daten Bank `timestamp` Typen, `varbinary`und dem Bytearray zugeordnet. Da `ToString()` in diesem Szenario nicht unterstützt wird, können diese Objekte nicht angezeigt werden.

- Ein Klassenmember, der einem Primärschlüssel zugeordnet ist, verfügt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] über einen Setter, unterstützt jedoch keine Änderung der Objekt Identität. Deshalb kann der primäre/eindeutige Schlüssel, der in der Zuordnung verwendet wird, nicht in der Datenbank aktualisiert werden. Eine Änderung im Raster löst eine Ausnahme aus, wenn aufgerufen <xref:System.Data.Linq.DataContext.SubmitChanges%2A>wird.

- Wird eine Entität an zwei separate Raster gebunden (z. B. für Master und Details), wird `Delete` im Master-Raster nicht an das Detail-Raster weitergeleitet&gt;.

## <a name="see-also"></a>Siehe auch

- [Hintergrundinformationen](background-information.md)
