---
title: Analysieren von LINQ to SQL-Quellcode
ms.date: 03/30/2017
ms.assetid: cba3eef8-e108-4478-b588-ad59580e133e
ms.openlocfilehash: 4b23e0df1ee762dd22d43cd1be050db70481db50
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964108"
---
# <a name="analyzing-linq-to-sql-source-code"></a><span data-ttu-id="01b15-102">Analysieren von LINQ to SQL-Quellcode</span><span class="sxs-lookup"><span data-stu-id="01b15-102">Analyzing LINQ to SQL Source Code</span></span>
<span data-ttu-id="01b15-103">Mithilfe der folgenden Schritte können Sie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Quellcode aus der Beispieldatenbank Northwind erstellen.</span><span class="sxs-lookup"><span data-stu-id="01b15-103">By using the following steps, you can produce [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] source code from the Northwind sample database.</span></span> <span data-ttu-id="01b15-104">Sie können Elemente des Objektmodells mit Datenbankelementen vergleichen, um zu ermitteln, wie die Zuweisung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="01b15-104">You can compare elements of the object model with elements of the database to better see how different items are mapped.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="01b15-105">Entwickler, die Visual Studio verwenden, können den O/R-Designer verwenden, um diesen Code zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="01b15-105">Developers using Visual Studio can use the O/R Designer to produce this code.</span></span>  
  
1. <span data-ttu-id="01b15-106">Ist die Beispieldatenbank Northwind noch nicht auf Ihrem Computer installiert, können Sie diese kostenlos herunterladen.</span><span class="sxs-lookup"><span data-stu-id="01b15-106">If you do not already have the Northwind sample database on your development computer, you can download it free of charge.</span></span> <span data-ttu-id="01b15-107">Weitere Informationen finden Sie unter [Herunterladen von Beispiel Datenbanken](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="01b15-107">For more information, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
2. <span data-ttu-id="01b15-108">Verwenden Sie das SqlMetal-Befehlszeilentool, um eine Visual Basic- oder C#-Quelldatei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="01b15-108">Use the SqlMetal command-line tool to generate a Visual Basic or C# source file.</span></span> <span data-ttu-id="01b15-109">Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="01b15-109">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span> <span data-ttu-id="01b15-110">Wenn Sie die folgenden Befehle an einer Eingabeaufforderung eingeben, können Sie Visual Basic- und C#-Quelldateien erzeugen, die gespeicherte Prozeduren und Funktionen enthalten:</span><span class="sxs-lookup"><span data-stu-id="01b15-110">By typing the following commands at a command prompt, you can generate Visual Basic and C# source files that include stored procedures and functions:</span></span>  
  
    - `sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
    - `sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
## <a name="see-also"></a><span data-ttu-id="01b15-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01b15-111">See also</span></span>

- [<span data-ttu-id="01b15-112">Verweis</span><span class="sxs-lookup"><span data-stu-id="01b15-112">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
- [<span data-ttu-id="01b15-113">Hintergrundinformationen</span><span class="sxs-lookup"><span data-stu-id="01b15-113">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
