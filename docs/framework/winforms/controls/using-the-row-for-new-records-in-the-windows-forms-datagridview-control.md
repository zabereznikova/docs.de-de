---
title: "Verwenden der Zeile f&#252;r neue Datens&#228;tze im DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
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
  - "DataGridView-Steuerelement [Windows Forms], Hinzufügen von Zeilen für neue Datensätze"
  - "DataGridView-Steuerelement [Windows Forms], Dateneingabe"
  - "Zeilen, Neue Datensätze"
ms.assetid: 6110f1ea-9794-442c-a98a-f104a1feeaf4
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Verwenden der Zeile f&#252;r neue Datens&#228;tze im DataGridView-Steuerelement in Windows Forms
Wenn Sie zur Bearbeitung von Daten in der Anwendung eine <xref:System.Windows.Forms.DataGridView> verwenden, möchten Sie den Benutzern häufig die Möglichkeit geben, neue Datenzeilen zum Datastore hinzuzufügen.  Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement unterstützt diese Funktionalität, indem es eine Zeile für neue Datensätze bereitstellt, die stets als letzte Zeile angezeigt wird.  Sie ist mit einem Sternchensymbol \(\*\) im Zeilenheader gekennzeichnet.  In den folgenden Abschnitten werden einige der Punkte erörtert, die Sie beim Programmieren beachten sollten, wenn die Zeile für neue Datensätze aktiviert ist.  
  
## Anzeigen der Zeile für neue Datensätze  
 Verwenden Sie die <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A>\-Eigenschaft, um anzugeben, ob die Zeile für neue Datensätze angezeigt wird.  Der Standardwert dieser Eigenschaft ist `true`.  
  
 Bei gebundenen Daten wird die Zeile für neue Datensätze angezeigt, wenn die <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A>\-Eigenschaft des Steuerelements und die <xref:System.ComponentModel.IBindingList.AllowNew%2A?displayProperty=fullName>\-Eigenschaft der Datenquelle beide auf `true` festgelegt sind.  Wenn eine der Eigenschaften auf `false` festgelegt ist, wird die Zeile nicht angezeigt.  
  
## Füllen der Zeile für neue Datensätze mit Standarddaten  
 Wenn der Benutzer die Zeile für neue Datensätze als aktuelle Zeile auswählt, löst das <xref:System.Windows.Forms.DataGridView>\-Steuerelement das <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>\-Ereignis aus.  
  
 Dieses Ereignis ermöglicht den Zugriff auf die neue <xref:System.Windows.Forms.DataGridViewRow> sowie das Füllen der neuen Zeile mit Standarddaten.  Weitere Informationen finden Sie unter [Gewusst wie: Angeben von Standardwerten für neue Zeilen im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/specify-default-values-for-new-rows-in-the-datagrid.md)  
  
## Die Zeilenauflistung  
 Die Zeile für neue Datensätze ist in der <xref:System.Windows.Forms.DataGridView.Rows%2A>\-Auflistung des <xref:System.Windows.Forms.DataGridView>\-Steuerelements enthalten, verhält sich aber in zweierlei Hinsicht verschieden:  
  
-   Die Zeile für neue Datensätze kann nicht programmgesteuert aus der <xref:System.Windows.Forms.DataGridView.Rows%2A>\-Auflistung entfernt werden.  Bei dem Versuch wird eine <xref:System.InvalidOperationException> ausgelöst.  Der Benutzer kann außerdem nicht die Zeile für neue Datensätze löschen.  Die <xref:System.Windows.Forms.DataGridViewRowCollection.Clear%2A?displayProperty=fullName>\-Methode entfernt diese Zeile nicht aus der <xref:System.Windows.Forms.DataGridView.Rows%2A>\-Auflistung.  
  
-   Nach der Zeile für neue Datensätze kann keine Zeile hinzugefügt werden.  Bei dem Versuch wird eine <xref:System.InvalidOperationException> ausgelöst.  Demzufolge ist die Zeile für neue Datensätze immer die letzte Zeile im <xref:System.Windows.Forms.DataGridView>\-Steuerelement.  Die Methoden für die <xref:System.Windows.Forms.DataGridViewRowCollection>, mit denen Zeilen hinzugefügt werden, nämlich <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A> und <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>, rufen intern Einfügungsmethoden auf, wenn die Zeile für neue Datensätze vorhanden ist.  
  
