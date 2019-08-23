---
title: 'Exemplarische Vorgehensweise: Ausschließliches Verwenden von gespeicherten Prozeduren (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 5a736a30-ba66-4adb-b87c-57d19476e862
ms.openlocfilehash: 159b65b4b58b9142a168401ea2a881af2714df5f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946638"
---
# <a name="walkthrough-using-only-stored-procedures-visual-basic"></a>Exemplarische Vorgehensweise: Ausschließliches Verwenden von gespeicherten Prozeduren (Visual Basic)
Diese exemplarische Vorgehensweise stellt ein grundlegendes End-to-End-[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Szenario für den Datenzugriff mithilfe von gespeicherten Prozeduren bereit. Dieser Ansatz wird oft von Datenbankadministratoren verwendet, um den Zugriff auf den Datenspeicher einzuschränken.  
  
> [!NOTE]
> Sie können gespeicherte Prozeduren außerdem in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Anwendungen verwenden, um das Standardverhalten zu überschreiben. Dies gilt vor allem für die Prozesse `Create`, `Update` und `Delete`. Weitere Informationen finden Sie unter [Anpassen von INSERT-, Update-und DELETE-Vorgängen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
  
 In dieser exemplarischen Vorgehensweise verwenden Sie zwei Methoden, die gespeicherten Prozeduren in der Beispieldatenbank Northwind zugeordnet wurden: CustOrdersDetail und CustOrderHist. Die Zuordnung erfolgt, wenn Sie das SQLMetal-Befehlszeilen Tool ausführen, um eine Visual Basic-Datei zu generieren. Weitere Informationen finden Sie im Abschnitt zu Voraussetzungen weiter unten in dieser exemplarischen Vorgehensweise.  
  
 Diese exemplarische Vorgehensweise beruht nicht auf der objektrelationaler Designer. Entwickler, die Visual Studio verwenden, können auch den O/R-Designer verwenden, um Funktionen der gespeicherten Prozedur zu implementieren. Weitere Informationen finden Sie [unter LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Diese exemplarische Vorgehensweise wurde mithilfe von Visual Basic-Entwicklungseinstellungen geschrieben.  
  
## <a name="prerequisites"></a>Vorraussetzungen  
 Für diese exemplarische Vorgehensweise wird Folgendes vorausgesetzt:  
  
- Diese exemplarische Vorgehensweise verwendet einen dedizierten Ordner ("c:\linqtest3") als Speicherort für Dateien. Erstellen Sie diesen Ordner, bevor Sie die exemplarische Vorgehensweise starten.  
  
- Die Beispieldatenbank Northwind.  
  
     Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie diese von der Microsoft Downloadsite herunterladen. Anweisungen hierzu finden Sie unter [Herunterladen von Beispiel Datenbanken](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md). Nachdem Sie die Datenbank heruntergeladen haben, kopieren Sie die Datei northwnd.mdf in den Ordner c:\linqtest3.  
  
- Eine von der Datenbank Northwind generierte Visual Basic-Codedatei.  
  
     Diese exemplarische Vorgehensweise wurde mithilfe des SQLMetal-Tools mit der folgenden Befehlszeile geschrieben:  
  
     **sqlmetal /code:"c:\linqtest3\northwind.vb" /language:vb "c:\linqtest3\northwnd.mdf" /sprocs /functions /pluralize**  
  
     Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="overview"></a>Übersicht  
 Diese exemplarische Vorgehensweise umfasst sechs Hauptaufgaben:  
  
- Einrichten der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Projekt Mappe in Visual Studio.  
  
- Hinzufügen der System.Data.Linq-Assembly zum Projekt  
  
- Hinzufügen der Datenbank-Codedatei zum Projekt.  
  
- Erstellen einer Verbindung mit der Datenbank  
  
- Einrichten der Benutzeroberfläche.  
  
- Ausführen und Testen der Anwendung.  
  
## <a name="creating-a-linq-to-sql-solution"></a>Erstellen einer LINQ to SQL-Lösung  
 In dieser ersten Aufgabe erstellen Sie eine Visual Studio-Projekt Mappe, die die erforderlichen Verweise zum Erstellen und Ausführen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] eines Projekts enthält.  
  
### <a name="to-create-a-linq-to-sql-solution"></a>So erstellen Sie eine LINQ to SQL-Lösung  
  
1. Klicken Sie in Visual Studio im Menü **Datei** auf **Neues Projekt**.  
  
2. Erweitern Sie im Bereich **Projekttypen** des Dialogfelds **Neues Projekt** den Eintrag **Visual Basic**, und klicken Sie dann auf **Windows**.  
  
3. Klicken Sie im Bereich **Vorlagen** auf **Windows Forms-Anwendung**.  
  
4. Geben Sie im Feld **Name den Namen** **sprokonlyapp**ein.  
  
5. Klicken Sie auf **OK**.  
  
     Der Windows Forms Designer wird geöffnet.  
  
## <a name="adding-the-linq-to-sql-assembly-reference"></a>Hinzufügen des LINQ to SQL-Assemblyverweises  
 Die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Assembly ist nicht in der Standardvorlage für Windows Forms-Anwendungen enthalten. Sie müssen die Assembly selbst hinzufügen. Siehe hierzu die folgenden Schritte:  
  
### <a name="to-add-systemdatalinqdll"></a>So fügen Sie die Datei System.Data.Linq.dll hinzu  
  
1. Klicken Sie in **Projektmappen-Explorer**auf **alle Dateien anzeigen**.  
  
2. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **Verweise**, und klicken Sie dann auf **Verweis hinzufügen**.  
  
3. Klicken Sie im Dialogfeld **Verweis hinzufügen** auf **.net**, klicken Sie auf die Assembly System. Data. Linq, und klicken Sie dann auf **OK**.  
  
     Dem Projekt wird die Assembly hinzugefügt.  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a>Hinzufügen der Northwind-Codedatei zum Projekt.  
 Bei diesem Schritt wird davon ausgegangen, dass Sie das SQLMetal-Tool zum Erzeugen einer Codedatei aus der Beispieldatenbank Northwind verwendet haben. Weitere Informationen finden Sie im Abschnitt zu Voraussetzungen weiter oben in dieser exemplarischen Vorgehensweise.  
  
### <a name="to-add-the-northwind-code-file-to-the-project"></a>So fügen Sie die Northwind-Codedatei dem Projekt hinzu.  
  
1. Klicken Sie im Menü **Projekt** auf **Vorhandenes Element hinzufügen**.  
  
2. Wechseln Sie im Dialogfeld **Vorhandenes Element hinzufügen** zu c:\linqtest3\northwind.vb, und klicken Sie dann auf **Hinzufügen**.  
  
     Die Datei northwind.vb wird dem Projekt hinzugefügt.  
  
## <a name="creating-a-database-connection"></a>Erstellen von Datenbankverbindungen  
 In diesem Schritt definieren Sie die Verbindung zur Beispieldatenbank Northwind. Diese exemplarische Vorgehensweise verwendet "c:\linqtest3\northwnd.mdf" als Pfad.  
  
### <a name="to-create-the-database-connection"></a>So erstellen Sie die Datenbankverbindung  
  
1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **Form1. vb**, und klicken Sie dann auf **Code anzeigen**.  
  
     `Class Form1` erscheint im Code-Editor.  
  
2. Geben Sie den folgenden Code in den `Form1`-Code-Block ein.  
  
     [!code-vb[DLinqWalk4VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#1)]  
  
## <a name="setting-up-the-user-interface"></a>Einrichten der Benutzeroberfläche  
 In dieser Aufgabe erstellen Sie eine Benutzeroberfläche, sodass Benutzer durch Ausführen gespeicherter Prozeduren auf die Daten in der Datenbank zugreifen können. In den von Ihnen hier entwickelten Anwendungen können Benutzer nur mithilfe der in der Anwendung eingebetteten gespeicherten Prozeduren auf die Daten zugreifen.  
  
### <a name="to-set-up-the-user-interface"></a>So richten Sie die Benutzeroberfläche ein  
  
1. Kehren Sie zum Windows Forms-Designer (**Form1. vb [Design]** ) zurück.  
  
2. Klicken Sie im Menü **Ansicht** auf **Toolbox**.  
  
     Die Toolbox wird geöffnet.  
  
    > [!NOTE]
    > Klicken Sie auf das **Autohide** -Pushpin, um die Toolbox geöffnet zu lassen, während Sie die verbleibenden Schritte in diesem Abschnitt ausführen.  
  
3. Ziehen Sie zwei Schaltflächen, zwei Textfelder und zwei Bezeichnungen aus der Toolbox auf **Form1**.  
  
     Ordnen Sie die Steuerelemente wie in der Abbildung an. Erweitern Sie **Form1** , damit die Steuerelemente problemlos angepasst werden.  
  
4. Klicken Sie mit der rechten Maustaste auf **Label1**, und klicken Sie auf **Eigenschaften**.  
  
5. Ändern Sie die **Text** -Eigenschaft von **Label1** in **Enter OrderID:** .  
  
6. Ändern Sie auf die gleiche Weise für **Label2**die **Text** -Eigenschaft von **Label2** in **Enter CustomerID:** .  
  
7. Ändern Sie auf die gleiche Weise die **Text** -Eigenschaft für **Button1** in **Order Details**.  
  
8. Ändern Sie die **Text** -Eigenschaft für **Button2** in **Order History**.  
  
     Erweitern Sie die Schaltflächen-Steuerelemente, damit der gesamte Text sichtbar ist.  
  
### <a name="to-handle-button-clicks"></a>Verarbeitung von Mausklicks auf die Schaltflächen  
  
1. Doppelklicken Sie auf **Order Details** auf **Form1** , um `Button1` den Ereignishandler zu erstellen und den Code-Editor zu öffnen.  
  
2. Geben Sie den folgenden Code in den `Button1`-Ereignishandler ein.  
  
     [!code-vb[DLinqWalk4VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#2)]  
  
3. Doppelklicken Sie nun auf **Button2** auf Form1, um `Button2` den Ereignishandler zu erstellen und den Code-Editor zu öffnen.  
  
4. Geben Sie den folgenden Code in den `Button2`-Ereignishandler ein.  
  
     [!code-vb[DLinqWalk4VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#3)]  
  
## <a name="testing-the-application"></a>Testen der Anwendung  
 Nun können Sie die Anwendung testen. Beachten Sie, dass die Verbindung zum Datastore auf die Aktionen der beiden gespeicherten Prozeduren beschränkt ist. Diese Aktionen geben die Produkte zu der von Ihnen eingegebenen OrderID und die Produkthistorie zu der von Ihnen eingegebenen CustomerID zurück.  
  
### <a name="to-test-the-application"></a>So testen Sie die Anwendung  
  
1. Drücken Sie die Taste F5, um mit dem Debuggen zu beginnen.  
  
     Form1 wird angezeigt.  
  
2. Geben Sie im Feld **Enter OrderID** den Text **10249** ein, und klicken Sie dann auf **Order Details**.  
  
     Ein Meldungsfeld listet die in Bestellung 10249 enthaltenen Produkte auf.  
  
     Klicken Sie auf **OK** , um das Nachrichtenfeld zu schließen.  
  
3. Geben Sie im Feld `ALFKI` **CustomerID eingeben** den Text ein, und klicken Sie dann auf **Auftrags Verlauf**.  
  
     Ein Meldungsfeld mit der Bestellhistorie für Kunde ALFKI wird angezeigt.  
  
     Klicken Sie auf **OK** , um das Nachrichtenfeld zu schließen.  
  
4. Geben Sie im Feld `123` **Geben Sie OrderID** ein, und klicken Sie dann auf **Order Details**.  
  
     Ein Meldungsfeld zeigt "Keine Ergebnisse" an.  
  
     Klicken Sie auf **OK** , um das Nachrichtenfeld zu schließen.  
  
5. Klicken Sie im Menü **Debuggen** auf **Debugging Debuggen**.  
  
     Die Debugsitzung schließt.  
  
6. Wenn Sie das Experimentieren abgeschlossen haben, können Sie im Menü **Datei** auf **Projekt schließen** klicken und das Projekt speichern, wenn Sie dazu aufgefordert werden.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Sie können dieses Projekt mit einigen Änderungen erweitern. Sie können beispielsweise die verfügbaren gespeicherten Prozeduren in einem Listenfeld aufführen, sodass der Benutzer diese auswählen kann. Sie könnten auch die Ausgabe von Berichten in eine Textdatei umleiten.  
  
## <a name="see-also"></a>Siehe auch

- [Lernen durch exemplarische Vorgehensweisen](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
- [Gespeicherte Prozeduren](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
