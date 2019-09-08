---
title: 'Vorgehensweise: Generieren des Objektmodells in Visual Basic oder C#'
ms.date: 03/30/2017
ms.assetid: a0c73b33-5650-420c-b9dc-f49310c201ee
ms.openlocfilehash: 07df915b5c826c7b82f2aaf16fcc22da0361d5f6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781913"
---
# <a name="how-to-generate-the-object-model-in-visual-basic-or-c"></a>Vorgehensweise: Generieren des Objektmodells in Visual Basic oder C\#
In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird einer relationalen Datenbank ein Objektmodell in einer eigenen Programmiersprache zugeordnet. Zum automatischen Erstellen einer Visual Basic oder C# eines Modells aus den Metadaten einer vorhandenen Datenbank stehen zwei Tools zur Verfügung.  
  
- Wenn Sie Visual Studio verwenden, können Sie das objektrelationaler Designer verwenden, um ein Objektmodell zu generieren. Der O/R-Designer stellt eine umfangreiche Benutzeroberfläche bereit, die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Sie beim Generieren eines-Objektmodells unterstützt. Weitere Informationen finden Sie unter [LINQ to SQL-Tools in Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).
  
- Das SQLMetal-Befehlszeilentool. Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
    > [!NOTE]
    > Wenn Sie nicht über eine vorhandene Datenbank verfügen, sondern diese aus einem Objektmodell erstellen möchten, erstellen Sie Ihr Objektmodell mit Ihrem Code-Editor und mit <xref:System.Data.Linq.DataContext.CreateDatabase%2A>. Weitere Informationen finden Sie unter [Vorgehensweise: Dynamisches Erstellen einer Datenbank](how-to-dynamically-create-a-database.md).  
  
 In der Dokumentation für den o/r-Designer finden Sie Beispiele für das generieren C# einer Visual Basic oder eines Objektmodells mit dem o/r-Designer. Die folgenden Informationen enthalten Beispiele für die Verwendung des SQLMetal-Befehlszeilentools. Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Beispiel  
 Die SQLMetal-Befehlszeile im folgenden Beispiel erzeugt Visual Basic-Code als Attribut basiertes Objektmodell der Beispieldatenbank Northwind. Gespeicherte Prozeduren und Funktionen werden ebenfalls gerendert.  
  
```  
sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions  
```  
  
## <a name="example"></a>Beispiel  
 Die SQLMetal-Befehlszeile im folgenden Beispiel erzeugt C#-Code als attributbasiertes Objektmodell der Beispieldatenbank Northwind. Gespeicherte Prozeduren und Funktionen werden ebenfalls gerendert, und Tabellennamen werden automatisch pluralisiert.  
  
```  
sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize  
```  
  
## <a name="see-also"></a>Siehe auch

- [Programmierhandbuch](programming-guide.md)
- [Das LINQ to SQL-Objektmodell](the-linq-to-sql-object-model.md)
- [Lernen durch exemplarische Vorgehensweisen](learning-by-walkthroughs.md)
- [Vorgehensweise: Anpassen von Entitäts Klassen mit dem Code-Editor](how-to-customize-entity-classes-by-using-the-code-editor.md)
- [Attributbasierte Zuordnung](attribute-based-mapping.md)
- [SqlMetal.exe (Tool zur Codegenerierung)](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [External Mapping (Externe Zuordnung)](external-mapping.md)
- [Downloading Sample Databases (Herunterladen von Beispieldatenbanken)](downloading-sample-databases.md)
- [Erstellen des Objektmodells](creating-the-object-model.md)
