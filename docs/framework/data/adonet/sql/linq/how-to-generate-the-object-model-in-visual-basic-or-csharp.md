---
title: 'Vorgehensweise: Generieren des Objektmodells in Visual Basic oder C#'
ms.date: 03/30/2017
ms.assetid: a0c73b33-5650-420c-b9dc-f49310c201ee
ms.openlocfilehash: e2491cf18be556cb26f084a178b7bf09448c6904
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546613"
---
# <a name="how-to-generate-the-object-model-in-visual-basic-or-c"></a>Gewusst wie: Generieren des Objektmodells in Visual Basic oder C\#
In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird einer relationalen Datenbank ein Objektmodell in einer eigenen Programmiersprache zugeordnet. Zum automatischen Erstellen eines Visual Basic-oder c#-Modells aus den Metadaten einer vorhandenen Datenbank stehen zwei Tools zur Verfügung.  
  
- Wenn Sie Visual Studio verwenden, können Sie das objektrelationaler Designer verwenden, um ein Objektmodell zu generieren. Der O/R-Designer stellt eine umfangreiche Benutzeroberfläche bereit, die Sie beim Generieren eines- [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Objektmodells unterstützt. Weitere Informationen finden Sie unter [LINQ to SQL-Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).
  
- Das SQLMetal-Befehlszeilentool. Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
    > [!NOTE]
    > Wenn Sie nicht über eine vorhandene Datenbank verfügen, sondern diese aus einem Objektmodell erstellen möchten, erstellen Sie Ihr Objektmodell mit Ihrem Code-Editor und mit <xref:System.Data.Linq.DataContext.CreateDatabase%2A>. Weitere Informationen finden Sie unter Gewusst [wie: Dynamisches Erstellen einer Datenbank](how-to-dynamically-create-a-database.md).  
  
 In der Dokumentation für den o/r-Designer finden Sie Beispiele für das Generieren eines Visual Basic-oder c#-Objektmodells mit dem o/r-Designer. Die folgenden Informationen enthalten Beispiele für die Verwendung des SQLMetal-Befehlszeilentools. Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Beispiel  
 Die SQLMetal-Befehlszeile im folgenden Beispiel erzeugt Visual Basic-Code als Attribut basiertes Objektmodell der Beispieldatenbank Northwind. Gespeicherte Prozeduren und Funktionen werden ebenfalls gerendert.  
  
```console  
sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions  
```  
  
## <a name="example"></a>Beispiel  
 Die SQLMetal-Befehlszeile im folgenden Beispiel erzeugt C#-Code als attributbasiertes Objektmodell der Beispieldatenbank Northwind. Gespeicherte Prozeduren und Funktionen werden ebenfalls gerendert, und Tabellennamen werden automatisch pluralisiert.  
  
```console  
sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize  
```  
  
## <a name="see-also"></a>Siehe auch

- [Programmierhandbuch](programming-guide.md)
- [Das LINQ to SQL-Objektmodell](the-linq-to-sql-object-model.md)
- [Lernen durch exemplarische Vorgehensweisen](learning-by-walkthroughs.md)
- [Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor](how-to-customize-entity-classes-by-using-the-code-editor.md)
- [Attributbasiertes Zuordnen](attribute-based-mapping.md)
- [SqlMetal.exe (Tool zur Codegenerierung)](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [External Mapping (Externe Zuordnung)](external-mapping.md)
- [Herunterladen von Beispieldatenbanken](downloading-sample-databases.md)
- [Erstellen des Objektmodells](creating-the-object-model.md)
