---
title: 'Vorgehensweise: Generieren von angepasstem Code durch Verändern einer DBML-Datei'
ms.date: 03/30/2017
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
ms.openlocfilehash: 6619f4b8c0a47b36a0b84fa21bab4109d26ef895
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002946"
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a><span data-ttu-id="9cbda-102">Vorgehensweise: Generieren von angepasstem Code durch Verändern einer DBML-Datei</span><span class="sxs-lookup"><span data-stu-id="9cbda-102">How to: Generate Customized Code by Modifying a DBML File</span></span>
<span data-ttu-id="9cbda-103">Sie können Visual Basic oder C# Quellcode aus einer DBML-Metadatendatei (Database Markup Language) generieren.</span><span class="sxs-lookup"><span data-stu-id="9cbda-103">You can generate Visual Basic or C# source code from a database markup language (.dbml) metadata file.</span></span> <span data-ttu-id="9cbda-104">Dieser Ansatz bietet die Möglichkeit zur Anpassung der standardmäßigen .dbml-Datei vor dem Erzeugen des Codes für die Anwendungszuweisung.</span><span class="sxs-lookup"><span data-stu-id="9cbda-104">This approach provides an opportunity to customize the default .dbml file before you generate the application mapping code.</span></span> <span data-ttu-id="9cbda-105">Dies ist eine erweiterte Funktion.</span><span class="sxs-lookup"><span data-stu-id="9cbda-105">This is an advanced feature.</span></span>  
  
 <span data-ttu-id="9cbda-106">Dieses Verfahren umfasst die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="9cbda-106">The steps in this process are as follows:</span></span>  
  
1. <span data-ttu-id="9cbda-107">Erzeugen einer .dbml-Datei.</span><span class="sxs-lookup"><span data-stu-id="9cbda-107">Generate a .dbml file.</span></span>  
  
2. <span data-ttu-id="9cbda-108">Verwenden eines Editors, um die .dbml-Datei zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9cbda-108">Use an editor to modify the .dbml file.</span></span> <span data-ttu-id="9cbda-109">Beachten Sie, dass die. dbml-Datei anhand der Schema Definitionsdatei (. xsd) für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. dbml-Dateien überprüft werden muss.</span><span class="sxs-lookup"><span data-stu-id="9cbda-109">Note that the .dbml file must validate against the schema definition (.xsd) file for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .dbml files.</span></span> <span data-ttu-id="9cbda-110">Weitere Informationen finden Sie unter [Code Generierung in LINQ to SQL](code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="9cbda-110">For more information, see [Code Generation in LINQ to SQL](code-generation-in-linq-to-sql.md).</span></span>  
  
3. <span data-ttu-id="9cbda-111">Generieren Sie die Visual Basic C# oder den Quellcode.</span><span class="sxs-lookup"><span data-stu-id="9cbda-111">Generate the Visual Basic or C# source code.</span></span>  
  
 <span data-ttu-id="9cbda-112">In den folgenden Beispielen wird das SQLMetal-Befehlszeilentool verwendet.</span><span class="sxs-lookup"><span data-stu-id="9cbda-112">The following examples use the SQLMetal command-line tool.</span></span> <span data-ttu-id="9cbda-113">Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="9cbda-113">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9cbda-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9cbda-114">Example</span></span>  
 <span data-ttu-id="9cbda-115">Im folgenden Code wird eine .dbml-Datei aus der Beispieldatenbank Northwind erzeugt.</span><span class="sxs-lookup"><span data-stu-id="9cbda-115">The following code generates a .dbml file from the Northwind sample database.</span></span> <span data-ttu-id="9cbda-116">Als Quelle für die Datenbank-Metadaten können Sie entweder den Namen der Datenbank oder den Namen der .mdf-Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="9cbda-116">As source for the database metadata, you can use either the name of the database or the name of the .mdf file.</span></span>  
  
```console  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a><span data-ttu-id="9cbda-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9cbda-117">Example</span></span>  
 <span data-ttu-id="9cbda-118">Der folgende Code generiert Visual Basic oder C# Quell Code Datei aus einer DBML-Datei.</span><span class="sxs-lookup"><span data-stu-id="9cbda-118">The following code generates Visual Basic or C# source code file from a .dbml file.</span></span>  
  
```console
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a><span data-ttu-id="9cbda-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9cbda-119">See also</span></span>

- [<span data-ttu-id="9cbda-120">Codegenerierung in LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="9cbda-120">Code Generation in LINQ to SQL</span></span>](code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="9cbda-121">SqlMetal.exe (Tool zur Codegenerierung)</span><span class="sxs-lookup"><span data-stu-id="9cbda-121">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [<span data-ttu-id="9cbda-122">Erstellen des Objektmodells</span><span class="sxs-lookup"><span data-stu-id="9cbda-122">Creating the Object Model</span></span>](creating-the-object-model.md)
