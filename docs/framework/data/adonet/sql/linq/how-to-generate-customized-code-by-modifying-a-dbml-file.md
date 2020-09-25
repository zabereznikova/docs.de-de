---
title: 'Vorgehensweise: Generieren von angepasstem Code durch Verändern einer DBML-Datei'
ms.date: 03/30/2017
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
ms.openlocfilehash: ab49f76a0d5e7338a93e21ae9a8d1d9d74a21e82
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173438"
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a>Vorgehensweise: Generieren von angepasstem Code durch Verändern einer DBML-Datei

Sie können Visual Basic-oder c#-Quellcode aus einer DBML-Metadatendatei (Database Markup Language) generieren. Dieser Ansatz bietet die Möglichkeit zur Anpassung der standardmäßigen .dbml-Datei vor dem Erzeugen des Codes für die Anwendungszuweisung. Dies ist eine erweiterte Funktion.  
  
 Dieses Verfahren umfasst die folgenden Schritte:  
  
1. Erzeugen einer .dbml-Datei.  
  
2. Verwenden eines Editors, um die .dbml-Datei zu ändern. Beachten Sie, dass die. dbml-Datei anhand der Schema Definitionsdatei (. xsd) für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] DBML-Dateien überprüft werden muss. Weitere Informationen finden Sie unter [Code Generierung in LINQ to SQL](code-generation-in-linq-to-sql.md).  
  
3. Generieren Sie den Visual Basic-oder c#-Quellcode.  
  
 In den folgenden Beispielen wird das SQLMetal-Befehlszeilentool verwendet. Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Beispiel  

 Im folgenden Code wird eine .dbml-Datei aus der Beispieldatenbank Northwind erzeugt. Als Quelle für die Datenbank-Metadaten können Sie entweder den Namen der Datenbank oder den Namen der .mdf-Datei verwenden.  
  
```console  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a>Beispiel  

 Der folgende Code generiert Visual Basic-oder c#-Quell Code Datei aus einer DBML-Datei.  
  
```console
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Codegenerierung in LINQ to SQL](code-generation-in-linq-to-sql.md)
- [SqlMetal.exe (Tool zur Codegenerierung)](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [Erstellen des Objektmodells](creating-the-object-model.md)
