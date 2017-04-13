---
title: "Gewusst wie: Abrufen von Daten aus der Zwischenablage | Microsoft Docs"
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
  - "Zwischenablage, Abrufen von Daten"
  - "Einfügen von Zwischenablagedaten"
ms.assetid: 99612537-2c8a-449f-aab5-2b3b28d656e7
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Abrufen von Daten aus der Zwischenablage
Die <xref:System.Windows.Forms.Clipboard>\-Klasse stellt Methoden für den Zugriff auf die Zwischenablage des Windows\-Betriebssystems bereit.  Viele Anwendungen verwenden die Zwischenablage als temporären Speicher für Daten.  In Textverarbeitungsprogrammen wird sie beispielsweise während der Operationen Ausschneiden, Kopieren und Einfügen eingesetzt.  Die Zwischenablage ist auch hilfreich, um Informationen von einer Anwendung in eine andere zu übertragen.  
  
 Einige Anwendungen speichern Daten in mehreren Formaten in der Zwischenablage, um die Anzahl weiterer Anwendungen zu erhöhen, die diese Daten nutzen können.  Ein Zwischenablageformat ist eine Zeichenfolge zur Kennzeichnung des Formats.  Eine Anwendung, die dieses Format verwendet, kann die zugeordneten Daten in der Zwischenablage abrufen.  Die <xref:System.Windows.Forms.DataFormats>\-Klasse stellt vordefinierte Formatnamen bereit.  Sie können auch eigene Formatnamen verwenden oder den Typ eines Objekts als Format verwenden.  Weitere Informationen zum Hinzufügen von Daten zur Zwischenablage finden Sie unter [Gewusst wie: Hinzufügen von Daten zur Zwischenablage](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md).  
  
 Um festzustellen, ob die Zwischenablage Daten in einem bestimmten Format enthält, verwenden Sie eine der `Contains`*Format*\-Methoden oder die <xref:System.Windows.Forms.Clipboard.GetData%2A>\-Methode.  Um Daten aus der Zwischenablage abzurufen, verwenden Sie eine der `Get`*Format*\-Methoden oder die <xref:System.Windows.Forms.Clipboard.GetData%2A>\-Methode.  Diese Methoden sind neu in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
 Um mit Versionen vor [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] auf Daten in der Zwischenablage zuzugreifen, verwenden Sie die <xref:System.Windows.Forms.Clipboard.GetDataObject%2A>\-Methode und rufen die Methoden des zurückgegebenen <xref:System.Windows.Forms.IDataObject> auf.  Um festzustellen, ob ein bestimmtes Format im zurückgegebenen Objekt verfügbar ist, rufen Sie beispielsweise die <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A>\-Methode auf.  
  
> [!NOTE]
>  Die Systemzwischenablage ist für alle Windows\-basierten Anwendungen freigegeben.  Aus diesem Grund kann sich der Inhalt ändern, wenn Sie zu einer anderen Anwendung wechseln.  
>   
>  Die <xref:System.Windows.Forms.Clipboard>\-Klasse kann nur in Threads verwendet werden, für die der STA\-Modus \(Single Thread Apartment\) aktiviert wurde.  Um diese Klasse zu verwenden, stellen Sie sicher, dass die `Main`\-Methode mit dem <xref:System.STAThreadAttribute>\-Attribut gekennzeichnet ist.  
  
### So rufen Sie Daten in einem einzelnen allgemeinen Format aus der Zwischenablage ab  
  
1.  Verwenden Sie die Methoden <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>, <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.GetImage%2A> oder <xref:System.Windows.Forms.Clipboard.GetText%2A>.  Optional können Sie zuerst auch die entsprechenden `Contains`*Format*\-Methoden verwenden, um festzustellen, ob Daten in einem bestimmten Format verfügbar sind.  Diese Methoden sind nur in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] verfügbar.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### So rufen Sie Daten in einem benutzerdefinierten Format aus der Zwischenablage ab  
  
1.  Verwenden Sie die <xref:System.Windows.Forms.Clipboard.GetData%2A>\-Methode mit einem benutzerdefinierten Formatnamen.  Diese Methode ist nur in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] verfügbar.  
  
     Sie können auch vordefinierte Formatnamen mit der <xref:System.Windows.Forms.Clipboard.SetData%2A>\-Methode verwenden.  Weitere Informationen finden Sie unter <xref:System.Windows.Forms.DataFormats>.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### So rufen Sie Daten in mehreren Formaten aus der Zwischenablage ab  
  
1.  Verwenden Sie die <xref:System.Windows.Forms.Clipboard.GetDataObject%2A>\-Methode.  Sie müssen diese Methode verwenden, um in Versionen vor [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] Daten aus der Zwischenablage abzurufen.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## Siehe auch  
 [Drag & Drop\-Operationen und Unterstützung der Zwischenablage](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)   
 [Gewusst wie: Hinzufügen von Daten zur Zwischenablage](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)