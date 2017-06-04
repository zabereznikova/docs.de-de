---
title: "Implementieren des virtuellen Modus mit Just-In-Time-Laden von Daten in das DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
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
  - "Daten [Windows Forms], Verwalten von großen Datasets"
  - "DataGridView-Steuerelement [Windows Forms], Große Datasets"
  - "DataGridView-Steuerelement [Windows Forms], Virtueller Modus"
  - "Beispiele [Windows Forms], Just-In-Time-Laden von Dateien"
  - "Just-In-Time-Laden von Dateien"
  - "Virtueller Modus, Just-In-Time-Laden von Dateien"
ms.assetid: c2a052b9-423c-4ff7-91dc-d8c7c79345f6
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Implementieren des virtuellen Modus mit Just-In-Time-Laden von Daten in das DataGridView-Steuerelement in Windows Forms
Wenn Daten nur bei Bedarf abgerufen werden, sollte der virtuelle Modus in das <xref:System.Windows.Forms.DataGridView>\-Steuerelement implementiert werden.  Diesen Vorgang bezeichnet man als *Just\-In\-Time\-Laden von Daten*.  
  
 Wenn Sie beispielsweise mit einer sehr großen Tabelle in einer Remotedatenbank arbeiten, möchten Sie möglicherweise Startverzögerungen vermeiden, indem Sie nur die Daten abrufen, die für die Anzeige benötigt werden. Weitere Daten werden nur abgerufen, wenn der Benutzer einen Bildlauf zu neuen Zeilen durchführt.  Wenn die Clientcomputer, auf denen die Anwendung ausgeführt wird, über beschränkten Speicherplatz für Daten verfügen, sollten Sie außerdem nicht verwendete Daten möglicherweise verwerfen, wenn Sie neue Werte aus der Datenbank abrufen.  
  
 In den folgenden Abschnitten wird beschrieben, wie ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement mit einem Just\-In\-Time\-Cache verwendet wird.  
  
 Informationen zum Kopieren des Codes in diesem Thema als einzelne Auflistung finden Sie unter [Gewusst wie: Implementieren des virtuellen Modus mit Just\-In\-Time\-Laden von Daten in das DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).  
  
## Das Formular  
 Das folgende Codebeispiel definiert ein Formular mit einem schreibgeschützten <xref:System.Windows.Forms.DataGridView>\-Steuerelement, das mit einem `Cache`\-Objekt über einen <xref:System.Windows.Forms.DataGridView.CellValueNeeded>\-Ereignishandler interagiert.  Das `Cache`\-Objekt verwaltet die lokal gespeicherten Werte und verwendet ein `DataRetriever`\-Objekt, um Werte aus der Tabelle Orders der Beispieldatenbank Northwind abzurufen.  Das `DataRetriever`\-Objekt, das die von der `Cache`\-Klasse benötigte `IDataPageRetriever`\-Schnittstelle implementiert, wird außerdem zum Initialisieren der Zeilen und Spalten des <xref:System.Windows.Forms.DataGridView>\-Steuerelements verwendet.  
  
 Die Typen `IDataPageRetriever`, `DataRetriever` und `Cache` werden später in diesem Thema beschrieben.  
  
