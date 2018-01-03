---
title: 'Gewusst wie: Verweisen auf COM-Objekte aus Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- COM interop [Visual Basic], referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a8ac167b40688b1d1116f148d0d5fd6afdcaada8
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a><span data-ttu-id="5623f-102">Gewusst wie: Verweisen auf COM-Objekte aus Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5623f-102">How to: Reference COM Objects from Visual Basic</span></span>
<span data-ttu-id="5623f-103">In [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], Hinzufügen von Verweisen auf COM-Objekte, die Typbibliotheken verfügen, ist die Erstellung einer Interop-Assembly für COM-Bibliothek erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5623f-103">In [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], adding references to COM objects that have type libraries requires the creation of an interop assembly for the COM library.</span></span> <span data-ttu-id="5623f-104">Verweise auf die Member des COM-Objekts sind auf die Interop-Assembly weitergeleitet, und klicken Sie dann auf das eigentliche COM-Objekt weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="5623f-104">References to the members of the COM object are routed to the interop assembly and then forwarded to the actual COM object.</span></span> <span data-ttu-id="5623f-105">Antworten von der COM-Objekt an die Interop-Assembly weitergeleitet und an weitergeleitet werden Ihre [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Anwendung.</span><span class="sxs-lookup"><span data-stu-id="5623f-105">Responses from the COM object are routed to the interop assembly and forwarded to your [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] application.</span></span>  
  
 <span data-ttu-id="5623f-106">Sie können ein COM-Objekt verweisen, ohne die Typinformationen für COM-Objekts in eine .NET-Assembly mithilfe einer Interop-Assembly.</span><span class="sxs-lookup"><span data-stu-id="5623f-106">You can reference a COM object without using an interop assembly by embedding the type information for the COM object in a .NET assembly.</span></span> <span data-ttu-id="5623f-107">Um Typinformationen einzubetten, legen die `Embed Interop Types` Eigenschaft `True` für den Verweis auf das COM-Objekt.</span><span class="sxs-lookup"><span data-stu-id="5623f-107">To embed type information, set the `Embed Interop Types` property to `True` for the reference to the COM object.</span></span> <span data-ttu-id="5623f-108">Wenn Sie mithilfe des Befehlszeilencompilers kompilieren, verwenden Sie die `/link` Option aus, um die COM-Bibliothek verweisen.</span><span class="sxs-lookup"><span data-stu-id="5623f-108">If you are compiling by using the command-line compiler, use the `/link` option to reference the COM library.</span></span> <span data-ttu-id="5623f-109">Weitere Informationen finden Sie unter [/Link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).</span><span class="sxs-lookup"><span data-stu-id="5623f-109">For more information, see [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).</span></span>  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="5623f-110">Interop-Assemblys erstellt automatisch, wenn Sie einen Verweis auf eine Typbibliothek aus der integrierten Entwicklungsumgebung (IDE) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5623f-110"> automatically creates interop assemblies when you add a reference to a type library from the integrated development environment (IDE).</span></span> <span data-ttu-id="5623f-111">Wenn Sie über die Befehlszeile zu arbeiten, können Sie das Tlbimp-Dienstprogramm, Interop-Assemblys manuell zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5623f-111">When working from the command line, you can use the Tlbimp utility to manually create interop assemblies.</span></span>  
  
### <a name="to-add-references-to-com-objects"></a><span data-ttu-id="5623f-112">Hinzufügen von Verweisen auf COM-Objekte</span><span class="sxs-lookup"><span data-stu-id="5623f-112">To add references to COM objects</span></span>  
  
1.  <span data-ttu-id="5623f-113">Auf der **Projekt** Menü wählen **Verweis hinzufügen** , und klicken Sie dann auf die **COM** Registerkarte im Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="5623f-113">On the **Project** menu, choose **Add Reference** and then click the **COM** tab in the dialog box.</span></span>  
  
2.  <span data-ttu-id="5623f-114">Wählen Sie die Komponente, die Sie aus der Liste der COM-Objekte verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="5623f-114">Select the component you want to use from the list of COM objects.</span></span>  
  
