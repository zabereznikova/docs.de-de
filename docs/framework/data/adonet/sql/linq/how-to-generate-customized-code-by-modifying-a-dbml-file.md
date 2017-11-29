---
title: "Gewusst wie: Generieren von angepasstem Code durch Verändern einer DBML-Datei"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 743e938df0b9c7f12a9c3a11a4b5558137add529
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a>Gewusst wie: Generieren von angepasstem Code durch Verändern einer DBML-Datei
Sie können generieren [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] oder C#-Quellcode aus einer Database Markup Language (.dbml)-Metadatendatei. Dieser Ansatz bietet die Möglichkeit zur Anpassung der standardmäßigen .dbml-Datei vor dem Erzeugen des Codes für die Anwendungszuweisung. Dies ist eine erweiterte Funktion.  
  
 Dieses Verfahren umfasst die folgenden Schritte:  
  
1.  Erzeugen einer .dbml-Datei.  
  
2.  Verwenden eines Editors, um die .dbml-Datei zu ändern. Beachten Sie, die anhand der Schemadefinitionsdatei (.xsd) für die DBML-Datei überprüfen muss [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] DBML-Dateien. Weitere Informationen finden Sie unter [Codegenerierung in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).  
  
3.  Erzeugen Sie den [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]-Quellcode oder den C#-Quellcode.  
  
 In den folgenden Beispielen wird das SQLMetal-Befehlszeilentool verwendet. Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Code wird eine .dbml-Datei aus der Beispieldatenbank Northwind erzeugt. Als Quelle für die Datenbank-Metadaten können Sie entweder den Namen der Datenbank oder den Namen der .mdf-Datei verwenden.  
  
```  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Code wird [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]-Quellcode oder C#-Quellcode aus einer .dbml-Datei erzeugt.  
  
```  
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Codegenerierung in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)  
 [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)  
 [Erstellen des Objektmodells](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
