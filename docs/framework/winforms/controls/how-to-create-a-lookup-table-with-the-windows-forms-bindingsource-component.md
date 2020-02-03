---
title: Erstellen einer Nachschlage Tabelle mit der BindingSource-Komponente
ms.date: 03/30/2017
helpviewer_keywords:
- lookup tables
- tables [Windows Forms], creating lookup tables
- BindingSource component [Windows Forms], creating a lookup table
- BindingSource component [Windows Forms], examples
ms.assetid: 622fce80-879d-44be-abbf-8350ec22ca2b
ms.openlocfilehash: ccf2bfa6cf3f56a38b55f8c87004c42a46172891
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736813"
---
# <a name="how-to-create-a-lookup-table-with-the-windows-forms-bindingsource-component"></a>Gewusst wie: Erstellen einer Suchtabelle mit der BindingSource-Komponente in Windows Forms
Eine Nachschlagetabelle ist eine Tabelle mit Daten, in der die Daten aus Datensätzen einer verknüpften Tabelle in einer Spalte dargestellt werden. In den folgenden Verfahren wird ein <xref:System.Windows.Forms.ComboBox>-Steuerelement für die Anzeige des Felds mit der Fremdschlüsselbeziehung von der übergeordneten zur untergeordneten Tabelle verwendet.  
  
 Zur Visualisierung dieser beiden Tabellen und dieser Beziehung finden Sie hier ein Beispiel einer über- und untergeordneten Tabelle:  
  
 KundenTabelle (übergeordnete Tabelle)  
  
|CustomerID|CustomerName|  
|----------------|------------------|  
|712|Paul Koch|  
|713|Tamara Johnston|  
  
 OrdersTable (untergeordnete Tabelle)  
  
|OrderID|OrderDate|CustomerID|  
|-------------|---------------|----------------|  
|903|Donnerstag, 12. Februar 2004|712|  
|904|13. Februar 2004|713|  
  
 In diesem Szenario speichert eine Tabelle, nämlich KundenTabelle, die tatsächlichen Daten, die Sie anzeigen und speichern möchten. Um aber Platz zu sparen, lässt die Tabelle Daten weg, was für Klarheit sorgt. Die andere Tabelle, BestellungenTabelle, enthält nur erscheinungsbezogene Daten darüber, welche Kunden-ID-Nummer welchem Bestelldatum und welcher Bestell-ID entspricht. Die Kundennamen werden nicht erwähnt.  
  
 Es sind vier wichtige Eigenschaften im [ComboBox-Steuerelement](combobox-control-windows-forms.md) für das Erstellen der Nachschlagetabelle festgelegt.  
  
- Die Eigenschaft <xref:System.Windows.Forms.ComboBox.DataSource%2A> enthält den Namen der Tabelle.  
  
- Die Eigenschaft <xref:System.Windows.Forms.ListControl.DisplayMember%2A> enthält die Datenspalte dieser Tabelle, die für die Anzeige des Text-Steuerelements (der Name des Kunden) anzeigt werden soll.  
  
- Die Eigenschaft <xref:System.Windows.Forms.ListControl.ValueMember%2A> enthält die Datenspalte der Tabelle mit den gespeicherten Informationen (der ID-Nummer und der übergeordneten Tabelle).  
  
- Die Eigenschaft <xref:System.Windows.Forms.ListControl.SelectedValue%2A> liefert den Nachschlagewert für die untergeordnete Tabelle auf Grundlage von <xref:System.Windows.Forms.ListControl.ValueMember%2A>.  
  
 Die Verfahren unten zeigen, wie Sie das Formular als Nachschlagetabelle gestalten und Daten mit den Steuerelementen darauf binden. Um die Verfahren erfolgreich durchführen zu können, benötigen Sie eine Datenquelle mit über- und untergeordneten Tabellen, die – wie bereits erwähnt – eine Fremdschlüsselbeziehung haben.  
  
### <a name="to-create-the-user-interface"></a>So erstellen Sie die Benutzeroberfläche  
  
1. Ziehen Sie ein <xref:System.Windows.Forms.ComboBox>-Steuerelement aus der **Toolbox**auf das Formular.  
  
     Dieses Steuerelement zeigt die Spalte aus der übergeordneten Tabelle an.  
  
