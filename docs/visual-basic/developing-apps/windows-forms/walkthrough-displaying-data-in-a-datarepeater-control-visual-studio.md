---
title: 'Exemplarische Vorgehensweise: Anzeigen von Daten in einem DataRepeater-Steuerelement (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, walkthrough
ms.assetid: 65dcdb95-6c3e-47cc-987d-190000f71653
ms.openlocfilehash: 8e64a819e9670a29e97140a32c81f5ff9006f83e
ms.sourcegitcommit: 2ad7d06f4f469b5d8a5280ac0e0289a81867fc8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2018
ms.locfileid: "35231507"
---
# <a name="walkthrough-displaying-data-in-a-datarepeater-control-visual-studio"></a>Exemplarische Vorgehensweise: Anzeigen von Daten in einem DataRepeater-Steuerelement (Visual Studio)
Diese exemplarische Vorgehensweise enthält ein grundlegendes Szenario von Anfang bis zum Ende der Anzeige von gebundenen Daten in einem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement.  
  
## <a name="prerequisite"></a>Vorbereitungsmaßnahme  
 Für dieses Beispiel wird die Beispieldatenbank Northwind benötigt.  
  
 Wenn Sie diese Datenbank nicht auf Ihrem Computer verfügen, können Sie es aus dem Microsoft Download Center herunterladen. Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
## <a name="overview"></a>Übersicht  
 Der erste Teil dieser exemplarischen Vorgehensweise besteht aus vier Hauptaufgaben:  
  
-   Erstellen einer Projektmappe  
  
-   Hinzufügen eines <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelements  
  
-   Erstellen einer Datenquelle  
  
-   Hinzufügen datengebundener Steuerelemente  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-a-datarepeater-solution"></a>Erstellen einer DataRepeater-Projektmappe  
 Im ersten Schritt erstellen Sie ein Projekt und eine Projektmappe.  
  
#### <a name="to-create-a-datarepeater-solution"></a>So erstellen Sie eine DataRepeater-Projektmappe  
  
1.  Klicken Sie in Visual Studio im Menü **Datei** auf **Neues Projekt**.  
  
2.  Erweitern Sie im Bereich **Projekttypen** des Dialogfelds **Neues Projekt** den Eintrag **Visual Basic**, und klicken Sie dann auf **Windows**.  
  
3.  Klicken Sie im Bereich **Vorlagen** auf **Windows Forms-Anwendung**.  
  
4.  Geben Sie im Feld **Name** `DataRepeaterApp`ein.  
  
5.  Klicken Sie auf **OK**.  
  
     Der Windows Forms Designer wird geöffnet.  
  
6.  Öffnen Sie das Formular im Windows Forms-Designer. Legen Sie im **Eigenschaften** -Fenster die Eigenschaft **Größe** auf `800, 700`fest.  
  
## <a name="adding-a-datarepeater-control"></a>Hinzufügen eines DataRepeater-Steuerelements  
 In diesem Schritt fügen Sie dem Formular ein <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement hinzu.  
  
#### <a name="to-add-a-datarepeater-control"></a>So fügen Sie ein DataRepeater-Steuerelement hinzu  
  
1.  Klicken Sie im Menü **Ansicht** auf **Toolbox**.  
  
     Die **Toolbox** wird geöffnet.  
  
2.  Wählen Sie die Registerkarte **Visual Basic PowerPacks** aus.  
  
3.  Ziehen Sie ein <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement auf **Form1**.  
  
4.  Legen Sie im Eigenschaftenfenster die Eigenschaft **Speicherort** auf `0, 25`fest.  
  
5.  Legen Sie für die **Größe** -Eigenschaft den Wert `460, 600`fest.  
  
## <a name="adding-a-data-source"></a>Hinzufügen einer Datenquelle  
 In diesem Schritt fügen Sie eine Datenquelle für das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement hinzu.  
  
