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
ms.openlocfilehash: fa40f1657a433f5f4ade3de25648ca04c37dfa67
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962599"
---
# <a name="implementing-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a>Implementieren des virtuellen Modus mit Just-In-Time-Laden von Daten in das DataGridView-Steuerelement in Windows Forms
Ein Grund für die Implementierung des <xref:System.Windows.Forms.DataGridView> virtuellen Modus im Steuerelement besteht darin, Daten nur nach Bedarf abzurufen. Dies wird als *Just-in-Time-Laden von Daten*bezeichnet.  
  
 Wenn Sie z. b. mit einer sehr großen Tabelle in einer Remote Datenbank arbeiten, möchten Sie möglicherweise Start Verzögerungen vermeiden, indem Sie nur die Daten abrufen, die für die Anzeige und das Abrufen zusätzlicher Daten benötigt werden, wenn der Benutzer in der Ansicht neue Zeilen durchläuft. Wenn auf den Client Computern, auf denen Ihre Anwendung ausgeführt wird, eine begrenzte Menge an Arbeitsspeicher zum Speichern von Daten verfügbar ist, sollten Sie beim Abrufen neuer Werte aus der Datenbank auch nicht verwendete Daten verwerfen.  
  
 In den folgenden Abschnitten wird beschrieben, wie <xref:System.Windows.Forms.DataGridView> Sie ein-Steuerelement mit einem Just-in-Time-Cache verwenden.  
  
 Zum Kopieren des Codes in diesem Thema als einzelne Auflistung lesen Sie [Vorgehensweise: Implementieren des virtuellen Modus mit Just-in-Time-Laden von Daten in das Windows Forms DataGridView-Steuer](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)Element.  
  
## <a name="the-form"></a>Das Formular  
 Im folgenden Codebeispiel wird ein Formular definiert, das ein <xref:System.Windows.Forms.DataGridView> Schreib geschütztes Steuerelement enthält, das mit einem `Cache` - <xref:System.Windows.Forms.DataGridView.CellValueNeeded> Objekt über einen-Ereignishandler interagiert. Das `Cache` -Objekt verwaltet die lokal gespeicherten Werte und verwendet `DataRetriever` ein-Objekt, um Werte aus der Orders-Tabelle der Northwind-Beispieldatenbank abzurufen. Das `DataRetriever` -Objekt, das die `IDataPageRetriever` -Schnittstelle implementiert `Cache` , die von der-Klasse benötigt wird, <xref:System.Windows.Forms.DataGridView> wird auch verwendet, um die Steuer Zeilen und Spalten zu initialisieren.  
  
 Die `IDataPageRetriever`Typen `DataRetriever`, und`Cache` werden weiter unten in diesem Thema beschrieben.  
  
> [!NOTE]
> Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen. Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows-Authentifizierung (wird auch als integrierte Sicherheit bezeichnet) sicherer steuern. Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../data/adonet/protecting-connection-information.md).  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#100)]  
  
## <a name="the-idatapageretriever-interface"></a>Die IDataPageRetriever-Schnittstelle  
 Im folgenden Codebeispiel wird die `IDataPageRetriever` -Schnittstelle definiert, die von `DataRetriever` der-Klasse implementiert wird. Die einzige in dieser Schnittstelle deklarierte Methode `SupplyPageOfData` ist die-Methode, die einen anfänglichen Zeilen Index und die Anzahl der Zeilen in einer einzelnen Datenseite erfordert. Diese Werte werden vom Implementierer verwendet, um eine Teilmenge der Daten aus einer Datenquelle abzurufen.  
  
 Ein `Cache` -Objekt verwendet eine Implementierung dieser Schnittstelle während der Erstellung, um zwei anfängliche Datenseiten zu laden. Wenn ein nicht zwischen gespeicherter Wert benötigt wird, verwirft der Cache eine dieser Seiten und fordert eine neue Seite an, die `IDataPageRetriever`den Wert aus der enthält.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#201)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#201)]  
  
## <a name="the-dataretriever-class"></a>Die DataRetriever-Klasse  
 Im folgenden Codebeispiel wird die `DataRetriever` -Klasse definiert, die `IDataPageRetriever` die-Schnittstelle implementiert, um Datenseiten von einem Server abzurufen. Die `DataRetriever` -Klasse stellt `Columns` außerdem-und-Eigenschaften <xref:System.Windows.Forms.DataGridView> bereit, die das- `RowCount` Steuerelement verwendet, um die erforderlichen Spalten zu erstellen <xref:System.Windows.Forms.DataGridView.Rows%2A> und der Auflistung die entsprechende Anzahl von leeren Zeilen hinzuzufügen. Das Hinzufügen der leeren Zeilen ist erforderlich, damit sich das Steuerelement so verhält, als ob es alle Daten in der Tabelle enthält. Dies bedeutet, dass das Bild Lauf Feld auf der Bild Lauf Leiste die entsprechende Größe hat und der Benutzer auf eine beliebige Zeile in der Tabelle zugreifen kann. Die Zeilen werden nur dann vom <xref:System.Windows.Forms.DataGridView.CellValueNeeded> Ereignishandler ausgefüllt, wenn Sie in die Ansicht gescrollt werden.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#200)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#200)]  
  
