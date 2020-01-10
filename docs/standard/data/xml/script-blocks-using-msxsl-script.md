---
title: Skriptblöcke, die "msxsl:script" verwenden
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: fde6f43f-c594-486f-abcb-2211197fae20
ms.openlocfilehash: a63452df16e452a90eff3977ac8726cc0a5ac439
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710192"
---
# <a name="script-blocks-using-msxslscript"></a><span data-ttu-id="98167-102">Skriptblöcke, die "msxsl:script" verwenden</span><span class="sxs-lookup"><span data-stu-id="98167-102">Script Blocks Using msxsl:script</span></span>
<span data-ttu-id="98167-103">Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse unterstützt eingebettete Skripts unter Verwendung des `msxsl:script`-Elements.</span><span class="sxs-lookup"><span data-stu-id="98167-103">The <xref:System.Xml.Xsl.XslCompiledTransform> class supports embedded scripts using the `msxsl:script` element.</span></span> <span data-ttu-id="98167-104">Beim Laden des Stylesheets werden alle definierten Funktionen von CodeDOM (Code Document Object Model) in die Microsoft Intermediate Language (MSIL) kompiliert und zur Laufzeit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="98167-104">When the style sheet is loaded, any defined functions are compiled to Microsoft intermediate language (MSIL) by the Code Document Object Model (CodeDOM) and are executed during run time.</span></span> <span data-ttu-id="98167-105">Die aus dem eingebetteten Skriptblock generierte Assembly und die für das Stylesheet generierte Assembly sind voneinander verschieden.</span><span class="sxs-lookup"><span data-stu-id="98167-105">The assembly generated from the embedded script block is separate than the assembly generated for the style sheet.</span></span>  
  
## <a name="enable-xslt-script"></a><span data-ttu-id="98167-106">Aktivieren von XSLT-Skript</span><span class="sxs-lookup"><span data-stu-id="98167-106">Enable XSLT Script</span></span>  
 <span data-ttu-id="98167-107">Die Unterstützung für eingebettete Skripts ist eine optionale XSLT-Einstellung für die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="98167-107">Support for embedded scripts is an optional XSLT setting on the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="98167-108">Die Skriptunterstützung ist in der Standardeinstellung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="98167-108">Script support is disabled by default.</span></span> <span data-ttu-id="98167-109">Sie können die Skriptunterstützung aktivieren, indem Sie ein <xref:System.Xml.Xsl.XsltSettings>-Objekt erstellen, bei dem die <xref:System.Xml.Xsl.XsltSettings.EnableScript%2A>-Eigenschaft auf `true` festgelegt wurde, und das Objekt an die <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>-Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="98167-109">To enable script support, create an <xref:System.Xml.Xsl.XsltSettings> object with the <xref:System.Xml.Xsl.XsltSettings.EnableScript%2A> property set to `true` and pass the object to the <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="98167-110">XSLT-Skripts sollten nur aktiviert werden, wenn eine Skriptunterstützung erforderlich ist und Sie mit einer vollständig vertrauenswürdigen Umgebung arbeiten.</span><span class="sxs-lookup"><span data-stu-id="98167-110">XSLT scripting should be enabled only if you require script support and you are working in a fully trusted environment.</span></span>  
  
## <a name="msxslscript-element-definition"></a><span data-ttu-id="98167-111">Elementdefinition von "msxsl:script"</span><span class="sxs-lookup"><span data-stu-id="98167-111">msxsl:script Element Definition</span></span>  
 <span data-ttu-id="98167-112">Das `msxsl:script`-Element ist eine Microsoft-Erweiterung der XSLT 1.0-Empfehlung und weist folgende Definition auf:</span><span class="sxs-lookup"><span data-stu-id="98167-112">The `msxsl:script` element is a Microsoft extension to the XSLT 1.0 recommendation and has the following definition:</span></span>  
  