#### <a name="to-add-a-data-source"></a>So fügen Sie eine Datenquelle hinzu  
  
1.  Klicken Sie im Menü **Daten** auf **Datenquellen anzeigen**.  
  
2.  Klicken Sie im **Datenquellenfenster** auf **Neue Datenquelle hinzufügen**.  
  
3.  Wählen Sie auf der Seite **Datenquellentyp auswählen** die Option **Datenbank** aus, und klicken Sie auf **Weiter**.  
  
4.  Führen Sie auf der Seite **Wählen Sie Ihre Datenverbindung aus** einen der folgenden Schritte aus:  
  
    -   Wenn in der Dropdownliste eine Datenverbindung zur Beispieldatenbank Northwind verfügbar ist, klicken Sie auf diese.  
  
         - oder -   
  
    -   Klicken Sie auf **Neue Verbindung** , um eine neue Datenverbindung zu konfigurieren. Weitere Informationen finden Sie unter [neue Verbindungen hinzufügen](/visualstudio/data-tools/add-new-connections).  
  
5.  Sollte für die Datenbank ein Kennwort erforderlich sein, wählen Sie die Option für die Einbeziehung vertraulicher Daten aus, und klicken Sie anschließend auf **Weiter**.  
  
    > [!NOTE]
    >  Wenn ein Dialogfeld angezeigt wird, wählen Sie **Ja** , um die Datei im Projekt zu speichern.  
  
6.  Klicken Sie auf der Seite **Verbindungszeichenfolge in der Programmkonfigurationsdatei speichern** auf **Weiter** .  
  
7.  Erweitern Sie auf der Seite **Datenbankobjekte auswählen** den Knoten **Tabellen** .  
  
8.  Aktivieren Sie die Kontrollkästchen für die Tabellen **Customers** und **Orders** , und klicken Sie dann auf **Fertig stellen**.  
  
     **NorthwindDataSet** wird dem Projekt hinzugefügt, und die Tabellen **Customers** und **Orders** werden im **Datenquellenfenster** angezeigt.  
  
## <a name="adding-data-bound-controls"></a>Hinzufügen datengebundener Steuerelemente  
 In diesem Schritt fügen Sie dem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>datengebundene Steuerelemente hinzu.  
  
#### <a name="to-add-data-bound-controls"></a>So fügen Sie datengebundene Steuerelemente hinzu  
  
1.  Wählen Sie im **Datenquellenfenster** den obersten Knoten für die **Customers** -Tabelle aus.  
  
2.  Ändern Sie den Ablagetyp für die Tabelle in **Details** , indem Sie in der Dropdownliste für den Tabellenknoten **Details** auswählen.  
  
3.  Wählen Sie den Tabellenknoten **Customers** aus, und ziehen Sie ihn in den Elementvorlagenbereich (oberer Bereich) des <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelements.  
  
     Dem Formular wird ein <xref:System.Windows.Forms.BindingNavigator> -Steuerelement hinzugefügt, und die Komponenten **NorthwindDataSet**, **CustomersBindingSource**, **CustomersTableAdapter**, **TableAdapterManager**und **CustomersBindingNavigator** werden der Komponentenleiste hinzugefügt.  
  
4.  Wählen Sie alle Felder und ihre zugeordneten Bezeichnungen aus, und positionieren Sie sie am linken Rand des Elementvorlagenbereichs.  
  
5.  Wählen Sie die letzten fünf Felder (**Region**, **Postal Code**, **Country**, **Phone**und **Fax**) und ihre zugeordneten Bezeichnungen aus, und verschieben Sie sie nach oben rechts neben die ersten sechs Felder.  
  
6.  Wählen Sie die Elementvorlage (oberer Bereich des Steuerelements) aus.  
  
