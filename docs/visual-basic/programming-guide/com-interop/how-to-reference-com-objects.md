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
ms.openlocfilehash: 34f46a1ea9c728cbaeb0456f8a6751ff529f2903
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43555221"
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a><span data-ttu-id="6b9b2-102">Gewusst wie: Verweisen auf COM-Objekte aus Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6b9b2-102">How to: Reference COM Objects from Visual Basic</span></span>
<span data-ttu-id="6b9b2-103">In Visual Basic ist beim Hinzufügen von Verweisen auf COM-Objekte, die über Typbibliotheken verfügen die Erstellung einer Interop-Assembly für COM-Bibliothek erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6b9b2-103">In Visual Basic, adding references to COM objects that have type libraries requires the creation of an interop assembly for the COM library.</span></span> <span data-ttu-id="6b9b2-104">Verweise auf die Member des COM-Objekts sind die interop-Assembly an, und klicken Sie dann auf die tatsächliche COM-Objekt weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="6b9b2-104">References to the members of the COM object are routed to the interop assembly and then forwarded to the actual COM object.</span></span> <span data-ttu-id="6b9b2-105">Antworten von der COM-Objekt an die Interop-Assembly und weitergeleitet wird, um Ihre [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Anwendung.</span><span class="sxs-lookup"><span data-stu-id="6b9b2-105">Responses from the COM object are routed to the interop assembly and forwarded to your [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] application.</span></span>  
  
 <span data-ttu-id="6b9b2-106">Sie können ein COM-Objekt verweisen, ohne eine interop-Assembly die Typinformationen für COM-Objekts in einer .NET-Assembly.</span><span class="sxs-lookup"><span data-stu-id="6b9b2-106">You can reference a COM object without using an interop assembly by embedding the type information for the COM object in a .NET assembly.</span></span> <span data-ttu-id="6b9b2-107">Legen Sie zum Einbetten von Typinformationen der `Embed Interop Types` Eigenschaft `True` für den Verweis auf das COM-Objekt.</span><span class="sxs-lookup"><span data-stu-id="6b9b2-107">To embed type information, set the `Embed Interop Types` property to `True` for the reference to the COM object.</span></span> <span data-ttu-id="6b9b2-108">Wenn Sie mithilfe des Befehlszeilencompilers kompilieren, verwenden Sie die `/link` Option aus, um die COM-Bibliothek verweisen.</span><span class="sxs-lookup"><span data-stu-id="6b9b2-108">If you are compiling by using the command-line compiler, use the `/link` option to reference the COM library.</span></span> <span data-ttu-id="6b9b2-109">Weitere Informationen finden Sie unter [/Link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).</span><span class="sxs-lookup"><span data-stu-id="6b9b2-109">For more information, see [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).</span></span>  
  
 <span data-ttu-id="6b9b2-110">Visual Basic erstellt automatisch interop-Assemblys auf, wenn Sie einen Verweis auf eine Typbibliothek aus der integrierten Entwicklungsumgebung (IDE) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6b9b2-110">Visual Basic automatically creates interop assemblies when you add a reference to a type library from the integrated development environment (IDE).</span></span> <span data-ttu-id="6b9b2-111">Wenn Sie über die Befehlszeile arbeiten, können Sie das Tlbimp-Dienstprogramm, interop-Assemblys manuell zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6b9b2-111">When working from the command line, you can use the Tlbimp utility to manually create interop assemblies.</span></span>  
  
### <a name="to-add-references-to-com-objects"></a><span data-ttu-id="6b9b2-112">Zum Hinzufügen von Verweisen auf COM-Objekte</span><span class="sxs-lookup"><span data-stu-id="6b9b2-112">To add references to COM objects</span></span>  
  
1.  <span data-ttu-id="6b9b2-113">Auf der **Projekt** Menü wählen **Verweis hinzufügen** , und klicken Sie dann auf die **COM** Registerkarte im Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="6b9b2-113">On the **Project** menu, choose **Add Reference** and then click the **COM** tab in the dialog box.</span></span>  
  
2.  <span data-ttu-id="6b9b2-114">Wählen Sie die Komponente, die Sie aus der Liste der COM-Objekte verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="6b9b2-114">Select the component you want to use from the list of COM objects.</span></span>  
  
