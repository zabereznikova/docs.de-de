---
title: -link (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- l compiler option [Visual Basic]
- EmbedInteropTypes
- embed interop types [COM Interop]
- -link compiler option [Visual Basic]
- /link compiler option [Visual Basic]
- link compiler option [Visual Basic]
- -l compiler option [Visual Basic]
- /l compiler option [Visual Basic]
ms.assetid: 1885f24a-86f5-486c-a064-9fb7e455ccec
ms.openlocfilehash: b13d8266d0702d831a0f5ebb3a9586864fe22ccb
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586528"
---
# <a name="-link-visual-basic"></a><span data-ttu-id="85005-102">-link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85005-102">-link (Visual Basic)</span></span>
<span data-ttu-id="85005-103">Bewirkt, dass der Compiler dem Projekt, das Sie aktuell kompilieren, COM-Typinformationen in den angegebenen Assemblys bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="85005-103">Causes the compiler to make COM type information in the specified assemblies available to the project that you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85005-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="85005-104">Syntax</span></span>  
  
```  
-link:fileList  
' -or-  
-l:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="85005-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="85005-105">Arguments</span></span>  
  
|<span data-ttu-id="85005-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="85005-106">Term</span></span>|<span data-ttu-id="85005-107">Definition</span><span class="sxs-lookup"><span data-stu-id="85005-107">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="85005-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="85005-108">Required.</span></span> <span data-ttu-id="85005-109">Durch Trennzeichen getrennte Liste von Assemblydateinamen.</span><span class="sxs-lookup"><span data-stu-id="85005-109">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="85005-110">Wenn der Dateiname ein Leerzeichen enthält, müssen Sie den Namen in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="85005-110">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85005-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="85005-111">Remarks</span></span>  
 <span data-ttu-id="85005-112">Die Option `-link` ermöglicht es Ihnen, eine Anwendung mit eingebetteten Typinformationen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="85005-112">The `-link` option enables you to deploy an application that has embedded type information.</span></span> <span data-ttu-id="85005-113">Die Anwendung kann dann Typen in einer Runtime-Assembly verwenden, die die eingebetteten Typinformationen implementieren, ohne dass ein Verweis auf die Runtime-Assembly erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="85005-113">The application can then use types in a runtime assembly that implement the embedded type information without requiring a reference to the runtime assembly.</span></span> <span data-ttu-id="85005-114">Wenn verschiedene Versionen der Runtime-Assembly veröffentlicht werden, kann die Anwendung, die die eingebetteten Typinformationen enthält, mit den verschiedenen Versionen arbeiten, ohne neu kompiliert werden zu müssen.</span><span class="sxs-lookup"><span data-stu-id="85005-114">If various versions of the runtime assembly are published, the application that contains the embedded type information can work with the various versions without having to be recompiled.</span></span> <span data-ttu-id="85005-115">Ein Beispiel finden Sie unter [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys](../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="85005-115">For an example, see [Walkthrough: Embedding Types from Managed Assemblies](../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md).</span></span>  
  
 <span data-ttu-id="85005-116">Die Option `-link` ist besonders nützlich, wenn Sie COM-Interop verwenden.</span><span class="sxs-lookup"><span data-stu-id="85005-116">Using the `-link` option is especially useful when you are working with COM interop.</span></span> <span data-ttu-id="85005-117">Sie können COM-Typen einbetten, sodass für Ihre Anwendung keine primäre Interopassembly (PIA) auf dem Zielcomputer mehr erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="85005-117">You can embed COM types so that your application no longer requires a primary interop assembly (PIA) on the target computer.</span></span> <span data-ttu-id="85005-118">Die Option `-link` weist den Compiler an, die COM-Typinformationen aus der Interopassembly, auf die verwiesen wird, in den resultierenden kompilierten Code einzubetten.</span><span class="sxs-lookup"><span data-stu-id="85005-118">The `-link` option instructs the compiler to embed the COM type information from the referenced interop assembly into the resulting compiled code.</span></span> <span data-ttu-id="85005-119">Der COM-Typ wird durch den CLSID (GUID)-Wert identifiziert.</span><span class="sxs-lookup"><span data-stu-id="85005-119">The COM type is identified by the CLSID (GUID) value.</span></span> <span data-ttu-id="85005-120">Dadurch kann Ihre Anwendung auf einem Zielcomputer ausgeführt werden, auf dem die gleichen COM-Typen mit den gleichen CLSID-Werten installiert sind.</span><span class="sxs-lookup"><span data-stu-id="85005-120">As a result, your application can run on a target computer that has installed the same COM types with the same CLSID values.</span></span> <span data-ttu-id="85005-121">Anwendungen, die Microsoft Office automatisieren, sind ein gutes Beispiel.</span><span class="sxs-lookup"><span data-stu-id="85005-121">Applications that automate Microsoft Office are a good example.</span></span> <span data-ttu-id="85005-122">Da Anwendungen wie Office in der Regel den gleichen CLSID-Wert in den verschiedenen Versionen behalten, kann die Anwendung die COM-Typen, auf die verwiesen wird, verwenden, wenn .NET Framework 4 oder höher auf dem Zielcomputer installiert ist und die Anwendung Methoden, Eigenschaften oder Ereignisse verwendet, die in den COM-Typen, auf die verwiesen wird, enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="85005-122">Because applications like Office usually keep the same CLSID value across different versions, your application can use the referenced COM types as long as .NET Framework 4 or later is installed on the target computer and your application uses methods, properties, or events that are included in the referenced COM types.</span></span>  
  
 <span data-ttu-id="85005-123">Die Option `-link` bettet nur Schnittstellen, Strukturen und Delegaten ein.</span><span class="sxs-lookup"><span data-stu-id="85005-123">The `-link` option embeds only interfaces, structures, and delegates.</span></span> <span data-ttu-id="85005-124">Das Einbetten von COM-Klassen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="85005-124">Embedding COM classes is not supported.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85005-125">Wenn Sie eine Instanz eines eingebetteten COM-Typs in Ihrem Code erstellen, müssen Sie die Instanz mithilfe der entsprechenden Schnittstelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="85005-125">When you create an instance of an embedded COM type in your code, you must create the instance by using the appropriate interface.</span></span> <span data-ttu-id="85005-126">Der Versuch, eine Instanz eines eingebetteten COM-Typs mit der Co-Klasse zu erstellen, verursacht einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="85005-126">Attempting to create an instance of an embedded COM type by using the CoClass causes an error.</span></span>  
  
 <span data-ttu-id="85005-127">Fügen Sie zum Festlegen der Option `-link` in Visual Studio einen Assemblyverweis hinzu, und legen Sie die `Embed Interop Types`-Eigenschaft auf **TRUE** fest.</span><span class="sxs-lookup"><span data-stu-id="85005-127">To set the `-link` option in Visual Studio, add an assembly reference and set the `Embed Interop Types` property to **true**.</span></span> <span data-ttu-id="85005-128">Der Standardwert der `Embed Interop Types`-Eigenschaft ist **false**.</span><span class="sxs-lookup"><span data-stu-id="85005-128">The default for the `Embed Interop Types` property is **false**.</span></span>  
  
 <span data-ttu-id="85005-129">Wenn Sie eine Verknüpfung mit einer COM-Assembly (Assembly A) erstellen, die selbst auf eine andere COM-Assembly (Assembly B) verweist, müssen Sie auch eine Verknüpfung mit Assembly B erstellen, wenn eine der folgenden Aussagen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="85005-129">If you link to a COM assembly (Assembly A) which itself references another COM assembly (Assembly B), you also have to link to Assembly B if either of the following is true:</span></span>  
  
- <span data-ttu-id="85005-130">Ein Typ von Assembly A erbt von einem Typ oder implementiert eine Schnittstelle aus Assembly B.</span><span class="sxs-lookup"><span data-stu-id="85005-130">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
- <span data-ttu-id="85005-131">Es wird ein Feld, eine Eigenschaft, ein Ereignis oder eine Methode aufgerufen, das/die über einen Rückgabetyp oder Parametertyp von Assembly B verfügt.</span><span class="sxs-lookup"><span data-stu-id="85005-131">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="85005-132">Verwendung [- Libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) auf das Verzeichnis anzugeben, in denen eine oder mehrere der Assemblyverweise befinden.</span><span class="sxs-lookup"><span data-stu-id="85005-132">Use [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="85005-133">Wie die [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) -Compileroption verwenden, die `-link` Compileroption verwendet die Vbc.rsp-Antwortdatei, der Verweise, häufig .NET Framework-Assemblys verwendete.</span><span class="sxs-lookup"><span data-stu-id="85005-133">Like the [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) compiler option, the `-link` compiler option uses the Vbc.rsp response file, which references frequently used .NET Framework assemblies.</span></span> <span data-ttu-id="85005-134">Verwenden Sie die [- Noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) Compileroption, wenn Sie nicht, dass den Compiler die Datei "vbc.rsp" zu verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="85005-134">Use the [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) compiler option if you do not want the compiler to use the Vbc.rsp file.</span></span>  
  
 <span data-ttu-id="85005-135">Die Kurzform von `-link` ist `-l`.</span><span class="sxs-lookup"><span data-stu-id="85005-135">The short form of `-link` is `-l`.</span></span>  
  
## <a name="generics-and-embedded-types"></a><span data-ttu-id="85005-136">Generics und eingebettete Typen</span><span class="sxs-lookup"><span data-stu-id="85005-136">Generics and Embedded Types</span></span>  
 <span data-ttu-id="85005-137">In den folgenden Abschnitten werden die Einschränkungen bei der Verwendung von generischen Typen in Anwendungen, die Interop-Typen einbetten, beschrieben.</span><span class="sxs-lookup"><span data-stu-id="85005-137">The following sections describe the limitations on using generic types in applications that embed interop types.</span></span>  
  
### <a name="generic-interfaces"></a><span data-ttu-id="85005-138">Generische Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="85005-138">Generic Interfaces</span></span>  
 <span data-ttu-id="85005-139">Generische Schnittstellen, die von einer Interopassembly eingebettet werden, können nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="85005-139">Generic interfaces that are embedded from an interop assembly cannot be used.</span></span> <span data-ttu-id="85005-140">Dies wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="85005-140">This is shown in the following example.</span></span>  
  
 [!code-vb[VbLinkCompiler#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/module1.vb#1)]  
  
### <a name="types-that-have-generic-parameters"></a><span data-ttu-id="85005-141">Typen, die generische Parameter aufweisen</span><span class="sxs-lookup"><span data-stu-id="85005-141">Types That Have Generic Parameters</span></span>  
 <span data-ttu-id="85005-142">Typen, die über einen generischen Parameter verfügen, dessen Typ aus einer Interop-Assembly eingebettet wird, können nicht verwendet werden, wenn dieser Typ aus einer externen Assembly stammt.</span><span class="sxs-lookup"><span data-stu-id="85005-142">Types that have a generic parameter whose type is embedded from an interop assembly cannot be used if that type is from an external assembly.</span></span> <span data-ttu-id="85005-143">Diese Einschränkung gilt nicht für Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="85005-143">This restriction does not apply to interfaces.</span></span> <span data-ttu-id="85005-144">Nehmen Sie z.B. die <xref:Microsoft.Office.Interop.Excel.Range> Schnittstellen, die in der <xref:Microsoft.Office.Interop.Excel>-Assembly definiert wird.</span><span class="sxs-lookup"><span data-stu-id="85005-144">For example, consider the <xref:Microsoft.Office.Interop.Excel.Range> interface that is defined in the <xref:Microsoft.Office.Interop.Excel> assembly.</span></span> <span data-ttu-id="85005-145">Wenn eine Bibliothek Interop-Typen aus der <xref:Microsoft.Office.Interop.Excel>-Assembly einbettet und eine Methode verfügbar macht, die einen generischen Typ zurückgibt, der einen Parameter mit dem Typ <xref:Microsoft.Office.Interop.Excel.Range>-Schnittstelle hat, muss diese Methode eine generische Schnittstelle zurückgeben, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="85005-145">If a library embeds interop types from the <xref:Microsoft.Office.Interop.Excel> assembly and exposes a method that returns a generic type that has a parameter whose type is the <xref:Microsoft.Office.Interop.Excel.Range> interface, that method must return a generic interface, as shown in the following code example.</span></span>  
  
 [!code-vb[VbLinkCompiler#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/utility.vb#2)]  
[!code-vb[VbLinkCompiler#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/utility.vb#3)]  
[!code-vb[VbLinkCompiler#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/utility.vb#4)]  
  
 <span data-ttu-id="85005-146">Im folgenden Beispiel kann der Clientcode die Methode aufrufen, die die generische Schnittstelle <xref:System.Collections.IList> ohne Fehler zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="85005-146">In the following example, client code can call the method that returns the <xref:System.Collections.IList> generic interface without error.</span></span>  
  
 [!code-vb[VbLinkCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/module1.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="85005-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="85005-147">Example</span></span>  
 <span data-ttu-id="85005-148">Die folgende Befehlszeile kompiliert die Quelldatei `OfficeApp.vb` und Verweisassemblys aus `COMData1.dll` und `COMData2.dll` erzeugt `OfficeApp.exe`.</span><span class="sxs-lookup"><span data-stu-id="85005-148">The following command line compiles source file `OfficeApp.vb` and reference assemblies from `COMData1.dll` and `COMData2.dll` to produce `OfficeApp.exe`.</span></span>  
  
```console  
vbc -link:COMData1.dll,COMData2.dll /out:OfficeApp.exe OfficeApp.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="85005-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85005-149">See also</span></span>

- [<span data-ttu-id="85005-150">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="85005-150">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="85005-151">Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="85005-151">Walkthrough: Embedding Types from Managed Assemblies</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md)
- [<span data-ttu-id="85005-152">-Referenz (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85005-152">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="85005-153">-noconfig</span><span class="sxs-lookup"><span data-stu-id="85005-153">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="85005-154">-libpath</span><span class="sxs-lookup"><span data-stu-id="85005-154">-libpath</span></span>](../../../visual-basic/reference/command-line-compiler/libpath.md)
- [<span data-ttu-id="85005-155">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="85005-155">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="85005-156">Einführung in COM-Interop</span><span class="sxs-lookup"><span data-stu-id="85005-156">Introduction to COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)
