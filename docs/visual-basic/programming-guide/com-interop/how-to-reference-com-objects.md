---
title: 'Gewusst wie: Verweisen auf COM-Objekte aus Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
ms.openlocfilehash: 2e2cbac6fad5e1686b7383c44619b8c6f5326483
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396803"
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a><span data-ttu-id="3059e-102">Gewusst wie: Verweisen auf COM-Objekte aus Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3059e-102">How to: Reference COM Objects from Visual Basic</span></span>
<span data-ttu-id="3059e-103">In Visual Basic erfordert das Hinzufügen von Verweisen auf COM-Objekte, die über Typbibliotheken verfügen, das Erstellen einer Interop-Assembly für die com-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="3059e-103">In Visual Basic, adding references to COM objects that have type libraries requires the creation of an interop assembly for the COM library.</span></span> <span data-ttu-id="3059e-104">Verweise auf die Member des COM-Objekts werden an die Interop-Assembly weitergeleitet und dann an das tatsächliche com-Objekt weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="3059e-104">References to the members of the COM object are routed to the interop assembly and then forwarded to the actual COM object.</span></span> <span data-ttu-id="3059e-105">Antworten aus dem COM-Objekt werden an die Interop-Assembly weitergeleitet und an Ihre .NET Framework Anwendung weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="3059e-105">Responses from the COM object are routed to the interop assembly and forwarded to your .NET Framework application.</span></span>  
  
 <span data-ttu-id="3059e-106">Sie können auf ein COM-Objekt verweisen, ohne eine Interopassembly zu verwenden, indem Sie die Typinformationen für das COM-Objekt in eine .NET-Assembly einbetten.</span><span class="sxs-lookup"><span data-stu-id="3059e-106">You can reference a COM object without using an interop assembly by embedding the type information for the COM object in a .NET assembly.</span></span> <span data-ttu-id="3059e-107">Um Typinformationen einzubetten, legen Sie die- `Embed Interop Types` Eigenschaft `True` für den Verweis auf das COM-Objekt auf fest.</span><span class="sxs-lookup"><span data-stu-id="3059e-107">To embed type information, set the `Embed Interop Types` property to `True` for the reference to the COM object.</span></span> <span data-ttu-id="3059e-108">Wenn Sie mithilfe des Befehlszeilen Compilers kompilieren, verwenden Sie die- `/link` Option, um auf die com-Bibliothek zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="3059e-108">If you are compiling by using the command-line compiler, use the `/link` option to reference the COM library.</span></span> <span data-ttu-id="3059e-109">Weitere Informationen finden Sie unter [Link (Visual Basic)](../../reference/command-line-compiler/link.md).</span><span class="sxs-lookup"><span data-stu-id="3059e-109">For more information, see [-link (Visual Basic)](../../reference/command-line-compiler/link.md).</span></span>  
  
 <span data-ttu-id="3059e-110">Visual Basic erstellt automatisch Interop-Assemblys, wenn Sie einen Verweis auf eine Typbibliothek aus der integrierten Entwicklungsumgebung (Integrated Development Environment, IDE) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3059e-110">Visual Basic automatically creates interop assemblies when you add a reference to a type library from the integrated development environment (IDE).</span></span> <span data-ttu-id="3059e-111">Wenn Sie von der Befehlszeile aus arbeiten, können Sie das Hilfsprogramm Tlbimp verwenden, um Interop-Assemblys manuell zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3059e-111">When working from the command line, you can use the Tlbimp utility to manually create interop assemblies.</span></span>  
  
### <a name="to-add-references-to-com-objects"></a><span data-ttu-id="3059e-112">So fügen Sie Verweise auf COM-Objekte hinzu</span><span class="sxs-lookup"><span data-stu-id="3059e-112">To add references to COM objects</span></span>  
  
1. <span data-ttu-id="3059e-113">Wählen Sie im Menü **Projekt** die Option **Verweis hinzufügen** aus, und klicken Sie dann im Dialogfeld auf die Registerkarte **com** .</span><span class="sxs-lookup"><span data-stu-id="3059e-113">On the **Project** menu, choose **Add Reference** and then click the **COM** tab in the dialog box.</span></span>  
  
2. <span data-ttu-id="3059e-114">Wählen Sie die Komponente aus der Liste der COM-Objekte aus, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="3059e-114">Select the component you want to use from the list of COM objects.</span></span>  
  
