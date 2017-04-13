---
title: "Exemplarische Vorgehensweise: Ausschlie&#223;liches Verwenden von gespeicherten Prozeduren (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5a736a30-ba66-4adb-b87c-57d19476e862
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Exemplarische Vorgehensweise: Ausschlie&#223;liches Verwenden von gespeicherten Prozeduren (Visual Basic)
Diese exemplarische Vorgehensweise stellt ein grundlegendes End\-to\-End\-[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Szenario für den Datenzugriff mithilfe von gespeicherten Prozeduren bereit.  Dieser Ansatz wird oft von Datenbankadministratoren verwendet, um den Zugriff auf den Datenspeicher einzuschränken.  
  
> [!NOTE]
>  Sie können gespeicherte Prozeduren außerdem in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Anwendungen verwenden, um das Standardverhalten zu überschreiben. Dies gilt vor allem für die Prozesse `Create`, `Update` und `Delete`.  Weitere Informationen finden Sie unter [Anpassen von Insert\-, Update\- und Delete\-Operationen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
  
 Im Rahmen dieser exemplarischen Vorgehensweise verwenden Sie zwei Methoden, die in der Beispieldatenbank Northwind gespeicherten Prozeduren zugeordnet wurden: CustOrdersDetail und CustOrderHist.  Die Zuordnung tritt auf, wenn Sie das SQLMetal\-Befehlszeilentool ausführen, um eine [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]\-Datei zu generieren.  Weitere Informationen finden Sie im Abschnitt zu Voraussetzungen weiter unten in dieser exemplarischen Vorgehensweise.  
  
 Diese exemplarische Vorgehensweise basiert nicht auf [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].  Entwickler, die mit [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] arbeiten, können auch [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] verwenden, um die Funktionalität einer gespeicherten Prozedur zu implementieren.  Informationen finden Sie unter [LINQ to SQL\-Tools in Visual Studio](../Topic/LINQ%20to%20SQL%20Tools%20in%20Visual%20Studio2.md).  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Diese exemplarische Vorgehensweise wurde mithilfe von Visual Basic\-Entwicklungseinstellungen geschrieben.  
  
## Vorbereitungsmaßnahmen  
 Für diese exemplarische Vorgehensweise wird Folgendes vorausgesetzt:  
  
-   Diese exemplarische Vorgehensweise verwendet einen dedizierten Ordner \("c:\\linqtest3"\) als Speicherort für Dateien.  Erstellen Sie diesen Ordner, bevor Sie die exemplarische Vorgehensweise starten.  
  
-   Die Beispieldatenbank Northwind.  
  
     Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie diese von der Microsoft Downloadsite herunterladen.  Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).  Nachdem Sie die Datenbank heruntergeladen haben, kopieren Sie die Datei northwnd.mdf in den Ordner c:\\linqtest3.  
  
-   Eine von der Datenbank Northwind generierte [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]\-Codedatei.  
  
     Diese exemplarische Vorgehensweise wurde mithilfe des SQLMetal\-Tools mit der folgenden Befehlszeile geschrieben:  
  
     **sqlmetal \/code:"c:\\linqtest3\\northwind.vb" \/language:vb "c:\\linqtest3\\northwnd.mdf" \/sprocs \/functions \/pluralize**  
  
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
  
1.  Klicken Sie im [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]\-Menü **Datei** auf **Neues Projekt**.  
  
2.  Erweitern Sie im Bereich **Projekttypen** des Dialogfelds **Neues Projekt** den Eintrag **Visual Basic**, und klicken Sie dann auf **Windows**.  
  
3.  Klicken Sie im Bereich **Vorlagen** auf **Windows Forms\-Anwendung**.  
  
4.  Geben Sie im Feld **Name** SprocOnlyApp ein.  
  
5.  Klicken Sie auf **OK**.  
  
     Der Windows Forms Designer wird geöffnet.  
  
## Hinzufügen des LINQ to SQL\-Assemblyverweises  
 Die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Assembly ist nicht in der Standardvorlage für Windows Forms\-Anwendungen enthalten.  Sie müssen die Assembly selbst hinzufügen. Siehe hierzu die folgenden Schritte:  
  
#### So fügen Sie die Datei System.Data.Linq.dll hinzu  
  
1.  Klicken Sie im **Projektmappen\-Explorer** auf **Alle Dateien anzeigen**.  
  
2.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf **Verweise**, und klicken Sie dann auf **Verweis hinzufügen**.  
  
3.  Klicken Sie im Dialogfeld **Verweis hinzufügen** auf **.NET**, klicken Sie auf die System.Data.Linq\-Assembly und dann auf **OK**.  
  
     Dem Projekt wird die Assembly hinzugefügt.  
  
## Hinzufügen der Northwind\-Codedatei zum Projekt.  
 Bei diesem Schritt wird davon ausgegangen, dass Sie das SQLMetal\-Tool zum Erzeugen einer Codedatei aus der Beispieldatenbank Northwind verwendet haben.  Weitere Informationen finden Sie im Abschnitt zu Voraussetzungen weiter oben in dieser exemplarischen Vorgehensweise.  
  
#### So fügen Sie die Northwind\-Codedatei dem Projekt hinzu.  
  
1.  Klicken Sie im Menü **Projekt** auf **Vorhandenes Element hinzufügen**.  
  
2.  Navigieren Sie im Dialogfeld **Vorhandenes Element hinzufügen** zu c:\\linqtest3\\northwind.vb, und klicken Sie dann auf **Hinzufügen**.  
  
     Die Datei northwind.vb wird dem Projekt hinzugefügt.  
  
## Erstellen von Datenbankverbindungen  
 In diesem Schritt definieren Sie die Verbindung zur Beispieldatenbank Northwind.  Diese exemplarische Vorgehensweise verwendet "c:\\linqtest3\\northwnd.mdf" als Pfad.  
  
#### So erstellen Sie die Datenbankverbindung  
  
1.  Klicken Sie im **Lösungs\-Explorer** mit der rechten Maustaste auf **Form1.vb**, und klicken Sie dann auf **Code anzeigen**.  
  
     `Class Form1` erscheint im Code\-Editor.  
  
2.  Geben Sie den folgenden Code in den `Form1`\-Code\-Block ein.  
  
     [!code-vb[DLinqWalk4VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#1)]  
  
## Einrichten der Benutzeroberfläche  
 In diesem Schritt erstellen Sie eine Benutzeroberfläche, sodass Benutzer durch Ausführen gespeicherter Prozeduren auf die Daten in der Datenbank zugreifen können.  In den von Ihnen hier entwickelten Anwendungen können Benutzer nur mithilfe der in der Anwendung eingebetteten gespeicherten Prozeduren auf die Daten zugreifen.  
  
#### So richten Sie die Benutzeroberfläche ein  
  
1.  Kehren Sie zum Windows Forms Designer \(**Form1.vb\[Design\]**\) zurück.  
  
2.  Klicken Sie im Menü **Ansicht** auf **Toolbox**.  
  
     Die Toolbox wird geöffnet.  
  
    > [!NOTE]
    >  Klicken Sie auf **AutomatischVerbergen**, damit die Toolbox während der folgenden Schritte geöffnet bleibt.  
  
3.  Ziehen Sie zwei Schaltflächen, zwei Textfelder und zwei Bezeichnungen von der Toolbox auf **Form1**.  
  
     Ordnen Sie die Steuerelemente wie in der Abbildung an.  Erweitern Sie **Form1**, damit die Steuerelemente platziert werden können.  
  
4.  Klicken Sie mit der rechten Maustaste auf **Label1**, und klicken Sie dann auf **Eigenschaften**.  
  
5.  Ändern Sie die **Text**\-Eigenschaft von **Label1** in **Enter OrderID:**.  
  
6.  Ändern Sie auf die gleiche Weise bei **lLabel2** die **Text**\-Eigenschaft von **Label2** in **Enter CustomerID:**.  
  
7.  Ändern Sie auf die gleiche Weise die **Text**\-Eigenschaft für **Button1** in **Order Details** .  
  
8.  Ändern Sie die **Text**\-Eigenschaft für **Button2** in **Order History**.  
  
     Erweitern Sie die Schaltflächen\-Steuerelemente, damit der gesamte Text sichtbar ist.  
  
#### Verarbeitung von Mausklicks auf die Schaltflächen  
  
1.  Doppelklicken Sie **Order Details** auf **Form1**, um den `Button1`\-Ereignishandler zu erstellen und den Code\-Editor zu öffnen.  
  
2.  Geben Sie den folgenden Code in den `Button1`\-Ereignishandler ein.  
  
     [!code-vb[DLinqWalk4VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#2)]  
  
3.  Doppelklicken Sie jetzt auf **Button2** in Form1, um den `Button2`\-Ereignishandler zu erstellen und den Code\-Editor zu öffnen.  
  
4.  Geben Sie den folgenden Code in den `Button2`\-Ereignishandler ein.  
  
     [!code-vb[DLinqWalk4VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#3)]  
  
## Testen der Anwendung  
 Nun können Sie die Anwendung testen.  Beachten Sie, dass die Verbindung zum Datastore auf die Aktionen der beiden gespeicherten Prozeduren beschränkt ist.  Diese Aktionen geben die Produkte zu der von Ihnen eingegebenen OrderID und die Produkthistorie zu der von Ihnen eingegebenen CustomerID zurück.  
  
#### So testen Sie die Anwendung  
  
1.  Drücken Sie die Taste F5, um mit dem Debuggen zu beginnen.  
  
     Form1 wird angezeigt.  
  
2.  Geben Sie im Feld **Enter OrderID** 10249 ein, und klicken Sie auf **Order Details**.  
  
     Ein Meldungsfeld listet die in Bestellung 10249 enthaltenen Produkte auf.  
  
     Klicken Sie auf **OK**, um das Dialogfeld zu schließen.  
  
3.  Geben Sie im Feld **Enter CustomerID** `ALFKI` ein, und klicken Sie dann auf **Order History**.  
  
     Ein Meldungsfeld mit der Bestellhistorie für Kunde ALFKI wird angezeigt.  
  
     Klicken Sie auf **OK**, um das Dialogfeld zu schließen.  
  
4.  Geben Sie im Feld **Enter OrderID** `123` ein, und klicken Sie auf **Order Details**.  
  
     Ein Meldungsfeld zeigt "Keine Ergebnisse" an.  
  
     Klicken Sie auf **OK**, um das Dialogfeld zu schließen.  
  
5.  Klicken Sie im Menü **Debuggen** auf **Debuggen beenden**.  
  
     Die Debugsitzung schließt.  
  
6.  Wenn Sie Ihre Versuche abgeschlossen haben, können Sie auf **Projekt schließen** im Menü **Datei** klicken und Ihr Projekt ggf. speichern.  
  
## Nächste Schritte  
 Sie können dieses Projekt mit einigen Änderungen erweitern.  Sie können beispielsweise die verfügbaren gespeicherten Prozeduren in einem Listenfeld aufführen, sodass der Benutzer diese auswählen kann.  Sie könnten auch die Ausgabe von Berichten in eine Textdatei umleiten.  
  
## Siehe auch  
 [Lernen mit exemplarischen Vorgehensweisen](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)   
 [Gespeicherte Prozeduren](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)