```xml  
<msxsl:script language = "language-name" implements-prefix = "prefix of user namespace"> </msxsl:script>  
```  
  
 <span data-ttu-id="98167-113">Das `msxsl`-Präfix ist an den `urn:schemas-microsoft-com:xslt`-Namespace-URI gebunden.</span><span class="sxs-lookup"><span data-stu-id="98167-113">The `msxsl` prefix is bound to the `urn:schemas-microsoft-com:xslt` namespace URI.</span></span> <span data-ttu-id="98167-114">Das Stylesheet muss die `xmlns:msxsl=urn:schemas-microsoft-com:xslt`-Namespacedeklaration enthalten.</span><span class="sxs-lookup"><span data-stu-id="98167-114">The style sheet must include the `xmlns:msxsl=urn:schemas-microsoft-com:xslt` namespace declaration.</span></span>  
  
 <span data-ttu-id="98167-115">Das `language`-Attribut ist optional.</span><span class="sxs-lookup"><span data-stu-id="98167-115">The `language` attribute is optional.</span></span> <span data-ttu-id="98167-116">Sein Wert entspricht der Codesprache des eingebetteten Codeblocks.</span><span class="sxs-lookup"><span data-stu-id="98167-116">Its value is the code language of the embedded code block.</span></span> <span data-ttu-id="98167-117">Die Sprache wird mithilfe der <xref:System.CodeDom.Compiler.CodeDomProvider.CreateProvider%2A?displayProperty=nameWithType>-Methode dem entsprechenden CodeDOM-Compiler zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="98167-117">The language is mapped to the appropriate CodeDOM compiler using the <xref:System.CodeDom.Compiler.CodeDomProvider.CreateProvider%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="98167-118">Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse unterstützt alle Microsoft .NET-Sprachen, vorausgesetzt, der entsprechende Anbieter ist auf dem Computer installiert und im Abschnitt "system.codedom" der Datei "machine.config" registriert.</span><span class="sxs-lookup"><span data-stu-id="98167-118">The <xref:System.Xml.Xsl.XslCompiledTransform> class can support any Microsoft .NET language, assuming the appropriate provider is installed on the machine and is registered in the system.codedom section of the machine.config file.</span></span> <span data-ttu-id="98167-119">Wenn kein `language`-Attribut angegeben ist, wird die Standardsprache JScript verwendet.</span><span class="sxs-lookup"><span data-stu-id="98167-119">If a `language` attribute is not specified, the language defaults to JScript.</span></span> <span data-ttu-id="98167-120">Beim Namen der Sprache wird die Groß- und Kleinschreibung nicht berücksichtigt, daher sind "JavaScript" und "javascript" identisch.</span><span class="sxs-lookup"><span data-stu-id="98167-120">The language name is not case-sensitive so 'JavaScript' and 'javascript' are equivalent.</span></span>  
  
 <span data-ttu-id="98167-121">Das `implements-prefix`-Attribut ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="98167-121">The `implements-prefix` attribute is mandatory.</span></span> <span data-ttu-id="98167-122">Mit diesem Attribut wird ein Namespace deklariert und mit dem Skriptblock verknüpft.</span><span class="sxs-lookup"><span data-stu-id="98167-122">This attribute is used to declare a namespace and associate it with the script block.</span></span> <span data-ttu-id="98167-123">Der Wert dieses Attributs ist das Präfix, das den Namespace darstellt.</span><span class="sxs-lookup"><span data-stu-id="98167-123">The value of this attribute is the prefix that represents the namespace.</span></span> <span data-ttu-id="98167-124">Dieses Präfix kann an einer beliebigen Stelle im Stylesheet definiert werden.</span><span class="sxs-lookup"><span data-stu-id="98167-124">This prefix can be defined somewhere in a style sheet.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="98167-125">Bei Verwendung des `msxsl:script`-Elements wird dringend empfohlen, das Skript ungeachtet der verwendeten Sprache in einem CDATA-Abschnitt zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="98167-125">When using the `msxsl:script` element, we strongly recommend that the script, regardless of language, be placed inside a CDATA section.</span></span> <span data-ttu-id="98167-126">Da das Skript Operatoren, Bezeichner oder Trennzeichen für eine bestimmte Sprache enthalten kann, wenn es nicht in einem CDATA-Abschnitt enthalten ist, kann es möglicherweise als XML fehlinterpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="98167-126">Because the script can contain operators, identifiers, or delimiters for a given language, if it is not contained within a CDATA section, it has the potential of being misinterpreted as XML.</span></span> <span data-ttu-id="98167-127">Der folgende XML-Code zeigt eine Vorlage des CDATA-Abschnitts, in dem Code platziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="98167-127">The following XML shows a template of the CDATA section where code can be placed.</span></span>  
  
```xml  
<msxsl:script implements-prefix='your-prefix' language='CSharp'>  
<![CDATA[  
// Code block.  
]]>  
</msxsl:script>  
```  
  
