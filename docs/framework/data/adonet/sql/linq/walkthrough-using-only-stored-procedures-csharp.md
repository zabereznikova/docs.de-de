---
title: "Exemplarische Vorgehensweise: Ausschließliches Verwenden von gespeicherten Prozeduren (C#)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ecde4bf2-fa4d-4252-b5e4-96a46b9e097d
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 52c9cfeab362a1603c1d18a9caa1601cd76711b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-using-only-stored-procedures-c"></a>Exemplarische Vorgehensweise: Ausschließliches Verwenden von gespeicherten Prozeduren (C#)
Diese exemplarische Vorgehensweise stellt ein grundlegendes End-to-End-Szenario für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] für den Datenzugriff mithilfe von gespeicherten Prozeduren bereit. Dieser Ansatz wird oft von Datenbankadministratoren verwendet, um den Zugriff auf den Datenspeicher einzuschränken.  
  
> [!NOTE]
>  Sie können gespeicherte Prozeduren außerdem in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Anwendungen verwenden, um das Standardverhalten zu überschreiben. Dies gilt vor allem für die Prozesse `Create`, `Update` und `Delete`. Weitere Informationen finden Sie unter [Anpassen von INSERT-, Update- und Delete-Operationen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
  
 Im Rahmen dieser exemplarischen Vorgehensweise verwenden Sie zwei Methoden, die in der Beispieldatenbank Northwind gespeicherten Prozeduren zugeordnet wurden: CustOrdersDetail und CustOrderHist. Die Zuordnung tritt auf, wenn Sie das SQLMetal-Befehlszeilentool ausführen, um eine C#-Datei zu generieren. Weitere Informationen finden Sie im Abschnitt zu Voraussetzungen weiter unten in dieser exemplarischen Vorgehensweise.  
  
 Diese exemplarische Vorgehensweise basiert nicht auf [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]. Entwickler, die mit [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] arbeiten, können auch [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] verwenden, um die Funktionalität einer gespeicherten Prozedur zu implementieren. Finden Sie unter [LINQ to SQL-Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Diese exemplarische Vorgehensweise wurde mithilfe von Visual C#-Entwicklungseinstellungen geschrieben.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Für diese exemplarische Vorgehensweise wird Folgendes vorausgesetzt:  
  
-   Diese exemplarische Vorgehensweise verwendet einen dedizierten Ordner ("c:\linqtest7") als Speicherort für Dateien. Erstellen Sie diesen Ordner, bevor Sie die exemplarische Vorgehensweise starten.  
  
-   Die Beispieldatenbank Northwind.  
  
     Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie diese von der Microsoft Downloadsite herunterladen. Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md). Nachdem Sie die Datenbank heruntergeladen haben, kopieren Sie die Datei northwnd.mdf in den Ordner c:\linqtest7.  
  
-   Eine von der Datenbank Northwind generierte C#-Codedatei.  
  
     Diese exemplarische Vorgehensweise wurde mithilfe des SQLMetal-Tools mit der folgenden Befehlszeile geschrieben:  
  
     **SqlMetal /code:"c:\linqtest7\northwind.cs" / Language: CSharp "c:\linqtest7\northwnd.mdf" /sprocs /functions / in den Singular**  
  
     Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="overview"></a>Übersicht  
 Diese exemplarische Vorgehensweise umfasst sechs Hauptaufgaben:  
  
-   Einrichten der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Lösung in [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)].  
  
-   Hinzufügen der System.Data.Linq-Assembly zum Projekt  
  
-   Hinzufügen der Datenbank-Codedatei zum Projekt.  
  
-   Erstellen einer Verbindung mit der Datenbank  
  
-   Einrichten der Benutzeroberfläche.  
  
-   Ausführen und Testen der Anwendung.  
  
