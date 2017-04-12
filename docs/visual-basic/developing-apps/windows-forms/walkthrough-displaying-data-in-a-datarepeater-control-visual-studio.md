---
title: 'Exemplarische Vorgehensweise: Anzeigen von Daten in einem DataRepeater-Steuerelement (Visual Studio) | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- DataRepeater, walkthrough
ms.assetid: 65dcdb95-6c3e-47cc-987d-190000f71653
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 09f15c94c3d5a3387935c8d3f4758c0ecfd7cfcd
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-displaying-data-in-a-datarepeater-control-visual-studio"></a>Exemplarische Vorgehensweise: Anzeigen von Daten in einem DataRepeater-Steuerelement (Visual Studio)
Diese exemplarische Vorgehensweise enthält ein grundlegende Anfang-Ende-Szenario zum Anzeigen von gebundenen Daten in einem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
## <a name="prerequisite"></a>Vorbereitungsmaßnahme  
 Für dieses Beispiel wird die Beispieldatenbank Northwind benötigt.  
  
 Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie sie aus dem [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088)herunterladen. Eine Anleitung hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](https://msdn.microsoft.com/library/bb399411).  
  
## <a name="overview"></a>Übersicht  
 Der erste Teil dieser exemplarischen Vorgehensweise besteht aus vier Hauptaufgaben:  
  
-   Erstellen einer Projektmappe  
  
-   Hinzufügen einer <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
-   Erstellen einer Datenquelle  
  
-   Hinzufügen datengebundener Steuerelemente  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
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
 In diesem Schritt fügen Sie eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>-Steuerelement auf das Formular.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
#### <a name="to-add-a-datarepeater-control"></a>So fügen Sie ein DataRepeater-Steuerelement hinzu  
  
1.  Klicken Sie im Menü **Ansicht** auf **Toolbox**.  
  
     Die **Toolbox** wird geöffnet.  
  
2.  Wählen Sie die Registerkarte **Visual Basic PowerPacks** aus.  
  
3.  Ziehen Sie eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>-Steuerelement auf **Form1**.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
4.  Legen Sie im Eigenschaftenfenster die Eigenschaft **Speicherort** auf `0, 25`fest.  
  
5.  Legen Sie für die **Größe** -Eigenschaft den Wert `460, 600`fest.  
  
## <a name="adding-a-data-source"></a>Hinzufügen einer Datenquelle  
 In diesem Schritt fügen Sie eine Datenquelle für die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
#### <a name="to-add-a-data-source"></a>So fügen Sie eine Datenquelle hinzu  
  
1.  Klicken Sie im Menü **Daten** auf **Datenquellen anzeigen**.  
  
2.  Klicken Sie im **Datenquellenfenster** auf **Neue Datenquelle hinzufügen**.  
  
3.  Wählen Sie auf der Seite **Datenquellentyp auswählen** die Option **Datenbank** aus, und klicken Sie auf **Weiter**.  
  
4.  Führen Sie auf der Seite **Wählen Sie Ihre Datenverbindung aus** einen der folgenden Schritte aus:  
  
    -   Wenn in der Dropdownliste eine Datenverbindung zur Beispieldatenbank Northwind verfügbar ist, klicken Sie auf diese.  
  
         - oder -  
  
    -   Klicken Sie auf **Neue Verbindung** , um eine neue Datenverbindung zu konfigurieren. Weitere Informationen finden Sie unter [Gewusst wie: Erstellen von Verbindungen mit SQL Server-Datenbanken](http://msdn.microsoft.com/en-us/360c340d-e5a6-4a7e-a569-e95d500be43d).  
  
5.  Sollte für die Datenbank ein Kennwort erforderlich sein, wählen Sie die Option für die Einbeziehung vertraulicher Daten aus, und klicken Sie anschließend auf **Weiter**.  
  
    > [!NOTE]
    >  Wenn ein Dialogfeld angezeigt wird, wählen Sie **Ja** , um die Datei im Projekt zu speichern.  
  
6.  Klicken Sie auf der Seite **Verbindungszeichenfolge in der Programmkonfigurationsdatei speichern** auf **Weiter** .  
  
7.  Erweitern Sie auf der Seite **Datenbankobjekte auswählen** den Knoten **Tabellen** .  
  
8.  Aktivieren Sie die Kontrollkästchen für die Tabellen **Customers** und **Orders** , und klicken Sie dann auf **Fertig stellen**.  
  
     **NorthwindDataSet** wird dem Projekt hinzugefügt, und die Tabellen **Customers** und **Orders** werden im **Datenquellenfenster** angezeigt.  
  
## <a name="adding-data-bound-controls"></a>Hinzufügen datengebundener Steuerelemente  
 In diesem Schritt fügen Sie datengebundene Steuerelemente mit dem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
#### <a name="to-add-data-bound-controls"></a>So fügen Sie datengebundene Steuerelemente hinzu  
  
1.  Wählen Sie im **Datenquellenfenster** den obersten Knoten für die **Customers** -Tabelle aus.  
  
2.  Ändern Sie den Ablagetyp für die Tabelle in **Details** , indem Sie in der Dropdownliste für den Tabellenknoten **Details** auswählen.  
  
3.  Wählen Sie die **Kunden** Knoten Tabelle, und ziehen Sie es auf den Elementvorlagenbereich (der obere Bereich) von der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
     Ein <xref:System.Windows.Forms.BindingNavigator>Steuerelement wird dem Formular hinzugefügt und die **NorthwindDataSet**, **CustomersBindingSource**, **CustomersTableAdapter**, **TableAdapterManager**, und **CustomersBindingNavigator** Komponenten werden auf der Komponentenleiste hinzugefügt.</xref:System.Windows.Forms.BindingNavigator>  
  
4.  Wählen Sie alle Felder und ihre zugeordneten Bezeichnungen aus, und positionieren Sie sie am linken Rand des Elementvorlagenbereichs.  
  
5.  Wählen Sie die letzten fünf Felder (**Region**, **Postal Code**, **Country**, **Phone**und **Fax**) und ihre zugeordneten Bezeichnungen aus, und verschieben Sie sie nach oben rechts neben die ersten sechs Felder.  
  
6.  Wählen Sie die Elementvorlage (oberer Bereich des Steuerelements) aus.  
  
7.  Legen Sie im Eigenschaftenfenster die Eigenschaft **Größe** auf `427, 170`fest.  
  
 An diesem Punkt haben Sie eine funktionierende Anwendung, die eine sich wiederholende Liste von Kunden anzeigt. Drücken Sie F5, um die Anwendung auszuführen, die Daten zu ändern und Kundendatensätze hinzuzufügen oder zu löschen.  
  
 Im nächsten optionalen Schritt erfahren Sie, wie Sie zum Anpassen der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
## <a name="next-steps-optional"></a>Nächste Schritte (optional)  
 Dieser Teil der exemplarischen Vorgehensweise besteht aus vier optionalen Aufgaben:  
  
-   Ändern der Darstellung von der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
-   Verhindern, dass Benutzer Datensätze hinzufügen oder löschen  
  
-   Hinzufügen einer Suchfunktion zu den <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
-   Hinzufügen einer Tabelle Master und Details zu den <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
## <a name="changing-the-appearance-of-the-datarepeater-control"></a>Ändern der Darstellung des DataRepeater-Steuerelements  
 In diesem optionalen Schritt ändern Sie die `BackColor` von der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>-Steuerelements zur Entwurfszeit.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Sie fügen auch Code hinzu, um Zeilen in unterschiedlichen Farben anzuzeigen und die `ForeColor` einer Bezeichnung in Abhängigkeit einer Bedingung zu ändern.  
  
#### <a name="to-change-the-appearance-of-the-control"></a>So ändern Sie die Darstellung des Steuerelements  
  
1.  Wählen Sie in der Windows Forms-Designer den Hauptbereich (unten), der die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
2.  Legen Sie im Eigenschaftenfenster die Eigenschaft `BackColor` auf „White“ fest.  
  
3.  Doppelklicken Sie auf die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>um den Code-Editor zu öffnen.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
4.  Klicken Sie im Code-Editor in der Dropdownliste „Ereignis“ auf **DrawItem**.  
  
5.  In der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>-Ereignishandler, fügen Sie den folgenden Code, um alternative der `BackColor`:</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>  
  
     [!code-cs[VbPowerPacksDataRepeaterWalkthrough&#1;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough Nr.&1;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.vb)]  
  
6.  In der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>Ereignishandler, fügen Sie folgenden Code zum Ändern der `ForeColor` einer Bezeichnung abhängig von einer Bedingung:</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>  
  
     [!code-cs[VbPowerPacksDataRepeaterWalkthrough&2;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough Nr.&2;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.vb)]  
  
7.  Drücken Sie F5, um die Anwendung auszuführen und die Anpassungen anzuzeigen.  
  
## <a name="preventing-users-from-adding-or-deleting-records"></a>Verhindern, dass Benutzer Datensätze hinzufügen oder löschen  
 In diesem optionalen Schritt fügen Sie Code, der verhindert, dass Benutzer hinzufügen oder Löschen von Datensätzen in der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
#### <a name="to-prevent-users-from-adding-and-deleting-records"></a>So verhindern Sie, dass Benutzer Datensätze hinzufügt oder löscht  
  
1.  Doppelklicken Sie im Windows Forms-Designer auf das Formular, um den Code-Editor zu öffnen.  
  
2.  Fügen Sie dem `Form_Load` -Ereignis folgenden Code hinzu:  
  
     [!code-cs[VbPowerPacksDataRepeaterWalkthrough&3;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough Nr.&3;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.vb)]  
  
3.  Klicken Sie in der Dropdownliste „Klassenname“ auf **BindingNavigatorDeleteItem**. Klicken Sie in der Dropdownliste „Methodenname“ auf **EnabledChanged**.  
  
4.  Fügen Sie dem `BindingNavigatorDeleteItem_EnabledChanged` -Ereignishandler folgenden Code hinzu:  
  
     [!code-cs[VbPowerPacksDataRepeaterWalkthrough&4;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough Nr.&4;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.vb)]  
  
    > [!NOTE]
    >  Dieser Schritt ist erforderlich, da die <xref:System.Windows.Forms.BindingSource>ermöglicht die **DeleteItem** Schaltfläche jeder Änderung des aktuellen Datensatzes.</xref:System.Windows.Forms.BindingSource>  
  
5.  Drücken Sie F5, um die Anwendung auszuführen. Beachten Sie, dass die **DeleteItem** -Schaltfläche deaktiviert ist und dass Sie keine Elemente durch Drücken der ENTF-Taste löschen können.  
  
## <a name="adding-search-capability-to-the-datarepeater-control"></a>Hinzufügen einer Suchfunktion zum DataRepeater-Steuerelement  
 In diesem optionalen Schritt implementieren Sie die Funktion zum Suchen nach einem Wert in der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Wenn die Suchzeichenfolge gefunden wird, wählt das Steuerelement das Element aus, das den Wert enthält, und führt einen Bildlauf zum Element durch.  
  
#### <a name="to-add-search-capability"></a>So fügen Sie eine Suchfunktion hinzu  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.TextBox>-Steuerelement aus der **Toolbox** auf das Formular mit den <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:System.Windows.Forms.TextBox>  
  
     Positionieren Sie es unter der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
2.  Ändern Sie im Eigenschaftenfenster die Eigenschaft **Name** in **SearchTextBox**.  
  
3.  Ziehen Sie eine <xref:System.Windows.Forms.Button>-Steuerelement aus der **Toolbox** auf das Formular mit den <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:System.Windows.Forms.Button> Positionieren Sie es unter der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
4.  Ändern Sie im Eigenschaftenfenster die Eigenschaft **Name** in **SearchButton**. Ändern Sie die **Text** -Eigenschaft in **Search**.  
  
5.  Doppelklicken Sie auf die <xref:System.Windows.Forms.Button>Steuerelement, um den Code-Editor zu öffnen, und fügen Sie den folgenden Code der `SearchButton_Click` -Ereignishandler.</xref:System.Windows.Forms.Button>  
  
     [!code-cs[VbPowerPacksDataRepeaterWalkthrough&5;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough&5;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.vb)]  
  
6.  Drücken Sie F5, um die Anwendung auszuführen. Geben Sie eine Kunden-ID in **SearchTextBox** ein, und klicken Sie auf die Schaltfläche **Search** .  
  
## <a name="adding-a-master-and-detail-table-to-the-datarepeater"></a>Hinzufügen einer Master- und Detailtabelle zum DataRepeater  
 In diesem optionalen Schritt fügen Sie eine zweite <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement, um verbundene Aufträge für jeden Kunden anzuzeigen.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
#### <a name="to-add-a-master-and-detail-table"></a>So fügen Sie eine Master- und Detailtabelle hinzu  
  
1.  Ziehen Sie eine zweite <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>-Steuerelement aus der **Visual Basic PowerPacks** Registerkarte der **Toolbox** auf das Formular.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
2.  Legen Sie im Eigenschaftenfenster die Eigenschaft **Speicherort** auf `465, 25`fest.  
  
3.  Legen Sie für die **Größe** -Eigenschaft den Wert `315, 600`fest.  
  
4.  Erweitern Sie im **Datenquellenfenster** den Tabellenknoten **Customers** , und wählen Sie den Detailknoten für die Tabelle **Orders** aus.  
  
5.  Ändern Sie den Ablagetyp für die **Orders** -Tabelle in „Details“, indem Sie in der Dropdownliste für den Tabellenknoten **Details** auswählen.  
  
6.  Ziehen Sie das **Aufträge** Knoten auf den Elementvorlagenbereich (der obere Bereich) des zweiten <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
     Eine **OrdersBindingSource** -Komponente und eine **OrdersTableAdapter** -Komponente werden der Komponentenleiste hinzugefügt.  
  
7.  Drücken Sie F5, um die Anwendung auszuführen. Wenn Sie jeden Kunden auswählen, in der ersten <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>steuern, die Aufträge für diesen Kunden werden angezeigt, in der zweiten <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in das DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Gewusst wie: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)   
 [Gewusst wie: Anzeigen von nicht gebundenen Steuerelementen in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)   
 [Gewusst wie: Ändern des Layouts eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)   
 [Gewusst wie: Anzeigen von Elementheadern in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)   
 [Gewusst wie: Suchen von Daten in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)   
 [Gewusst wie: Erstellen einer Master-/Detailformulars mit zwei DataRepeater-Steuerelementen (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)   
 [Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)   
 [Gewusst wie: Deaktivieren des Hinzufügens und Löschens von DataRepeater-Elementen](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)   
 [Problembehandlung beim DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
