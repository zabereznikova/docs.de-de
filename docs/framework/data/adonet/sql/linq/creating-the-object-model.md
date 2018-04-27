---
title: Erstellen des Objektmodells
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 27afce86-9b1d-45fb-8e0b-636bf671a236
caps.latest.revision: 3
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 8686b46545699ab8c07b5d3b5f3ea26080261036
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="creating-the-object-model"></a><span data-ttu-id="f5705-102">Erstellen des Objektmodells</span><span class="sxs-lookup"><span data-stu-id="f5705-102">Creating the Object Model</span></span>
<span data-ttu-id="f5705-103">Sie können Ihr Objektmodell aus einer vorhandenen Datenbank erstellen und dieses in seinem Standardzustand verwenden.</span><span class="sxs-lookup"><span data-stu-id="f5705-103">You can create your object model from an existing database and use the model in its default state.</span></span> <span data-ttu-id="f5705-104">Sie können auch zahlreiche Aspekte des Modells und seines Verhaltens anpassen.</span><span class="sxs-lookup"><span data-stu-id="f5705-104">You can also customize many aspects of the model and its behavior.</span></span>  
  
 <span data-ttu-id="f5705-105">Wenn Sie Visual Studio verwenden, können Sie mithilfe der [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] zum Erstellen des Objektmodells.</span><span class="sxs-lookup"><span data-stu-id="f5705-105">If you are using Visual Studio, you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create your object model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f5705-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f5705-106">In This Section</span></span>  
 [<span data-ttu-id="f5705-107">Gewusst wie: Generieren des Objektmodells in Visual Basic oder C#</span><span class="sxs-lookup"><span data-stu-id="f5705-107">How to: Generate the Object Model in Visual Basic or C#</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)  
 <span data-ttu-id="f5705-108">Beschreibt die Verwendung des SQLMetal-Befehlszeilentools.</span><span class="sxs-lookup"><span data-stu-id="f5705-108">Describes how to use the SQLMetal command-line tool.</span></span> <span data-ttu-id="f5705-109">Bietet außerdem einen Link zu der [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] für Visual Studio-Benutzer</span><span class="sxs-lookup"><span data-stu-id="f5705-109">Also provides a link to the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] for Visual Studio users</span></span>  
  
 [<span data-ttu-id="f5705-110">Vorgehensweise: Generieren des Objektmodells als externe Datei</span><span class="sxs-lookup"><span data-stu-id="f5705-110">How to: Generate the Object Model as an External File</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-as-an-external-file.md)  
 <span data-ttu-id="f5705-111">Beschreibt, wie anstelle der attributbasierten Zuordnung eine externe Zuordnungsdatei generiert wird.</span><span class="sxs-lookup"><span data-stu-id="f5705-111">Describes how to generate an external mapping file instead of using attribute-based mapping.</span></span>  
  
 [<span data-ttu-id="f5705-112">Vorgehensweise: Generieren von angepasstem Code durch Verändern einer DBML-Datei</span><span class="sxs-lookup"><span data-stu-id="f5705-112">How to: Generate Customized Code by Modifying a DBML File</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-customized-code-by-modifying-a-dbml-file.md)  
 <span data-ttu-id="f5705-113">Beschreibt, wie Visual Basic- oder C#-Code aus einer DBML-Metadatendatei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="f5705-113">Describes how to generate Visual Basic or C# code from a DBML metadata file.</span></span>  
  
 [<span data-ttu-id="f5705-114">Vorgehensweise: Überprüfen von DBML- und externen Zuordnungsdateien</span><span class="sxs-lookup"><span data-stu-id="f5705-114">How to: Validate DBML and External Mapping Files</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-validate-dbml-and-external-mapping-files.md)  
 <span data-ttu-id="f5705-115">Beschreibt, wie Zuordnungsdateien überprüft werden, die Sie geändert (erweitert) haben.</span><span class="sxs-lookup"><span data-stu-id="f5705-115">Describes how to validate mapping files that you have modified (advanced).</span></span>  
  
 [<span data-ttu-id="f5705-116">Vorgehensweise: Aktivieren der Serialisierbarkeit von Entitäten</span><span class="sxs-lookup"><span data-stu-id="f5705-116">How to: Make Entities Serializable</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-make-entities-serializable.md)  
 <span data-ttu-id="f5705-117">Beschreibt, wie entsprechende Attribute hinzugefügt werden, um die Serialisierbarkeit von Entitäten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f5705-117">Describes how to add appropriate attributes to make entities serializable.</span></span>  
  
 [<span data-ttu-id="f5705-118">Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="f5705-118">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)  
 <span data-ttu-id="f5705-119">Beschreibt die Verwendung des Code-Editors zum Schreiben Ihres eigenen Zuordnungscodes oder zum Anpassen von Code, der automatisch generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="f5705-119">Describes how to use the code editor to write your own mapping code, or customize code that has been autogenerated.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f5705-120">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="f5705-120">Related Sections</span></span>  
 [<span data-ttu-id="f5705-121">Das LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="f5705-121">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 <span data-ttu-id="f5705-122">Enthält Informationen über die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] -Objektmodell.</span><span class="sxs-lookup"><span data-stu-id="f5705-122">Provides details about the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="f5705-123">Typische Schritte bei der Verwendung von LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f5705-123">Typical Steps for Using LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md)  
 <span data-ttu-id="f5705-124">Erläutert die typischen Schritte zur Implementierung einer [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="f5705-124">Explains the typical steps that you follow to implement a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] application.</span></span>
