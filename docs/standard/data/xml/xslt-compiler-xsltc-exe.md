---
title: XSLT-Compiler (xsltc.exe)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 672a5ac8-8305-4d28-ba10-11089c2c0924
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 1148af537ef9b502c6f3a9a3cc0588eaed39ac2f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="xslt-compiler-xsltcexe"></a><span data-ttu-id="2e839-102">XSLT-Compiler (xsltc.exe)</span><span class="sxs-lookup"><span data-stu-id="2e839-102">XSLT Compiler (xsltc.exe)</span></span>
<span data-ttu-id="2e839-103">Der XSLT-Compiler (xsltc.exe) kompiliert XSLT-Stylesheets und generiert eine Assembly.</span><span class="sxs-lookup"><span data-stu-id="2e839-103">The XSLT compiler (xsltc.exe) compiles XSLT style sheets and generates an assembly.</span></span> <span data-ttu-id="2e839-104">Das kompilierte Stylesheet kann dann direkt in die <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType>-Methode übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="2e839-104">The compiled style sheet can then be passed directly into the <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="2e839-105">Sie können mit xsltc.exe keine signierten Assemblys generieren.</span><span class="sxs-lookup"><span data-stu-id="2e839-105">You cannot generate signed assemblies with xsltc.exe.</span></span>  
  
 <span data-ttu-id="2e839-106">Das Tool <legacyBold>xsltc.exe</legacyBold> ist Bestandteil von Visual Studio 2008.</span><span class="sxs-lookup"><span data-stu-id="2e839-106">The xsltc.exe tool is included with Visual Studio 2008.</span></span> <span data-ttu-id="2e839-107">Weitere Informationen finden Sie im [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkId=89463).</span><span class="sxs-lookup"><span data-stu-id="2e839-107">For more information, see the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkId=89463).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e839-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="2e839-108">Syntax</span></span>  
  
```  
xsltc [options] [/class:<name>] <sourceFile> [[/class:<name>] <sourceFile>...]  
```  
  
## <a name="argument"></a><span data-ttu-id="2e839-109">Argument</span><span class="sxs-lookup"><span data-stu-id="2e839-109">Argument</span></span>  
  
|<span data-ttu-id="2e839-110">Argument</span><span class="sxs-lookup"><span data-stu-id="2e839-110">Argument</span></span>|<span data-ttu-id="2e839-111">description</span><span class="sxs-lookup"><span data-stu-id="2e839-111">Description</span></span>|  
|--------------|-----------------|  
|`sourceFile`|<span data-ttu-id="2e839-112">Gibt den Namen des Stylesheets an.</span><span class="sxs-lookup"><span data-stu-id="2e839-112">Specifies the name of the style sheet.</span></span> <span data-ttu-id="2e839-113">Das Stylesheet muss eine lokale Datei sein oder sich im Intranet befinden.</span><span class="sxs-lookup"><span data-stu-id="2e839-113">The style sheet must be a local file or be located on the intranet.</span></span>|  
  
## <a name="options"></a><span data-ttu-id="2e839-114">Optionen</span><span class="sxs-lookup"><span data-stu-id="2e839-114">Options</span></span>  
  