## Visuelle Anpassung der Zeile für neue Datensätze  
 Wenn die Zeile für neue Datensätze erstellt wird, basiert sie auf der Zeile, die durch die <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>\-Eigenschaft angegeben wird.  Alle Zellenstile, die nicht für diese Zeile angegeben sind, werden von anderen Eigenschaften geerbt.  Weitere Informationen über die Vererbung von Zellenstilen finden Sie unter [Zellstile im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
 Die Anfangswerte der Zellen in der Zeile für neue Datensätze werden aus der <xref:System.Windows.Forms.DataGridViewCell.DefaultNewRowValue%2A>\-Eigenschaft der jeweiligen Zellen abgerufen.  Bei Zellen des Typs <xref:System.Windows.Forms.DataGridViewImageCell> gibt diese Eigenschaft ein Platzhalterbild zurück.  Andernfalls gibt diese Eigenschaft `null` zurück.  Sie können diese Eigenschaft überschreiben, um einen benutzerdefinierten Wert zurückzugeben.  Diese Anfangswerte können jedoch durch einen <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>\-Ereignishandler ersetzt werden, wenn die Zeile für neue Datensätze den Fokus hat.  
  
 Die Standardsymbole für den Header dieser Zeile, ein Pfeil oder ein Sternchen, werden nicht öffentlich verfügbar gemacht.  Wenn Sie die Symbole anpassen möchten, müssen Sie eine benutzerdefinierte <xref:System.Windows.Forms.DataGridViewRowHeaderCell>\-Klasse erstellen.  
  
 Die Standardsymbole verwenden die <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>\-Eigenschaft des <xref:System.Windows.Forms.DataGridViewCellStyle> der Zeilenheaderzelle.  Die Standardsymbole werden nicht gerendert, wenn nicht genug Platz vorhanden ist, um sie vollständig anzuzeigen.  
  
 Wenn für die Zeilenheaderzelle ein Zeichenfolgenwert festgelegt ist und nicht genug Platz für den Text und das Symbol ist, wird das Symbol nicht angezeigt.  
  
## Sortieren  
 Im ungebundenen Modus werden neue Datensätze stets am Ende der <xref:System.Windows.Forms.DataGridView> hinzugefügt, auch wenn der Benutzer den Inhalt der <xref:System.Windows.Forms.DataGridView> sortiert hat.  Der Benutzer muss erneut sortieren, damit die Zeile in der richtigen Position angezeigt wird. Dieses Verhalten ist vergleichbar mit dem des <xref:System.Windows.Forms.ListView>\-Steuerelements.  
  
 Im datengebundenen und virtuellen Modus hängt das Einfügeverhalten beim Sortieren von der Implementierung des Datenmodells ab.  Für [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] wird die Zeile sofort richtig sortiert.  
  
## Andere Hinweise zur Zeile für neue Datensätze  
 Sie können die <xref:System.Windows.Forms.DataGridViewRow.Visible%2A>\-Eigenschaft dieser Zeile nicht auf `false` festlegen.  Bei dem Versuch wird eine <xref:System.InvalidOperationException> ausgelöst.  
  
 Die Zeile für neue Datensätze wird immer im nicht ausgewählten Zustand erstellt.  
  
## Virtueller Modus  
 Wenn Sie den virtuellen Modus implementieren, müssen Sie verfolgen, wann eine Zeile für neue Datensätze im Datenmodell erforderlich ist und wann sie wieder entfernt werden kann.  Die genaue Implementierung dieser Funktion hängt von der Implementierung des Datenmodells und seiner Transaktionssemantik ab, beispielsweise ob sich der Commit\-Bereich auf Zellenebene oder Zeilenebene befindet.  Weitere Informationen finden Sie unter [Virtueller Modus im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=fullName>   
 [Dateneingabe im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)   
 [Gewusst wie: Angeben von Standardwerten für neue Zeilen im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/specify-default-values-for-new-rows-in-the-datagrid.md)