---
title: Implementieren des virtuellen Modus mit Just-In-Time-Laden von Daten in das DataGridView-Steuerelement in Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], just-in-time data loading
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- just-in-time data loading
- DataGridView control [Windows Forms], large data sets
- virtual mode [Windows Forms], just-in-time data loading
ms.assetid: c2a052b9-423c-4ff7-91dc-d8c7c79345f6
ms.openlocfilehash: 641db19cc6493a20c9f9a34622f466e3623c32ad
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59088651"
---
# <a name="implementing-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a>Implementieren des virtuellen Modus mit Just-In-Time-Laden von Daten in das DataGridView-Steuerelement in Windows Forms
Ein Grund für das Implementieren des virtuellen Modus in den <xref:System.Windows.Forms.DataGridView> Steuerelement wird zum Abrufen von Daten nur bei Bedarf ist. Dies wird als bezeichnet *just-in-Time-Datenladevorgang*.  
  
 Wenn Sie mit einer sehr großen Tabelle in einer Remotedatenbank arbeiten, z. B. möchten vermeiden Verzögerungen bei der Start, indem Sie nur die Daten abzurufen, die für die Anzeige erforderlich ist und nur während der Benutzer neue Zeilen in der Ansicht einen Bildlauf zum Abrufen von zusätzliche Daten. Wenn die Clientcomputer, die Ausführung Ihrer Anwendung eine begrenzte Menge an Arbeitsspeicher zum Speichern von Daten zur Verfügung haben, möchten Sie auch nicht verwendete Daten verwerfen, wenn Sie neue Werte aus der Datenbank abrufen.  
  
 In den folgenden Abschnitten wird beschrieben, wie eine <xref:System.Windows.Forms.DataGridView> Steuerelement mit einem just-in-Time-Cache.  
  
 Zum Kopieren des Codes in diesem Thema als einzelne Auflistung lesen Sie [Vorgehensweise: Implementieren des virtuellen Modus mit Just-in-Time-Daten laden in das Windows Forms-DataGridView-Steuerelement](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).  
  
## <a name="the-form"></a>Das Formular  
 Das folgende Codebeispiel definiert ein Formular mit einem nur-Lese- <xref:System.Windows.Forms.DataGridView> -Steuerelement, das für die Interaktion mit einem `Cache` -Objekt über eine <xref:System.Windows.Forms.DataGridView.CellValueNeeded> -Ereignishandler. Die `Cache` -Objekt verwaltet die lokal gespeicherten Werte und verwendet eine `DataRetriever` Objekt Werte aus der Orders-Tabelle der Northwind-Beispieldatenbank abgerufen. Die `DataRetriever` Objekt, das implementiert die `IDataPageRetriever` durch erforderliche Schnittstelle die `Cache` Klasse, dient auch zum Initialisieren der <xref:System.Windows.Forms.DataGridView> Zeilen und Spalten zu steuern.  
  
 Die `IDataPageRetriever`, `DataRetriever`, und `Cache` werden weiter unten in diesem Thema beschrieben.  
  
> [!NOTE]
>  Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen. Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows-Authentifizierung (wird auch als integrierte Sicherheit bezeichnet) sicherer steuern. Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../data/adonet/protecting-connection-information.md).  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#100)]  
  
## <a name="the-idatapageretriever-interface"></a>Die IDataPageRetriever-Schnittstelle  
 Das folgende Codebeispiel definiert die `IDataPageRetriever` -Schnittstelle, die Implementierung wird durch die `DataRetriever` Klasse. Ist die einzige Methode, die in diese Schnittstelle deklariert die `SupplyPageOfData` -Methode, die einen anfänglichen Zeilenindex und die Anzahl von Zeilen in einer einzelnen Seite mit Daten erforderlich sind. Diese Werte werden durch die Implementierung verwendet, um eine Teilmenge der Daten aus einer Datenquelle abzurufen.  
  
 Ein `Cache` Objekt verwendet eine Implementierung dieser Schnittstelle während der Erstellung, um die beiden ersten Seiten mit Daten zu laden. Wenn ein nicht zwischengespeicherter Wert benötigt wird, wird der Cache verwirft eine dieser Seiten und fordert eine neue Seite mit dem Wert aus der `IDataPageRetriever`.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#201)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#201)]  
  
