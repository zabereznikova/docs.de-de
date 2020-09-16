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
# <a name="how-to-generate-the-object-model-in-visual-basic-or-c"></a><span data-ttu-id="49fb2-102">Gewusst wie: Generieren des Objektmodells in Visual Basic oder C\#</span><span class="sxs-lookup"><span data-stu-id="49fb2-102">How to: Generate the Object Model in Visual Basic or C\#</span></span>
<span data-ttu-id="49fb2-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird einer relationalen Datenbank ein Objektmodell in einer eigenen Programmiersprache zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="49fb2-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], an object model in your own programming language is mapped to a relational database.</span></span> <span data-ttu-id="49fb2-104">Zum automatischen Erstellen eines Visual Basic-oder c#-Modells aus den Metadaten einer vorhandenen Datenbank stehen zwei Tools zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="49fb2-104">Two tools are available for automatically generating a Visual Basic or C# model from the metadata of an existing database.</span></span>  
  
- <span data-ttu-id="49fb2-105">Wenn Sie Visual Studio verwenden, können Sie das objektrelationaler Designer verwenden, um ein Objektmodell zu generieren.</span><span class="sxs-lookup"><span data-stu-id="49fb2-105">If you are using Visual Studio, you can use the Object Relational Designer to generate an object model.</span></span> <span data-ttu-id="49fb2-106">Der O/R-Designer stellt eine umfangreiche Benutzeroberfläche bereit, die Sie beim Generieren eines- [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Objektmodells unterstützt.</span><span class="sxs-lookup"><span data-stu-id="49fb2-106">The O/R Designer provides a rich user interface to help you generate a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="49fb2-107">Weitere Informationen finden Sie unter [LINQ to SQL-Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span><span class="sxs-lookup"><span data-stu-id="49fb2-107">For more information see, [Linq to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>
  
- <span data-ttu-id="49fb2-108">Das SQLMetal-Befehlszeilentool.</span><span class="sxs-lookup"><span data-stu-id="49fb2-108">The SQLMetal command-line tool.</span></span> <span data-ttu-id="49fb2-109">Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="49fb2-109">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="49fb2-110">Wenn Sie nicht über eine vorhandene Datenbank verfügen, sondern diese aus einem Objektmodell erstellen möchten, erstellen Sie Ihr Objektmodell mit Ihrem Code-Editor und mit <xref:System.Data.Linq.DataContext.CreateDatabase%2A>.</span><span class="sxs-lookup"><span data-stu-id="49fb2-110">If you do not have an existing database and want to create one from an object model, you can create your object model by using your code editor and <xref:System.Data.Linq.DataContext.CreateDatabase%2A>.</span></span> <span data-ttu-id="49fb2-111">Weitere Informationen finden Sie unter Gewusst [wie: Dynamisches Erstellen einer Datenbank](how-to-dynamically-create-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="49fb2-111">For more information, see [How to: Dynamically Create a Database](how-to-dynamically-create-a-database.md).</span></span>  
  
 <span data-ttu-id="49fb2-112">In der Dokumentation für den o/r-Designer finden Sie Beispiele für das Generieren eines Visual Basic-oder c#-Objektmodells mit dem o/r-Designer.</span><span class="sxs-lookup"><span data-stu-id="49fb2-112">Documentation for the O/R Designer provides examples of how to generate a Visual Basic or C# object model by using the O/R Designer.</span></span> <span data-ttu-id="49fb2-113">Die folgenden Informationen enthalten Beispiele für die Verwendung des SQLMetal-Befehlszeilentools.</span><span class="sxs-lookup"><span data-stu-id="49fb2-113">The following information provide examples of how to use the SQLMetal command-line tool.</span></span> <span data-ttu-id="49fb2-114">Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="49fb2-114">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="49fb2-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="49fb2-115">Example</span></span>  
 <span data-ttu-id="49fb2-116">Die SQLMetal-Befehlszeile im folgenden Beispiel erzeugt Visual Basic-Code als Attribut basiertes Objektmodell der Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="49fb2-116">The SQLMetal command line shown in the following example produces Visual Basic code as the attribute-based object model of the Northwind sample database.</span></span> <span data-ttu-id="49fb2-117">Gespeicherte Prozeduren und Funktionen werden ebenfalls gerendert.</span><span class="sxs-lookup"><span data-stu-id="49fb2-117">Stored procedures and functions are also rendered.</span></span>  
  
```console  
sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions  
```  
  
## <a name="example"></a><span data-ttu-id="49fb2-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="49fb2-118">Example</span></span>  
 <span data-ttu-id="49fb2-119">Die SQLMetal-Befehlszeile im folgenden Beispiel erzeugt C#-Code als attributbasiertes Objektmodell der Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="49fb2-119">The SQLMetal command line shown in the following example produces C# code as the attribute-based object model of the Northwind sample database.</span></span> <span data-ttu-id="49fb2-120">Gespeicherte Prozeduren und Funktionen werden ebenfalls gerendert, und Tabellennamen werden automatisch pluralisiert.</span><span class="sxs-lookup"><span data-stu-id="49fb2-120">Stored procedures and functions are also rendered, and table names are automatically pluralized.</span></span>  
  
```console  
sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize  
```  
  
## <a name="see-also"></a><span data-ttu-id="49fb2-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49fb2-121">See also</span></span>

- [<span data-ttu-id="49fb2-122">Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="49fb2-122">Programming Guide</span></span>](programming-guide.md)
- [<span data-ttu-id="49fb2-123">Das LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="49fb2-123">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="49fb2-124">Lernen durch exemplarische Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="49fb2-124">Learning by Walkthroughs</span></span>](learning-by-walkthroughs.md)
- [<span data-ttu-id="49fb2-125">Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="49fb2-125">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
- [<span data-ttu-id="49fb2-126">Attributbasiertes Zuordnen</span><span class="sxs-lookup"><span data-stu-id="49fb2-126">Attribute-Based Mapping</span></span>](attribute-based-mapping.md)
- [<span data-ttu-id="49fb2-127">SqlMetal.exe (Tool zur Codegenerierung)</span><span class="sxs-lookup"><span data-stu-id="49fb2-127">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [<span data-ttu-id="49fb2-128">External Mapping (Externe Zuordnung)</span><span class="sxs-lookup"><span data-stu-id="49fb2-128">External Mapping</span></span>](external-mapping.md)
- [<span data-ttu-id="49fb2-129">Herunterladen von Beispieldatenbanken</span><span class="sxs-lookup"><span data-stu-id="49fb2-129">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="49fb2-130">Erstellen des Objektmodells</span><span class="sxs-lookup"><span data-stu-id="49fb2-130">Creating the Object Model</span></span>](creating-the-object-model.md)