> [!NOTE]
>  Das Speichern vertraulicher Informationen, beispielsweise Kennwörter, innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen.  Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows\-Authentifizierung \(wird auch als integrierte Sicherheit bezeichnet\) sicherer steuern.  Weitere Informationen finden Sie unter [Schützen von Verbindungsinformationen](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#100)]  
  
## Die IDataPageRetriever\-Schnittstelle  
 Im folgenden Codebeispiel wird die `IDataPageRetriever`\-Schnittstelle, die von der `DataRetriever`\-Klasse implementiert wird, definiert.  Die einzige Methode, die in dieser Schnittstelle deklariert wird, ist die `SupplyPageOfData`\-Methode, die einen anfänglichen Zeilenindex und die Anzahl der Zeilen auf einer einzelnen Datenseite benötigt.  Diese Werte werden vom Implementierer verwendet, um aus einer Datenquelle einen Teil der Daten abzurufen.  
  
 Ein `Cache`\-Objekt verwendet die Implementierung dieser Schnittstelle während der Erstellung, um zwei erste Datenseiten zu laden.  Wenn ein nicht zwischengespeicherter Wert benötigt wird, verwirft der Cache eine dieser Seiten und fordert vom `IDataPageRetriever` einen neue Seite mit dem entsprechenden Wert an.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#201)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#201)]  
  
## Die DataRetriever\-Klasse  
 Im folgenden Codebeispiel wird die `DataRetriever`\-Klasse definiert, die die `IDataPageRetriever`\-Schnittstelle implementiert, um Datenseiten von einem Server abzufragen.  Die `DataRetriever`\-Klasse stellt zudem die `Columns`\-Eigenschaft und `RowCount`\-Eigenschaft bereit, die das <xref:System.Windows.Forms.DataGridView>\-Steuerelement verwendet, um die erforderlichen Spalten zu erstellen und die entsprechende Anzahl leerer Zeilen zur <xref:System.Windows.Forms.DataGridView.Rows%2A>\-Auflistung hinzuzufügen.  Die leeren Zeilen müssen hinzugefügt werden, damit das Steuerelement sich so verhält, als würde es alle Daten in der Tabelle enthalten.  Das bedeutet, dass das Bildlauffeld in der Schiebeleiste die entsprechende Größe hat und der Benutzer auf jede Zeile in der Tabelle zugreifen kann.  Die Zeilen werden vom <xref:System.Windows.Forms.DataGridView.CellValueNeeded>\-Ereignishandler nur gefüllt, wenn ein Bildlauf zu ihnen durchgeführt wird.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#200)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#200)]  
  
## Die Cache\-Klasse  
 Im folgenden Codebeispiel wird die `Cache`\-Klasse definiert, die zwei Datenseiten verwaltet, die durch eine `IDataPageRetriever`\-Implementierung gefüllt werden.  Die `Cache`\-Klasse definiert eine innere `DataPage`\-Struktur, die eine <xref:System.Data.DataTable> enthält, die die Werte in einer einzelnen Cacheseite speichert und die Zeilenindizes berechnet, die der oberen und unteren Umgrenzung der Seite entsprechen.  
  
 Die `Cache`\-Klasse lädt zur Konstruktionszeit zwei Datenseiten.  Wenn das <xref:System.Windows.Forms.DataGridView.CellValueNeeded>\-Ereignis einen Wert anfordert, bestimmt das `Cache`\-Objekt, ob der Wert in einer der beiden Seiten verfügbar ist, und gibt sie in diesem Fall zurück.  Wenn der Wert lokal nicht verfügbar ist, bestimmt das `Cache`\-Objekt, welche der beiden Seiten von den derzeit angezeigten Zeilen am weitesten entfernt ist und ersetzt die Seite durch eine neue Seite mit dem angeforderten Wert, der daraufhin zurückgegeben wird.  
  
 Vorausgesetzt, dass die Anzahl der Zeilen in einer Datenseite mit der Anzahl der Zeilen, die gleichzeitig auf dem Bildschirm angezeigt werden können, identisch ist, können Benutzer mit diesem Modell einen Bildlauf durch die Tabelle durchführen, um die zuletzt angezeigte Seite effizient zurückzugeben.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#300)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#300)]  
  
## Weitere Überlegungen  
 Die vorherigen Codebeispiele werden zur Veranschaulichung des Just\-In\-Time\-Ladens von Daten bereitgestellt.  Um maximale Effizienz zu erreichen, müssen Sie den Code an Ihre jeweiligen Anforderungen anpassen.  Dabei müssen Sie zumindest einen geeigneten Wert für die Anzahl der Zeilen pro Datenseite im Cache auswählen.  Dieser Wert wird an den `Cache`\-Konstruktor übergeben.  Die Anzahl der Zeilen pro Seite sollte nicht geringer sein als die Anzahl der Zeilen, die gleichzeitig im <xref:System.Windows.Forms.DataGridView>\-Steuerelement angezeigt werden können.  
  
 Um optimale Ergebnisse zu erzielen, müssen Sie Leistungs\- und Verwendbarkeitstests ausführen, damit Sie die Anforderungen des Systems und der Benutzer bestimmen können.  Zu den zahlreichen Faktoren, die Sie berücksichtigen müssen, gehören der Speicherplatz auf den Clientrechnern, auf denen die Anwendung ausgeführt wird, die verfügbare Bandbreite der verwendeten Netzwerkverbindung und die Wartezeit des verwendeten Servers.  Die Bandbreite und die Wartezeit sollten bei höchster Auslastung bestimmt werden.  
  
 Um die Bildlaufleistung der Anwendung zu verbessern, können Sie die lokal gespeicherte Datenmenge erhöhen.  Um aber die Startzeit zu verbessern, dürfen Sie anfänglich nicht zu viele Daten laden.  Unter Umständen sollten Sie die `Cache`\-Klasse ändern, um die Anzahl der Datenseiten zu erhöhen, die sie speichern kann.  Wenn Sie mehr Datenseiten verwenden, können Sie die Bildlaufeffizienz verbessern. Je nach verfügbarer Bandbreite und Wartezeit des Servers müssen Sie jedoch die ideale Anzahl der Zeilen in einer Datenseite bestimmen.  Bei kleineren Seiten erfolgt der Zugriff auf den Server zwar häufiger, die Rückgabe der Daten nimmt jedoch weniger Zeit in Anspruch.  Wenn die Wartezeit ein größeres Problems als die Bandbreite darstellt, sollten Sie größere Datenseiten verwenden.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>   
 [Leistungsoptimierung im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)   
 [Empfohlene Vorgehensweisen für das Skalieren des DataGridView\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)   
 [Virtueller Modus im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)   
 [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)   
 [Gewusst wie: Implementieren des virtuellen Modus mit Just\-In\-Time\-Laden von Daten in das DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)