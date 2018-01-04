---
title: Implementieren des virtuellen Modus mit Just-In-Time-Laden von Daten in das DataGridView-Steuerelement in Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2a830c11e8df73b71f16c1b9dfd1007461d910f5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="implementing-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a>Implementieren des virtuellen Modus mit Just-In-Time-Laden von Daten in das DataGridView-Steuerelement in Windows Forms
Ein Grund für das Implementieren des virtuellen Modus in den <xref:System.Windows.Forms.DataGridView> Steuerelement wird zum Abrufen von Daten nur, wenn er benötigt wird. Hierbei spricht *Just-in-Time-Laden von Dateien*.  
  
 Wenn Sie eine sehr große Tabelle in einer Remotedatenbank arbeiten, z. B. empfiehlt zur Vermeidung von Start Verzögerungen durch Abrufen nur der Daten, die erforderlich sind für die Anzeige und das Abrufen von zusätzlicher Daten, nur, wenn neue Zeilen in der Ansicht Bildlauf. Wenn die Clientcomputer, die Ausführung Ihrer Anwendung eine begrenzte Menge an Arbeitsspeicher zum Speichern von Daten haben, möchten Sie möglicherweise auch nicht verwendete Daten verwerfen, wenn Sie neue Werte aus der Datenbank abrufen.  
  
 In den folgenden Abschnitten wird beschrieben, wie ein <xref:System.Windows.Forms.DataGridView> Steuerelement mit einem Just-in-Time-Cache.  
  
 Um den Code in diesem Thema als einzelne Auflistung kopieren zu können, finden Sie unter [wie: Implementieren des virtuellen Modus mit Just-in-Time-Laden von Daten im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).  
  
## <a name="the-form"></a>Das Formular  
 Das folgende Codebeispiel definiert ein Formular mit einem schreibgeschützten <xref:System.Windows.Forms.DataGridView> Steuerelement, interagiert mit, einer `Cache` -Objekt über ein <xref:System.Windows.Forms.DataGridView.CellValueNeeded> -Ereignishandler. Die `Cache` -Objekt verwaltet die lokal gespeicherten Werte und verwendet eine `DataRetriever` Objekt Werte aus der Orders-Tabelle der Northwind-Beispieldatenbank abgerufen. Die `DataRetriever` -Objekt, das implementiert die `IDataPageRetriever` durch erforderliche Schnittstelle die `Cache` Klasse, dient außerdem zum Initialisieren der <xref:System.Windows.Forms.DataGridView> Zeilen und Spalten zu steuern.  
  
 Die `IDataPageRetriever`, `DataRetriever`, und `Cache` Typen werden weiter unten in diesem Thema beschrieben.  
  
> [!NOTE]
>  Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen. Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows-Authentifizierung (wird auch als integrierte Sicherheit bezeichnet) sicherer steuern. Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#100)]  
  
## <a name="the-idatapageretriever-interface"></a>Die IDataPageRetriever-Schnittstelle  
 Das folgende Codebeispiel definiert die `IDataPageRetriever` -Schnittstelle, die implementiert wird die `DataRetriever` Klasse. Die einzige Methode, die in dieser Schnittstelle deklariert ist die `SupplyPageOfData` Methode, die einen Zeilenindex der ersten und die Anzahl von Zeilen in einer einzelnen Seite mit Daten benötigt. Diese Werte werden durch die Implementierung verwendet, um eine Teilmenge der Daten aus einer Datenquelle abzurufen.  
  
 Ein `Cache` Objekt verwendet eine Implementierung dieser Schnittstelle während der Erstellung, um die beiden erste Seiten der Daten zu laden. Wenn ein zwischengespeicherter Wert benötigt wird, wird der Cache verwirft eine der folgenden Seiten, und fordert eine neue Seite mit dem Wert aus der `IDataPageRetriever`.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#201)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#201)]  
  
## <a name="the-dataretriever-class"></a>Die DataRetriever-Klasse  
 Das folgende Codebeispiel definiert die `DataRetriever` Klasse implementiert die `IDataPageRetriever` Schnittstelle, um Seiten mit Daten von einem Server abzurufen. Die `DataRetriever` -Klasse stellt außerdem `Columns` und `RowCount` Eigenschaften, die die <xref:System.Windows.Forms.DataGridView> Steuerelement verwendet, um die benötigten Spalten zu erstellen und die entsprechende Anzahl leerer Zeilen hinzufügen der <xref:System.Windows.Forms.DataGridView.Rows%2A> Auflistung. Hinzufügen von leeren Zeilen ist erforderlich, damit das Steuerelement verhält, als wären sie alle Daten in der Tabelle enthält. Dies bedeutet, dass das Bildlauffeld auf der Bildlaufleiste angemessen groß, und des Benutzers auf eine beliebige Zeile in der Tabelle zugreifen. Die Zeilen aufgefüllt werden, indem die <xref:System.Windows.Forms.DataGridView.CellValueNeeded> Ereignishandler nur, wenn sie einen Bildlauf angezeigt werden.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#200)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#200)]  
  
