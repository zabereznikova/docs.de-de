---
title: LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 73d13345-eece-471a-af40-4cc7a2f11655
ms.openlocfilehash: 532813f68c0996337ce3bed8172a826425db1ec0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902602"
---
# <a name="linq-to-sql"></a>LINQ to SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ist eine Komponente von [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] Version 3.5, die eine Laufzeitinfrastruktur für die Verwaltung relationaler Daten als Objekte bereitstellt.  
  
> [!NOTE]
>  Relationale Daten erscheinen als Auflistung zweidimensionaler Tabellen (*Beziehungen* oder *Flatfiles*), bei denen gemeinsame Spalten Tabellen verbinden. Zur effektiven Verwendung von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] müssen Sie mit den zugrunde liegenden Prinzipien relationaler Datenbanken vertraut sein.  
  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird das Datenmodell einer relationalen Datenbank einem Objektmodell zugeordnet, das in der Programmiersprache des Entwicklers ausgedrückt ist. Wenn Sie die Anwendung ausführen, übersetzt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die sprachintegrierten Abfragen im Objektmodell in SQL und sendet sie zur Ausführung an die Datenbank. Wenn die Datenbank die Ergebnisse zurückgibt, übersetzt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] diese zurück in Objekte, die Sie mit Ihrer eigenen Programmiersprache bearbeiten können.  
  
 Entwickler, die in der Regel mithilfe von Visual Studio verwenden, die [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)], die bietet eine Benutzeroberfläche zur Implementierung zahlreicher Funktionen von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 Die Dokumentation zu diesem Release von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] beschreibt die grundlegenden Bausteine, Verfahren und Techniken zur Erstellung von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Anwendungen. Sie können auch Microsoft Docs nach speziellen Themen suchen und Sie können teilnehmen, der [LINQ-Forum](https://go.microsoft.com/fwlink/?LinkId=76488), Hier können Sie komplexere Themen ausführlich mit Experten diskutieren. Zum Schluss die [LINQ to SQL: .NET Language-Integrated Query for Relational Data](https://go.microsoft.com/fwlink/?LinkId=93205) Whitepaper Details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] -Technologie sowie Beispiele für Visual Basic und C#-Code.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Erste Schritte](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)  
 Bietet eine komprimierte Übersicht über [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sowie Informationen zu den ersten Schritten mit [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Programmierhandbuch](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 Bietet schrittweise Anleitungen für Zuordnung, Abfrage, Update, Debugging und ähnlichen Aufgaben.  
  
 [Verweis](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 Enthält Referenzinformationen zu verschiedenen Aspekten der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Programmierung. Die Themen umfassen SQL-CLR-Typzuordnung, Übersetzung von Standardabfrageoperatoren und mehr.  
  
 [Beispiele](../../../../../../docs/framework/data/adonet/sql/linq/samples.md)  
 Enthält Links zu Visual Basic und C#-Beispielen.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Language-Integrated Query (LINQ) - C#](../../../../../csharp/programming-guide/concepts/linq/index.md)\
 Bietet eine Übersicht der LINQ-Technologien in C#.
 
 [Language Integrated Query (LINQ) – Visual Basic](../../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 Bietet eine Übersicht der LINQ-Technologien in Visual Basic.
  
 [LINQ](../../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 Beschreibt [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] Technologien für die Visual Basic-Benutzer.  
  
 [LINQ und ADO.NET](../../../../../../docs/framework/data/adonet/linq-and-ado-net.md)  
 Links zum [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]-Portal.  
  
 [LINQ to SQL Walkthroughs (Exemplarische Vorgehensweisen für LINQ to SQL)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb386295(v=vs.90))  
 Listet exemplarische Vorgehensweisen für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] auf.  
  
 [Downloading Sample Databases (Herunterladen von Beispieldatenbanken)](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 Beschreibt, wie die in der Dokumentation verwendeten Beispieldatenbanken heruntergeladen werden.  
  
 [Übersicht über LinqDataSource Webserver-Steuerelement](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100))  
 Erläutert, wie das <xref:System.Web.UI.WebControls.LinqDataSource>-Steuerelement über die [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)]-Datenquellen-Steuerarchitektur [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] für Web-Entwickler bereitstellt.
