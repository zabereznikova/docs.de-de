---
title: "How to: Call a Stored Procedure by Using LINQ (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "queries [LINQ in Visual Basic], stored procedure calls"
  - "stored procedures sample [Visual Basic]"
  - "stored procedures [LINQ to SQL]"
  - "queries [LINQ in Visual Basic], how-to topics"
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Call a Stored Procedure by Using LINQ (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Die sprachintegrierte Abfrage \(LINQ\) erleichtert den Zugriff auf Datenbankinformationen, einschließlich Datenbankobjekten wie beispielsweise gespeicherten Prozeduren.  
  
 Im folgenden Beispiel wird das Erstellen einer Anwendung dargestellt, von der eine gespeicherte Prozedur in einer SQL Server\-Datenbank aufgerufen wird.  Im Beispiel wird gezeigt, wie zwei verschiedene gespeicherte Prozeduren in der Datenbank aufgerufen werden.  Jede Prozedur gibt die Ergebnisse einer Abfrage zurück.  Von der einen Prozedur werden Eingabeparameter verwendet, von der anderen nicht.  
  
 In den Beispielen dieses Themas wird die Beispieldatenbank Northwind verwendet.  Wenn die Beispieldatenbank Northwind auf dem Entwicklungscomputer nicht installiert ist, können Sie sie von der Website [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) herunterladen.  Anweisungen dazu finden Sie unter [Herunterladen von Beispieldatenbanken](../Topic/Downloading%20Sample%20Databases.md).  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### So erstellen Sie eine Verbindung zu einer Datenbank  
  
1.  Öffnen Sie in Visual Studio den **Server\-Explorer**\/**Datenbank\-Explorer**, indem Sie im Menü **Ansicht** auf **Server\-Explorer**\/**Datenbank\-Explorer** klicken.  
  
2.  Klicken Sie im **Server\-Explorer**\/**Datenbank\-Explorer** mit der rechten Maustaste auf **Datenverbindungen** und anschließend auf **Verbindung hinzufügen**.  
  
3.  Geben Sie eine gültige Verbindung zur Beispieldatenbank Northwind an.  
  
### So fügen Sie ein Projekt hinzu, das eine LINQ to SQL\-Datei enthält  
  
1.  Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.  Wählen Sie Visual Basic\-**Windows Forms\-Anwendung** als Projekttyp aus.  
  
2.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.  Wählen Sie die Elementvorlage **LINQ to SQL\-Klassen** aus.  
  
3.  Nennen Sie die Datei `northwind.dbml`.  Klicken Sie auf **Hinzufügen**.  Der Object Relational Designer \(O\/R\-Designer\) wird für die Datei northwind.dbml geöffnet.  
  
### So fügen Sie dem O\/R\-Designer gespeicherte Prozeduren hinzu  
  
1.  Erweitern Sie im **Server\-Explorer**\/**Datenbank\-Explorer** die Verbindung zur Datenbank Northwind.  Erweitern Sie den Ordner **Gespeicherten Prozeduren**.  
  
     Wenn Sie den O\/R\-Designer geschlossen haben, können Sie ihn durch Doppelklicken auf die zuvor hinzugefügte Datei northwind.dbml erneut öffnen.  
  
2.  Klicken Sie auf die gespeicherte Prozedur **Sales by Year**, und ziehen Sie diese in den rechten Bereich des Designers.  Klicken Sie auf die gespeicherte Prozedur **Ten Most Expensive Products**, und ziehen Sie diese in den rechten Bereich des Designers.  
  
3.  Speichern Sie die Änderungen, und schließen Sie den Designer.  
  
4.  Speichern Sie das Projekt.  
  
### So fügen Sie Code hinzu, um die Ergebnisse der gespeicherten Prozeduren anzuzeigen  
  
1.  Ziehen Sie aus der **Toolbox** ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement auf das Standard\-Windows Form \(Form1\) des Projekts.  
  
2.  Doppelklicken Sie auf Form1, um dem `Load`\-Ereignis Code hinzuzufügen.  
  
3.  Wenn Sie dem O\/R\-Designer gespeicherte Prozeduren hinzugefügt haben, wurde dem Projekt vom Designer ein <xref:System.Data.Linq.DataContext>\-Objekt hinzugefügt.  Dieses Objekt enthält den Code, den Sie zum Zugriff auf diese Prozeduren benötigen.  Das <xref:System.Data.Linq.DataContext>\-Objekt für das Projekt wird auf Grundlage des Namens der DBML\-Datei benannt.  Für dieses Projekt lautet der Name des <xref:System.Data.Linq.DataContext>\-Objekts `northwindDataContext`.  
  
     Sie können im Code eine Instanz von <xref:System.Data.Linq.DataContext> erstellen und die vom O\/R\-Designer festgelegten gespeicherten Prozeduren aufrufen.  Um eine Bindung zum <xref:System.Windows.Forms.DataGridView>\-Objekt vorzunehmen, müssen Sie möglicherweise ein sofortiges Ausführen der Abfrage erzwingen, indem Sie die <xref:System.Linq.Enumerable.ToList%2A>\-Methode für die Ergebnisse der gespeicherten Prozedur aufrufen.  
  
     Fügen Sie den folgenden Code zum `Load`\-Ereignis hinzu, um eine der gespeicherten Prozeduren aufzurufen, die als Methoden für Ihren Datenkontext verfügbar sind.  
  
     [!code-vb[VbLINQtoSQLHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/StoredProcedureHowTo/Form3.vb#1)]  
    [!code-vb[VbLINQtoSQLHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/StoredProcedureHowTo/Form3.vb#2)]  
  
4.  Drücken Sie F5, um das Projekt auszuführen und die Ergebnisse anzuzeigen.  
  
## Siehe auch  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Queries](../../../../visual-basic/language-reference/queries/queries.md)   
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)   
 [DataContext\-Methoden \(O\/R\-Designer\)](/visual-studio/data-tools/datacontext-methods-o-r-designer)   
 [Vorgehensweise: Zuweisen von gespeicherten Prozeduren zur Durchführung von Update\-, Einfüge\- und Löschvorgängen \(O\/R\-Designer\)](../Topic/How%20to:%20Assign%20stored%20procedures%20to%20perform%20updates,%20inserts,%20and%20deletes%20\(O-R%20Designer\).md)   
 [Exemplarische Vorgehensweise: Erstellen von LINQ to SQL\-Klassen \(O\/R\-Designer\)](../Topic/Walkthrough:%20Creating%20LINQ%20to%20SQL%20Classes%20\(O-R%20Designer\).md)