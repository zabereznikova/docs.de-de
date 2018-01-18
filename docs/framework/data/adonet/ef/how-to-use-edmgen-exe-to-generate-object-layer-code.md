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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: f7be6ce53b103accb48dcf75d4a0583a351eba0e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a><span data-ttu-id="c1396-102">Gewusst wie: Generieren von Objektebenencode mit "EdmGen.exe"</span><span class="sxs-lookup"><span data-stu-id="c1396-102">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>
<span data-ttu-id="c1396-103">In diesem Thema zeigt, wie die [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) Tool zum Generieren von Objektebenencode auf Grundlage der CSDL-Datei.</span><span class="sxs-lookup"><span data-stu-id="c1396-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) tool to generate object-layer code  based on the .csdl file.</span></span>  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a><span data-ttu-id="c1396-104">So generieren Sie mithilfe von EdmGen.exe den Objektebenencode für das Modell "School" für ein Visual Basic-Projekt</span><span class="sxs-lookup"><span data-stu-id="c1396-104">To generate object-layer code for the School model for a Visual Basic project using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="c1396-105">Erstellen der Datenbank "School".</span><span class="sxs-lookup"><span data-stu-id="c1396-105">Create the School database.</span></span> <span data-ttu-id="c1396-106">Weitere Informationen finden Sie unter [Erstellen der Beispieldatenbank "School"](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span><span class="sxs-lookup"><span data-stu-id="c1396-106">For more information, see [Creating the School Sample Database](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span></span>  
  
2.  <span data-ttu-id="c1396-107">Generieren Sie das Modell "School", oder verwenden Sie die Datei School.csdl.</span><span class="sxs-lookup"><span data-stu-id="c1396-107">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="c1396-108">Weitere Informationen finden Sie unter [Vorgehensweise: verwenden EdmGen.exe generiert die Modell- und Zuordnen von Dateien](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="c1396-108">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="c1396-109">Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:</span><span class="sxs-lookup"><span data-stu-id="c1396-109">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a><span data-ttu-id="c1396-110">So generieren Sie mithilfe von EdmGen.exe den Objektebenencode für das Modell "School" für ein C#-Projekt</span><span class="sxs-lookup"><span data-stu-id="c1396-110">To generate object-layer code for the School model for a C# project using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="c1396-111">Erstellen der Datenbank "School".</span><span class="sxs-lookup"><span data-stu-id="c1396-111">Create the School database.</span></span> <span data-ttu-id="c1396-112">Weitere Informationen finden Sie unter [Erstellen der Beispieldatenbank "School"](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span><span class="sxs-lookup"><span data-stu-id="c1396-112">For more information, see [Creating the School Sample Database](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span></span>  
  
2.  <span data-ttu-id="c1396-113">Generieren Sie das Modell "School", oder verwenden Sie die Datei School.csdl.</span><span class="sxs-lookup"><span data-stu-id="c1396-113">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="c1396-114">Weitere Informationen finden Sie unter [Vorgehensweise: verwenden EdmGen.exe generiert die Modell- und Zuordnen von Dateien](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="c1396-114">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="c1396-115">Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:</span><span class="sxs-lookup"><span data-stu-id="c1396-115">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c1396-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1396-116">See Also</span></span>  
 [<span data-ttu-id="c1396-117">Modellieren und Zuordnen</span><span class="sxs-lookup"><span data-stu-id="c1396-117">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)  
 [<span data-ttu-id="c1396-118">Vorgehensweise: Manuelles Konfigurieren ein Entity Framework-Projekts</span><span class="sxs-lookup"><span data-stu-id="c1396-118">How to: Manually Configure an Entity Framework Project</span></span>](http://msdn.microsoft.com/en-us/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)  
 [<span data-ttu-id="c1396-119">ADO.NET Entity Data Model Tools (ADO.NET Entity Data Model-Tools)</span><span class="sxs-lookup"><span data-stu-id="c1396-119">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)  
 [<span data-ttu-id="c1396-120">Vorgehensweise: Vorabgenerieren von Sichten, um die Abfrageleistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="c1396-120">How to: Pre-Generate Views to Improve Query Performance</span></span>](http://msdn.microsoft.com/en-us/b18a9d16-e10b-4043-ba91-b632f85a2579)  
 [<span data-ttu-id="c1396-121">Vorgehensweise: Generieren von Modell- und Zuordnungsdateien mit „EdmGen.exe“</span><span class="sxs-lookup"><span data-stu-id="c1396-121">How to: Use EdmGen.exe to Generate the Model and Mapping Files</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
