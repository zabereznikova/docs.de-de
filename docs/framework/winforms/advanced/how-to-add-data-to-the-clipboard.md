---
title: "Gewusst wie: Hinzuf&#252;gen von Daten zur Zwischenablage | Microsoft Docs"
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
  - "Zwischenablage, Kopieren von Daten nach"
  - "Daten [Windows Forms], Kopieren in die Zwischenablage"
ms.assetid: 25152454-0e78-40a9-8a9e-a2a5a274e517
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Hinzuf&#252;gen von Daten zur Zwischenablage
Die <xref:System.Windows.Forms.Clipboard>\-Klasse stellt Methoden für den Zugriff auf die Zwischenablage des Windows\-Betriebssystems bereit.  Viele Anwendungen verwenden die Zwischenablage als temporären Speicher für Daten.  In Textverarbeitungsprogrammen wird sie beispielsweise während der Operationen Ausschneiden, Kopieren und Einfügen eingesetzt.  Die Zwischenablage ist auch hilfreich, um Informationen von einer Anwendung an eine andere zu übertragen.  
  
 Wenn Sie der Zwischenablage Daten hinzufügen, können Sie das Datenformat angeben. Auf diese Weise können andere Anwendungen, die das angegebene Format unterstützen, die Daten korrekt abrufen.  Darüber hinaus können Sie der Zwischenablage Daten in vielen verschiedenen Formaten hinzufügen, um die Anzahl der Anwendungen zu erweitern, die die Daten nutzen können.  
  
 Ein Zwischenablageformat ist eine Zeichenfolge zur Kennzeichnung des Formats, sodass eine Anwendung, die dieses Format unterstützt, die zugehörigen Daten abrufen kann.  Die <xref:System.Windows.Forms.DataFormats>\-Klasse stellt vordefinierte Formatnamen bereit.  Sie können auch eigene Formatnamen verwenden oder den Typ eines Objekts als Format verwenden.  
  
 Um Daten in einem oder mehreren Formaten in die Zwischenablage aufzunehmen, verwenden Sie die <xref:System.Windows.Forms.Clipboard.SetDataObject%2A>\-Methode.  Sie können beliebige Objekte an diese Methode übergeben. Um Daten in mehreren Formaten hinzuzufügen, müssen Sie die Daten jedoch zuerst einem separaten Objekt hinzufügen, das das Arbeiten mit mehreren Formaten unterstützt.  Normalerweise werden die Daten <xref:System.Windows.Forms.DataObject> hinzugefügt. Ihnen steht jedoch die Verwendung eines beliebigen Typs frei, durch den die <xref:System.Windows.Forms.IDataObject>\-Schnittstelle implementiert wird.  
  
 In [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] können Sie Daten direkt zur Zwischenablage hinzufügen, da mithilfe neuer Methoden die grundlegenden Aufgaben beim Arbeiten mit der Zwischenablage vereinfacht werden.  Verwenden Sie diese Methoden, wenn Sie Daten in einem einzelnen allgemeinen Format, z. B. Text, verwenden.  
  
> [!NOTE]
>  Alle Windows\-basierten Anwendungen können auf die Zwischenablage zugreifen.  Aus diesem Grund kann sich der Inhalt ändern, wenn Sie zu einer anderen Anwendung wechseln.  
>   
>  Die <xref:System.Windows.Forms.Clipboard>\-Klasse kann nur in Threads verwendet werden, für die der STA\-Modus \(Single Thread Apartment\) aktiviert wurde.  Um diese Klasse zu verwenden, stellen Sie sicher, dass die `Main`\-Methode mit dem <xref:System.STAThreadAttribute>\-Attribut gekennzeichnet ist.  
>   
>  Damit ein Objekt in der Zwischenablage abgelegt werden kann, muss es serialisierbar sein.  Um einen Typ serialisierbar zu machen, kennzeichnen Sie ihn mit dem <xref:System.SerializableAttribute>\-Attribut.  Wenn Sie ein nicht serialisierbares Objekt an eine Clipboard\-Methode übergeben, schlägt die Methode fehl, ohne dass eine Ausnahme ausgelöst wird.  Weitere Informationen zur Serialisierung finden Sie unter <xref:System.Runtime.Serialization>.  
  
### So fügen Sie Daten in einem einzelnen allgemeinen Format zur Zwischenablage hinzu  
  
1.  Verwenden Sie die Methoden <xref:System.Windows.Forms.Clipboard.SetAudio%2A>, <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A> oder <xref:System.Windows.Forms.Clipboard.SetText%2A>.  Diese Methoden sind nur in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] verfügbar.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### So fügen Sie Daten in einem benutzerdefinierten Format zur Zwischenablage hinzu  
  
1.  Verwenden Sie die <xref:System.Windows.Forms.Clipboard.SetData%2A>\-Methode mit einem benutzerdefinierten Formatnamen.  Diese Methode ist nur in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] verfügbar.  
  
     Sie können auch vordefinierte Formatnamen mit der <xref:System.Windows.Forms.Clipboard.SetData%2A>\-Methode verwenden.  Weitere Informationen finden Sie unter <xref:System.Windows.Forms.DataFormats>.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### So fügen Sie Daten in mehreren Formaten zur Zwischenablage hinzu  
  
1.  Verwenden Sie die <xref:System.Windows.Forms.Clipboard.SetDataObject%2A>\-Methode, und übergeben Sie ein <xref:System.Windows.Forms.DataObject>, das Ihre Daten enthält.  In Versionen vor [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] müssen Sie diese Methode verwenden, um der Zwischenablage Daten hinzuzufügen.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## Siehe auch  
 [Drag & Drop\-Operationen und Unterstützung der Zwischenablage](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)   
 [Gewusst wie: Abrufen von Daten aus der Zwischenablage](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)