7.  Legen Sie im Eigenschaftenfenster die Eigenschaft **Größe** auf `427, 170`fest.  
  
 An diesem Punkt haben Sie eine funktionierende Anwendung, die eine sich wiederholende Liste von Kunden anzeigt. Drücken Sie F5, um die Anwendung auszuführen, die Daten zu ändern und Kundendatensätze hinzuzufügen oder zu löschen.  
  
 Im nächsten optionalen Schritt erfahren Sie, wie Sie das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement anpassen können.  
  
## <a name="next-steps-optional"></a>Nächste Schritte (optional)  
 Dieser Teil der exemplarischen Vorgehensweise besteht aus vier optionalen Aufgaben:  
  
-   Ändern der Darstellung des <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelements  
  
-   Verhindern, dass Benutzer Datensätze hinzufügen oder löschen  
  
-   Hinzufügen einer Suchfunktion zum <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement  
  
-   Hinzufügen einer Master- und Detailtabelle zum <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement  
  
## <a name="changing-the-appearance-of-the-datarepeater-control"></a>Ändern der Darstellung des DataRepeater-Steuerelements  
 In diesem optionalen Schritt ändern Sie die `BackColor` des <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelements zur Entwurfszeit. Sie fügen auch Code hinzu, um Zeilen in unterschiedlichen Farben anzuzeigen und die `ForeColor` einer Bezeichnung in Abhängigkeit einer Bedingung zu ändern.  
  
#### <a name="to-change-the-appearance-of-the-control"></a>So ändern Sie die Darstellung des Steuerelements  
  
1.  Wählen Sie im Windows Forms-Designer den Hauptbereich (unten) des <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelements.  
  
2.  Legen Sie im Eigenschaftenfenster die Eigenschaft `BackColor` auf „White“ fest.  
  
3.  Doppelklicken Sie auf den <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> , um den Code-Editor zu öffnen.  
  
4.  Klicken Sie im Code-Editor in der Dropdownliste „Ereignis“ auf **DrawItem**.  
  
5.  Fügen Sie im <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> -Ereignishandler den folgenden Code hinzu, um die `BackColor`abzuwechseln:  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.vb)]  
  
6.  Fügen Sie im <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> -Ereignishandler den folgenden Code hinzu, um die `ForeColor` einer Bezeichnung in Abhängigkeit einer Bedingung zu ändern:  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.vb)]  
  
7.  Drücken Sie F5, um die Anwendung auszuführen und die Anpassungen anzuzeigen.  
  
## <a name="preventing-users-from-adding-or-deleting-records"></a>Verhindern, dass Benutzer Datensätze hinzufügen oder löschen  
 In diesem optionalen Schritt fügen Sie Code hinzu, der verhindert, dass Benutzer Datensätze im <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement hinzufügen oder löschen kann.  
  
#### <a name="to-prevent-users-from-adding-and-deleting-records"></a>So verhindern Sie, dass Benutzer Datensätze hinzufügt oder löscht  
  
1.  Doppelklicken Sie im Windows Forms-Designer auf das Formular, um den Code-Editor zu öffnen.  
  
2.  Fügen Sie dem `Form_Load` -Ereignis folgenden Code hinzu:  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.vb)]  
  
3.  Klicken Sie in der Dropdownliste „Klassenname“ auf **BindingNavigatorDeleteItem**. Klicken Sie in der Dropdownliste „Methodenname“ auf **EnabledChanged**.  
  
4.  Fügen Sie dem `BindingNavigatorDeleteItem_EnabledChanged` -Ereignishandler folgenden Code hinzu:  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.vb)]  
  
    > [!NOTE]
    >  Dieser Schritt ist erforderlich, da die <xref:System.Windows.Forms.BindingSource> die **DeleteItem** -Schaltfläche bei jeder Änderung des aktuellen Datensatzes aktiviert.  
  
5.  Drücken Sie F5, um die Anwendung auszuführen. Beachten Sie, dass die **DeleteItem** -Schaltfläche deaktiviert ist und dass Sie keine Elemente durch Drücken der ENTF-Taste löschen können.  
  
