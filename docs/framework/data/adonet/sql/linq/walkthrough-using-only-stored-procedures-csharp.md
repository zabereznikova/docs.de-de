---
title: "Exemplarische Vorgehensweise: Ausschlie&#223;liches Verwenden von gespeicherten Prozeduren (C#) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ecde4bf2-fa4d-4252-b5e4-96a46b9e097d
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Exemplarische Vorgehensweise: Ausschlie&#223;liches Verwenden von gespeicherten Prozeduren (C#)
Diese exemplarische Vorgehensweise stellt ein grundlegendes End\-to\-End\-Szenario für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] für den Datenzugriff mithilfe von gespeicherten Prozeduren bereit.  Dieser Ansatz wird oft von Datenbankadministratoren verwendet, um den Zugriff auf den Datenspeicher einzuschränken.  
  
> [!NOTE]
>  Sie können gespeicherte Prozeduren außerdem in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Anwendungen verwenden, um das Standardverhalten zu überschreiben. Dies gilt vor allem für die Prozesse `Create`, `Update` und `Delete`.  Weitere Informationen finden Sie unter [Anpassen von Insert\-, Update\- und Delete\-Operationen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
  
 Im Rahmen dieser exemplarischen Vorgehensweise verwenden Sie zwei Methoden, die in der Beispieldatenbank Northwind gespeicherten Prozeduren zugeordnet wurden: CustOrdersDetail und CustOrderHist.  Die Zuordnung tritt auf, wenn Sie das SQLMetal\-Befehlszeilentool ausführen, um eine C\#\-Datei zu generieren.  Weitere Informationen finden Sie im Abschnitt zu Voraussetzungen weiter unten in dieser exemplarischen Vorgehensweise.  
  
 Diese exemplarische Vorgehensweise basiert nicht auf [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].  Entwickler, die mit [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] arbeiten, können auch [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] verwenden, um die Funktionalität einer gespeicherten Prozedur zu implementieren.  Informationen finden Sie unter [LINQ to SQL\-Tools in Visual Studio](../Topic/LINQ%20to%20SQL%20Tools%20in%20Visual%20Studio2.md).  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Diese exemplarische Vorgehensweise wurde mithilfe von Visual C\#\-Entwicklungseinstellungen geschrieben.  
  
## Vorbereitungsmaßnahmen  
 Für diese exemplarische Vorgehensweise wird Folgendes vorausgesetzt:  
  
-   Diese exemplarische Vorgehensweise verwendet einen dedizierten Ordner \("c:\\linqtest7"\) als Speicherort für Dateien.  Erstellen Sie diesen Ordner, bevor Sie die exemplarische Vorgehensweise starten.  
  
-   Die Beispieldatenbank Northwind.  
  
     Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie diese von der Microsoft Downloadsite herunterladen.  Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).  Nachdem Sie die Datenbank heruntergeladen haben, kopieren Sie die Datei northwnd.mdf in den Ordner c:\\linqtest7.  
  
-   Eine von der Datenbank Northwind generierte C\#\-Codedatei.  
  
     Diese exemplarische Vorgehensweise wurde mithilfe des SQLMetal\-Tools mit der folgenden Befehlszeile geschrieben:  
  
     **sqlmetal \/code:"c:\\linqtest7\\northwind.cs" \/language:csharp "c:\\linqtest7\\northwnd.mdf" \/sprocs \/functions \/pluralize**  
  
     Weitere Informationen finden Sie unter [SqlMetal.exe \(Tool zur Codegenerierung\)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## Überblick  
 Diese exemplarische Vorgehensweise umfasst sechs Hauptaufgaben:  
  
-   Einrichten der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Lösung in [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)].  
  
-   Hinzufügen der System.Data.Linq\-Assembly zum Projekt  
  
-   Hinzufügen der Datenbank\-Codedatei zum Projekt.  
  
-   Erstellen einer Verbindung mit der Datenbank  
  
-   Einrichten der Benutzeroberfläche.  
  
-   Ausführen und Testen der Anwendung.  
  