3.  <span data-ttu-id="5623f-115">Um den Zugriff auf die Interop-Assembly zu vereinfachen, fügen Sie eine `Imports` Anweisungen am Anfang der Klasse oder des Moduls, in dem Sie das COM-Objekt verwenden.</span><span class="sxs-lookup"><span data-stu-id="5623f-115">To simplify access to the interop assembly, add an `Imports` statement to the top of the class or module in which you will use the COM object.</span></span> <span data-ttu-id="5623f-116">Im folgenden Codebeispiel wird importiert z. B. den Namespace `INKEDLib` für Objekte der `Microsoft InkEdit Control 1.0` Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="5623f-116">For example, the following code example imports the namespace `INKEDLib` for objects referenced in the `Microsoft InkEdit Control 1.0` library.</span></span>  
  
     [!code-vb[VbVbalrInterop#40](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a><span data-ttu-id="5623f-117">Zum Erstellen einer Interop-Assembly, die mithilfe von Tlbimp</span><span class="sxs-lookup"><span data-stu-id="5623f-117">To create an interop assembly using Tlbimp</span></span>  
  
1.  <span data-ttu-id="5623f-118">Fügen Sie den Speicherort der Tlbimp den Suchpfad hinzu, wenn er nicht bereits Teil des Suchpfades und Sie nicht im Verzeichnis momentan, in dem er sich befindet.</span><span class="sxs-lookup"><span data-stu-id="5623f-118">Add the location of Tlbimp to the search path, if it is not already part of the search path and you are not currently in the directory where it is located.</span></span>  
  
2.  <span data-ttu-id="5623f-119">Rufen Sie Tlbimp aus der Eingabeaufforderung die folgenden Informationen angeben:</span><span class="sxs-lookup"><span data-stu-id="5623f-119">Call Tlbimp from a command prompt, providing the following information:</span></span>  
  
    -   <span data-ttu-id="5623f-120">Name und Speicherort der DLL, die die Typbibliothek enthält.</span><span class="sxs-lookup"><span data-stu-id="5623f-120">Name and location of the DLL that contains the type library</span></span>  
  
    -   <span data-ttu-id="5623f-121">Name und Speicherort des Namespace, in dem die Informationen platziert werden soll</span><span class="sxs-lookup"><span data-stu-id="5623f-121">Name and location of the namespace where the information should be placed</span></span>  
  
    -   <span data-ttu-id="5623f-122">Name und Speicherort der Ziel-Interop-Assembly</span><span class="sxs-lookup"><span data-stu-id="5623f-122">Name and location of the target interop assembly</span></span>  
  
     <span data-ttu-id="5623f-123">Der folgende Code veranschaulicht dies:</span><span class="sxs-lookup"><span data-stu-id="5623f-123">The following code provides an example:</span></span>  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     <span data-ttu-id="5623f-124">Sie können Tlbimp verwenden, Erstellen von Interop-Assemblys für Typbibliotheken und sogar für nicht registrierte COM-Objekte.</span><span class="sxs-lookup"><span data-stu-id="5623f-124">You can use Tlbimp to create interop assemblies for type libraries, even for unregistered COM objects.</span></span> <span data-ttu-id="5623f-125">Die COM-Objekte verweist Interop-Assemblys müssen jedoch ordnungsgemäß auf dem Computer registriert werden, in denen sie verwendet werden, werden.</span><span class="sxs-lookup"><span data-stu-id="5623f-125">However, the COM objects referred to by interop assemblies must be properly registered on the computer where they are to be used.</span></span> <span data-ttu-id="5623f-126">Sie können ein COM-Objekt registrieren, mit dem Dienstprogramm "regsvr32" mit dem Windows-Betriebssystem enthalten.</span><span class="sxs-lookup"><span data-stu-id="5623f-126">You can register a COM object by using the Regsvr32 utility included with the Windows operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5623f-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5623f-127">See Also</span></span>  
 [<span data-ttu-id="5623f-128">COM-Interop</span><span class="sxs-lookup"><span data-stu-id="5623f-128">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 [<span data-ttu-id="5623f-129">Tlbimp.exe (Type Library Importer-Tool)</span><span class="sxs-lookup"><span data-stu-id="5623f-129">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 [<span data-ttu-id="5623f-130">Tlbexp.exe (Type Library Exporter-Tool)</span><span class="sxs-lookup"><span data-stu-id="5623f-130">Tlbexp.exe (Type Library Exporter)</span></span>](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)  
 [<span data-ttu-id="5623f-131">Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten</span><span class="sxs-lookup"><span data-stu-id="5623f-131">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [<span data-ttu-id="5623f-132">Problembehandlung bei der Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="5623f-132">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 [<span data-ttu-id="5623f-133">Imports-Anweisung (.NET-Namespace und -Typ)</span><span class="sxs-lookup"><span data-stu-id="5623f-133">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
