---
title: 'Vorgehensweise: Mithilfe von EdmGen.exe um Objektebenencode zu generieren.'
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: 63542866441cb347362e64b08b5de11bde19d50b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654567"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a><span data-ttu-id="3a582-102">Vorgehensweise: Mithilfe von EdmGen.exe um Objektebenencode zu generieren.</span><span class="sxs-lookup"><span data-stu-id="3a582-102">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>
<span data-ttu-id="3a582-103">In diesem Thema wird gezeigt, wie Sie mit der [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) Tool zum Generieren von Objektebenencode basierend auf der die CSDL-Datei.</span><span class="sxs-lookup"><span data-stu-id="3a582-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) tool to generate object-layer code  based on the .csdl file.</span></span>  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a><span data-ttu-id="3a582-104">So generieren Sie mithilfe von EdmGen.exe den Objektebenencode für das Modell "School" für ein Visual Basic-Projekt</span><span class="sxs-lookup"><span data-stu-id="3a582-104">To generate object-layer code for the School model for a Visual Basic project using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="3a582-105">Erstellen der Datenbank "School".</span><span class="sxs-lookup"><span data-stu-id="3a582-105">Create the School database.</span></span> <span data-ttu-id="3a582-106">Weitere Informationen finden Sie unter [Erstellen der Beispieldatenbank "School"](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span><span class="sxs-lookup"><span data-stu-id="3a582-106">For more information, see [Creating the School Sample Database](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span></span>  
  
2.  <span data-ttu-id="3a582-107">Generieren Sie das Modell "School", oder verwenden Sie die Datei School.csdl.</span><span class="sxs-lookup"><span data-stu-id="3a582-107">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="3a582-108">Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden Sie zum Generieren von Modell- und Zuordnungsdateien EdmGen.exe](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="3a582-108">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="3a582-109">Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:</span><span class="sxs-lookup"><span data-stu-id="3a582-109">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a><span data-ttu-id="3a582-110">So generieren Sie mithilfe von EdmGen.exe den Objektebenencode für das Modell "School" für ein C#-Projekt</span><span class="sxs-lookup"><span data-stu-id="3a582-110">To generate object-layer code for the School model for a C# project using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="3a582-111">Erstellen der Datenbank "School".</span><span class="sxs-lookup"><span data-stu-id="3a582-111">Create the School database.</span></span> <span data-ttu-id="3a582-112">Weitere Informationen finden Sie unter [Erstellen der Beispieldatenbank "School"](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span><span class="sxs-lookup"><span data-stu-id="3a582-112">For more information, see [Creating the School Sample Database](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span></span>  
  
2.  <span data-ttu-id="3a582-113">Generieren Sie das Modell "School", oder verwenden Sie die Datei School.csdl.</span><span class="sxs-lookup"><span data-stu-id="3a582-113">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="3a582-114">Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden Sie zum Generieren von Modell- und Zuordnungsdateien EdmGen.exe](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="3a582-114">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="3a582-115">Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:</span><span class="sxs-lookup"><span data-stu-id="3a582-115">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3a582-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a582-116">See also</span></span>
- [<span data-ttu-id="3a582-117">Modellieren und Zuordnen</span><span class="sxs-lookup"><span data-stu-id="3a582-117">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [<span data-ttu-id="3a582-118">Vorgehensweise: Manuelles Konfigurieren eines Entity Framework-Projekts</span><span class="sxs-lookup"><span data-stu-id="3a582-118">How to: Manually Configure an Entity Framework Project</span></span>](https://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)
- [<span data-ttu-id="3a582-119">ADO.NET Entity Data Model Tools (ADO.NET Entity Data Model-Tools)</span><span class="sxs-lookup"><span data-stu-id="3a582-119">ADO.NET Entity Data Model  Tools</span></span>](https://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)
- [<span data-ttu-id="3a582-120">Vorgehensweise: Vorgenerieren von Ansichten zur Verbesserung der Abfrageleistung</span><span class="sxs-lookup"><span data-stu-id="3a582-120">How to: Pre-Generate Views to Improve Query Performance</span></span>](https://msdn.microsoft.com/library/b18a9d16-e10b-4043-ba91-b632f85a2579)
- [<span data-ttu-id="3a582-121">Vorgehensweise: Verwenden von EdmGen.exe zum Generieren von Modell- und Zuordnungsdateien</span><span class="sxs-lookup"><span data-stu-id="3a582-121">How to: Use EdmGen.exe to Generate the Model and Mapping Files</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
