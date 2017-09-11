---
title: 'Gewusst wie: Verweisen auf COM-Objekte aus Visual Basic | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- COM interop, referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 5f7f1112161d9be995cc80378ad9dd95c522198d
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-reference-com-objects-from-visual-basic"></a><span data-ttu-id="7f643-102">Gewusst wie: Verweisen auf COM-Objekte aus Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7f643-102">How to: Reference COM Objects from Visual Basic</span></span>
<span data-ttu-id="7f643-103">In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], Hinzufügen von Verweisen auf COM-Objekte mit Typbibliotheken erfordert die Erstellung einer Interop-Assembly für die COM-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="7f643-103">In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], adding references to COM objects that have type libraries requires the creation of an interop assembly for the COM library.</span></span> <span data-ttu-id="7f643-104">Verweise auf die Member des COM-Objekts werden an die Interop-Assembly und dann an das eigentliche COM-Objekt weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="7f643-104">References to the members of the COM object are routed to the interop assembly and then forwarded to the actual COM object.</span></span> <span data-ttu-id="7f643-105">Antworten vom COM-Objekt werden an die Interop-Assembly und übermittelt die [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Anwendung.</span><span class="sxs-lookup"><span data-stu-id="7f643-105">Responses from the COM object are routed to the interop assembly and forwarded to your [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] application.</span></span>  
  
 <span data-ttu-id="7f643-106">Ein COM-Objekt können Sie ohne eine Interop-Assembly die Typinformationen für COM-Objekt in einer .NET Framework-Assembly verweisen.</span><span class="sxs-lookup"><span data-stu-id="7f643-106">You can reference a COM object without using an interop assembly by embedding the type information for the COM object in a .NET assembly.</span></span> <span data-ttu-id="7f643-107">Um Typinformationen einzubetten, legen Sie die `Embed Interop Types` Eigenschaft `True` für den Verweis auf das COM-Objekt.</span><span class="sxs-lookup"><span data-stu-id="7f643-107">To embed type information, set the `Embed Interop Types` property to `True` for the reference to the COM object.</span></span> <span data-ttu-id="7f643-108">Wenn Sie mit dem Befehlszeilencompiler kompilieren, verwenden Sie die `/link` Option aus, um die COM-Bibliothek zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="7f643-108">If you are compiling by using the command-line compiler, use the `/link` option to reference the COM library.</span></span> <span data-ttu-id="7f643-109">Weitere Informationen finden Sie unter [/Link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).</span><span class="sxs-lookup"><span data-stu-id="7f643-109">For more information, see [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).</span></span>  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="7f643-110">Interop-Assemblys erstellt automatisch, wenn Sie einen Verweis auf eine Typbibliothek aus der integrierten Entwicklungsumgebung (IDE) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7f643-110"> automatically creates interop assemblies when you add a reference to a type library from the integrated development environment (IDE).</span></span> <span data-ttu-id="7f643-111">Wenn Sie über die Befehlszeile arbeiten, können Sie das Tlbimp-Dienstprogramm, Interop-Assemblys manuell zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7f643-111">When working from the command line, you can use the Tlbimp utility to manually create interop assemblies.</span></span>  
  
### <a name="to-add-references-to-com-objects"></a><span data-ttu-id="7f643-112">Hinzufügen von Verweisen auf COM-Objekte</span><span class="sxs-lookup"><span data-stu-id="7f643-112">To add references to COM objects</span></span>  
  
1.  <span data-ttu-id="7f643-113">Auf der **Projekt** Menü wählen **Verweis hinzufügen** , und klicken Sie dann auf die **COM** Registerkarte im Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="7f643-113">On the **Project** menu, choose **Add Reference** and then click the **COM** tab in the dialog box.</span></span>  
  
2.  <span data-ttu-id="7f643-114">Wählen Sie die Komponente, die Sie aus der Liste der COM-Objekte verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="7f643-114">Select the component you want to use from the list of COM objects.</span></span>  
  
3.  <span data-ttu-id="7f643-115">Um den Zugriff auf die Interop-Assembly zu vereinfachen, fügen Sie eine `Imports` -Anweisung am Anfang der Klasse oder des Moduls, in dem Sie das COM-Objekt verwenden.</span><span class="sxs-lookup"><span data-stu-id="7f643-115">To simplify access to the interop assembly, add an `Imports` statement to the top of the class or module in which you will use the COM object.</span></span> <span data-ttu-id="7f643-116">Im folgenden Codebeispiel wird importiert z. B. den Namespace `INKEDLib` für Objekte, die in der die `Microsoft InkEdit Control 1.0` Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="7f643-116">For example, the following code example imports the namespace `INKEDLib` for objects referenced in the `Microsoft InkEdit Control 1.0` library.</span></span>  
  
     <span data-ttu-id="7f643-117">[!code-vb[VbVbalrInterop&#40;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="7f643-117">[!code-vb[VbVbalrInterop#40](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]</span></span>  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a><span data-ttu-id="7f643-118">Erstellen Sie eine Interop-Assembly, die mittels Tlbimp</span><span class="sxs-lookup"><span data-stu-id="7f643-118">To create an interop assembly using Tlbimp</span></span>  
  
1.  <span data-ttu-id="7f643-119">Fügen Sie den Speicherort von Tlbimp dem Suchpfad hinzu, wenn es nicht bereits Teil des Suchpfads und Sie zurzeit in das Verzeichnis sind, in dem er sich befindet.</span><span class="sxs-lookup"><span data-stu-id="7f643-119">Add the location of Tlbimp to the search path, if it is not already part of the search path and you are not currently in the directory where it is located.</span></span>  
  
2.  <span data-ttu-id="7f643-120">Rufen Sie Tlbimp über eine Befehlszeile, die folgenden Informationen angeben:</span><span class="sxs-lookup"><span data-stu-id="7f643-120">Call Tlbimp from a command prompt, providing the following information:</span></span>  
  
    -   <span data-ttu-id="7f643-121">Name und Speicherort der DLL, die die Typbibliothek enthält.</span><span class="sxs-lookup"><span data-stu-id="7f643-121">Name and location of the DLL that contains the type library</span></span>  
  
    -   <span data-ttu-id="7f643-122">Name und Speicherort des Namespaces, in dem die Daten platziert werden soll</span><span class="sxs-lookup"><span data-stu-id="7f643-122">Name and location of the namespace where the information should be placed</span></span>  
  
    -   <span data-ttu-id="7f643-123">Name und Speicherort der Ziel-Interop-Assembly</span><span class="sxs-lookup"><span data-stu-id="7f643-123">Name and location of the target interop assembly</span></span>  
  
     <span data-ttu-id="7f643-124">Der folgende Code veranschaulicht dies:</span><span class="sxs-lookup"><span data-stu-id="7f643-124">The following code provides an example:</span></span>  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     <span data-ttu-id="7f643-125">Tlbimp können Sie die um Interop-Assemblys für Typbibliotheken und sogar für nicht registrierte COM-Objekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7f643-125">You can use Tlbimp to create interop assemblies for type libraries, even for unregistered COM objects.</span></span> <span data-ttu-id="7f643-126">Die COM-Objekte, die von Interop-Assemblys bezeichnet müssen jedoch ordnungsgemäß auf dem Computer registriert werden, wo sie sind verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7f643-126">However, the COM objects referred to by interop assemblies must be properly registered on the computer where they are to be used.</span></span> <span data-ttu-id="7f643-127">Sie können ein COM-Objekt mithilfe der mit dem Betriebssystem Windows enthaltene Dienstprogramm Regsvr32 registrieren.</span><span class="sxs-lookup"><span data-stu-id="7f643-127">You can register a COM object by using the Regsvr32 utility included with the Windows operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f643-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f643-128">See Also</span></span>  
 <span data-ttu-id="7f643-129">[COM-Interop](../../../visual-basic/programming-guide/com-interop/index.md) </span><span class="sxs-lookup"><span data-stu-id="7f643-129">[COM Interop](../../../visual-basic/programming-guide/com-interop/index.md) </span></span>  
<span data-ttu-id="7f643-130"> [Tlbimp.exe (Type Library Importer-Tool)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382) </span><span class="sxs-lookup"><span data-stu-id="7f643-130"> [Tlbimp.exe (Type Library Importer)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382) </span></span>  
<span data-ttu-id="7f643-131"> [Tlbexp.exe (Type Library Exporter-Tool)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d) </span><span class="sxs-lookup"><span data-stu-id="7f643-131"> [Tlbexp.exe (Type Library Exporter)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d) </span></span>  
<span data-ttu-id="7f643-132"> [Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md) </span><span class="sxs-lookup"><span data-stu-id="7f643-132"> [Walkthrough: Implementing Inheritance with COM Objects](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md) </span></span>  
<span data-ttu-id="7f643-133"> [Problembehandlung bei der Interoperabilität](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md) </span><span class="sxs-lookup"><span data-stu-id="7f643-133"> [Troubleshooting Interoperability](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md) </span></span>  
<span data-ttu-id="7f643-134"> [Imports-Anweisung (.NET-Namespace und -Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)</span><span class="sxs-lookup"><span data-stu-id="7f643-134"> [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)</span></span>