## <a name="the-dataretriever-class"></a>Die DataRetriever-Klasse  
 Das folgende Codebeispiel definiert die `DataRetriever` Klasse implementiert die `IDataPageRetriever` Schnittstelle, um Seiten mit Daten von einem Server abzurufen. Die `DataRetriever` Klasse bietet auch `Columns` und `RowCount` Eigenschaften, die die <xref:System.Windows.Forms.DataGridView> -Steuerelement verwendet, um die erforderlichen Spalten zu erstellen und die entsprechende Anzahl von leeren Zeilen hinzufügen der <xref:System.Windows.Forms.DataGridView.Rows%2A> Auflistung. Hinzufügen von leeren Zeilen ist erforderlich, damit das Steuerelement verhält, als ob sie alle Daten in der Tabelle enthält. Dies bedeutet, dass das Bildlauffeld auf der Bildlaufleiste wird die richtige Größe haben, und des Benutzers auf eine beliebige Zeile in der Tabelle zugreifen. Die Zeilen aufgefüllt werden, indem die <xref:System.Windows.Forms.DataGridView.CellValueNeeded> Ereignishandler nur dann, wenn sie in die Ansicht gescrollt werden.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#200)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#200)]  
  
## <a name="the-cache-class"></a>Die Cacheklasse  
 Das folgende Codebeispiel definiert die `Cache` Klasse, die zwei Seiten mit Daten, die durch aufgefüllt verwaltet eine `IDataPageRetriever` Implementierung. Die `Cache` -Klasse definiert eine innere `DataPage` Struktur, die enthält eine <xref:System.Data.DataTable> um die Werte in einem einzigen Cache speichern-Seite und berechnet die Zeile indiziert, für die die oberen und unteren Grenzen der Seite darstellen.  
  
 Die `Cache` -Klasse lädt die zwei Seiten mit Daten zur Entwurfszeit. Wenn die <xref:System.Windows.Forms.DataGridView.CellValueNeeded> Ereignis anfordert, einen Wert, der `Cache` Objekt bestimmt, ob der Wert in verfügbar ist einer der beiden Seiten und, wenn dies der Fall ist, gibt sie zurück. Wenn der Wert nicht lokal verfügbar ist die `Cache` Objekt bestimmt, welche der beiden Seiten am weitesten entfernt den aktuell angezeigten Zeilen ist und ersetzt die Seite durch eine neue Seite mit den angeforderten Wert, der wird dann zurückgegeben.  
  
 Vorausgesetzt, dass die Anzahl der Zeilen, Seiten mit dem die Anzahl der Zeilen, die gleichzeitig auf dem Bildschirm angezeigt werden können entspricht, ermöglicht dieses Modell paging für die Tabelle effizient an die zuletzt angezeigte Seite zurückzugeben.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#300)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#300)]  
  
## <a name="additional-considerations"></a>Weitere Überlegungen  
 Die vorherigen Codebeispielen dienen zur Veranschaulichung der just-in-Time-Daten werden geladen. Sie müssen zum Ändern des Codes für Ihre eigenen Anforderungen zum Erzielen einer maximalen Effizienz zu erzielen. Zumindest müssen Sie einen entsprechenden Wert für die Anzahl der Zeilen pro Seite mit Daten im Cache auswählen. Dieser Wert wird übergeben, in der `Cache` Konstruktor. Die Anzahl der Zeilen pro Seite sollte nicht kleiner als die Anzahl der Zeilen, die gleichzeitig in angezeigt werden, können Ihre <xref:System.Windows.Forms.DataGridView> Steuerelement.  
  
 Für optimale Ergebnisse müssen Sie zum Testen der Leistung und Nutzbarkeit zu testen, um zu bestimmen, die Anforderungen des Systems und Ihre Benutzer durchführen. Mehrere Faktoren, die Sie berücksichtigen müssen enthalten die Größe des Arbeitsspeichers auf dem Clientcomputer, die mit Ihrer Anwendung, die verfügbare Bandbreite der Verbindung verwendet und die Latenz des Servers verwendet. Gelegentlich sollte die Bandbreite und Latenz der spitzenauslastung bestimmt werden.  
  
 Um die bildlaufleistung Ihrer Anwendung zu verbessern, können Sie die Menge der Daten, die lokal gespeicherten erhöhen. Zur Verbesserung der Startzeit müssen Sie jedoch vermeiden Anfangs zu viele Daten zu laden. Sie ändern möchten die `Cache` Klasse, um die Anzahl der Datenseiten zu erhöhen, kann es zu speichern. Kann bei Verwendung von mehr Datenseiten Bildlauf Effizienz verbessern, aber Sie müssen die ideale Anzahl von Zeilen in eine Datenseite, abhängig von der verfügbaren Bandbreite und die Server-Wartezeit bestimmen. Bei kleineren Seiten der Server häufiger zugegriffen wird, aber nimmt weniger Zeit in die angeforderten Daten zurück. Wenn Latenz ein Problem als Bandbreite mehr ist, können Sie größere Datenseiten verwenden möchten.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- [Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Virtueller Modus im DataGridView-Steuerelement in Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms](implementing-virtual-mode-wf-datagridview-control.md)
- [Vorgehensweise: Implementieren des virtuellen Modus mit Just-in-Time-Daten laden in das DataGridView-Steuerelement in Windows Forms](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)
