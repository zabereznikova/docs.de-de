---
title: 'Gewusst wie: Filtern von Abfrageergebnissen unter Verwendung von LINQ (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- filtering [Visual Basic]
- filtering data [LINQ in Visual Basic]
- filtering [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], filtering results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- filtering data [Visual Basic]
ms.assetid: ef103092-9bed-4134-97f4-2db696e83c12
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5aee7c3b07bcb8e623fb9090218a2b4bc8426ee3
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a>Gewusst wie: Filtern von Abfrageergebnissen unter Verwendung von LINQ (Visual Basic)
Language-Integrated Query (LINQ) erleichtert den Zugriff auf Datenbankinformationen und Abfragen ausführen.  
  
 Im folgenden Beispiel wird veranschaulicht, wie eine neue Anwendung erstellen, die eine SQL Server-Datenbank abfragt und filtert die Ergebnisse nach einem bestimmten Wert mithilfe der `Where` Klausel. Weitere Informationen finden Sie unter [Where-Klausel](../../../../visual-basic/language-reference/queries/where-clause.md).  
  
 In den Beispielen in diesem Thema verwenden die Beispieldatenbank Northwind. Wenn Sie die Beispieldatenbank Northwind auf dem Entwicklungscomputer nicht haben, können Sie herunterladen aus der [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Website. Eine Anleitung hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](https://msdn.microsoft.com/library/bb399411).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>Um eine Verbindung mit einer Datenbank zu erstellen.  
  
1.  Öffnen Sie in Visual Studio **Server-Explorer**/**Datenbank-Explorer** durch Klicken auf **Server-Explorer**/**Datenbank-Explorer** auf der **Ansicht** Menü.  
  
2.  Mit der rechten Maustaste **Datenverbindungen** in **Server-Explorer**/**Datenbank-Explorer** , und klicken Sie dann auf **Verbindung hinzufügen**.  
  
3.  Geben Sie eine gültige Verbindung mit der Beispieldatenbank Northwind.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Ein Projekt hinzufügen, die eine LINQ to SQL-Datei enthält.  
  
1.  In Visual Studio auf die **Datei** auf **neu** , und klicken Sie dann auf **Projekt**. Wählen Sie Visual Basic **Windows Forms-Anwendung** als Projekttyp.  
  
2.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**. Wählen Sie die **LINQ to SQL Classes** Elementvorlage.  
  
3.  Nennen Sie die Datei `northwind.dbml`. Klicken Sie auf **Hinzufügen**. Der Object Relational Designer (O/R-Designer) wird für die Datei northwind.dbml geöffnet.  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a>Zum Hinzufügen von Tabellen in den O/R-Designer Abfragen  
  
1.  In **Server-Explorer**/**Datenbank-Explorer**, erweitern Sie die Verbindung zur Northwind-Datenbank. Erweitern Sie die **Tabellen** Ordner.  
  
     Wenn Sie den O/R-Designer geschlossen haben, können Sie es durch Doppelklicken auf die Sie zuvor hinzugefügte Datei northwind.dbml erneut öffnen.  
  
2.  Klicken Sie auf die Tabelle Customers, und ziehen Sie es auf den linken Bereich des Designers. Klicken Sie auf die Tabelle Orders, und ziehen Sie es auf den linken Bereich des Designers.  
  
     Der Designer erstellt neue `Customer` und `Order` -Objekte für das Projekt. Beachten Sie, dass der Designer Beziehungen zwischen den Tabellen erkennt automatisch und untergeordnete Eigenschaften für verknüpfte Objekte erstellt. Z. B. IntelliSense wird angezeigt, die `Customer` Objekt verfügt über eine `Orders` -Eigenschaft für alle Aufträge im Zusammenhang mit diesen Kunden.  
  
3.  Speichern Sie die Änderungen und schließen Sie den Designer.  
  
4.  Speichern Sie das Projekt.  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a>Hinzufügen von Code, um die Datenbank abzufragen und die Ergebnisse werden angezeigt.  
  
1.  Aus der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.DataGridView>-Steuerelement auf das Standard-Windows Form für Ihr Projekt, Form1.</xref:System.Windows.Forms.DataGridView>  
  
2.  Doppelklicken Sie auf Form1, um Code zum Hinzufügen der `Load` -Ereignis des Formulars.  
  
3.  Wenn Sie den O/R-Designer Tabellen hinzugefügt haben, wird der Designer hinzugefügt ein <xref:System.Data.Linq.DataContext>-Objekt für das Projekt.</xref:System.Data.Linq.DataContext> Dieses Objekt enthält den Code, den zum Zugriff auf die Tabellen, neben der einzelnen Objekte und Sammlungen für jede Tabelle. Das <xref:System.Data.Linq.DataContext>-Objekt für das Projekt mit dem Namen basierend auf den Namen der DBML-Datei.</xref:System.Data.Linq.DataContext> Für dieses Projekt die <xref:System.Data.Linq.DataContext>-Objekt mit dem Namen `northwindDataContext`.</xref:System.Data.Linq.DataContext>  
  
     Erstellen Sie können eine Instanz von der <xref:System.Data.Linq.DataContext>in Ihrem Code und die Abfrage der Tabellen, die vom O/R-Designer angegeben.</xref:System.Data.Linq.DataContext>  
  
     Fügen Sie den folgenden Code der `Load` Ereignis, um die Tabellen zu Abfragen, die als Eigenschaften des Datenkontexts verfügbar gemacht werden. Die Abfrage filtert die Ergebnisse und gibt nur die Kunden, die in gespeichert sind `London`.  
  
     [!code-vb[VbLINQToSQLHowTos&#11;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_1.vb)]  
  
4.  Drücken Sie F5, um das Projekt auszuführen und die Ergebnisse anzuzeigen.  
  
5.  Im folgenden werden einige weitere Filter, die Sie ausprobieren können.  
  
     [!code-vb[VbLINQToSQLHowTos&#12;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Abfragen](../../../../visual-basic/language-reference/queries/queries.md)   
 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)   
 [DataContext-Methoden (O/R-Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)