3.  <span data-ttu-id="6b9b2-115">Um den Zugriff auf die interop-Assembly zu vereinfachen, fügen eine `Imports` Anweisung am Anfang der Klasse oder das Modul, in dem Sie das COM-Objekt verwenden.</span><span class="sxs-lookup"><span data-stu-id="6b9b2-115">To simplify access to the interop assembly, add an `Imports` statement to the top of the class or module in which you will use the COM object.</span></span> <span data-ttu-id="6b9b2-116">Das folgende Codebeispiel importiert z. B. den Namespace `INKEDLib` für Objekte, die auf die verwiesen wird der `Microsoft InkEdit Control 1.0` Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="6b9b2-116">For example, the following code example imports the namespace `INKEDLib` for objects referenced in the `Microsoft InkEdit Control 1.0` library.</span></span>  
  
     [!code-vb[VbVbalrInterop#40](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a><span data-ttu-id="6b9b2-117">Eine Interop-Assembly, die über "Tlbimp" erstellen</span><span class="sxs-lookup"><span data-stu-id="6b9b2-117">To create an interop assembly using Tlbimp</span></span>  
  
1.  <span data-ttu-id="6b9b2-118">Fügen Sie den Speicherort des "Tlbimp" dem Suchpfad hinzu, wenn es nicht bereits Teil des Pfads für die Suche und Sie aktuell nicht in das Verzeichnis werden, in dem er sich befindet.</span><span class="sxs-lookup"><span data-stu-id="6b9b2-118">Add the location of Tlbimp to the search path, if it is not already part of the search path and you are not currently in the directory where it is located.</span></span>  
  
2.  <span data-ttu-id="6b9b2-119">Rufen Sie "Tlbimp" über eine Eingabeaufforderung, die die folgenden Informationen angeben:</span><span class="sxs-lookup"><span data-stu-id="6b9b2-119">Call Tlbimp from a command prompt, providing the following information:</span></span>  
  
    -   <span data-ttu-id="6b9b2-120">Name und Speicherort der DLL, die die Typbibliothek enthält.</span><span class="sxs-lookup"><span data-stu-id="6b9b2-120">Name and location of the DLL that contains the type library</span></span>  
  
    -   <span data-ttu-id="6b9b2-121">Name und Speicherort des Namespace, in dem die Informationen platziert werden soll</span><span class="sxs-lookup"><span data-stu-id="6b9b2-121">Name and location of the namespace where the information should be placed</span></span>  
  
    -   <span data-ttu-id="6b9b2-122">Name und Speicherort der Ziel-Interop-Assembly</span><span class="sxs-lookup"><span data-stu-id="6b9b2-122">Name and location of the target interop assembly</span></span>  
  
     <span data-ttu-id="6b9b2-123">Der folgende Code veranschaulicht dies:</span><span class="sxs-lookup"><span data-stu-id="6b9b2-123">The following code provides an example:</span></span>  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     <span data-ttu-id="6b9b2-124">Sie können "Tlbimp" verwenden, um interop-Assemblys für Typbibliotheken und sogar für nicht registrierte COM-Objekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6b9b2-124">You can use Tlbimp to create interop assemblies for type libraries, even for unregistered COM objects.</span></span> <span data-ttu-id="6b9b2-125">Die COM-Objekte, die interop-Assemblys verweist müssen jedoch ordnungsgemäß auf dem Computer registriert werden, wo sie sind, verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6b9b2-125">However, the COM objects referred to by interop assemblies must be properly registered on the computer where they are to be used.</span></span> <span data-ttu-id="6b9b2-126">Sie können ein COM-Objekt registrieren, mit dem Dienstprogramm "Regsvr32" mit dem Windows-Betriebssystem enthalten.</span><span class="sxs-lookup"><span data-stu-id="6b9b2-126">You can register a COM object by using the Regsvr32 utility included with the Windows operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b9b2-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b9b2-127">See Also</span></span>  
 [<span data-ttu-id="6b9b2-128">COM-Interop</span><span class="sxs-lookup"><span data-stu-id="6b9b2-128">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 [<span data-ttu-id="6b9b2-129">Tlbimp.exe (Type Library Importer-Tool)</span><span class="sxs-lookup"><span data-stu-id="6b9b2-129">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 [<span data-ttu-id="6b9b2-130">Tlbexp.exe (Type Library Exporter-Tool)</span><span class="sxs-lookup"><span data-stu-id="6b9b2-130">Tlbexp.exe (Type Library Exporter)</span></span>](https://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)  
 [<span data-ttu-id="6b9b2-131">Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten</span><span class="sxs-lookup"><span data-stu-id="6b9b2-131">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [<span data-ttu-id="6b9b2-132">Problembehandlung bei der Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="6b9b2-132">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 [<span data-ttu-id="6b9b2-133">Imports-Anweisung (.NET-Namespace und -Typ)</span><span class="sxs-lookup"><span data-stu-id="6b9b2-133">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
