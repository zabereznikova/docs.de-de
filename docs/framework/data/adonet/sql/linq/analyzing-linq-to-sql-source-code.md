---
title: Analysieren von LINQ to SQL-Quellcode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cba3eef8-e108-4478-b588-ad59580e133e
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0e1677d8e30b083efe99f916b28672ddb6c3dd99
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="analyzing-linq-to-sql-source-code"></a>Analysieren von LINQ to SQL-Quellcode
Mithilfe der folgenden Schritte können Sie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Quellcode aus der Beispieldatenbank Northwind erstellen. Sie können Elemente des Objektmodells mit Datenbankelementen vergleichen, um zu ermitteln, wie die Zuweisung erfolgt.  
  
> [!NOTE]
>  Entwickler mit [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] können diesen Code mithilfe des [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] erzeugen.  
  
1.  Ist die Beispieldatenbank Northwind noch nicht auf Ihrem Computer installiert, können Sie diese kostenlos herunterladen. Weitere Informationen finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
2.  Verwenden Sie das SqlMetal-Befehlszeilentool, um eine Visual Basic- oder C#-Quelldatei zu generieren. Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md). Wenn Sie die folgenden Befehle an einer Eingabeaufforderung eingeben, können Sie Visual Basic- und C#-Quelldateien erzeugen, die gespeicherte Prozeduren und Funktionen enthalten:  
  
    -   `sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
    -   `sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
## <a name="see-also"></a>Siehe auch  
 [Referenz](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 [Hintergrundinformationen](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