3. <span data-ttu-id="3059e-115">Fügen Sie zum Vereinfachen des Zugriffs auf die Interop-Assembly am `Imports` Anfang der Klasse oder des Moduls, in dem Sie das COM-Objekt verwenden, eine-Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="3059e-115">To simplify access to the interop assembly, add an `Imports` statement to the top of the class or module in which you will use the COM object.</span></span> <span data-ttu-id="3059e-116">Im folgenden Codebeispiel wird der-Namespace `INKEDLib` für Objekte importiert, auf die in der-Bibliothek verwiesen wird `Microsoft InkEdit Control 1.0` .</span><span class="sxs-lookup"><span data-stu-id="3059e-116">For example, the following code example imports the namespace `INKEDLib` for objects referenced in the `Microsoft InkEdit Control 1.0` library.</span></span>  
  
     [!code-vb[VbVbalrInterop#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#40)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a><span data-ttu-id="3059e-117">So erstellen Sie eine Interop-Assembly mit Tlbimp</span><span class="sxs-lookup"><span data-stu-id="3059e-117">To create an interop assembly using Tlbimp</span></span>  
  
1. <span data-ttu-id="3059e-118">Fügen Sie den Speicherort von Tlbimp dem Suchpfad hinzu, wenn er nicht bereits Teil des Suchpfads ist und Sie sich derzeit nicht in dem Verzeichnis befinden, in dem es sich befindet.</span><span class="sxs-lookup"><span data-stu-id="3059e-118">Add the location of Tlbimp to the search path, if it is not already part of the search path and you are not currently in the directory where it is located.</span></span>  
  
2. <span data-ttu-id="3059e-119">Wenden Sie Tlbimp über eine Eingabeaufforderung an, und geben Sie dabei die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="3059e-119">Call Tlbimp from a command prompt, providing the following information:</span></span>  
  
    - <span data-ttu-id="3059e-120">Name und Speicherort der dll, die die Typbibliothek enthält</span><span class="sxs-lookup"><span data-stu-id="3059e-120">Name and location of the DLL that contains the type library</span></span>  
  
    - <span data-ttu-id="3059e-121">Name und Speicherort des Namespace, in dem die Informationen abgelegt werden sollen</span><span class="sxs-lookup"><span data-stu-id="3059e-121">Name and location of the namespace where the information should be placed</span></span>  
  
    - <span data-ttu-id="3059e-122">Name und Speicherort der zielinterop-Assembly</span><span class="sxs-lookup"><span data-stu-id="3059e-122">Name and location of the target interop assembly</span></span>  
  
     <span data-ttu-id="3059e-123">Der folgende Code veranschaulicht dies:</span><span class="sxs-lookup"><span data-stu-id="3059e-123">The following code provides an example:</span></span>  
  
    ```console  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     <span data-ttu-id="3059e-124">Mit Tlbimp können Sie Interop-Assemblys für Typbibliotheken erstellen, auch für nicht registrierte COM-Objekte.</span><span class="sxs-lookup"><span data-stu-id="3059e-124">You can use Tlbimp to create interop assemblies for type libraries, even for unregistered COM objects.</span></span> <span data-ttu-id="3059e-125">Die COM-Objekte, auf die von Interopassemblys verwiesen wird, müssen jedoch auf dem Computer, auf dem Sie verwendet werden sollen, ordnungsgemäß registriert werden.</span><span class="sxs-lookup"><span data-stu-id="3059e-125">However, the COM objects referred to by interop assemblies must be properly registered on the computer where they are to be used.</span></span> <span data-ttu-id="3059e-126">Sie können ein COM-Objekt registrieren, indem Sie das im Windows-Betriebssystem enthaltene regsvr32-Hilfsprogramm verwenden.</span><span class="sxs-lookup"><span data-stu-id="3059e-126">You can register a COM object by using the Regsvr32 utility included with the Windows operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3059e-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3059e-127">See also</span></span>

- [<span data-ttu-id="3059e-128">COM-Interop</span><span class="sxs-lookup"><span data-stu-id="3059e-128">COM Interop</span></span>](index.md)
- [<span data-ttu-id="3059e-129">Tlbimp.exe (Type Library Importer-Tool)</span><span class="sxs-lookup"><span data-stu-id="3059e-129">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [<span data-ttu-id="3059e-130">Tlbexp.exe (Type Library Exporter-Tool)</span><span class="sxs-lookup"><span data-stu-id="3059e-130">Tlbexp.exe (Type Library Exporter)</span></span>](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [<span data-ttu-id="3059e-131">Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten</span><span class="sxs-lookup"><span data-stu-id="3059e-131">Walkthrough: Implementing Inheritance with COM Objects</span></span>](walkthrough-implementing-inheritance-with-com-objects.md)
- [<span data-ttu-id="3059e-132">Problembehandlung bei der Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="3059e-132">Troubleshooting Interoperability</span></span>](troubleshooting-interoperability.md)
- [<span data-ttu-id="3059e-133">Imports-Anweisung (.NET-Namespace und Typ)</span><span class="sxs-lookup"><span data-stu-id="3059e-133">Imports Statement (.NET Namespace and Type)</span></span>](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