## <a name="the-cache-class"></a>Die Cacheklasse  
 Das folgende Codebeispiel definiert die `Cache` Klasse, die aufgefüllt, die über zwei Datenseiten verwaltet eine `IDataPageRetriever` Implementierung. Die `Cache` Klasse definiert eine innere `DataPage` -Struktur, die enthält eine <xref:System.Data.DataTable> zum Speichern der Werte in einen einzigen Cache-Seite und berechnet, die Zeile Indizes dar, die oberen und unteren Grenzen der Seite darstellen.  
  
 Die `Cache` Klasse zwei Seiten der Daten zur Entwurfszeit geladen. Wenn die <xref:System.Windows.Forms.DataGridView.CellValueNeeded> Ereignis fordert einen Wert der `Cache` Objekt bestimmt, ob der Wert in verfügbar ist einer der beiden Seiten und, wenn dies der Fall ist, wird zurückgegeben. Wenn der Wert nicht lokal verfügbar ist die `Cache` Objekt bestimmt, welche der beiden Seiten Gesamtbreite der aktuell angezeigten Zeilen ist und ersetzt die Seite durch eine neue Seite mit den angeforderten Wert, der daraufhin zurückgegeben.  
  
 Vorausgesetzt, die Anzahl der Zeilen in einer Datenseite identisch mit der Anzahl der Zeilen, die gleichzeitig auf dem Bildschirm angezeigt werden können, kann dieses Modell paging durch die Tabelle Benutzer effizient zu der die zuletzt angezeigte Seite zurückzukehren.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#300)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#300)]  
  
## <a name="additional-considerations"></a>Weitere Überlegungen  
 Die vorherigen Codebeispiele werden zur Veranschaulichung der Just-in-Time-Datenladevorgangs bereitgestellt. Sie müssen zum Ändern des Codes für Ihre eigenen Anforderungen erreichen maximalen Effizienz. Sie benötigen mindestens wählen einen entsprechenden Wert für die Anzahl der Zeilen pro Seite der Daten im Cache. Dieser Wert wird übergeben, in der `Cache` Konstruktor. Die Anzahl der Zeilen pro Seite sollte nicht kleiner als die Anzahl der Zeilen, die gleichzeitig im angezeigt werden, können Ihre <xref:System.Windows.Forms.DataGridView> Steuerelement.  
  
 Optimale Ergebnisse zu erzielen müssen Sie zum Testen der Leistung und Verwendbarkeit zu testen, um zu bestimmen, die Anforderungen des Systems und Ihre Benutzer durchführen. Mehrere Faktoren, die Sie berücksichtigen müssen enthalten die Menge an Arbeitsspeicher in den Clientcomputern ausgeführt werden, die Anwendung, die verfügbare Bandbreite der Verbindung verwendet und die Latenz des Servers verwendet. Die Bandbreite und Wartezeit sollte der spitzenauslastung manchmal bestimmt werden.  
  
 Um das Durchführen eines Bildlaufs Leistung der Anwendung zu verbessern, können Sie die Datenmenge, die lokal gespeicherten erhöhen. Um die Dauer des verbindungsstarts zu verbessern, müssen Sie jedoch vermeiden Anfangs zu viele Daten zu laden. Sie ändern möchten die `Cache` Klasse, um die Anzahl der Datenseiten zu erhöhen, kann es zu speichern. Mehr Datenseiten kann Effizienz verbessern, Durchführen eines Bildlaufs, aber Sie müssen die ideale Anzahl von Zeilen in einer Datenseite, je nach der verfügbaren Bandbreite und die serverlatenz zu bestimmen. Bei kleineren Seiten vom Server wird häufiger zugegriffen werden, aber weniger Zeit die angeforderten Daten zurück. Wenn Latenz ein Problem als Bandbreite liegt, können Sie größere Datenseiten verwenden möchten.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 [Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 [Virtueller Modus im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 [Gewusst wie: Implementieren des virtuellen Modus mit Just-In-Time-Laden von Daten in das DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)
