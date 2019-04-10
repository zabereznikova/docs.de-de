---
title: 'Exemplarische Vorgehensweise: Ausschließliches Verwenden von gespeicherten Prozeduren (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 5a736a30-ba66-4adb-b87c-57d19476e862
ms.openlocfilehash: 1527e3b4b614d4e700ae0c2c0fc555e14c7bc8d2
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59314827"
---
# <a name="walkthrough-using-only-stored-procedures-visual-basic"></a>Exemplarische Vorgehensweise: Ausschließliches Verwenden von gespeicherten Prozeduren (Visual Basic)
Diese exemplarische Vorgehensweise stellt ein grundlegendes End-to-End-[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Szenario für den Datenzugriff mithilfe von gespeicherten Prozeduren bereit. Dieser Ansatz wird oft von Datenbankadministratoren verwendet, um den Zugriff auf den Datenspeicher einzuschränken.  
  
> [!NOTE]
>  Sie können gespeicherte Prozeduren außerdem in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Anwendungen verwenden, um das Standardverhalten zu überschreiben. Dies gilt vor allem für die Prozesse `Create`, `Update` und `Delete`. Weitere Informationen finden Sie unter [Anpassen von INSERT-, Update- und Delete-Operationen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
  
 Für die Zwecke dieser exemplarischen Vorgehensweise verwenden Sie zwei Methoden, die von gespeicherten Prozeduren in der Northwind-Beispieldatenbank zugeordnet wurden: CustOrdersDetail und CustOrderHist. Die Zuordnung tritt auf, wenn Sie das Befehlszeilentool SqlMetal verwenden, generiert Visual Basic-Datei ausführen. Weitere Informationen finden Sie im Abschnitt zu Voraussetzungen weiter unten in dieser exemplarischen Vorgehensweise.  
  
 Diese exemplarische Vorgehensweise basiert nicht auf [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]. Entwickler, die mit Visual Studio können auch die [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] Funktionalität einer gespeicherten Prozedur zu implementieren. Finden Sie unter [LINQ to SQL-Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Diese exemplarische Vorgehensweise wurde mithilfe von Visual Basic-Entwicklungseinstellungen geschrieben.  
  
## <a name="prerequisites"></a>Vorraussetzungen  
 Für diese exemplarische Vorgehensweise wird Folgendes vorausgesetzt:  
  
-   Diese exemplarische Vorgehensweise verwendet einen dedizierten Ordner ("c:\linqtest3") als Speicherort für Dateien. Erstellen Sie diesen Ordner, bevor Sie die exemplarische Vorgehensweise starten.  
  
-   Die Beispieldatenbank Northwind.  
  
     Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie diese von der Microsoft Downloadsite herunterladen. Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md). Nachdem Sie die Datenbank heruntergeladen haben, kopieren Sie die Datei northwnd.mdf in den Ordner c:\linqtest3.  
  
-   Eine von der Datenbank Northwind generierte Visual Basic-Codedatei.  
  
     Diese exemplarische Vorgehensweise wurde mithilfe des SQLMetal-Tools mit der folgenden Befehlszeile geschrieben:  
  
     **sqlmetal /code:"c:\linqtest3\northwind.vb" /language:vb "c:\linqtest3\northwnd.mdf" /sprocs /functions /pluralize**  
  
     Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="overview"></a>Übersicht  
 Diese exemplarische Vorgehensweise umfasst sechs Hauptaufgaben:  
  
-   Einrichten der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Projektmappe in Visual Studio.  
  
-   Hinzufügen der System.Data.Linq-Assembly zum Projekt  
  
-   Hinzufügen der Datenbank-Codedatei zum Projekt.  
  
-   Erstellen einer Verbindung mit der Datenbank  
  
-   Einrichten der Benutzeroberfläche.  
  
-   Ausführen und Testen der Anwendung.  
  
## <a name="creating-a-linq-to-sql-solution"></a>Erstellen einer LINQ to SQL-Lösung  
 In dieser ersten Aufgabe erstellen Sie eine Visual Studio-Projektmappe, die die erforderlichen Verweise zur Erstellung und Ausführung enthält eine [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Projekt.  
  
#### <a name="to-create-a-linq-to-sql-solution"></a>So erstellen Sie eine LINQ to SQL-Lösung  
  
1. Klicken Sie in Visual Studio im Menü **Datei** auf **Neues Projekt**.  
  
2. Erweitern Sie im Bereich **Projekttypen** des Dialogfelds **Neues Projekt** den Eintrag **Visual Basic**, und klicken Sie dann auf **Windows**.  
  
3. Klicken Sie im Bereich **Vorlagen** auf **Windows Forms-Anwendung**.  
  
4. In der **Namen** geben **SprocOnlyApp**.  
  
5. Klicken Sie auf **OK**.  
  
     Der Windows Forms Designer wird geöffnet.  
  
## <a name="adding-the-linq-to-sql-assembly-reference"></a>Hinzufügen des LINQ to SQL-Assemblyverweises  
 Die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Assembly ist nicht in der Standardvorlage für Windows Forms-Anwendungen enthalten. Sie müssen die Assembly selbst hinzufügen. Siehe hierzu die folgenden Schritte:  
  
#### <a name="to-add-systemdatalinqdll"></a>So fügen Sie die Datei System.Data.Linq.dll hinzu  
  
1. In **Projektmappen-Explorer**, klicken Sie auf **alle Dateien anzeigen**.  
  
2. In **Projektmappen-Explorer**, mit der rechten Maustaste **Verweise**, und klicken Sie dann auf **Verweis hinzufügen**.  
  
3. In der **Verweis hinzufügen** Dialogfeld klicken Sie auf **.NET**, klicken Sie auf die System.Data.Linq-Assembly, und klicken Sie dann auf **OK**.  
  
     Dem Projekt wird die Assembly hinzugefügt.  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a>Hinzufügen der Northwind-Codedatei zum Projekt.  
 Bei diesem Schritt wird davon ausgegangen, dass Sie das SQLMetal-Tool zum Erzeugen einer Codedatei aus der Beispieldatenbank Northwind verwendet haben. Weitere Informationen finden Sie im Abschnitt zu Voraussetzungen weiter oben in dieser exemplarischen Vorgehensweise.  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a>So fügen Sie die Northwind-Codedatei dem Projekt hinzu.  
  
1. Auf der **Projekt** Menü klicken Sie auf **vorhandenes Element hinzufügen**.  
  
2. In der **vorhandenes Element hinzufügen** Dialogfeld zu c:\linqtest3\northwind.vb verschieben, und klicken Sie dann auf **hinzufügen**.  
  
     Die Datei northwind.vb wird dem Projekt hinzugefügt.  
  
## <a name="creating-a-database-connection"></a>Erstellen von Datenbankverbindungen  
 In diesem Schritt definieren Sie die Verbindung zur Beispieldatenbank Northwind. Diese exemplarische Vorgehensweise verwendet "c:\linqtest3\northwnd.mdf" als Pfad.  
  
#### <a name="to-create-the-database-connection"></a>So erstellen Sie die Datenbankverbindung  
  
1. In **Projektmappen-Explorer**, mit der rechten Maustaste **Form1.vb**, und klicken Sie dann auf **Ansichtscode**.  
  
     `Class Form1` wird im Code-Editor angezeigt.  
  
2. Geben Sie den folgenden Code in den `Form1`-Code-Block ein.  
  
     [!code-vb[DLinqWalk4VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#1)]  
  
## <a name="setting-up-the-user-interface"></a>Einrichten der Benutzeroberfläche  
 In dieser Aufgabe erstellen Sie eine Benutzeroberfläche, sodass Benutzer durch Ausführen gespeicherter Prozeduren auf die Daten in der Datenbank zugreifen können. In den von Ihnen hier entwickelten Anwendungen können Benutzer nur mithilfe der in der Anwendung eingebetteten gespeicherten Prozeduren auf die Daten zugreifen.  
  
#### <a name="to-set-up-the-user-interface"></a>So richten Sie die Benutzeroberfläche ein  
  
1. Wechseln Sie zurück zur der Windows Forms-Designer (**Form1.vb]**).  
  
2. Klicken Sie im Menü **Ansicht** auf **Toolbox**.  
  
     Die Toolbox wird geöffnet.  
  
    > [!NOTE]
    >  Klicken Sie auf die **automatisch im Hintergrund** PIN, die Toolbox geöffnet zu lassen, während der folgenden Schritte in diesem Abschnitt.  
  
3. Ziehen Sie zwei Schaltflächen, zwei Textfelder und zwei Bezeichnungen aus der Toolbox auf **Form1**.  
  
     Ordnen Sie die Steuerelemente wie in der Abbildung an. Erweitern Sie **Form1** , damit die Steuerelemente platziert.  
  
4. Mit der rechten Maustaste **Label1**, und klicken Sie dann auf **Eigenschaften**.  
  
5. Ändern der **Text** Eigenschaft **Label1** zu **Enter OrderID:**.  
  
6. Für die gleiche Weise **Label2**, ändern Sie die **Text** Eigenschaft aus **Label2** zu **Enter CustomerID:**.  
  
7. Ändern Sie in die gleiche Weise die **Text** -Eigenschaft für **"Button1"** zu **Bestelldetails**.  
  
8. Ändern der **Text** -Eigenschaft für **Button2** zu **Bestellverlauf**.  
  
     Erweitern Sie die Schaltflächen-Steuerelemente, damit der gesamte Text sichtbar ist.  
  
#### <a name="to-handle-button-clicks"></a>Verarbeitung von Mausklicks auf die Schaltflächen  
  
1. Doppelklicken Sie auf **Bestelldetails** auf **Form1** zum Erstellen der `Button1` -Ereignishandler und den Codeeditor zu öffnen.  
  
2. Geben Sie den folgenden Code in den `Button1`-Ereignishandler ein.  
  
     [!code-vb[DLinqWalk4VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#2)]  
  
3. Doppelklicken Sie jetzt auf **Button2** auf Form1 für das Erstellen der `Button2` -Ereignishandler und den Codeeditor zu öffnen.  
  
4. Geben Sie den folgenden Code in den `Button2`-Ereignishandler ein.  
  
     [!code-vb[DLinqWalk4VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#3)]  
  
## <a name="testing-the-application"></a>Testen der Anwendung  
 Nun können Sie die Anwendung testen. Beachten Sie, dass die Verbindung zum Datastore auf die Aktionen der beiden gespeicherten Prozeduren beschränkt ist. Diese Aktionen geben die Produkte zu der von Ihnen eingegebenen OrderID und die Produkthistorie zu der von Ihnen eingegebenen CustomerID zurück.  
  
#### <a name="to-test-the-application"></a>So testen Sie die Anwendung  
  
1. Drücken Sie die Taste F5, um mit dem Debuggen zu beginnen.  
  
     Form1 wird angezeigt.  
  
2. In der **Enter OrderID** geben **10249** , und klicken Sie dann auf **Bestelldetails**.  
  
     Ein Meldungsfeld listet die in Bestellung 10249 enthaltenen Produkte auf.  
  
     Klicken Sie auf **OK** um das Meldungsfeld zu schließen.  
  
3. In der **Enter CustomerID** geben `ALFKI`, und klicken Sie dann auf **Bestellverlauf**.  
  
     Ein Meldungsfeld mit der Bestellhistorie für Kunde ALFKI wird angezeigt.  
  
     Klicken Sie auf **OK** um das Meldungsfeld zu schließen.  
  
4. In der **Enter OrderID** geben `123`, und klicken Sie dann auf **Bestelldetails**.  
  
     Ein Meldungsfeld zeigt "Keine Ergebnisse" an.  
  
     Klicken Sie auf **OK** um das Meldungsfeld zu schließen.  
  
5. Auf der **Debuggen** Menü klicken Sie auf **Beenden des Debuggens**.  
  
     Die Debugsitzung schließt.  
  
6. Wenn Sie mit dem Experimentieren fertig sind, können Sie klicken **Projekt schließen** auf die **Datei** Menü, und speichern Sie das Projekt aus, wenn Sie aufgefordert werden.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Sie können dieses Projekt mit einigen Änderungen erweitern. Sie können beispielsweise die verfügbaren gespeicherten Prozeduren in einem Listenfeld aufführen, sodass der Benutzer diese auswählen kann. Sie könnten auch die Ausgabe von Berichten in eine Textdatei umleiten.  
  
## <a name="see-also"></a>Siehe auch

- [Lernen durch exemplarische Vorgehensweisen](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
- [Gespeicherte Prozeduren](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
