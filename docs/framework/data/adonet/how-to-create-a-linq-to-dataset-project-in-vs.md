---
title: Erstellen eines LINQ to DataSet Projekts in Visual Studio
ms.date: 08/15/2018
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
ms.openlocfilehash: 91032766248b11e51b90aa788b1c64c140347c25
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802026"
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a><span data-ttu-id="b3941-102">Vorgehensweise: Erstellen eines LINQ to DataSet Projekts in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b3941-102">How to: Create a LINQ to DataSet project in Visual Studio</span></span>

<span data-ttu-id="b3941-103">Die unterschiedlichen Arten von LINQ-Projekten benötigen bestimmte Assemblyverweise und importierte Namespaces (Visual Basic) oder [using](../../../csharp/language-reference/keywords/using-directive.md)-Anweisungen (C#).</span><span class="sxs-lookup"><span data-stu-id="b3941-103">The different types of LINQ projects require certain assembly references and imported namespaces (Visual Basic) or [using](../../../csharp/language-reference/keywords/using-directive.md) directives (C#).</span></span> <span data-ttu-id="b3941-104">Die Mindestanforderung für LINQ ist ein Verweis auf " *System. Core. dll* " und eine `using`-Direktive für <xref:System.Linq>.</span><span class="sxs-lookup"><span data-stu-id="b3941-104">The minimum requirement for LINQ is a reference to *System.Core.dll* and a `using` directive for <xref:System.Linq>.</span></span>

<span data-ttu-id="b3941-105">Diese Anforderungen werden standardmäßig bereitgestellt, wenn Sie ein C# neues Konsolen-App-Projekt in Visual Studio 2017 oder einer neueren Version erstellen.</span><span class="sxs-lookup"><span data-stu-id="b3941-105">These requirements are supplied by default if you create a new C# console app project in Visual Studio 2017 or a later version.</span></span> <span data-ttu-id="b3941-106">Wenn Sie ein Projekt von einer früheren Version von Visual Studio aktualisieren, müssen Sie diese LINQ-bezogenen Verweise möglicherweise manuell angeben.</span><span class="sxs-lookup"><span data-stu-id="b3941-106">If you're upgrading a project from an earlier version of Visual Studio, you might have to supply these LINQ-related references manually.</span></span>

<span data-ttu-id="b3941-107">LINQ to DataSet erfordert zwei zusätzliche Verweise auf *System. Data. dll* und *System. Data. DataSetExtensions. dll*.</span><span class="sxs-lookup"><span data-stu-id="b3941-107">LINQ to DataSet requires two additional references to *System.Data.dll* and *System.Data.DataSetExtensions.dll*.</span></span>

> [!NOTE]
> <span data-ttu-id="b3941-108">Wenn Sie von einer Eingabeaufforderung aus erstellen, müssen Sie manuell auf die LINQ-bezogenen DLLs in *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*verweisen.</span><span class="sxs-lookup"><span data-stu-id="b3941-108">If you're building from a command prompt, you must manually reference the LINQ-related DLLs in *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.</span></span>

## <a name="to-enable-linq-to-dataset-functionality"></a><span data-ttu-id="b3941-109">So aktivieren Sie die LINQ to DataSet-Funktionalität</span><span class="sxs-lookup"><span data-stu-id="b3941-109">To enable LINQ to DataSet functionality</span></span>

<span data-ttu-id="b3941-110">Führen Sie die folgenden Schritte aus, um LINQ to DataSet Funktionalität in einem vorhandenen-Projekt zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b3941-110">Follow these steps to enable LINQ to DataSet functionality in an existing project.</span></span>

1. <span data-ttu-id="b3941-111">Fügen Sie Verweise auf **System. Core**, **System. Data**und **System. Data. DataSetExtensions**hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3941-111">Add references to **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span>

   <span data-ttu-id="b3941-112">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf den Knoten **Verweise** , und wählen Sie **Verweis hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="b3941-112">In **Solution Explorer**, right-click on the **References** node and select **Add Reference**.</span></span> <span data-ttu-id="b3941-113">Wählen Sie im Dialogfeld **Verweis-Manager** die Option **System. Core**, **System. Data**und **System. Data. DataSetExtensions**aus.</span><span class="sxs-lookup"><span data-stu-id="b3941-113">In the **Reference Manager** dialog box, select **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span> <span data-ttu-id="b3941-114">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3941-114">Select **OK**.</span></span>

1. <span data-ttu-id="b3941-115">Fügen Sie [using](../../../csharp/language-reference/keywords/using-directive.md) -Direktiven (oder [Imports-Anweisungen](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) in Visual Basic) für **System. Data** und **System. Linq**hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3941-115">Add [using](../../../csharp/language-reference/keywords/using-directive.md) directives (or [Imports statements](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) in Visual Basic) for **System.Data** and **System.Linq**.</span></span>

   ```csharp
   using System.Data;
   using System.Linq;
   ```

1. <span data-ttu-id="b3941-116">Fügen Sie optional eine `using`-Direktive (oder `Imports`-Anweisung) für " **System. Data. Common** " oder " **System. Data. SqlClient**" hinzu, je nachdem, wie Sie eine Verbindung mit der Datenbank herstellen.</span><span class="sxs-lookup"><span data-stu-id="b3941-116">Optionally, add a `using` directive (or `Imports` statement) for **System.Data.Common** or **System.Data.SqlClient**, depending on how you connect to the database.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3941-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3941-117">See also</span></span>

- [<span data-ttu-id="b3941-118">Beginnen Sie mit LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="b3941-118">Get started with LINQ to DataSet</span></span>](getting-started-linq-to-dataset.md)
