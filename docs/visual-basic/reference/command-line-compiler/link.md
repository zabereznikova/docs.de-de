---
title: / Link (Visual Basic) | Microsoft-Dokumentation
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
- l compiler option [Visual Basic]
- EmbedInteropTypes
- embed interop types [COM Interop]
- -link compiler option [Visual Basic]
- /link compiler option [Visual Basic]
- link compiler option [Visual Basic]
- -l compiler option [Visual Basic]
- /l compiler option [Visual Basic]
ms.assetid: 1885f24a-86f5-486c-a064-9fb7e455ccec
caps.latest.revision: 27
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
ms.openlocfilehash: 71ecefc898ca37cbf7299d97518e1ce2547a58da
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="link-visual-basic"></a><span data-ttu-id="8ec1f-102">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ec1f-102">/link (Visual Basic)</span></span>
<span data-ttu-id="8ec1f-103">Veranlasst den Compiler, COM-Typinformationen in den angegebenen Assemblys für das Projekt verfügbar, die Sie gerade kompilieren.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-103">Causes the compiler to make COM type information in the specified assemblies available to the project that you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ec1f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ec1f-104">Syntax</span></span>  
  
```  
/link:fileList  
' -or-  
/l:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="8ec1f-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="8ec1f-105">Arguments</span></span>  
  
|<span data-ttu-id="8ec1f-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="8ec1f-106">Term</span></span>|<span data-ttu-id="8ec1f-107">Definition</span><span class="sxs-lookup"><span data-stu-id="8ec1f-107">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="8ec1f-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-108">Required.</span></span> <span data-ttu-id="8ec1f-109">Durch Trennzeichen getrennte Liste von Assemblydateinamen.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-109">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="8ec1f-110">Wenn der Dateiname ein Leerzeichen enthält, müssen Sie den Namen in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-110">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ec1f-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8ec1f-111">Remarks</span></span>  
 <span data-ttu-id="8ec1f-112">Die `/link` Option ermöglicht es Ihnen, eine Anwendung bereitzustellen, die eingebetteten Typinformationen.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-112">The `/link` option enables you to deploy an application that has embedded type information.</span></span> <span data-ttu-id="8ec1f-113">Die Anwendung kann dann Typen in einer Assembly der Common Language Runtime verwenden, die die eingebetteten Typinformationen implementieren, ohne einen Verweis auf die Common Language Runtime-Assembly.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-113">The application can then use types in a runtime assembly that implement the embedded type information without requiring a reference to the runtime assembly.</span></span> <span data-ttu-id="8ec1f-114">Wenn verschiedene Versionen der Laufzeitassembly veröffentlicht werden, kann die Anwendung, die die eingebetteten Typinformationen mit verschiedenen Versionen arbeiten, ohne neu kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-114">If various versions of the runtime assembly are published, the application that contains the embedded type information can work with the various versions without having to be recompiled.</span></span> <span data-ttu-id="8ec1f-115">Ein Beispiel finden Sie unter [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).</span><span class="sxs-lookup"><span data-stu-id="8ec1f-115">For an example, see [Walkthrough: Embedding Types from Managed Assemblies](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).</span></span>  
  
 <span data-ttu-id="8ec1f-116">Mithilfe der `/link` Option ist besonders nützlich, wenn Sie COM-Interop verwenden.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-116">Using the `/link` option is especially useful when you are working with COM interop.</span></span> <span data-ttu-id="8ec1f-117">Sie können COM-Typen einbetten, sodass Ihre Anwendung eine primäre Interopassembly (PIA) auf dem Zielcomputer nicht mehr erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-117">You can embed COM types so that your application no longer requires a primary interop assembly (PIA) on the target computer.</span></span> <span data-ttu-id="8ec1f-118">Die `/link` Option weist den Compiler an, die COM-Typinformationen aus der referenzierten Interop-Assembly in den resultierenden kompilierten Code einzubetten.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-118">The `/link` option instructs the compiler to embed the COM type information from the referenced interop assembly into the resulting compiled code.</span></span> <span data-ttu-id="8ec1f-119">Der COM-Typ wird durch den Wert für die CLSID (GUID) identifiziert.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-119">The COM type is identified by the CLSID (GUID) value.</span></span> <span data-ttu-id="8ec1f-120">Daher können Ihre Anwendung auf einem Zielcomputer ausführen, die die gleichen COM-Typen mit denselben CLSID-Werten installiert hat.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-120">As a result, your application can run on a target computer that has installed the same COM types with the same CLSID values.</span></span> <span data-ttu-id="8ec1f-121">Clientanwendungen, die Microsoft Office automatisieren sind ein gutes Beispiel.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-121">Applications that automate Microsoft Office are a good example.</span></span> <span data-ttu-id="8ec1f-122">Da Clientanwendungen wie Office in der Regel den gleichen CLSID-Wert in den verschiedenen Versionen halten, kann die Anwendung verwiesen wird COM-Typen verwenden, wie .NET Framework 4 oder höher auf dem Zielcomputer installiert ist und die Anwendung verwendet die Methoden, Eigenschaften oder Ereignisse, die in den referenzierten COM-Typen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-122">Because applications like Office usually keep the same CLSID value across different versions, your application can use the referenced COM types as long as .NET Framework 4 or later is installed on the target computer and your application uses methods, properties, or events that are included in the referenced COM types.</span></span>  
  
 <span data-ttu-id="8ec1f-123">Die `/link` -Option bettet nur Schnittstellen, Strukturen und Delegaten.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-123">The `/link` option embeds only interfaces, structures, and delegates.</span></span> <span data-ttu-id="8ec1f-124">Einbetten von COM-Klassen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-124">Embedding COM classes is not supported.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ec1f-125">Wenn Sie eine Instanz eines eingebetteten COM-Typs in Ihrem Code erstellen, müssen Sie die Instanz mithilfe der entsprechenden Schnittstelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-125">When you create an instance of an embedded COM type in your code, you must create the instance by using the appropriate interface.</span></span> <span data-ttu-id="8ec1f-126">Versuch, eine Instanz eines eingebetteten COM-Typs zu erstellen, mit CoClass verursacht einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-126">Attempting to create an instance of an embedded COM type by using the CoClass causes an error.</span></span>  
  
 <span data-ttu-id="8ec1f-127">Festlegen der `/link` option [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]einen Assemblyverweis hinzu, und legen die `Embed Interop Types` -Eigenschaft **true**.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-127">To set the `/link` option in [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], add an assembly reference and set the `Embed Interop Types` property to **true**.</span></span> <span data-ttu-id="8ec1f-128">Die Standardeinstellung für die `Embed Interop Types` Eigenschaft **false**.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-128">The default for the `Embed Interop Types` property is **false**.</span></span>  
  
 <span data-ttu-id="8ec1f-129">Wenn Sie eine COM-Assembly (Assembly A) verknüpfen, verweist auf eine andere COM-Assembly (Assembly B), müssen Sie auch mit der Assembly B zu verknüpfen, wenn eine der folgenden Aussagen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8ec1f-129">If you link to a COM assembly (Assembly A) which itself references another COM assembly (Assembly B), you also have to link to Assembly B if either of the following is true:</span></span>  
  
-   <span data-ttu-id="8ec1f-130">Ein Typ von Assembly A erbt von einem Typ oder implementiert eine Schnittstelle aus Assembly B.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-130">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
-   <span data-ttu-id="8ec1f-131">Ein Feld, Eigenschaft, Ereignis oder -Methode, die einen Rückgabetyp für oder Parametertyp aus Assembly B wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-131">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="8ec1f-132">Verwendung [/LIBPATH](../../../visual-basic/reference/command-line-compiler/libpath.md) an das Verzeichnis, in dem eine oder mehrere der Assemblyverweise befindet.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-132">Use [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="8ec1f-133">Wie die [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) -Compileroption, die `/link` -Compileroption verwendet der Vbc.rsp-Antwortdatei, die häufig Verweise verwendet [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Assemblys.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-133">Like the [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) compiler option, the `/link` compiler option uses the Vbc.rsp response file, which references frequently used [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies.</span></span> <span data-ttu-id="8ec1f-134">Verwenden Sie die [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) (Compileroption), wenn Sie nicht, dass den Compiler die Datei Vbc.rsp verwendet möchten.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-134">Use the [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) compiler option if you do not want the compiler to use the Vbc.rsp file.</span></span>  
  
 <span data-ttu-id="8ec1f-135">Die Kurzform der `/link` ist `/l`.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-135">The short form of `/link` is `/l`.</span></span>  
  
## <a name="generics-and-embedded-types"></a><span data-ttu-id="8ec1f-136">Generika und eingebettete Typen</span><span class="sxs-lookup"><span data-stu-id="8ec1f-136">Generics and Embedded Types</span></span>  
 <span data-ttu-id="8ec1f-137">In den folgenden Abschnitten werden die Einschränkungen beschrieben, über die Verwendung von generischer Typen in Clientanwendungen, die Interop-Typen einbetten.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-137">The following sections describe the limitations on using generic types in applications that embed interop types.</span></span>  
  
### <a name="generic-interfaces"></a><span data-ttu-id="8ec1f-138">Generische Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8ec1f-138">Generic Interfaces</span></span>  
 <span data-ttu-id="8ec1f-139">Generische Schnittstellen, die von einer Interop-Assembly eingebettet sind, können nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-139">Generic interfaces that are embedded from an interop assembly cannot be used.</span></span> <span data-ttu-id="8ec1f-140">Dies wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-140">This is shown in the following example.</span></span>  
  
 <span data-ttu-id="8ec1f-141">[!code-vb[VbLinkCompiler&#1;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8ec1f-141">[!code-vb[VbLinkCompiler#1](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_1.vb)]</span></span>  
  
### <a name="types-that-have-generic-parameters"></a><span data-ttu-id="8ec1f-142">Typen, die generische Parameter aufweisen</span><span class="sxs-lookup"><span data-stu-id="8ec1f-142">Types That Have Generic Parameters</span></span>  
 <span data-ttu-id="8ec1f-143">Typen, die einen generischen Parameter verfügen, deren Typ aus einer Interop-Assembly eingebettet ist, nicht wenn vorgesehen, die aus einer externen Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-143">Types that have a generic parameter whose type is embedded from an interop assembly cannot be used if that type is from an external assembly.</span></span> <span data-ttu-id="8ec1f-144">Diese Einschränkung gilt nicht für Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-144">This restriction does not apply to interfaces.</span></span> <span data-ttu-id="8ec1f-145">Betrachten Sie z. B. die <xref:Microsoft.Office.Interop.Excel.Range>-Schnittstelle, die in definiert ist die <xref:Microsoft.Office.Interop.Excel>Assembly.</xref:Microsoft.Office.Interop.Excel> </xref:Microsoft.Office.Interop.Excel.Range></span><span class="sxs-lookup"><span data-stu-id="8ec1f-145">For example, consider the <xref:Microsoft.Office.Interop.Excel.Range> interface that is defined in the <xref:Microsoft.Office.Interop.Excel> assembly.</span></span> <span data-ttu-id="8ec1f-146">Wenn eine Bibliothek Interop-Typen aus bettet die <xref:Microsoft.Office.Interop.Excel>Assembly und stellt eine Methode, die einem generischen Typ, der einen Parameter, dessen Typ zurückgegeben wird die <xref:Microsoft.Office.Interop.Excel.Range>Schnittstelle, muss diese Methode eine generische Schnittstelle zurückgeben, wie im folgenden Codebeispiel gezeigt.</xref:Microsoft.Office.Interop.Excel.Range> </xref:Microsoft.Office.Interop.Excel></span><span class="sxs-lookup"><span data-stu-id="8ec1f-146">If a library embeds interop types from the <xref:Microsoft.Office.Interop.Excel> assembly and exposes a method that returns a generic type that has a parameter whose type is the <xref:Microsoft.Office.Interop.Excel.Range> interface, that method must return a generic interface, as shown in the following code example.</span></span>  
  
 <span data-ttu-id="8ec1f-147">[!code-vb[VbLinkCompiler&#2;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="8ec1f-147">[!code-vb[VbLinkCompiler#2](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_2.vb)]</span></span>  
<span data-ttu-id="8ec1f-148">[!code-vb[VbLinkCompiler&3;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="8ec1f-148">[!code-vb[VbLinkCompiler#3](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_3.vb)]</span></span>  
<span data-ttu-id="8ec1f-149">[!code-vb[VbLinkCompiler&4;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="8ec1f-149">[!code-vb[VbLinkCompiler#4](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_4.vb)]</span></span>  
  
 <span data-ttu-id="8ec1f-150">Im folgenden Beispiel Clientcode die Methode, die zurückgibt Aufrufen der <xref:System.Collections.IList>generische Schnittstelle ohne Fehler.</xref:System.Collections.IList></span><span class="sxs-lookup"><span data-stu-id="8ec1f-150">In the following example, client code can call the method that returns the <xref:System.Collections.IList> generic interface without error.</span></span>  
  
 <span data-ttu-id="8ec1f-151">[!code-vb[VbLinkCompiler&5;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="8ec1f-151">[!code-vb[VbLinkCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_5.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ec1f-152">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8ec1f-152">Example</span></span>  
 <span data-ttu-id="8ec1f-153">Im folgenden Code wird die Quelldatei `OfficeApp.vb` und verweisen auf Assemblys aus `COMData1.dll` und `COMData2.dll` zu `OfficeApp.exe`.</span><span class="sxs-lookup"><span data-stu-id="8ec1f-153">The following code compiles source file `OfficeApp.vb` and reference assemblies from `COMData1.dll` and `COMData2.dll` to produce `OfficeApp.exe`.</span></span>  
  
```vb  
vbc /link:COMData1.dll,COMData2.dll /out:OfficeApp.exe OfficeApp.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="8ec1f-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ec1f-154">See Also</span></span>  
 <span data-ttu-id="8ec1f-155">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="8ec1f-155">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="8ec1f-156"> [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21) </span><span class="sxs-lookup"><span data-stu-id="8ec1f-156"> [Walkthrough: Embedding Types from Managed Assemblies](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21) </span></span>  
<span data-ttu-id="8ec1f-157"> [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span><span class="sxs-lookup"><span data-stu-id="8ec1f-157"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span></span>  
<span data-ttu-id="8ec1f-158"> [/ noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span><span class="sxs-lookup"><span data-stu-id="8ec1f-158"> [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span></span>  
<span data-ttu-id="8ec1f-159"> [/ LIBPATH](../../../visual-basic/reference/command-line-compiler/libpath.md) </span><span class="sxs-lookup"><span data-stu-id="8ec1f-159"> [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) </span></span>  
<span data-ttu-id="8ec1f-160"> [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="8ec1f-160"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="8ec1f-161"> [Einführung in COM-Interop](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)</span><span class="sxs-lookup"><span data-stu-id="8ec1f-161"> [Introduction to COM Interop](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)</span></span>