## <a name="creating-a-linq-to-sql-solution"></a>Erstellen einer LINQ to SQL-Lösung  
 In dieser ersten Aufgabe erstellen Sie eine [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]-Lösung, die die erforderlichen Verweise zur Erstellung und Ausführung eines [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Projekts enthält.  
  
#### <a name="to-create-a-linq-to-sql-solution"></a>So erstellen Sie eine LINQ to SQL-Lösung  
  
1.  Auf der [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] **Datei** Sie im Menü **neu**, und klicken Sie dann auf **Projekt**.  
  
2.  In der **-Projekttypen** im Bereich der **neues Projekt** (Dialogfeld), klicken Sie auf **Visual C#-**.  
  
3.  Klicken Sie im Bereich **Vorlagen** auf **Windows Forms-Anwendung**.  
  
4.  In der **Namen** geben **SprocOnlyApp**.  
  
5.  In der **Speicherort** Vergewissern Sie sich, wo die Projektdateien gespeichert werden sollen.  
  
6.  Klicken Sie auf **OK**.  
  
     Der Windows Forms Designer wird geöffnet.  
  
## <a name="adding-the-linq-to-sql-assembly-reference"></a>Hinzufügen des LINQ to SQL-Assemblyverweises  
 Die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Assembly ist nicht in der Standardvorlage für Windows Forms-Anwendungen enthalten. Sie müssen die Assembly selbst hinzufügen. Siehe hierzu die folgenden Schritte:  
  
#### <a name="to-add-systemdatalinqdll"></a>So fügen Sie die Datei System.Data.Linq.dll hinzu  
  
1.  In **Projektmappen-Explorer**, mit der rechten Maustaste **Verweise**, und klicken Sie dann auf **Verweis hinzufügen**.  
  
2.  In der **Verweis hinzufügen** (Dialogfeld), klicken Sie auf **.NET**, klicken Sie auf die System.Data.Linq-Assembly, und klicken Sie dann auf **OK**.  
  
     Dem Projekt wird die Assembly hinzugefügt.  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a>Hinzufügen der Northwind-Codedatei zum Projekt.  
 Bei diesem Schritt wird davon ausgegangen, dass Sie das SQLMetal-Tool zum Erzeugen einer Codedatei aus der Beispieldatenbank Northwind verwendet haben. Weitere Informationen finden Sie im Abschnitt zu Voraussetzungen weiter oben in dieser exemplarischen Vorgehensweise.  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a>So fügen Sie die Northwind-Codedatei dem Projekt hinzu.  
  
1.  Auf der **Projekt** Menü klicken Sie auf **vorhandenes Element hinzufügen**.  
  
2.  In der **vorhandenes Element hinzufügen** c:\linqtest7\northwind.cs ANS (Dialogfeld), und klicken Sie dann auf **hinzufügen**.  
  
     Die Datei northwind.cs wird dem Projekt hinzugefügt.  
  
## <a name="creating-a-database-connection"></a>Erstellen von Datenbankverbindungen  
 In diesem Schritt definieren Sie die Verbindung zur Beispieldatenbank Northwind. Diese exemplarische Vorgehensweise verwendet "c:\linqtest7\northwnd.mdf" als Pfad.  
  
#### <a name="to-create-the-database-connection"></a>So erstellen Sie die Datenbankverbindung  
  
1.  In **Projektmappen-Explorer**, mit der rechten Maustaste **"Form1.cs"**, und klicken Sie dann auf **Code anzeigen**.  
  
2.  Geben Sie den folgenden Code in die `Form1`-Klasse ein:  
  
     [!code-csharp[DLinqWalk4CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#1)]  
  
## <a name="setting-up-the-user-interface"></a>Einrichten der Benutzeroberfläche  
 In diesem Schritt richten Sie eine Benutzeroberfläche ein, sodass Benutzer durch Ausführen gespeicherter Prozeduren auf die Daten in der Datenbank zugreifen können. In den von Ihnen hier entwickelten Anwendungen können Benutzer nur mithilfe der in der Anwendung eingebetteten gespeicherten Prozeduren auf die Daten zugreifen.  
  
#### <a name="to-set-up-the-user-interface"></a>So richten Sie die Benutzeroberfläche ein  
  
1.  Zurück zu den Windows Forms-Designer (**Form1.cs]**).  
  
2.  Klicken Sie im Menü **Ansicht** auf **Toolbox**.  
  
     Die Toolbox wird geöffnet.  
  
    > [!NOTE]
    >  Klicken Sie auf die **Taskleisten** PIN Toolbox geöffnet zu lassen, während Sie die folgenden Schritte in diesem Abschnitt.  
  
3.  Ziehen Sie zwei Schaltflächen, zwei Textfelder und zwei Bezeichnungen von der Toolbox auf **Form1**.  
  
     Ordnen Sie die Steuerelemente wie in der Abbildung an. Erweitern Sie **Form1** , damit die Steuerelemente problemlos angepasst.  
  
4.  Mit der rechten Maustaste **label1**, und klicken Sie dann auf **Eigenschaften**.  
  
5.  Ändern der **Text** Eigenschaft von **label1** auf **Enter OrderID:**.  
  
6.  Auf die gleiche Weise für **label2**, ändern Sie die **Text** Eigenschaft von **label2** zu **Enter CustomerID:**.  
  
7.  Ändern Sie auf die gleiche Weise die **Text** -Eigenschaft für **button1** auf **Bestelldetails**.  
  
8.  Ändern der **Text** -Eigenschaft für **button2** auf **Bestellverlauf**.  
  
     Erweitern Sie die Schaltflächen-Steuerelemente, damit der gesamte Text sichtbar ist.  
  
#### <a name="to-handle-button-clicks"></a>Verarbeitung von Mausklicks auf die Schaltflächen  
  
1.  Doppelklicken Sie auf **Bestelldetails** auf **Form1** um den button1-Ereignishandler im Codeeditor zu öffnen.  
  
2.  Geben Sie den folgenden Code in den `button1`-Ereignishandler ein.  
  
     [!code-csharp[DLinqWalk4CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#2)]  
  
3.  Doppelklicken Sie jetzt auf **button2** auf **Form1** So öffnen die `button2` Handler  
  
4.  Geben Sie den folgenden Code in den `button2`-Ereignishandler ein.  
  
     [!code-csharp[DLinqWalk4CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#3)]  
  
## <a name="testing-the-application"></a>Testen der Anwendung  
 Nun können Sie die Anwendung testen. Beachten Sie, dass die Verbindung zum Datastore auf die Aktionen der beiden gespeicherten Prozeduren beschränkt ist. Diese Aktionen geben die Produkte zu der von Ihnen eingegebenen OrderID und die Produkthistorie zu der von Ihnen eingegebenen CustomerID zurück.  
  
#### <a name="to-test-the-application"></a>So testen Sie die Anwendung  
  
1.  Drücken Sie die Taste F5, um mit dem Debuggen zu beginnen.  
  
     Form1 wird angezeigt.  
  
2.  In der **Enter OrderID** geben `10249`, und klicken Sie dann auf **Bestelldetails**.  
  
     Ein Meldungsfeld listet die in Bestellung 10249 enthaltenen Produkte auf.  
  
     Klicken Sie auf **OK** um das Dialogfeld zu schließen.  
  
3.  In der **Enter CustomerID** geben `ALFKI`, und klicken Sie dann auf **Bestellverlauf**.  
  
     Ein Meldungsfeld mit der Bestellhistorie für den Kunden ALFKI wird angezeigt.  
  
     Klicken Sie auf **OK** um das Dialogfeld zu schließen.  
  
4.  In der **Enter OrderID** geben `123`, und klicken Sie dann auf **Bestelldetails**.  
  
     Die Meldung "Keine Ergebnisse" erscheint.  
  
     Klicken Sie auf **OK** um das Dialogfeld zu schließen.  
  
5.  Auf der **Debuggen** Menü klicken Sie auf **Beenden des Debuggens**.  
  
     Die Debugsitzung schließt.  
  
6.  Wenn Sie Ihre Versuche abgeschlossen haben, können Sie klicken **Projekt schließen** auf die **Datei** Menü, und speichern Sie das Projekt aus, wenn Sie aufgefordert werden.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Sie können dieses Projekt mit einigen Änderungen erweitern. Sie können beispielsweise die verfügbaren gespeicherten Prozeduren in einem Listenfeld aufführen, sodass der Benutzer diese auswählen kann. Sie könnten auch die Ausgabe von Berichten in eine Textdatei umleiten.  
  
## <a name="see-also"></a>Siehe auch  
 [Lernen durch Exemplarische Vorgehensweisen](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)  
 [Gespeicherte Prozeduren](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
