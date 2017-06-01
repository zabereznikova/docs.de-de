---
title: "Gewusst wie: Navigieren durch Daten in Windows Forms | Microsoft Docs"
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
  - "CurrencyManager-Klasse, Navigieren durch Windows Forms-Daten"
  - "Cursor, Datenquellen"
  - "Daten [Windows Forms], Navigieren"
  - "Datenquellen, Windows Forms"
  - "Windows Forms, Navigieren"
ms.assetid: 97360f7b-b181-4084-966a-4c62518f735b
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Navigieren durch Daten in Windows Forms
In einer Windows\-Anwendung besteht die einfachste Möglichkeit zum Navigieren zwischen Datensätzen in einer Datenquelle darin, eine <xref:System.Windows.Forms.BindingSource>\-Komponente an die Datenquelle und dann Steuerelemente an <xref:System.Windows.Forms.BindingSource> zu binden.  Sie können dann die integrierte Navigationsmethode in <xref:System.Windows.Forms.BindingSource> verwenden, z. B. <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A>, <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> und <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>.  Mithilfe dieser Methoden werden die <xref:System.Windows.Forms.BindingSource.Position%2A>\-Eigenschaft und die <xref:System.Windows.Forms.BindingSource.Current%2A>\-Eigenschaft von <xref:System.Windows.Forms.BindingSource> entsprechend angepasst.  Sie können ein Element auch suchen, um es als aktuelles Element festzulegen. Dazu legen Sie die <xref:System.Windows.Forms.BindingSource.Position%2A>\-Eigenschaft fest.  
  
### So erhöhen Sie die Position in einer Datenquelle  
  
1.  Legen Sie die <xref:System.Windows.Forms.BindingSource.Position%2A>\-Eigenschaft von <xref:System.Windows.Forms.BindingSource> für die gebundenen Daten auf die entsprechende Datensatzposition fest.  Im folgenden Beispiel wird mithilfe der <xref:System.Windows.Forms.BindingSource.MoveNext%2A>\-Methode von <xref:System.Windows.Forms.BindingSource> veranschaulicht, wie die <xref:System.Windows.Forms.BindingSource.Position%2A>\-Eigenschaft beim Klicken auf `nextButton` erhöht wird.  <xref:System.Windows.Forms.BindingSource> ist mit der Tabelle `Customers` eines `Northwind`\-DataSets verknüpft.  
  
    > [!NOTE]
    >  Das Festlegen der <xref:System.Windows.Forms.BindingSource.Position%2A>\-Eigenschaft auf einen Wert, der über den ersten oder letzten Datensatz hinausgeht, verursacht keinen Fehler, da [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] verhindert, dass Sie die Position auf einen Wert außerhalb der durch die Liste vorgegebenen Grenzen festlegen.  Wenn es in der Anwendung von Bedeutung ist, dass Sie wissen, ob Sie den ersten oder letzten Datensatz überschritten haben, verwenden Sie Logik zum Testen, ob die Datenelementeanzahl überschritten wird.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### So prüfen Sie, ob das Ende oder der Anfang überschritten wurde  
  
1.  Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.BindingSource.PositionChanged>\-Ereignis.  Im Rahmen der Behandlungsroutine können Sie überprüfen, ob der vorgeschlagene Positionswert die tatsächliche Datenelementanzahl überschreitet.  
  
     Im folgenden Beispiel wird demonstriert, wie Sie überprüfen können, ob das letzte Datenelement erreicht wurde.  Wenn im Beispiel das letzte Element erreicht wurde, ist die Schaltfläche **Weiter** im Formular deaktiviert.  
  
    > [!NOTE]
    >  Wenn Sie die Liste ändern, in der Sie im Code navigieren, müssen Sie die Schaltfläche **Weiter** erneut aktivieren, damit die Benutzer die neue Liste in ihrer gesamten Länge durchsuchen können.  Achten Sie außerdem darauf, dass das oben angegebene <xref:System.Windows.Forms.BindingSource.PositionChanged>\-Ereignis für das verwendete <xref:System.Windows.Forms.BindingSource>\-Element der entsprechenden Ereignisbehandlungsmethode zugeordnet sein muss.  Im Folgenden finden Sie ein Beispiel für eine Methode zum Behandeln des <xref:System.Windows.Forms.BindingSource.PositionChanged>\-Ereignisses:  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### So suchen Sie ein Element und legen es als aktuelles Element fest  
  
1.  Suchen Sie den Datensatz, den Sie als aktuelles Element festlegen möchten.  Sie können dazu die <xref:System.Windows.Forms.BindingSource.Find%2A>\-Methode von <xref:System.Windows.Forms.BindingSource> verwenden, wenn die Datenquelle <xref:System.ComponentModel.IBindingList> implementiert.  Einige Beispiele für Datenquellen, die <xref:System.ComponentModel.IBindingList> implementieren, sind <xref:System.ComponentModel.BindingList%601> und <xref:System.Data.DataView>.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## Siehe auch  
 [Von Windows Forms unterstützte Datenquellen](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)   
 [Änderungsbenachrichtigung in der Windows Forms\-Datenbindung](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)   
 [Datenbindung und Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)   
 [Datenbindung in Web Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)