## <a name="adding-search-capability-to-the-datarepeater-control"></a>Hinzufügen einer Suchfunktion zum DataRepeater-Steuerelement  
 In diesem optionalen Schritt implementieren Sie eine Funktion zum Suchen nach einem Wert im <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement. Wenn die Suchzeichenfolge gefunden wird, wählt das Steuerelement das Element aus, das den Wert enthält, und führt einen Bildlauf zum Element durch.  
  
#### <a name="to-add-search-capability"></a>So fügen Sie eine Suchfunktion hinzu  
  
1.  Ziehen Sie ein <xref:System.Windows.Forms.TextBox> -Steuerelement aus der **Toolbox** auf das Formular, das das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement enthält.  
  
     Positionieren Sie es unter dem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement.  
  
2.  Ändern Sie im Eigenschaftenfenster die Eigenschaft **Name** in **SearchTextBox**.  
  
3.  Ziehen Sie ein <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular, das das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement enthält. Positionieren Sie es unter dem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement.  
  
4.  Ändern Sie im Eigenschaftenfenster die Eigenschaft **Name** in **SearchButton**. Ändern Sie die **Text** -Eigenschaft in **Search**.  
  
5.  Doppelklicken Sie auf das <xref:System.Windows.Forms.Button> -Steuerelement, um den Code-Editor zu öffnen, und fügen Sie dem `SearchButton_Click` -Ereignishandler den folgenden Code hinzu:  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.vb)]  
  
6.  Drücken Sie F5, um die Anwendung auszuführen. Geben Sie eine Kunden-ID in **SearchTextBox** ein, und klicken Sie auf die Schaltfläche **Search** .  
  
## <a name="adding-a-master-and-detail-table-to-the-datarepeater"></a>Hinzufügen einer Master- und Detailtabelle zum DataRepeater  
 In diesem optionalen Schritt fügen Sie ein zweites <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement hinzu, um verbundene Aufträge für jeden Kunden anzuzeigen.  
  
#### <a name="to-add-a-master-and-detail-table"></a>So fügen Sie eine Master- und Detailtabelle hinzu  
  
1.  Ziehen Sie das zweite <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement aus der Registerkarte **Visual Basic PowerPacks** in der **Toolbox** auf das Formular.  
  
2.  Legen Sie im Eigenschaftenfenster die Eigenschaft **Speicherort** auf `465, 25`fest.  
  
3.  Legen Sie für die **Größe** -Eigenschaft den Wert `315, 600`fest.  
  
4.  Erweitern Sie im **Datenquellenfenster** den Tabellenknoten **Customers** , und wählen Sie den Detailknoten für die Tabelle **Orders** aus.  
  
5.  Ändern Sie den Ablagetyp für die **Orders** -Tabelle in „Details“, indem Sie in der Dropdownliste für den Tabellenknoten **Details** auswählen.  
  
6.  Ziehen Sie den Tabellenknoten **Orders** in den Elementvorlagenbereich (oberer Bereich) des zweiten <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelements.  
  
     Eine **OrdersBindingSource** -Komponente und eine **OrdersTableAdapter** -Komponente werden der Komponentenleiste hinzugefügt.  
  
7.  Drücken Sie F5, um die Anwendung auszuführen. Wenn Sie jeden Kunden im ersten <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement auswählen, werden die Aufträge für diesen Kunden im zweiten <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in das DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Gewusst wie: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [Gewusst wie: Anzeigen von nicht gebundenen Steuerelementen in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [Gewusst wie: Ändern des Layouts eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)  
 [Gewusst wie: Anzeigen von Elementheadern in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)  
 [Gewusst wie: Suchen von Daten in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)  
 [Vorgehensweise: erstellen ein Master-/Detailformulars mit zwei DataRepeater-Steuerelementen (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [Gewusst wie: Deaktivieren des Hinzufügens und Löschens von DataRepeater-Elementen](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)  
 [Problembehandlung beim DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