|<span data-ttu-id="2e839-115">Option</span><span class="sxs-lookup"><span data-stu-id="2e839-115">Option</span></span>|<span data-ttu-id="2e839-116">description</span><span class="sxs-lookup"><span data-stu-id="2e839-116">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2e839-117">`/c[lass]:` `name`</span><span class="sxs-lookup"><span data-stu-id="2e839-117">`/c[lass]:` `name`</span></span>|<span data-ttu-id="2e839-118">Gibt den Namen der Klasse für das folgende Stylesheet an.</span><span class="sxs-lookup"><span data-stu-id="2e839-118">Specifies the name of the class for the following style sheet.</span></span> <span data-ttu-id="2e839-119">Der Klassenname kann vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="2e839-119">The class name can be fully qualified.</span></span><br /><br /> <span data-ttu-id="2e839-120">In der Standardeinstellung ist der Klassenname mit dem Namen des Stylesheets identisch.</span><span class="sxs-lookup"><span data-stu-id="2e839-120">The class name defaults to the name of the style sheet.</span></span> <span data-ttu-id="2e839-121">Wenn zum Beispiel das Stylesheet <legacyBold>customers.xsl</legacyBold> kompiliert wird, lautet der standardmäßige Klassenname <legacyBold>customers</legacyBold>.</span><span class="sxs-lookup"><span data-stu-id="2e839-121">For example, if the style sheet customers.xsl is compiled, the default class name is customers.</span></span>|  
|<span data-ttu-id="2e839-122">`/debug[`+&#124;-`]`</span><span class="sxs-lookup"><span data-stu-id="2e839-122">`/debug[`+&#124;-`]`</span></span>|<span data-ttu-id="2e839-123">Gibt an, ob Debuginformationen generiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2e839-123">Specifies whether to generate debugging information.</span></span><br /><br /> <span data-ttu-id="2e839-124">Wenn `+` oder `/debug` angegeben wird, generiert der Compiler Debuginformationen und speichert sie in einer Programmdatenbankdatei (PDB-Datei).</span><span class="sxs-lookup"><span data-stu-id="2e839-124">Specifying `+` or `/debug`, causes the compiler to generate debugging information and put it in a program database (PDB) file.</span></span> <span data-ttu-id="2e839-125">Der Name der generierten PDB-Datei lautet `assemblyName`.pdb.</span><span class="sxs-lookup"><span data-stu-id="2e839-125">The name of the generated PDB file is `assemblyName`.pdb.</span></span><br /><br /> <span data-ttu-id="2e839-126">Wenn Sie `-` angeben, was im Endeffekt dasselbe ist, wie `/debug` nicht anzugeben, werden keine Debuginformationen erstellt.</span><span class="sxs-lookup"><span data-stu-id="2e839-126">Specifying `-`, which is in effect if you do not specify `/debug`, causes no debug information to be created.</span></span> <span data-ttu-id="2e839-127">Es wird eine Retailassembly generiert.</span><span class="sxs-lookup"><span data-stu-id="2e839-127">A retail assembly is generated.</span></span> <span data-ttu-id="2e839-128">**Hinweis:** Beim Kompilieren im Debugmodus kann sich die XSLT-Leistung spürbar verringern.</span><span class="sxs-lookup"><span data-stu-id="2e839-128">**Note:**  Compiling in debug mode can affect XSLT performance significantly.</span></span>|  
|`/help`|<span data-ttu-id="2e839-129">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="2e839-129">Displays command syntax and options for the tool.</span></span>|  
|`/nologo`|<span data-ttu-id="2e839-130">Unterdrückt die Anzeige der Compilercopyrightmeldung.</span><span class="sxs-lookup"><span data-stu-id="2e839-130">Suppresses the compiler copyright message from displaying.</span></span>|  
|<span data-ttu-id="2e839-131">`/platform:` `string`</span><span class="sxs-lookup"><span data-stu-id="2e839-131">`/platform:` `string`</span></span>|<span data-ttu-id="2e839-132">Gibt die Plattformen an, auf denen die Assembly ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="2e839-132">Specifies the platforms that the assembly can be run on.</span></span> <span data-ttu-id="2e839-133">Im Folgenden werden die gültigen Plattformwerte beschrieben:</span><span class="sxs-lookup"><span data-stu-id="2e839-133">The following describes the valid platform values:</span></span><br /><br /> <span data-ttu-id="2e839-134">`x86` kompiliert die Assembly für die 32-Bit-x86-kompatible CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="2e839-134">`x86` compiles your assembly to be run by the 32-bit, x86-compatible common language runtime</span></span><br /><br /> <span data-ttu-id="2e839-135">`x64` kompiliert die Assembly für die 64-Bit-CLR auf einem Computer, der den AMD64- oder EM64T-Anweisungssatz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2e839-135">`x64` compiles your assembly to be run by the 64-bit common language runtime on a computer that supports the AMD64 or EM64T instruction set.</span></span><br /><br /> [!INCLUDE[vcpritanium](../../../../includes/vcpritanium-md.md)]<span data-ttu-id="2e839-136"> kompiliert die Assembly für die 64-Bit-CLR (Common Language Runtime) auf einem Computer mit einem [!INCLUDE[vcpritanium](../../../../includes/vcpritanium-md.md)]-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="2e839-136"> compiles your assembly to be run by the 64-bit common language runtime on a computer that has an [!INCLUDE[vcpritanium](../../../../includes/vcpritanium-md.md)] processor.</span></span><br /><br /> <span data-ttu-id="2e839-137">`anycpu` kompiliert die Assembly für die Ausführung auf einer beliebigen Plattform.</span><span class="sxs-lookup"><span data-stu-id="2e839-137">`anycpu` compiles your assembly to run on any platform.</span></span> <span data-ttu-id="2e839-138">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="2e839-138">This is the default.</span></span>|  
|<span data-ttu-id="2e839-139">`/out:` `assemblyName`</span><span class="sxs-lookup"><span data-stu-id="2e839-139">`/out:` `assemblyName`</span></span>|<span data-ttu-id="2e839-140">Gibt den Namen der Assembly an, die ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2e839-140">Specifies the name of the assembly that is output.</span></span> <span data-ttu-id="2e839-141">Der Assemblyname entspricht standardmäßig dem Namen des Hauptstylesheets bzw. des ersten Stylesheets, falls es mehrere Stylesheets gibt.</span><span class="sxs-lookup"><span data-stu-id="2e839-141">The assembly name defaults to the name of the main style sheet or the first style sheet if multiple style sheets are present.</span></span><br /><br /> <span data-ttu-id="2e839-142">Wenn das Stylesheet Skripts enthält, werden die Skripts in einer separaten Assembly gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2e839-142">If the style sheet contains scripts, the scripts are saved to a separate assembly.</span></span> <span data-ttu-id="2e839-143">Die Namen der Skriptassemblys werden auf der Grundlage des Namens der Hauptassembly generiert.</span><span class="sxs-lookup"><span data-stu-id="2e839-143">Script assembly names are generated from the main assembly name.</span></span> <span data-ttu-id="2e839-144">Wenn Sie z. B. als Assemblynamen <legacyBold>CustOrders.dll</legacyBold> angegeben haben, wird die erste Skriptassembly <legacyBold>CustOrders_Script1.dll</legacyBold> genannt.</span><span class="sxs-lookup"><span data-stu-id="2e839-144">For example, if you specified CustOrders.dll for your assembly name, the first script assembly is named CustOrders_Script1.dll.</span></span>|  
|<span data-ttu-id="2e839-145">`/settings:` `document+-, script+-, DTD+-,`</span><span class="sxs-lookup"><span data-stu-id="2e839-145">`/settings:` `document+-, script+-, DTD+-,`</span></span>|<span data-ttu-id="2e839-146">Gibt an, ob `document()`-Funktionen, XSLT-Skripts oder Dokumenttypdefinitionen (DTD) im Stylesheet zugelassen sind.</span><span class="sxs-lookup"><span data-stu-id="2e839-146">Specifies whether to allow `document()` functions, XSLT script, or document type definition (DTD) in the style sheet.</span></span><br /><br /> <span data-ttu-id="2e839-147">In der Standardeinstellung werden DTD, die `document()`-Funktion und Skripts nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2e839-147">The default behavior disables support for DTD, the `document()` function and scripting.</span></span>|  
|<span data-ttu-id="2e839-148">`@` `file`</span><span class="sxs-lookup"><span data-stu-id="2e839-148">`@` `file`</span></span>|<span data-ttu-id="2e839-149">Ermöglicht die Angabe einer Datei, die Compileroptionen enthält.</span><span class="sxs-lookup"><span data-stu-id="2e839-149">Lets you specify a file that contains the compiler options.</span></span>|  
|`?`|<span data-ttu-id="2e839-150">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="2e839-150">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e839-151">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2e839-151">Remarks</span></span>  
 <span data-ttu-id="2e839-152">XSLT-Lösungen können aus mehreren Stylesheetmodulen bestehen.</span><span class="sxs-lookup"><span data-stu-id="2e839-152">XSLT solutions can consist of multiple style sheet modules.</span></span> <span data-ttu-id="2e839-153">Das Tool <legacyBold>xsltc.exe</legacyBold> generiert Assemblys auf der Grundlage von Stylesheets.</span><span class="sxs-lookup"><span data-stu-id="2e839-153">The xsltc.exe tool generates assemblies from style sheets.</span></span> <span data-ttu-id="2e839-154">Die Assemblys können dann direkt in die <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType>-Methode übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="2e839-154">The assemblies can then be passed into the <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="2e839-155">Auf diese Weise lassen sich in einigen XSLT-Bereitstellungsszenarios die zu verzeichnenden Leistungseinbußen verringern.</span><span class="sxs-lookup"><span data-stu-id="2e839-155">This can help decrease performance costs in some XSLT deployment scenarios.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e839-156">Sie müssen auch die kompilierte Assembly als Verweis in die Anwendung einschließen.</span><span class="sxs-lookup"><span data-stu-id="2e839-156">You must also include the compiled assembly as a reference in your application.</span></span>  
  
 <span data-ttu-id="2e839-157">Das Tool „xsltc.exe“ überprüft weder den Namen der Klasse (`/class:``name`) noch den der Assembly (`/out:``assemblyName`).</span><span class="sxs-lookup"><span data-stu-id="2e839-157">The xsltc.exe tool does not validate the class (`/class:``name`) or assembly (`/out:``assemblyName`) names.</span></span> <span data-ttu-id="2e839-158">Wenn die Namen nicht gültig sind, gibt die CLR entsprechende Fehlermeldungen aus.</span><span class="sxs-lookup"><span data-stu-id="2e839-158">Errors are thrown by the common language runtime if the names are not valid.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2e839-159">Beispiele</span><span class="sxs-lookup"><span data-stu-id="2e839-159">Examples</span></span>  
 <span data-ttu-id="2e839-160">Der folgende Befehl kompiliert das Stylesheet und erstellt eine Assembly mit dem Namen <legacyBold>booksort.dll</legacyBold>.</span><span class="sxs-lookup"><span data-stu-id="2e839-160">The following command compiles the style sheet and creates an assembly named booksort.dll.</span></span>  
  