## <a name="script-functions"></a><span data-ttu-id="98167-128">Skriptfunktionen</span><span class="sxs-lookup"><span data-stu-id="98167-128">Script Functions</span></span>  
 <span data-ttu-id="98167-129">Funktionen können innerhalb des `msxsl:script`-Elements deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="98167-129">Functions can be declared within the `msxsl:script` element.</span></span> <span data-ttu-id="98167-130">Wenn eine Funktion deklariert wurde, ist sie in einem Skriptblock enthalten.</span><span class="sxs-lookup"><span data-stu-id="98167-130">When a function is declared, it is contained in a script block.</span></span> <span data-ttu-id="98167-131">Stylesheets können mehrere voneinander unabhängige Skriptblöcke enthalten.</span><span class="sxs-lookup"><span data-stu-id="98167-131">Style sheets can contain multiple script blocks, each operating independent of the other.</span></span> <span data-ttu-id="98167-132">Sie können daher bei der Ausführung innerhalb eines Skriptblocks nur dann eine Funktion aufrufen, die Sie in einem anderen Skriptblock definiert haben, wenn diese Funktion so deklariert wurde, dass sie den gleichen Namespace und die gleiche Skriptsprache verwendet.</span><span class="sxs-lookup"><span data-stu-id="98167-132">That means that if you are executing inside a script block, you cannot call a function that you defined in another script block unless it is declared to have the same namespace and the same scripting language.</span></span> <span data-ttu-id="98167-133">Da jeder Skriptblock in einer eigenen Sprache vorliegen kann und der Block gemäß der Grammatikregeln für den betreffenden Sprachparser analysiert wird, wird empfohlen, die korrekte Syntax für die verwendete Sprache einzuhalten.</span><span class="sxs-lookup"><span data-stu-id="98167-133">Because each script block can be in its own language, and the block is parsed according to the grammar rules of that language parser we recommend that you use the correct syntax for the language in use.</span></span> <span data-ttu-id="98167-134">Verwenden Sie z. B. in einem Microsoft C#-Skriptblock die Kommentarsyntax von C#.</span><span class="sxs-lookup"><span data-stu-id="98167-134">For example, if you are in a Microsoft C# script block, use the C# comment syntax.</span></span>  
  
 <span data-ttu-id="98167-135">Die bereitgestellten Argumente und Rückgabewerte für die Funktion können einen beliebigen Typ aufweisen.</span><span class="sxs-lookup"><span data-stu-id="98167-135">The supplied arguments and return values to the function can be of any type.</span></span> <span data-ttu-id="98167-136">Da die XPath-Typen des W3C eine Teilmenge der CLR-Typen (Common Language Runtime) sind, findet die Typkonvertierung für Typen statt, die nicht als XPath-Typen betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="98167-136">Because the W3C XPath types are a subset of the common language runtime (CLR) types, type conversion takes place on types that are not considered to be an XPath type.</span></span> <span data-ttu-id="98167-137">In der folgenden Tabelle werden die entsprechenden W3C-Typen und die äquivalenten CLR-Typen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="98167-137">The following table shows the corresponding W3C types and the equivalent CLR type.</span></span>  
  
|<span data-ttu-id="98167-138">W3C-Typ</span><span class="sxs-lookup"><span data-stu-id="98167-138">W3C type</span></span>|<span data-ttu-id="98167-139">CLR-Typ</span><span class="sxs-lookup"><span data-stu-id="98167-139">CLR type</span></span>|  
|--------------|--------------|  
|`String`|<xref:System.String>|  
|`Boolean`|<xref:System.Boolean>|  
|`Number`|<xref:System.Double>|  
|`Result Tree Fragment`|<xref:System.Xml.XPath.XPathNavigator>|  
|`Node Set`|<xref:System.Xml.XPath.XPathNodeIterator>|  
  
 <span data-ttu-id="98167-140">Numerische CLR-Typen werden in <xref:System.Double> konvertiert.</span><span class="sxs-lookup"><span data-stu-id="98167-140">CLR numeric types are converted to <xref:System.Double>.</span></span> <span data-ttu-id="98167-141">Der <xref:System.DateTime>-Typ wird in <xref:System.String> konvertiert.</span><span class="sxs-lookup"><span data-stu-id="98167-141">The <xref:System.DateTime> type is converted to <xref:System.String>.</span></span> <span data-ttu-id="98167-142"><xref:System.Xml.XPath.IXPathNavigable>-Typen werden in <xref:System.Xml.XPath.XPathNavigator> konvertiert.</span><span class="sxs-lookup"><span data-stu-id="98167-142"><xref:System.Xml.XPath.IXPathNavigable> types are converted to <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="98167-143">**XPathNavigator[]** wird in <xref:System.Xml.XPath.XPathNodeIterator> konvertiert.</span><span class="sxs-lookup"><span data-stu-id="98167-143">**XPathNavigator[]** is converted to <xref:System.Xml.XPath.XPathNodeIterator>.</span></span>  
  
 <span data-ttu-id="98167-144">Alle anderen Typen lösen einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="98167-144">All other types throw an error.</span></span>  
  
