---
title: 'Gewusst wie: Generieren des Objektmodells in Visual Basic oder C#'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0c73b33-5650-420c-b9dc-f49310c201ee
caps.latest.revision: 3
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 77d7020a985abb8ed56af4fdd9f50a98bfc478c4
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-generate-the-object-model-in-visual-basic-or-c"></a>Gewusst wie: Generieren des Objektmodells in Visual Basic oder C# #
In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird einer relationalen Datenbank ein Objektmodell in einer eigenen Programmiersprache zugeordnet. Zwei Tools zur Verfügung, für die automatische Generierung eines Visual Basic- oder C#-Modells aus den Metadaten einer vorhandenen Datenbank.  
  
-   Wenn Sie Visual Studio verwenden, können Sie mithilfe der [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] ein Objektmodell generieren. Die [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] bietet eine umfangreiche Benutzeroberfläche zum Generieren einer [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] -Objektmodell. Weitere Informationen finden Sie unter [Linq to SQL-Tools in Visual Studio](https://docs.microsoft.com/en-us/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).
  
-   Das SQLMetal-Befehlszeilentool. Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
    > [!NOTE]
    >  Wenn Sie nicht über eine vorhandene Datenbank verfügen, sondern diese aus einem Objektmodell erstellen möchten, erstellen Sie Ihr Objektmodell mit Ihrem Code-Editor und mit <xref:System.Data.Linq.DataContext.CreateDatabase%2A>. Weitere Informationen finden Sie unter [wie: Dynamisches Erstellen einer Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md).  
  
 Dokumentation für die [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] enthält Beispiele zum Generieren Sie ein Visual Basic- oder C#-Objektmodell mithilfe von der [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]. Die folgenden Informationen enthalten Beispiele für die Verwendung des SQLMetal-Befehlszeilentools. Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Beispiel  
 Die SQLMetal-Befehlszeile im folgenden Beispiel werden Visual Basic-Code als attributbasiertes Objektmodell der Beispieldatenbank Northwind erzeugt. Gespeicherte Prozeduren und Funktionen werden ebenfalls gerendert.  
  
```  
sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions  
```  
  
## <a name="example"></a>Beispiel  
 Die SQLMetal-Befehlszeile im folgenden Beispiel erzeugt C#-Code als attributbasiertes Objektmodell der Beispieldatenbank Northwind. Gespeicherte Prozeduren und Funktionen werden ebenfalls gerendert, und Tabellennamen werden automatisch pluralisiert.  
  
```  
sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Programmierhandbuch](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 [Das LINQ to SQL-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [Lernen durch exemplarische Vorgehensweisen](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)  
 [Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)  
 [Attributbasierte Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)  
 [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)  
 [External Mapping (Externe Zuordnung)](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)  
 [Downloading Sample Databases (Herunterladen von Beispieldatenbanken)](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [Erstellen des Objektmodells](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
