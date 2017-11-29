---
title: 'Gewusst wie: Generieren von Objektebenencode mit "EdmGen.exe"'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 4abb20ca2ff26fa4e2105bae87274028592aa510
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a><span data-ttu-id="1264e-102">Gewusst wie: Generieren von Objektebenencode mit "EdmGen.exe"</span><span class="sxs-lookup"><span data-stu-id="1264e-102">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>
<span data-ttu-id="1264e-103">In diesem Thema zeigt, wie die [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) Tool zum Generieren von Objektebenencode auf Grundlage der CSDL-Datei.</span><span class="sxs-lookup"><span data-stu-id="1264e-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) tool to generate object-layer code  based on the .csdl file.</span></span>  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a><span data-ttu-id="1264e-104">So generieren Sie mithilfe von EdmGen.exe den Objektebenencode für das Modell "School" für ein Visual Basic-Projekt</span><span class="sxs-lookup"><span data-stu-id="1264e-104">To generate object-layer code for the School model for a Visual Basic project using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="1264e-105">Erstellen der Datenbank "School".</span><span class="sxs-lookup"><span data-stu-id="1264e-105">Create the School database.</span></span> <span data-ttu-id="1264e-106">Weitere Informationen finden Sie unter [Erstellen der Beispieldatenbank "School"](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span><span class="sxs-lookup"><span data-stu-id="1264e-106">For more information, see [Creating the School Sample Database](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span></span>  
  
2.  <span data-ttu-id="1264e-107">Generieren Sie das Modell "School", oder verwenden Sie die Datei School.csdl.</span><span class="sxs-lookup"><span data-stu-id="1264e-107">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="1264e-108">Weitere Informationen finden Sie unter [Vorgehensweise: verwenden EdmGen.exe generiert die Modell- und Zuordnen von Dateien](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="1264e-108">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="1264e-109">Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:</span><span class="sxs-lookup"><span data-stu-id="1264e-109">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a><span data-ttu-id="1264e-110">So generieren Sie mithilfe von EdmGen.exe den Objektebenencode für das Modell "School" für ein C#-Projekt</span><span class="sxs-lookup"><span data-stu-id="1264e-110">To generate object-layer code for the School model for a C# project using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="1264e-111">Erstellen der Datenbank "School".</span><span class="sxs-lookup"><span data-stu-id="1264e-111">Create the School database.</span></span> <span data-ttu-id="1264e-112">Weitere Informationen finden Sie unter [Erstellen der Beispieldatenbank "School"](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span><span class="sxs-lookup"><span data-stu-id="1264e-112">For more information, see [Creating the School Sample Database](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span></span>  
  
2.  <span data-ttu-id="1264e-113">Generieren Sie das Modell "School", oder verwenden Sie die Datei School.csdl.</span><span class="sxs-lookup"><span data-stu-id="1264e-113">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="1264e-114">Weitere Informationen finden Sie unter [Vorgehensweise: verwenden EdmGen.exe generiert die Modell- und Zuordnen von Dateien](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="1264e-114">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="1264e-115">Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:</span><span class="sxs-lookup"><span data-stu-id="1264e-115">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1264e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1264e-116">See Also</span></span>  
 [<span data-ttu-id="1264e-117">Modellieren und zuordnen</span><span class="sxs-lookup"><span data-stu-id="1264e-117">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)  
 [<span data-ttu-id="1264e-118">Vorgehensweise: Manuelles Konfigurieren ein Entity Framework-Projekts</span><span class="sxs-lookup"><span data-stu-id="1264e-118">How to: Manually Configure an Entity Framework Project</span></span>](http://msdn.microsoft.com/en-us/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)  
 [<span data-ttu-id="1264e-119">ADO.NET Entity Data Model Tools (ADO.NET Entity Data Model-Tools)</span><span class="sxs-lookup"><span data-stu-id="1264e-119">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)  
 [<span data-ttu-id="1264e-120">Vorgehensweise: Vorabgenerieren von Sichten, um die Abfrageleistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="1264e-120">How to: Pre-Generate Views to Improve Query Performance</span></span>](http://msdn.microsoft.com/en-us/b18a9d16-e10b-4043-ba91-b632f85a2579)  
 [<span data-ttu-id="1264e-121">Vorgehensweise: Verwenden Sie EdmGen.exe, um die Modell- und Zuordnungsdateien zu generieren.</span><span class="sxs-lookup"><span data-stu-id="1264e-121">How to: Use EdmGen.exe to Generate the Model and Mapping Files</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