## <a name="the-cache-class"></a>Die Cache-Klasse  
 Im folgenden Codebeispiel wird die `Cache` -Klasse definiert, die zwei Datenseiten verwaltet, die `IDataPageRetriever` durch eine-Implementierung aufgefüllt werden. Die `Cache` -Klasse definiert eine `DataPage` innere Struktur, die eine <xref:System.Data.DataTable> enthält, um die Werte auf einer einzelnen Cache Seite zu speichern und die Zeilen Indizes zu berechnen, die die oberen und unteren Grenzen der Seite darstellen.  
  
 Die `Cache` -Klasse lädt zwei Datenseiten zur Konstruktionszeit. Wenn das <xref:System.Windows.Forms.DataGridView.CellValueNeeded> Ereignis einen Wert anfordert, `Cache` bestimmt das Objekt, ob der Wert auf einer der beiden Seiten verfügbar ist, und gibt, wenn dies der Fall ist, ihn zurück. Wenn der Wert nicht lokal verfügbar ist, bestimmt `Cache` das Objekt, welche der beiden Seiten von den aktuell angezeigten Zeilen entfernt werden, und ersetzt die Seite durch einen neuen, der den angeforderten Wert enthält, der dann zurückgegeben wird.  
  
 Wenn die Anzahl der Zeilen auf einer Datenseite mit der Anzahl der Zeilen identisch ist, die auf dem Bildschirm gleichzeitig angezeigt werden können, ermöglicht dieses Modell Benutzern das Paging durch die Tabelle, um effizient zur zuletzt angezeigten Seite zurückzukehren.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#300)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#300)]  
  
## <a name="additional-considerations"></a>Weitere Überlegungen  
 Die vorherigen Codebeispiele werden als Demonstration von Just-in-Time-Daten Ladevorgängen bereitgestellt. Sie müssen den Code für Ihre eigenen Anforderungen ändern, um eine maximale Effizienz zu erzielen. Sie müssen mindestens einen entsprechenden Wert für die Anzahl der Zeilen pro Datenseite im Cache auswählen. Dieser Wert wird an den `Cache` -Konstruktor übergeben. Die Anzahl der Zeilen pro Seite darf nicht kleiner sein als die Anzahl der Zeilen, die gleichzeitig im <xref:System.Windows.Forms.DataGridView> Steuerelement angezeigt werden können.  
  
 Um optimale Ergebnisse zu erzielen, müssen Sie Leistungstests und Nutzbarkeits Tests durchführen, um die Anforderungen Ihres Systems und ihrer Benutzer zu bestimmen. Sie müssen auch die Menge an Arbeitsspeicher auf den Client Computern, auf denen Ihre Anwendung ausgeführt wird, sowie die verfügbare Bandbreite der verwendeten Netzwerkverbindung und die Wartezeit des verwendeten Servers berücksichtigen. Bandbreite und Latenz sollten zu Zeiten der Spitzen Auslastung bestimmt werden.  
  
 Um die scrollleistung Ihrer Anwendung zu verbessern, können Sie die Datenmenge, die lokal gespeichert ist, erhöhen. Um die Startzeit zu verbessern, müssen Sie jedoch zunächst vermeiden, zu viele Daten zu laden. Möglicherweise möchten Sie die `Cache` -Klasse ändern, um die Anzahl der Datenseiten zu erhöhen, die Sie speichern kann. Die Verwendung von mehr Datenseiten kann die Bild Lauf Effizienz verbessern, Sie müssen jedoch die ideale Anzahl von Zeilen auf einer Datenseite bestimmen, abhängig von der verfügbaren Bandbreite und der Server Latenz. Bei kleineren Seiten erfolgt der Zugriff auf den Server häufiger, aber es dauert weniger Zeit, um die angeforderten Daten zurückzugeben. Wenn die Latenz eher ein Problem als die Bandbreite ist, empfiehlt es sich, größere Datenseiten zu verwenden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- [Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Virtueller Modus im DataGridView-Steuerelement in Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement Windows Forms](implementing-virtual-mode-wf-datagridview-control.md)
- [Vorgehensweise: Implementieren des virtuellen Modus mit Just-in-Time-Laden von Daten in das Windows Forms DataGridView-Steuerelement](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)