## Erstellen einer LINQ to SQL\-Lösung  
 In dieser ersten Aufgabe erstellen Sie eine [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]\-Lösung, die die erforderlichen Verweise zur Erstellung und Ausführung eines [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Projekts enthält.  
  
#### So erstellen Sie eine LINQ to SQL\-Lösung  
  
1.  Zeigen Sie im [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]\-Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.  
  
2.  Klicken Sie im Bereich **Projekttypen** des Dialogfelds **Neues Projekt** auf **Visual C\#**.  
  
3.  Klicken Sie im Bereich **Vorlagen** auf **Windows Forms\-Anwendung**.  
  
4.  Geben Sie im Feld **Name** SprocOnlyApp ein.  
  
5.  Geben Sie im Feld **Position** an, wo die Projektdateien gespeichert werden sollen.  
  
6.  Klicken Sie auf **OK**.  
  
     Der Windows Forms Designer wird geöffnet.  
  
## Hinzufügen des LINQ to SQL\-Assemblyverweises  
 Die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Assembly ist nicht in der Standardvorlage für Windows Forms\-Anwendungen enthalten.  Sie müssen die Assembly selbst hinzufügen. Siehe hierzu die folgenden Schritte:  
  
#### So fügen Sie die Datei System.Data.Linq.dll hinzu  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf **Verweise**, und klicken Sie dann auf **Verweis hinzufügen**.  
  
2.  Klicken Sie im Dialogfeld **Verweis hinzufügen** auf **.NET**, klicken Sie auf die System.Data.Linq\-Assembly und dann auf **OK**.  
  
     Dem Projekt wird die Assembly hinzugefügt.  
  
## Hinzufügen der Northwind\-Codedatei zum Projekt.  
 Bei diesem Schritt wird davon ausgegangen, dass Sie das SQLMetal\-Tool zum Erzeugen einer Codedatei aus der Beispieldatenbank Northwind verwendet haben.  Weitere Informationen finden Sie im Abschnitt zu Voraussetzungen weiter oben in dieser exemplarischen Vorgehensweise.  
  
#### So fügen Sie die Northwind\-Codedatei dem Projekt hinzu.  
  
1.  Klicken Sie im Menü **Projekt** auf **Vorhandenes Element hinzufügen**.  
  
2.  Navigieren Sie im Dialogfeld **Vorhandenes Element hinzufügen** zu c:\\linqtest7\\northwind.cs, und klicken Sie dann auf **Hinzufügen**.  
  
     Die Datei northwind.cs wird dem Projekt hinzugefügt.  
  
## Erstellen von Datenbankverbindungen  
 In diesem Schritt definieren Sie die Verbindung zur Beispieldatenbank Northwind.  Diese exemplarische Vorgehensweise verwendet "c:\\linqtest7\\northwnd.mdf" als Pfad.  
  
#### So erstellen Sie die Datenbankverbindung  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf **Form1.cs**, und klicken Sie dann auf **Code anzeigen**.  
  
2.  Geben Sie den folgenden Code in die `Form1`\-Klasse ein:  
  
     [!code-csharp[DLinqWalk4CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#1)]  
  
## Einrichten der Benutzeroberfläche  
 In diesem Schritt richten Sie eine Benutzeroberfläche ein, sodass Benutzer durch Ausführen gespeicherter Prozeduren auf die Daten in der Datenbank zugreifen können.  In den von Ihnen hier entwickelten Anwendungen können Benutzer nur mithilfe der in der Anwendung eingebetteten gespeicherten Prozeduren auf die Daten zugreifen.  
  
#### So richten Sie die Benutzeroberfläche ein  
  
1.  Kehren Sie zum Windows Forms Designer \(**Form1.cs\[Design\]**\) zurück.  
  
2.  Klicken Sie im Menü **Ansicht** auf **Toolbox**.  
  
     Die Toolbox wird geöffnet.  
  
    > [!NOTE]
    >  Klicken Sie auf **AutomatischVerbergen**, damit die Toolbox während der folgenden Schritte geöffnet bleibt.  
  
3.  Ziehen Sie zwei Schaltflächen, zwei Textfelder und zwei Bezeichnungen von der Toolbox auf **Form1**.  
  
     Ordnen Sie die Steuerelemente wie in der Abbildung an.  Erweitern Sie **Form1**, damit die Steuerelemente platziert werden können.  
  
4.  Klicken Sie mit der rechten Maustaste auf **label1**, und klicken Sie dann auf **Eigenschaften**.  
  
5.  Ändern Sie die **Text**\-Eigenschaft von **label1** in **Enter OrderID:**.  
  
6.  Ändern Sie auf die gleiche Weise bei **label2** die **Text**\-Eigenschaft von **label2** in **Enter CustomerID:**.  
  
7.  Ändern Sie auf die gleiche Weise die **Text**\-Eigenschaft für **button1** in **Order Details** .  
  
8.  Ändern Sie die **Text**\-Eigenschaft für **button2** in **Order History**.  
  
     Erweitern Sie die Schaltflächen\-Steuerelemente, damit der gesamte Text sichtbar ist.  
  
#### Verarbeitung von Mausklicks auf die Schaltflächen  
  
1.  Doppelklicken Sie auf **Order Details** in **Form1**, um den button1\-Ereignishandler im Code\-Editor zu öffnen.  
  
2.  Geben Sie den folgenden Code in den `button1`\-Ereignishandler ein.  
  
     [!code-csharp[DLinqWalk4CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#2)]  
  
3.  Doppelklicken Sie nun auf **button2** in **Form1**, um den `button2`\-Ereignishandler zu öffnen.  
  
4.  Geben Sie den folgenden Code in den `button2`\-Ereignishandler ein.  
  
     [!code-csharp[DLinqWalk4CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#3)]  
  
## Testen der Anwendung  
 Nun können Sie die Anwendung testen.  Beachten Sie, dass die Verbindung zum Datastore auf die Aktionen der beiden gespeicherten Prozeduren beschränkt ist.  Diese Aktionen geben die Produkte zu der von Ihnen eingegebenen OrderID und die Produkthistorie zu der von Ihnen eingegebenen CustomerID zurück.  
  
#### So testen Sie die Anwendung  
  
1.  Drücken Sie die Taste F5, um mit dem Debuggen zu beginnen.  
  
     Form1 wird angezeigt.  
  
2.  Geben Sie im Feld **Enter OrderID** `10249` ein, und klicken Sie auf **Order Details**.  
  
     Ein Meldungsfeld listet die in Bestellung 10249 enthaltenen Produkte auf.  
  
     Klicken Sie auf **OK**, um das Dialogfeld zu schließen.  
  
3.  Geben Sie im Feld **Enter CustomerID** `ALFKI` ein, und klicken Sie dann auf **Order History**.  
  
     Ein Meldungsfeld mit der Bestellhistorie für den Kunden ALFKI wird angezeigt.  
  
     Klicken Sie auf **OK**, um das Dialogfeld zu schließen.  
  
4.  Geben Sie im Feld **Enter OrderID** `123` ein, und klicken Sie auf **Order Details**.  
  
     Die Meldung "Keine Ergebnisse" erscheint.  
  
     Klicken Sie auf **OK**, um das Dialogfeld zu schließen.  
  
5.  Klicken Sie im Menü **Debuggen** auf **Debuggen beenden**.  
  
     Die Debugsitzung schließt.  
  
6.  Wenn Sie Ihre Versuche abgeschlossen haben, können Sie auf **Projekt schließen** im Menü **Datei** klicken und Ihr Projekt ggf. speichern.  
  
## Nächste Schritte  
 Sie können dieses Projekt mit einigen Änderungen erweitern.  Sie können beispielsweise die verfügbaren gespeicherten Prozeduren in einem Listenfeld aufführen, sodass der Benutzer diese auswählen kann.  Sie könnten auch die Ausgabe von Berichten in eine Textdatei umleiten.  
  
## Siehe auch  
 [Lernen mit exemplarischen Vorgehensweisen](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)   
 [Gespeicherte Prozeduren](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)