### <a name="importing-namespaces-and-assemblies"></a><span data-ttu-id="98167-145">Importieren von Namespaces und Assemblys</span><span class="sxs-lookup"><span data-stu-id="98167-145">Importing Namespaces and Assemblies</span></span>  
 <span data-ttu-id="98167-146">Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse definiert eine Gruppe von Assemblys und Namespaces vor, die in der Standardeinstellung vom `msxsl:script`-Element unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="98167-146">The <xref:System.Xml.Xsl.XslCompiledTransform> class predefines a set of assemblies and namespaces that are supported by default by the `msxsl:script` element.</span></span> <span data-ttu-id="98167-147">Sie können jedoch Klassen und Member verwenden, die zu einem Namespace gehören, der nicht in der vordefinierten Liste aufgeführt ist, indem Sie die Assembly und den Namespace in den `msxsl:script`-Block importieren.</span><span class="sxs-lookup"><span data-stu-id="98167-147">However, you can use classes and members belonging to a namespace that is not on the predefined list by importing the assembly and namespace in `msxsl:script` block.</span></span>  
  
#### <a name="assemblies"></a><span data-ttu-id="98167-148">Assemblys</span><span class="sxs-lookup"><span data-stu-id="98167-148">Assemblies</span></span>  
 <span data-ttu-id="98167-149">In der Standardeinstellung wird auf die folgenden zwei Assemblys verwiesen:</span><span class="sxs-lookup"><span data-stu-id="98167-149">The following two assemblies are referenced by default:</span></span>  
  
- <span data-ttu-id="98167-150">System.dll</span><span class="sxs-lookup"><span data-stu-id="98167-150">System.dll</span></span>  
  
- <span data-ttu-id="98167-151">System.Xml.dll</span><span class="sxs-lookup"><span data-stu-id="98167-151">System.Xml.dll</span></span>  
  
- <span data-ttu-id="98167-152">Microsoft.VisualBasic.dll (bei Skriptsprache VB)</span><span class="sxs-lookup"><span data-stu-id="98167-152">Microsoft.VisualBasic.dll (when the script language is VB)</span></span>  
  
 <span data-ttu-id="98167-153">Mithilfe des `msxsl:assembly`-Elements können Sie die zusätzlichen Assemblys importieren.</span><span class="sxs-lookup"><span data-stu-id="98167-153">You can import the additional assemblies using the `msxsl:assembly` element.</span></span> <span data-ttu-id="98167-154">Dies gilt auch für die Assembly beim Kompilieren des Stylesheets.</span><span class="sxs-lookup"><span data-stu-id="98167-154">This includes the assembly when the style sheet is compiled.</span></span> <span data-ttu-id="98167-155">Das `msxsl:assembly`-Element weist folgende Definition auf:</span><span class="sxs-lookup"><span data-stu-id="98167-155">The `msxsl:assembly` element has the following definition:</span></span>  
  
```xml  
<msxsl:script>  
  <msxsl:assembly name="system.assemblyName" />  
  <msxsl:assembly href="path-name" />  
    <![CDATA[  
    // User code  
    ]]>  
</msxsl:script>  
```  
  
 <span data-ttu-id="98167-156">Das `name`-Attribut enthält den Namen der Assembly, und das `href`-Attribut enthält den Pfad der Assembly.</span><span class="sxs-lookup"><span data-stu-id="98167-156">The `name` attribute contains the name of the assembly and the `href` attribute contains the path to the assembly.</span></span> <span data-ttu-id="98167-157">Der Assemblyname kann ein vollständiger Name sein, z. B. "System.Data, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b77a5c561934e089", oder ein Kurzname wie "System.Web".</span><span class="sxs-lookup"><span data-stu-id="98167-157">The assembly name can be a full name, such as "System.Data, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b77a5c561934e089", or a short name, such as "System.Web".</span></span>  
  
