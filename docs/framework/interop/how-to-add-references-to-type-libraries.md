---
title: "Gewusst wie: Hinzufügen von Verweisen zu Typbibliotheken"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- type libraries
- COM interop, importing type library
ms.assetid: f5cfa6ba-cc25-4017-82cd-ba7391859113
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4e80c4bf5142a9bbbd2b7f75d67553db73f0ff22
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-references-to-type-libraries"></a><span data-ttu-id="4f7c6-102">Gewusst wie: Hinzufügen von Verweisen zu Typbibliotheken</span><span class="sxs-lookup"><span data-stu-id="4f7c6-102">How to: Add References to Type Libraries</span></span>
<span data-ttu-id="4f7c6-103">Visual Studio generiert eine Interopassembly mit Metadaten, wenn Sie einer Typbibliothek einen Verweis hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4f7c6-103">Visual Studio generates an interop assembly containing metadata when you add a reference to a type library.</span></span> <span data-ttu-id="4f7c6-104">Wenn eine primäre Interopassembly verfügbar ist, verwendet Visual Studio die bereits vorhandene Assembly, bevor eine neue Interopassembly generiert wird.</span><span class="sxs-lookup"><span data-stu-id="4f7c6-104">If a primary interop assembly is available, Visual Studio uses the existing assembly before generating a new interop assembly.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-in-visual-studio"></a><span data-ttu-id="4f7c6-105">So fügen Sie einer Typbibliothek in Visual Studio einen Verweis hinzu</span><span class="sxs-lookup"><span data-stu-id="4f7c6-105">To add a reference to a type library in Visual Studio</span></span>  
  
1.  <span data-ttu-id="4f7c6-106">Installieren Sie die COM DLL- oder EXE-Datei auf Ihrem Computer, es sei denn, die Installation wird mithilfe einer Windows Setup.exe-Datei durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="4f7c6-106">Install the COM DLL or EXE file on your computer, unless a Windows Setup.exe file performs the installation for you.</span></span>  
  
2.  <span data-ttu-id="4f7c6-107">Wählen Sie **Projekt** > **Verweis hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="4f7c6-107">Choose **Project**, **Add Reference**.</span></span>  
  
3.  <span data-ttu-id="4f7c6-108">Anschließend wählen Sie im Verweis-Manager **COM** aus.</span><span class="sxs-lookup"><span data-stu-id="4f7c6-108">In the Reference Manager, choose **COM**.</span></span>  
  
4.  <span data-ttu-id="4f7c6-109">Wählen Sie die Typbibliothek aus der Liste aus, oder suchen Sie nach der TLB-Datei.</span><span class="sxs-lookup"><span data-stu-id="4f7c6-109">Select the type library from the list, or browse for the .tlb file.</span></span>  
  
5.  <span data-ttu-id="4f7c6-110">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f7c6-110">Choose **OK**.</span></span>  
  
6.  <span data-ttu-id="4f7c6-111">Öffnen Sie im Projektmappen-Explorer das Kontextmenü für den gerade hinzugefügten Verweis, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="4f7c6-111">In Solution Explorer, open the shortcut menu for the reference you just added, and then choose **Properties**.</span></span>  
  
7.  <span data-ttu-id="4f7c6-112">Vergewissern Sie sich, dass im Fenster **Eigenschaften** die Eigenschaft **Interop-Typen einbetten** auf **TRUE** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4f7c6-112">In the **Properties** window, make sure that the **Embed Interop Types** property is set to **True**.</span></span> <span data-ttu-id="4f7c6-113">Daraufhin bettet Visual Studio Typinformationen für COM-Typen in Ihre ausführbaren Dateien ein, sodass keine primären Interopassemblys über Ihre App bereitgestellt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="4f7c6-113">This causes Visual Studio to embed type information for COM types in your executables, eliminating the need to deploy primary interop assemblies with your app.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f7c6-114">Die Menü- und Dialogfeldoptionen können abhängig von der verwendeten Visual Studio-Version variieren.</span><span class="sxs-lookup"><span data-stu-id="4f7c6-114">The menu and dialog box options may vary depending on the version of Visual Studio you're using.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-for-command-line-compilation"></a><span data-ttu-id="4f7c6-115">So fügen Sie einer Typbibliothek einen Verweis zur Befehlszeilenkompilierung hinzu</span><span class="sxs-lookup"><span data-stu-id="4f7c6-115">To add a reference to a type library for command-line compilation</span></span>  
  
1.  <span data-ttu-id="4f7c6-116">Generieren Sie, wie in [Vorgehensweise: Generieren von Interop-Assemblys aus Typbibliotheken](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md) beschrieben, eine Interop-Assembly.</span><span class="sxs-lookup"><span data-stu-id="4f7c6-116">Generate an interop assembly as described in [How to: Generate Interop Assemblies from Type Libraries](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md).</span></span>  
  
2.  <span data-ttu-id="4f7c6-117">Verwenden Sie die Compileroption [/link (C#-Compileroptionen)](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md) oder [/link (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/link.md) mit dem Namen der Interop-Assembly, um Typinformationen für COM-Typen in Ihre ausführbaren Dateien einzubetten.</span><span class="sxs-lookup"><span data-stu-id="4f7c6-117">Use the [/link (C# Compiler Options)](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md) or [/link (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/link.md) compiler option with the interop assembly name to embed type information for COM types in your executables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f7c6-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f7c6-118">See Also</span></span>  
 [<span data-ttu-id="4f7c6-119">Importing a Type Library as an Assembly (Importieren einer Typbibliothek als Assembly)</span><span class="sxs-lookup"><span data-stu-id="4f7c6-119">Importing a Type Library as an Assembly</span></span>](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)  
 [<span data-ttu-id="4f7c6-120">Verfügbarmachen von COM-Komponenten für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4f7c6-120">Exposing COM Components to the .NET Framework</span></span>](../../../docs/framework/interop/exposing-com-components.md)  
 [<span data-ttu-id="4f7c6-121">Exemplarische Vorgehensweise: Einbetten von Typinformationen aus Microsoft Office-Assemblys</span><span class="sxs-lookup"><span data-stu-id="4f7c6-121">Walkthrough: Embedding Type Information from Microsoft Office Assemblies</span></span>](http://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3)  
 [<span data-ttu-id="4f7c6-122">Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys</span><span class="sxs-lookup"><span data-stu-id="4f7c6-122">Walkthrough: Embedding Types from Managed Assemblies</span></span>](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)  
 [<span data-ttu-id="4f7c6-123">-link (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="4f7c6-123">/link (C# Compiler Options)</span></span>](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md)  
 [<span data-ttu-id="4f7c6-124">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f7c6-124">/link (Visual Basic)</span></span>](~/docs/visual-basic/reference/command-line-compiler/link.md)