```  
xsltc booksort.xsl  
```  
  
 <span data-ttu-id="2e839-161">Der folgende Befehl kompiliert das Stylesheet und erstellt eine Assembly mit dem Namen <legacyBold>booksort.dll</legacyBold> und eine PDB-Datei mit dem Namen <legacyBold>booksort.pdb</legacyBold>.</span><span class="sxs-lookup"><span data-stu-id="2e839-161">The following command compiles the style sheet and creates an assembly and PDB file that are named booksort.dll and booksort.pdb respectively.</span></span>  
  
```  
xsltc booksort.xsl /debug  
```  
  
 <span data-ttu-id="2e839-162">Der folgende Befehl kompiliert ein Stylesheet, das ein <legacyBold>msxsl:script</legacyBold>-Element enthält, und erstellt zwei Assemblys namens <legacyBold>calc.dll</legacyBold> und <legacyBold>calc_Script1.dll</legacyBold>.</span><span class="sxs-lookup"><span data-stu-id="2e839-162">The following command compiles a style sheet that contains an msxsl:script element and creates two assemblies named calc.dll and calc_Script1.dll.</span></span>  
  
```  
xsltc /settings:script+ calc.xsl  
```  
  
 <span data-ttu-id="2e839-163">Der folgende Befehl aktiviert die DTD-Verarbeitung und die Unterstützung für Skripts und erstellt zwei Assemblys namens <legacyBold>myTest.dll</legacyBold> und <legacyBold>myTest_Script1.dll</legacyBold>.</span><span class="sxs-lookup"><span data-stu-id="2e839-163">The following command enables DTD processing and script support and creates two assemblies named myTest.dll and myTest_Script1.dll.</span></span>  
  
```  
xsltc /settings:DTD+,script+ /out:myTest calc.xsl  
```  
  
 <span data-ttu-id="2e839-164">Der folgende Befehl kompiliert zwei Stylesheetmodule und eine Assembly mit dem Namen <legacyBold>booksort.dll</legacyBold>.</span><span class="sxs-lookup"><span data-stu-id="2e839-164">The following command compiles two style sheet modules and creates a single assembly named booksort.dll.</span></span>  
  
```  
xsltc booksort.xsl output.xsl  
```  
  
## <a name="see-also"></a><span data-ttu-id="2e839-165">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e839-165">See Also</span></span>  
 <xref:System.Xml.Xsl.XslCompiledTransform>  
 [<span data-ttu-id="2e839-166">Vorgehensweise: Ausführen einer XSLT-Transformation mittels einer Assembly</span><span class="sxs-lookup"><span data-stu-id="2e839-166">How to: Perform an XSLT Transformation by Using an Assembly</span></span>](../../../../docs/standard/data/xml/how-to-perform-an-xslt-transformation-by-using-an-assembly.md)  
 [<span data-ttu-id="2e839-167">XSLT Transformations (XSLT-Transformationen)</span><span class="sxs-lookup"><span data-stu-id="2e839-167">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)
