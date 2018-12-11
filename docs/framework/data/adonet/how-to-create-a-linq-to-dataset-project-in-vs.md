---
title: Erstellen eines LINQ to DataSet-Projekt In Visual Studio
ms.date: 08/15/2018
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
ms.openlocfilehash: 22763d3b9581d09d7bdda0c09480f8d36bb8e2ec
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53154033"
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a><span data-ttu-id="86553-102">Vorgehensweise: Erstellen eines LINQ to DataSet-Projekt In Visual Studio</span><span class="sxs-lookup"><span data-stu-id="86553-102">How to: Create a LINQ to DataSet project In Visual Studio</span></span>

<span data-ttu-id="86553-103">Die verschiedenen Typen von LINQ-Projekten erfordern bestimmte Assemblyverweise und importierten Namespaces (Visual Basic) oder [mit](../../../csharp/language-reference/keywords/using-directive.md) -Direktiven (c#).</span><span class="sxs-lookup"><span data-stu-id="86553-103">The different types of LINQ projects require certain assembly references and imported namespaces (Visual Basic) or [using](../../../csharp/language-reference/keywords/using-directive.md) directives (C#).</span></span> <span data-ttu-id="86553-104">Die Mindestanforderung für LINQ ist ein Verweis auf *"System.Core.dll"* und `using` -Direktive für <xref:System.Linq>.</span><span class="sxs-lookup"><span data-stu-id="86553-104">The minimum requirement for LINQ is a reference to *System.Core.dll* and a `using` directive for <xref:System.Linq>.</span></span>

<span data-ttu-id="86553-105">Diese Anforderungen werden standardmäßig bereitgestellt werden, wenn Sie ein neues C#-Konsolenanwendungsprojekt in Visual Studio 2017 erstellen.</span><span class="sxs-lookup"><span data-stu-id="86553-105">These requirements are supplied by default if you create a new C# console app project in Visual Studio 2017.</span></span> <span data-ttu-id="86553-106">Wenn Sie ein Projekt von einer früheren Version von Visual Studio aktualisieren, müssen Sie möglicherweise diese LINQ-Verweise manuell bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="86553-106">If you're upgrading a project from an earlier version of Visual Studio, you might have to supply these LINQ-related references manually.</span></span>

<span data-ttu-id="86553-107">LINQ to DataSet erfordert zwei zusätzliche Verweise auf *"System.Data.dll"* und *System.Data.DataSetExtensions.dll*.</span><span class="sxs-lookup"><span data-stu-id="86553-107">LINQ to DataSet requires two additional references to *System.Data.dll* and *System.Data.DataSetExtensions.dll*.</span></span>

> [!NOTE]
> <span data-ttu-id="86553-108">Wenn Sie über eine Eingabeaufforderung erstellen, müssen Sie manuell die LINQ-bezogenen DLLs in verweisen *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.</span><span class="sxs-lookup"><span data-stu-id="86553-108">If you're building from a command prompt, you must manually reference the LINQ-related DLLs in *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.</span></span>

## <a name="to-enable-linq-to-dataset-functionality"></a><span data-ttu-id="86553-109">So aktivieren Sie die LINQ to DataSet-Funktionalität</span><span class="sxs-lookup"><span data-stu-id="86553-109">To enable LINQ to DataSet functionality</span></span>

<span data-ttu-id="86553-110">Führen Sie diese Schritte zum Aktivieren von LINQ to DataSet-Funktionalität in einem vorhandenen Projekt.</span><span class="sxs-lookup"><span data-stu-id="86553-110">Follow these steps to enable LINQ to DataSet functionality in an existing project.</span></span>

1. <span data-ttu-id="86553-111">Fügen Sie Verweise auf **System.Core**, **"System.Data"**, und **System.Data.DataSetExtensions**.</span><span class="sxs-lookup"><span data-stu-id="86553-111">Add references to **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span>

   <span data-ttu-id="86553-112">In **Projektmappen-Explorer**, mit der rechten Maustaste auf die **Verweise** Knoten, und wählen **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="86553-112">In **Solution Explorer**, right-click on the **References** node and select **Add Reference**.</span></span> <span data-ttu-id="86553-113">In der **Verweis-Manager** wählen Sie im Dialogfeld **System.Core**, **"System.Data"**, und **System.Data.DataSetExtensions**.</span><span class="sxs-lookup"><span data-stu-id="86553-113">In the **Reference Manager** dialog box, select **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span> <span data-ttu-id="86553-114">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="86553-114">Select **OK**.</span></span>

1. <span data-ttu-id="86553-115">Hinzufügen [mit](../../../csharp/language-reference/keywords/using-directive.md) Anweisungen (oder [Imports-Anweisungen](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) in Visual Basic) für **"System.Data"** und **"System.Linq"**.</span><span class="sxs-lookup"><span data-stu-id="86553-115">Add [using](../../../csharp/language-reference/keywords/using-directive.md) directives (or [Imports statements](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) in Visual Basic) for **System.Data** and **System.Linq**.</span></span>

   ```csharp
   using System.Data;
   using System.Linq;
   ```

1. <span data-ttu-id="86553-116">Fügen Sie optional eine `using` Richtlinie (oder `Imports` Anweisung) für **System.Data.Common** oder **"System.Data.SqlClient"**, je nachdem, wie Sie eine Verbindung mit der Datenbank herstellen.</span><span class="sxs-lookup"><span data-stu-id="86553-116">Optionally, add a `using` directive (or `Imports` statement) for **System.Data.Common** or **System.Data.SqlClient**, depending on how you connect to the database.</span></span>

## <a name="see-also"></a><span data-ttu-id="86553-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86553-117">See also</span></span>

- [<span data-ttu-id="86553-118">Erste Schritte mit LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="86553-118">Get started with LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)
