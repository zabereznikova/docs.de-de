---
title: 'Vorgehensweise: Hinzufügen von Verweisen zu Typbibliotheken'
description: Erfahren Sie, wie Verweise auf Typbibliotheken in Visual Studio oder für die Kompilierung über die Befehlszeile hinzugefügt werden können.
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- type libraries
- COM interop, importing type library
ms.assetid: f5cfa6ba-cc25-4017-82cd-ba7391859113
ms.openlocfilehash: a3c24385c9cc7debe95aa10369b050897415bc46
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617430"
---
# <a name="how-to-add-references-to-type-libraries"></a><span data-ttu-id="3470c-103">Vorgehensweise: Hinzufügen von Verweisen zu Typbibliotheken</span><span class="sxs-lookup"><span data-stu-id="3470c-103">How to: Add References to Type Libraries</span></span>
<span data-ttu-id="3470c-104">Visual Studio generiert eine Interopassembly mit Metadaten, wenn Sie einer Typbibliothek einen Verweis hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3470c-104">Visual Studio generates an interop assembly containing metadata when you add a reference to a type library.</span></span> <span data-ttu-id="3470c-105">Wenn eine primäre Interopassembly verfügbar ist, verwendet Visual Studio die bereits vorhandene Assembly, bevor eine neue Interopassembly generiert wird.</span><span class="sxs-lookup"><span data-stu-id="3470c-105">If a primary interop assembly is available, Visual Studio uses the existing assembly before generating a new interop assembly.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-in-visual-studio"></a><span data-ttu-id="3470c-106">So fügen Sie einer Typbibliothek in Visual Studio einen Verweis hinzu</span><span class="sxs-lookup"><span data-stu-id="3470c-106">To add a reference to a type library in Visual Studio</span></span>  
  
1. <span data-ttu-id="3470c-107">Installieren Sie die COM DLL- oder EXE-Datei auf Ihrem Computer, es sei denn, die Installation wird mithilfe einer Windows Setup.exe-Datei durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="3470c-107">Install the COM DLL or EXE file on your computer, unless a Windows Setup.exe file performs the installation for you.</span></span>  
  
2. <span data-ttu-id="3470c-108">Wählen Sie **Projekt** > **Verweis hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="3470c-108">Choose **Project**, **Add Reference**.</span></span>  
  
3. <span data-ttu-id="3470c-109">Anschließend wählen Sie im Verweis-Manager **COM** aus.</span><span class="sxs-lookup"><span data-stu-id="3470c-109">In the Reference Manager, choose **COM**.</span></span>  
  
4. <span data-ttu-id="3470c-110">Wählen Sie die Typbibliothek aus der Liste aus, oder suchen Sie nach der TLB-Datei.</span><span class="sxs-lookup"><span data-stu-id="3470c-110">Select the type library from the list, or browse for the .tlb file.</span></span>  
  
5. <span data-ttu-id="3470c-111">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3470c-111">Choose **OK**.</span></span>  
  
6. <span data-ttu-id="3470c-112">Öffnen Sie im Projektmappen-Explorer das Kontextmenü für den gerade hinzugefügten Verweis, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="3470c-112">In Solution Explorer, open the shortcut menu for the reference you just added, and then choose **Properties**.</span></span>  
  
7. <span data-ttu-id="3470c-113">Vergewissern Sie sich, dass im Fenster **Eigenschaften** die Eigenschaft **Interop-Typen einbetten** auf **TRUE** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="3470c-113">In the **Properties** window, make sure that the **Embed Interop Types** property is set to **True**.</span></span> <span data-ttu-id="3470c-114">Daraufhin bettet Visual Studio Typinformationen für COM-Typen in Ihre ausführbaren Dateien ein, sodass keine primären Interopassemblys über Ihre App bereitgestellt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="3470c-114">This causes Visual Studio to embed type information for COM types in your executables, eliminating the need to deploy primary interop assemblies with your app.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3470c-115">Die Menü- und Dialogfeldoptionen können abhängig von der verwendeten Visual Studio-Version variieren.</span><span class="sxs-lookup"><span data-stu-id="3470c-115">The menu and dialog box options may vary depending on the version of Visual Studio you're using.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-for-command-line-compilation"></a><span data-ttu-id="3470c-116">So fügen Sie einer Typbibliothek einen Verweis zur Befehlszeilenkompilierung hinzu</span><span class="sxs-lookup"><span data-stu-id="3470c-116">To add a reference to a type library for command-line compilation</span></span>  
  
1. <span data-ttu-id="3470c-117">Generieren Sie eine Interopassembly wie unter [Vorgehensweise: Generieren von Interopassemblys aus Typbibliotheken](how-to-generate-interop-assemblies-from-type-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="3470c-117">Generate an interop assembly as described in [How to: Generate Interop Assemblies from Type Libraries](how-to-generate-interop-assemblies-from-type-libraries.md).</span></span>  
  
2. <span data-ttu-id="3470c-118">Verwenden Sie die Compileroption [-Link (C#-Compileroptionen)](../../csharp/language-reference/compiler-options/link-compiler-option.md) oder [-Link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) mit dem Namen der Interop-Assembly, um Typinformationen für COM-Typen in Ihre ausführbaren Dateien einzubetten.</span><span class="sxs-lookup"><span data-stu-id="3470c-118">Use the [-link (C# Compiler Options)](../../csharp/language-reference/compiler-options/link-compiler-option.md) or [-link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) compiler option with the interop assembly name to embed type information for COM types in your executables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3470c-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3470c-119">See also</span></span>

- [<span data-ttu-id="3470c-120">Importing a Type Library as an Assembly (Importieren einer Typbibliothek als Assembly)</span><span class="sxs-lookup"><span data-stu-id="3470c-120">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)
- [<span data-ttu-id="3470c-121">Verfügbarmachen von COM-Komponenten für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3470c-121">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)
- [<span data-ttu-id="3470c-122">Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3470c-122">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio</span></span>](../../standard/assembly/embed-types-visual-studio.md)
- [<span data-ttu-id="3470c-123">-link (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="3470c-123">-link (C# Compiler Options)</span></span>](../../csharp/language-reference/compiler-options/link-compiler-option.md)
- [<span data-ttu-id="3470c-124">-link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3470c-124">-link (Visual Basic)</span></span>](../../visual-basic/reference/command-line-compiler/link.md)
