---
title: Analysieren von LINQ to SQL-Quellcode
ms.date: 03/30/2017
ms.assetid: cba3eef8-e108-4478-b588-ad59580e133e
ms.openlocfilehash: dda19800a9aea0d644740c5378f6d5065181993e
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248082"
---
# <a name="analyzing-linq-to-sql-source-code"></a><span data-ttu-id="d8282-102">Analysieren von LINQ to SQL-Quellcode</span><span class="sxs-lookup"><span data-stu-id="d8282-102">Analyzing LINQ to SQL Source Code</span></span>
<span data-ttu-id="d8282-103">Mithilfe der folgenden Schritte können Sie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Quellcode aus der Beispieldatenbank Northwind erstellen.</span><span class="sxs-lookup"><span data-stu-id="d8282-103">By using the following steps, you can produce [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] source code from the Northwind sample database.</span></span> <span data-ttu-id="d8282-104">Sie können Elemente des Objektmodells mit Datenbankelementen vergleichen, um zu ermitteln, wie die Zuweisung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="d8282-104">You can compare elements of the object model with elements of the database to better see how different items are mapped.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d8282-105">Entwickler, die Visual Studio verwenden, können den O/R-Designer verwenden, um diesen Code zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="d8282-105">Developers using Visual Studio can use the O/R Designer to produce this code.</span></span>  
  
1. <span data-ttu-id="d8282-106">Ist die Beispieldatenbank Northwind noch nicht auf Ihrem Computer installiert, können Sie diese kostenlos herunterladen.</span><span class="sxs-lookup"><span data-stu-id="d8282-106">If you do not already have the Northwind sample database on your development computer, you can download it free of charge.</span></span> <span data-ttu-id="d8282-107">Weitere Informationen finden Sie unter [Herunterladen von Beispiel Datenbanken](downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="d8282-107">For more information, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span>  
  
2. <span data-ttu-id="d8282-108">Verwenden Sie das SqlMetal-Befehlszeilentool, um eine Visual Basic- oder C#-Quelldatei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="d8282-108">Use the SqlMetal command-line tool to generate a Visual Basic or C# source file.</span></span> <span data-ttu-id="d8282-109">Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="d8282-109">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span> <span data-ttu-id="d8282-110">Wenn Sie die folgenden Befehle an einer Eingabeaufforderung eingeben, können Sie Visual Basic- und C#-Quelldateien erzeugen, die gespeicherte Prozeduren und Funktionen enthalten:</span><span class="sxs-lookup"><span data-stu-id="d8282-110">By typing the following commands at a command prompt, you can generate Visual Basic and C# source files that include stored procedures and functions:</span></span>  
  
    - `sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
    - `sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
## <a name="see-also"></a><span data-ttu-id="d8282-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8282-111">See also</span></span>

- [<span data-ttu-id="d8282-112">Verweis</span><span class="sxs-lookup"><span data-stu-id="d8282-112">Reference</span></span>](reference.md)
- [<span data-ttu-id="d8282-113">Hintergrundinformationen</span><span class="sxs-lookup"><span data-stu-id="d8282-113">Background Information</span></span>](background-information.md)