#### <a name="namespaces"></a><span data-ttu-id="98167-158">-Namespaces</span><span class="sxs-lookup"><span data-stu-id="98167-158">Namespaces</span></span>  
 <span data-ttu-id="98167-159">In der Standardeinstellung sind die folgenden Namespaces enthalten:</span><span class="sxs-lookup"><span data-stu-id="98167-159">The following namespaces are included by default:</span></span>  
  
- <span data-ttu-id="98167-160">System</span><span class="sxs-lookup"><span data-stu-id="98167-160">System</span></span>  
  
- <span data-ttu-id="98167-161">System.Collection</span><span class="sxs-lookup"><span data-stu-id="98167-161">System.Collection</span></span>  
  
- <span data-ttu-id="98167-162">System.Text</span><span class="sxs-lookup"><span data-stu-id="98167-162">System.Text</span></span>  
  
- <span data-ttu-id="98167-163">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="98167-163">System.Text.RegularExpressions</span></span>  
  
- <span data-ttu-id="98167-164">System.Xml</span><span class="sxs-lookup"><span data-stu-id="98167-164">System.Xml</span></span>  
  
- <span data-ttu-id="98167-165">System.Xml.Xsl</span><span class="sxs-lookup"><span data-stu-id="98167-165">System.Xml.Xsl</span></span>  
  
- <span data-ttu-id="98167-166">System.Xml.XPath</span><span class="sxs-lookup"><span data-stu-id="98167-166">System.Xml.XPath</span></span>  
  
- <span data-ttu-id="98167-167">Microsoft.VisualBasic (bei Skriptsprache VB)</span><span class="sxs-lookup"><span data-stu-id="98167-167">Microsoft.VisualBasic (when the script language is VB)</span></span>  
  
 <span data-ttu-id="98167-168">Mithilfe des `namespace`-Attributs können Sie Unterstützung für zusätzliche Namespaces hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="98167-168">You can add support for additional namespaces using the `namespace` attribute.</span></span> <span data-ttu-id="98167-169">Der Attributwert ist der Name des Namespaces.</span><span class="sxs-lookup"><span data-stu-id="98167-169">The attribute value is the name of the namespace.</span></span>  
  
```xml  
<msxsl:script>  
  <msxsl:using namespace="system.namespaceName" />  
    <![CDATA[  
    // User code  
    ]]>  
</msxsl:script>  
```  
  
## <a name="example"></a><span data-ttu-id="98167-170">Beispiel</span><span class="sxs-lookup"><span data-stu-id="98167-170">Example</span></span>  
 <span data-ttu-id="98167-171">Im folgenden Beispiel wird der Umfang eines Kreises bei angegebenem Radius unter Verwendung eines eingebetteten Skripts berechnet.</span><span class="sxs-lookup"><span data-stu-id="98167-171">The following example uses an embedded script to calculate the circumference of a circle given its radius.</span></span>  
  
 [!code-csharp[XSLT_Script#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_Script/CS/xslt_script.cs#1)]
 [!code-vb[XSLT_Script#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_Script/VB/xslt_script.vb#1)]  
  
#### <a name="numberxml"></a><span data-ttu-id="98167-172">number.xml</span><span class="sxs-lookup"><span data-stu-id="98167-172">number.xml</span></span>  
 [!code-xml[XSLT_Script#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Script/XML/number.xml#2)]  
  
#### <a name="calcxsl"></a><span data-ttu-id="98167-173">calc.xsl</span><span class="sxs-lookup"><span data-stu-id="98167-173">calc.xsl</span></span>  
 [!code-xml[XSLT_Script#3](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Script/XML/calc.xsl#3)]  
  
### <a name="output"></a><span data-ttu-id="98167-174">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="98167-174">Output</span></span>  
  
```xml  
<circles xmlns:msxsl="urn:schemas-microsoft-com:xslt" xmlns:user="urn:my-scripts">  
  <circle>  
    <radius>12</radius>  
    <circumference>75.36</circumference>  
  </circle>  
  <circle>  
    <radius>37.5</radius>  
    <circumference>235.5</circumference>  
  </circle>  
</circles>  
```  
  
## <a name="see-also"></a><span data-ttu-id="98167-175">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98167-175">See also</span></span>

- [<span data-ttu-id="98167-176">XSLT Transformations (XSLT-Transformationen)</span><span class="sxs-lookup"><span data-stu-id="98167-176">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)
- [<span data-ttu-id="98167-177">Generieren und Kompilieren von dynamischem Quellcode</span><span class="sxs-lookup"><span data-stu-id="98167-177">Dynamic Source Code Generation and Compilation</span></span>](../../../../docs/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)
