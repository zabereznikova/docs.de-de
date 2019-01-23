---
title: 'Vorgehensweise: Generieren von angepasstem Code durch Verändern einer DBML-Datei'
ms.date: 03/30/2017
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
ms.openlocfilehash: b17743f20cf9fcb01cdd39dc7afc3f6b4419ebff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499092"
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a><span data-ttu-id="89f22-102">Vorgehensweise: Generieren von angepasstem Code durch Verändern einer DBML-Datei</span><span class="sxs-lookup"><span data-stu-id="89f22-102">How to: Generate Customized Code by Modifying a DBML File</span></span>
<span data-ttu-id="89f22-103">Sie können Visual Basic generieren oder C# Quellcode aus einer Database Markup Language (.dbml)-Metadatendatei.</span><span class="sxs-lookup"><span data-stu-id="89f22-103">You can generate Visual Basic or C# source code from a database markup language (.dbml) metadata file.</span></span> <span data-ttu-id="89f22-104">Dieser Ansatz bietet die Möglichkeit zur Anpassung der standardmäßigen .dbml-Datei vor dem Erzeugen des Codes für die Anwendungszuweisung.</span><span class="sxs-lookup"><span data-stu-id="89f22-104">This approach provides an opportunity to customize the default .dbml file before you generate the application mapping code.</span></span> <span data-ttu-id="89f22-105">Dies ist eine erweiterte Funktion.</span><span class="sxs-lookup"><span data-stu-id="89f22-105">This is an advanced feature.</span></span>  
  
 <span data-ttu-id="89f22-106">Dieses Verfahren umfasst die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="89f22-106">The steps in this process are as follows:</span></span>  
  
1.  <span data-ttu-id="89f22-107">Erzeugen einer .dbml-Datei.</span><span class="sxs-lookup"><span data-stu-id="89f22-107">Generate a .dbml file.</span></span>  
  
2.  <span data-ttu-id="89f22-108">Verwenden eines Editors, um die .dbml-Datei zu ändern.</span><span class="sxs-lookup"><span data-stu-id="89f22-108">Use an editor to modify the .dbml file.</span></span> <span data-ttu-id="89f22-109">Beachten Sie, die anhand der Schemadefinitionsdatei (.xsd) für die DBML-Datei validieren muss [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] DBML-Dateien.</span><span class="sxs-lookup"><span data-stu-id="89f22-109">Note that the .dbml file must validate against the schema definition (.xsd) file for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .dbml files.</span></span> <span data-ttu-id="89f22-110">Weitere Informationen finden Sie unter [Codegenerierung in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="89f22-110">For more information, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
3.  <span data-ttu-id="89f22-111">Generieren Sie die Visual Basic oder C# Quellcode.</span><span class="sxs-lookup"><span data-stu-id="89f22-111">Generate the Visual Basic or C# source code.</span></span>  
  
 <span data-ttu-id="89f22-112">In den folgenden Beispielen wird das SQLMetal-Befehlszeilentool verwendet.</span><span class="sxs-lookup"><span data-stu-id="89f22-112">The following examples use the SQLMetal command-line tool.</span></span> <span data-ttu-id="89f22-113">Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="89f22-113">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="89f22-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89f22-114">Example</span></span>  
 <span data-ttu-id="89f22-115">Im folgenden Code wird eine .dbml-Datei aus der Beispieldatenbank Northwind erzeugt.</span><span class="sxs-lookup"><span data-stu-id="89f22-115">The following code generates a .dbml file from the Northwind sample database.</span></span> <span data-ttu-id="89f22-116">Als Quelle für die Datenbank-Metadaten können Sie entweder den Namen der Datenbank oder den Namen der .mdf-Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="89f22-116">As source for the database metadata, you can use either the name of the database or the name of the .mdf file.</span></span>  
  
```  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a><span data-ttu-id="89f22-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89f22-117">Example</span></span>  
 <span data-ttu-id="89f22-118">Der folgende Code generiert Visual Basic oder C# Quellcodedatei aus einer DBML-Datei.</span><span class="sxs-lookup"><span data-stu-id="89f22-118">The following code generates Visual Basic or C# source code file from a .dbml file.</span></span>  
  
```  
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a><span data-ttu-id="89f22-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89f22-119">See also</span></span>
- [<span data-ttu-id="89f22-120">Codegenerierung in LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="89f22-120">Code Generation in LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="89f22-121">SqlMetal.exe (Tool zur Codegenerierung)</span><span class="sxs-lookup"><span data-stu-id="89f22-121">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)
- [<span data-ttu-id="89f22-122">Erstellen des Objektmodells</span><span class="sxs-lookup"><span data-stu-id="89f22-122">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