2. Ziehen Sie andere Steuerelemente zur Anzeige von Details aus der untergeordneten Tabelle. Das Format der Daten in der Tabelle bestimmt die Auswahl der Steuerelemente. Weitere Informationen finden Sie unter [Windows Forms-Steuerelemente nach Funktion](windows-forms-controls-by-function.md).  
  
3. Ziehen Sie ein <xref:System.Windows.Forms.BindingNavigator>-Steuerelement auf das Formular; damit können Sie die Daten in die untergeordnete Tabelle navigieren.  
  
### <a name="to-connect-to-the-data-and-bind-it-to-controls"></a>So verbinden Sie die Daten und binden diese an die Steuerelemente  
  
1. Wählen Sie die <xref:System.Windows.Forms.ComboBox> und klicken Sie das Symbol Smarttask, sodass das Dialogfeld Smarttask angezeigt wird.  
  
2. Wählen Sie **An Daten gebundene Elemente verwenden** aus.  
  
3. Klicken Sie auf den Pfeil neben dem Dropdownfeld **Datenquelle**. Wenn eine Datenquelle bereits für das Projekt oder Formular konfiguriert wurde, wird sie angezeigt; ansonsten führen Sie bitte die folgenden Schritte durch (In diesem Beispiel werden die Kunden- und Bestellungentabellen der Northwind-Beispieldatenbank verwendet, auf die in Klammern verwiesen wird).  
  
    1. Klicken Sie auf **Projektdatenquelle hinzufügen**, um die Daten zu verbinden und die Datenquelle zu erzeugen.  
  
    2. Klicken Sie auf der Startseite des **Assistenten zum Konfigurieren von Datenquellen** auf **Weiter**.  
  
    3. Wählen Sie auf der Seite **Datenquellentyp auswählen** die Option **Datenbank** aus.  
  
    4. Wählen Sie auf der Seite **Wählen Sie Ihre Datenverbindung aus** eine Datenverbindung aus der Liste verfügbar Verbindungen aus. Wenn die gewünschte Datenverbindung nicht verfügbar ist, wählen Sie **Neue Verbindung** aus, und legen Sie eine neue Verbindung an.  
  
    5. Klicken Sie auf **Ja, Verbindung speichern unter**, um die Verbindungszeichenfolge in der Anwendungskonfigurationsdatei zu speichern.  
  
    6. Wählen Sie die Datenbankobjekte, die in die Anwendung gebracht werden sollen. In diesem Fall wählen Sie eine übergeordnete und eine untergeordnete Tabelle (z. B. Kunden und Bestellungen) mit einer Fremdschlüsselbeziehung.  
  
    7. Ersetzen Sie den Standardnamen des Datasets falls gewünscht.  
  
    8. Klicken Sie auf **Fertig stellen**.  
  
4. Wählen Sie im Dropdownfeld **Member anzeigen** den Spaltennamen aus (z.B. ContactName), der im Kombinationsfeld angezeigt werden soll.  
  
5. Wählen Sie im Dropdownfeld **Wertemember** die Spalte (z.B. CustomerID) für das Durchführen des Nachschlagevorgangs in der untergeordneten Tabelle aus.  
  
6. Navigieren Sie im Dropdownfeld **Ausgewählter Wert** zu **Projektdatenquellen** und dem eben erstellten Dataset mit den über- und untergeordneten Tabellen. Wählen Sie dieselbe Eigenschaft der untergeordneten Tabelle, die ein Wertemember der übergeordneten Tabelle ist (z. B. Orders.CustomerID). Das entsprechende Datenset <xref:System.Windows.Forms.BindingSource> und die Tabelleadapterkomponenten werden erstellt und dem Formular hinzugefügt.  
  
7. Binden Sie das Steuerelement <xref:System.Windows.Forms.BindingNavigator> an die untergeordnete Tabelle <xref:System.Windows.Forms.BindingSource> (z. B. `OrdersBindingSource`).  
  
8. Binden Sie die Steuerelement außer <xref:System.Windows.Forms.ComboBox> und <xref:System.Windows.Forms.BindingNavigator> an das Feld "Details" aus der <xref:System.Windows.Forms.BindingSource> der untergeordneten Tabelle (z. B. `OrdersBindingSource`), die Sie anzeigen möchten.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.BindingSource>
- [BindingSource-Komponente](bindingsource-component.md)
- [ComboBox-Steuerelement](combobox-control-windows-forms.md)
- [Binden von Steuerelementen an Daten in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
