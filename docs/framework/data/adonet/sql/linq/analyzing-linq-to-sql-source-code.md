---
title: Analysieren von LINQ to SQL-Quellcode
ms.date: 03/30/2017
ms.assetid: cba3eef8-e108-4478-b588-ad59580e133e
ms.openlocfilehash: e39b1686269442044beb73bb7e572738832bec27
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164583"
---
# <a name="analyzing-linq-to-sql-source-code"></a>Analysieren von LINQ to SQL-Quellcode

Mithilfe der folgenden Schritte können Sie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Quellcode aus der Beispieldatenbank Northwind erstellen. Sie können Elemente des Objektmodells mit Datenbankelementen vergleichen, um zu ermitteln, wie die Zuweisung erfolgt.  
  
> [!NOTE]
> Entwickler, die Visual Studio verwenden, können den O/R-Designer verwenden, um diesen Code zu entwickeln.  
  
1. Ist die Beispieldatenbank Northwind noch nicht auf Ihrem Computer installiert, können Sie diese kostenlos herunterladen. Weitere Informationen finden Sie unter [Herunterladen von Beispiel Datenbanken](downloading-sample-databases.md).  
  
2. Verwenden Sie das SqlMetal-Befehlszeilentool, um eine Visual Basic- oder C#-Quelldatei zu generieren. Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../tools/sqlmetal-exe-code-generation-tool.md). Wenn Sie die folgenden Befehle an einer Eingabeaufforderung eingeben, können Sie Visual Basic- und C#-Quelldateien erzeugen, die gespeicherte Prozeduren und Funktionen enthalten:  
  
    - `sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
    - `sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
## <a name="see-also"></a>Weitere Informationen

- [Verweis](reference.md)
- [Hintergrundinformationen](background-information.md)
