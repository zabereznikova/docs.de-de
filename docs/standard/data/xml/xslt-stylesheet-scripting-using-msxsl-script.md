---
title: Skripterstellung für ein XSLT-Stylesheet mit <msxsl:script>
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 60e2541b-0cea-4b2e-a4fa-85f4c50f1bef
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 32695d3bc29693ab4cf1e2f9d721d35598ecfb86
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344722"
---
# <a name="xslt-stylesheet-scripting-using-msxslscript"></a><span data-ttu-id="4aae2-102">Skripterstellung für ein XSLT-Stylesheet mit \<msxsl:script></span><span class="sxs-lookup"><span data-stu-id="4aae2-102">XSLT Stylesheet Scripting Using \<msxsl:script></span></span>
<span data-ttu-id="4aae2-103">Die <xref:System.Xml.Xsl.XslTransform>-Klasse unterstützt die Erstellung eingebetteter Skripts mit dem `script`-Element.</span><span class="sxs-lookup"><span data-stu-id="4aae2-103">The <xref:System.Xml.Xsl.XslTransform> class supports embedded scripting using the `script` element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4aae2-104">Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist in .NET Framework 2.0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4aae2-104">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="4aae2-105">Mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse können Sie XSLT-Transformationen (Extensible Stylesheet Language for Transformations) vornehmen.</span><span class="sxs-lookup"><span data-stu-id="4aae2-105">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="4aae2-106">Weitere Informationen finden Sie unter [Verwenden der XslCompiledTransform-Klasse](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) und [Migrieren von der XslTransform-Klasse](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).</span><span class="sxs-lookup"><span data-stu-id="4aae2-106">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="4aae2-107">Die <xref:System.Xml.Xsl.XslTransform>-Klasse unterstützt die Erstellung eingebetteter Skripts mit dem `script`-Element.</span><span class="sxs-lookup"><span data-stu-id="4aae2-107">The <xref:System.Xml.Xsl.XslTransform> class supports embedded scripting using the `script` element.</span></span> <span data-ttu-id="4aae2-108">Wenn das Stylesheet geladen wird, werden alle definierten Funktionen durch Wrapping in eine Klassendefinition in die Microsoft Intermediate Language (MSIL) kompiliert, sodass kein Leistungsverlust auftritt.</span><span class="sxs-lookup"><span data-stu-id="4aae2-108">When the style sheet is loaded, any defined functions are compiled to Microsoft intermediate language (MSIL) by being wrapped in a class definition and have no performance loss as a result.</span></span>  
  
 <span data-ttu-id="4aae2-109">Das `<msxsl:script>`-Element wird im Folgenden definiert:</span><span class="sxs-lookup"><span data-stu-id="4aae2-109">The `<msxsl:script>` element is defined below:</span></span>  
  
```xml  
<msxsl:script language = "language-name" implements-prefix = "prefix of user namespace"> </msxsl:script>  
```  
  
 <span data-ttu-id="4aae2-110">Dabei ist `msxsl` ein an den Namespace `urn:schemas-microsoft-com:xslt` gebundenes Präfix.</span><span class="sxs-lookup"><span data-stu-id="4aae2-110">where `msxsl` is a prefix bound to the namespace `urn:schemas-microsoft-com:xslt`.</span></span>  
  
 <span data-ttu-id="4aae2-111">Das `language`-Attribut ist nicht obligatorisch, aber wenn es angegeben ist, muss sein Wert einer der folgenden sein: `C#`, `VB`, `JScript`, `JavaScript`, `VisualBasic`oder `CSharp`.</span><span class="sxs-lookup"><span data-stu-id="4aae2-111">The `language` attribute is not mandatory, but if specified, its value must be one of the following: `C#`, `VB`, `JScript`, `JavaScript`, `VisualBasic`, or `CSharp`.</span></span> <span data-ttu-id="4aae2-112">Wenn es nicht angegeben wird, wird die Standardsprache JScript verwendet.</span><span class="sxs-lookup"><span data-stu-id="4aae2-112">If not specified, the language defaults to JScript.</span></span> <span data-ttu-id="4aae2-113">Beim `language-name` wird die Groß- und Kleinschreibung nicht unterschieden, daher sind "JavaScript" und "javascript" identisch.</span><span class="sxs-lookup"><span data-stu-id="4aae2-113">The `language-name` is not case-sensitive, so 'JavaScript' and 'javascript' are equivalent.</span></span>  
  
 <span data-ttu-id="4aae2-114">Das `implements-prefix`-Attribut ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4aae2-114">The `implements-prefix` attribute is mandatory.</span></span> <span data-ttu-id="4aae2-115">Mit diesem Attribut wird ein Namespace deklariert und mit dem Skriptblock verknüpft.</span><span class="sxs-lookup"><span data-stu-id="4aae2-115">This attribute is used to declare a namespace and associate it with the script block.</span></span> <span data-ttu-id="4aae2-116">Der Wert dieses Attributs ist das Präfix, das den Namespace darstellt.</span><span class="sxs-lookup"><span data-stu-id="4aae2-116">The value of this attribute is the prefix that represents the namespace.</span></span> <span data-ttu-id="4aae2-117">Dieser Namespace kann an einer beliebigen Stelle im Stylesheet definiert werden.</span><span class="sxs-lookup"><span data-stu-id="4aae2-117">This namespace can be defined somewhere in a style sheet.</span></span>  
  
 <span data-ttu-id="4aae2-118">Da das `msxsl:script`-Element zum `urn:schemas-microsoft-com:xslt`-Namespace gehört, muss das Stylesheet die `xmlns:msxsl=urn:schemas-microsoft-com:xslt`-Namespacedeklaration enthalten.</span><span class="sxs-lookup"><span data-stu-id="4aae2-118">Because the `msxsl:script` element belongs to the namespace `urn:schemas-microsoft-com:xslt`, the style sheet must include the namespace declaration `xmlns:msxsl=urn:schemas-microsoft-com:xslt`.</span></span>  
  
 <span data-ttu-id="4aae2-119">Wenn der Aufrufer des Skripts nicht über die <xref:System.Security.Permissions.SecurityPermissionFlag>-Zugriffsberechtigung verfügt, wird das Skript in einem Stylesheet nicht kompiliert, und der Aufruf von <xref:System.Xml.Xsl.XslTransform.Load%2A> schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="4aae2-119">If the caller of the script does not have <xref:System.Security.Permissions.SecurityPermissionFlag> access permission, then the script in a style sheet will never compile and the call to <xref:System.Xml.Xsl.XslTransform.Load%2A> will fail.</span></span>  
  
 <span data-ttu-id="4aae2-120">Wenn der Aufrufer über die `UnmanagedCode`-Berechtigung verfügt, wird das Skript kompiliert. Die zulässigen Vorgänge hängen vom Beweis ab, der zur Ladezeit bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="4aae2-120">If the caller has `UnmanagedCode` permission, the script compiles, but the operations that are allowed are dependent on the evidence that is supplied at load time.</span></span>  
  
 <span data-ttu-id="4aae2-121">Wenn Sie eine der <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methoden verwenden, die zum Laden des Stylesheets einen <xref:System.Xml.XmlReader> oder einen <xref:System.Xml.XPath.XPathNavigator> akzeptiert, müssen Sie die <xref:System.Xml.Xsl.XslTransform.Load%2A>-Überladung verwenden, die einen <xref:System.Security.Policy.Evidence>-Parameter als Argument akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="4aae2-121">If you are using one of the <xref:System.Xml.Xsl.XslTransform.Load%2A> methods that take an <xref:System.Xml.XmlReader> or <xref:System.Xml.XPath.XPathNavigator> to load the style sheet, you need to use the <xref:System.Xml.Xsl.XslTransform.Load%2A> overload that takes an <xref:System.Security.Policy.Evidence> parameter as one of its arguments.</span></span> <span data-ttu-id="4aae2-122">Zum Bereitstellen eines Beweises muss der Aufrufer über die <xref:System.Security.Permissions.SecurityPermissionFlag>-Berechtigung verfügen, um `Evidence` für die Skriptassembly zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="4aae2-122">To provide evidence, the caller must have <xref:System.Security.Permissions.SecurityPermissionFlag> permission to supply `Evidence` for the script assembly.</span></span> <span data-ttu-id="4aae2-123">Wenn der Aufrufer nicht über diese Berechtigung verfügt, kann der `Evidence`-Parameter auf `null` festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4aae2-123">If the caller does not have this permission, then they can set the `Evidence` parameter to `null`.</span></span> <span data-ttu-id="4aae2-124">Auf diese Weise schlägt die <xref:System.Xml.Xsl.XslTransform.Load%2A>-Funktion fehl, falls ein Skript gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="4aae2-124">This causes the <xref:System.Xml.Xsl.XslTransform.Load%2A> function to fail if it finds script.</span></span> <span data-ttu-id="4aae2-125">Die `ControlEvidence`-Berechtigung ist äußerst umfassend und sollte nur für in hohem Maße vertrauenswürdigen Code erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="4aae2-125">The `ControlEvidence` permission is considered a very powerful permission that should only be granted to highly trusted code.</span></span>  
  
 <span data-ttu-id="4aae2-126">Zum Abrufen des Beweises aus der Assembly verwenden Sie `this.GetType().Assembly.Evidence`.</span><span class="sxs-lookup"><span data-stu-id="4aae2-126">To get the evidence from your assembly, use `this.GetType().Assembly.Evidence`.</span></span> <span data-ttu-id="4aae2-127">Zum Abrufen des Beweises aus einem URI (Uniform Resource Identifier) verwenden Sie `Evidence e = XmlSecureResolver.CreateEvidenceForUrl(stylesheetURI)`.</span><span class="sxs-lookup"><span data-stu-id="4aae2-127">To get the evidence from a Uniform Resource Identifier (URI), use `Evidence e = XmlSecureResolver.CreateEvidenceForUrl(stylesheetURI)`.</span></span>  
  
 <span data-ttu-id="4aae2-128">Wenn Sie <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methoden verwenden, die einen <xref:System.Xml.XmlResolver> akzeptieren, nicht jedoch `Evidence`, wird in der Standardeinstellung als Sicherheitszone für die Assembly "Voll vertrauenswürdig" verwendet.</span><span class="sxs-lookup"><span data-stu-id="4aae2-128">If you use <xref:System.Xml.Xsl.XslTransform.Load%2A> methods that take an <xref:System.Xml.XmlResolver> but no `Evidence`, the security zone for the assembly defaults to Full Trust.</span></span> <span data-ttu-id="4aae2-129">Weitere Informationen finden Sie unter <xref:System.Security.SecurityZone> und [Benannte Berechtigungssätze](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/4652tyx7(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="4aae2-129">For more information, see <xref:System.Security.SecurityZone> and [Named Permission Sets](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/4652tyx7(v=vs.100)).</span></span>  
  
 <span data-ttu-id="4aae2-130">Funktionen können innerhalb des `msxsl:script`-Elements deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="4aae2-130">Functions can be declared within the `msxsl:script` element.</span></span> <span data-ttu-id="4aae2-131">In der folgenden Tabelle werden die Namespaces angezeigt, die standardmäßig unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="4aae2-131">The following table shows the namespaces that are supported by default.</span></span> <span data-ttu-id="4aae2-132">Sie können Klassen außerhalb der aufgeführten Namespaces verwenden.</span><span class="sxs-lookup"><span data-stu-id="4aae2-132">You can use classes outside the listed namespaces.</span></span> <span data-ttu-id="4aae2-133">Diese Klassen müssen jedoch voll qualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="4aae2-133">However, these classes must be fully qualified.</span></span>  
  
|<span data-ttu-id="4aae2-134">Standardnamespaces</span><span class="sxs-lookup"><span data-stu-id="4aae2-134">Default Namespaces</span></span>|<span data-ttu-id="4aae2-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4aae2-135">Description</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="4aae2-136">System</span><span class="sxs-lookup"><span data-stu-id="4aae2-136">System</span></span>|<span data-ttu-id="4aae2-137">Systemklasse.</span><span class="sxs-lookup"><span data-stu-id="4aae2-137">System class.</span></span>|  
|<span data-ttu-id="4aae2-138">System.Collection</span><span class="sxs-lookup"><span data-stu-id="4aae2-138">System.Collection</span></span>|<span data-ttu-id="4aae2-139">Auflistungsklassen.</span><span class="sxs-lookup"><span data-stu-id="4aae2-139">Collection classes.</span></span>|  
|<span data-ttu-id="4aae2-140">System.Text</span><span class="sxs-lookup"><span data-stu-id="4aae2-140">System.Text</span></span>|<span data-ttu-id="4aae2-141">Textklassen.</span><span class="sxs-lookup"><span data-stu-id="4aae2-141">Text classes.</span></span>|  
|<span data-ttu-id="4aae2-142">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="4aae2-142">System.Text.RegularExpressions</span></span>|<span data-ttu-id="4aae2-143">Klassen für reguläre Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="4aae2-143">Regular expression classes.</span></span>|  
|<span data-ttu-id="4aae2-144">System.Xml</span><span class="sxs-lookup"><span data-stu-id="4aae2-144">System.Xml</span></span>|<span data-ttu-id="4aae2-145">Kern-XML-Klassen.</span><span class="sxs-lookup"><span data-stu-id="4aae2-145">Core XML classes.</span></span>|  
|<span data-ttu-id="4aae2-146">System.Xml.Xsl</span><span class="sxs-lookup"><span data-stu-id="4aae2-146">System.Xml.Xsl</span></span>|<span data-ttu-id="4aae2-147">XSLT-Klassen.</span><span class="sxs-lookup"><span data-stu-id="4aae2-147">XSLT classes.</span></span>|  
|<span data-ttu-id="4aae2-148">System.Xml.XPath</span><span class="sxs-lookup"><span data-stu-id="4aae2-148">System.Xml.XPath</span></span>|<span data-ttu-id="4aae2-149">XPath-Klassen (XML Path Language).</span><span class="sxs-lookup"><span data-stu-id="4aae2-149">XML Path Language (XPath) classes.</span></span>|  
|<span data-ttu-id="4aae2-150">Microsoft.VisualBasic</span><span class="sxs-lookup"><span data-stu-id="4aae2-150">Microsoft.VisualBasic</span></span>|<span data-ttu-id="4aae2-151">Klassen für Microsoft Visual Basic-Skripts</span><span class="sxs-lookup"><span data-stu-id="4aae2-151">Classes for Microsoft Visual Basic scripts.</span></span>|  
  
 <span data-ttu-id="4aae2-152">Wenn eine Funktion deklariert wurde, ist sie in einem Skriptblock enthalten.</span><span class="sxs-lookup"><span data-stu-id="4aae2-152">When a function is declared, it is contained in a script block.</span></span> <span data-ttu-id="4aae2-153">Stylesheets können mehrere voneinander unabhängige Skriptblöcke enthalten.</span><span class="sxs-lookup"><span data-stu-id="4aae2-153">Style sheets can contain multiple script blocks, each operating independent of the other.</span></span> <span data-ttu-id="4aae2-154">Sie können daher bei der Ausführung innerhalb eines Skriptblocks nur dann eine Funktion aufrufen, die Sie in einem anderen Skriptblock definiert haben, wenn diese Funktion so deklariert wurde, dass sie den gleichen Namespace und die gleiche Skriptsprache verwendet.</span><span class="sxs-lookup"><span data-stu-id="4aae2-154">That means that if you are executing inside a script block, you cannot call a function that you defined in another script block unless it is declared to have the same namespace and the same scripting language.</span></span> <span data-ttu-id="4aae2-155">Da jeder Skriptblock in einer eigenen Sprache vorliegen kann und der Block gemäß der Grammatikregeln für den betreffenden Sprachparser analysiert wird, müssen Sie die korrekte Syntax für die verwendete Sprache einhalten.</span><span class="sxs-lookup"><span data-stu-id="4aae2-155">Because each script block can be in its own language, and the block is parsed according to the grammar rules of that language parser, you must use the correct syntax for the language in use.</span></span> <span data-ttu-id="4aae2-156">Beispiel: Wenn Sie in einem C#-Skriptblock arbeiten, darf in dem Block kein XML-Kommentarknoten `<!-- an XML comment -->` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4aae2-156">For example, if you are in a C# script block, then it is an error to use an XML comment node `<!-- an XML comment -->` in the block.</span></span>  
  
 <span data-ttu-id="4aae2-157">Die bereitgestellten, durch die Skriptfunktionen definierten Argumente und Rückgabewerte müssen zu einem der XPath- oder XSLT-Typen des W3C (World Wide Web Consortium) gehören.</span><span class="sxs-lookup"><span data-stu-id="4aae2-157">The supplied arguments and return values defined by the script functions must be one of the World Wide Web Consortium (W3C) XPath or XSLT types.</span></span> <span data-ttu-id="4aae2-158">In der folgenden Tabelle werden die jeweiligen W3C-Typen mit den entsprechenden .NET Framework-Klassen (Typen) samt der Informationen aufgeführt, ob es sich bei einem W3C-Typ um einen XPath-Typ oder einen XSLT-Typ handelt.</span><span class="sxs-lookup"><span data-stu-id="4aae2-158">The following table shows the corresponding W3C types, the equivalent .NET Framework classes (Type), and whether the W3C type is an XPath type or XSLT type.</span></span>  
  
|<span data-ttu-id="4aae2-159">Typ</span><span class="sxs-lookup"><span data-stu-id="4aae2-159">Type</span></span>|<span data-ttu-id="4aae2-160">Entsprechende .NET Framework-Klasse (Typ)</span><span class="sxs-lookup"><span data-stu-id="4aae2-160">Equivalent .NET Framework Class (Type)</span></span>|<span data-ttu-id="4aae2-161">XPath-Typ oder XSLT-Typ</span><span class="sxs-lookup"><span data-stu-id="4aae2-161">XPath type or XSLT type</span></span>|  
|----------|----------------------------------------------|-----------------------------|  
|<span data-ttu-id="4aae2-162">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4aae2-162">String</span></span>|<span data-ttu-id="4aae2-163">System.String</span><span class="sxs-lookup"><span data-stu-id="4aae2-163">System.String</span></span>|<span data-ttu-id="4aae2-164">XPath</span><span class="sxs-lookup"><span data-stu-id="4aae2-164">XPath</span></span>|  
|<span data-ttu-id="4aae2-165">Boolean</span><span class="sxs-lookup"><span data-stu-id="4aae2-165">Boolean</span></span>|<span data-ttu-id="4aae2-166">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="4aae2-166">System.Boolean</span></span>|<span data-ttu-id="4aae2-167">XPath</span><span class="sxs-lookup"><span data-stu-id="4aae2-167">XPath</span></span>|  
|<span data-ttu-id="4aae2-168">Number</span><span class="sxs-lookup"><span data-stu-id="4aae2-168">Number</span></span>|<span data-ttu-id="4aae2-169">System.Double</span><span class="sxs-lookup"><span data-stu-id="4aae2-169">System.Double</span></span>|<span data-ttu-id="4aae2-170">XPath</span><span class="sxs-lookup"><span data-stu-id="4aae2-170">XPath</span></span>|  
|<span data-ttu-id="4aae2-171">Ergebnisstrukturfragment</span><span class="sxs-lookup"><span data-stu-id="4aae2-171">Result Tree Fragment</span></span>|<span data-ttu-id="4aae2-172">System.Xml.XPath.XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="4aae2-172">System.Xml.XPath.XPathNavigator</span></span>|<span data-ttu-id="4aae2-173">XSLT</span><span class="sxs-lookup"><span data-stu-id="4aae2-173">XSLT</span></span>|  
|<span data-ttu-id="4aae2-174">Knotengruppe</span><span class="sxs-lookup"><span data-stu-id="4aae2-174">Node Set</span></span>|<span data-ttu-id="4aae2-175">System.Xml.XPath.XPathNodeIterator</span><span class="sxs-lookup"><span data-stu-id="4aae2-175">System.Xml.XPath.XPathNodeIterator</span></span>|<span data-ttu-id="4aae2-176">XPath</span><span class="sxs-lookup"><span data-stu-id="4aae2-176">XPath</span></span>|  
  
 <span data-ttu-id="4aae2-177">Wenn die Skriptfunktion einen der folgenden numerischen Typen verwendet: Int16, UInt16, Int32, UInt32, Int64, UInt64, Single oder Decimal, werden diese Typen in Double umgewandelt, wodurch eine Zuordnung zur XPath-Typnummer des W3C erfolgt.</span><span class="sxs-lookup"><span data-stu-id="4aae2-177">If the script function utilizes one of the following numeric types: Int16, UInt16, Int32, UInt32, Int64, UInt64, Single, or Decimal, they are forced to Double, which maps to the W3C XPath type number.</span></span> <span data-ttu-id="4aae2-178">Für alle anderen Typen wird durch einen Aufruf der `ToString`-Methode eine Umwandlung in string erzwungen.</span><span class="sxs-lookup"><span data-stu-id="4aae2-178">All other types are forced to a string by calling the `ToString` method.</span></span>  
  
 <span data-ttu-id="4aae2-179">Wenn die Skriptfunktion einen anderen als die oben genannten Typen verwendet oder wenn sie beim Laden des Stylesheets in das <xref:System.Xml.Xsl.XslTransform>-Objekt nicht kompiliert wird, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="4aae2-179">If the script function utilizes a type other than the ones mentioned above, or if the function does not compile when the style sheet is loaded into the <xref:System.Xml.Xsl.XslTransform> object, an exception is thrown.</span></span>  
  
 <span data-ttu-id="4aae2-180">Bei Verwendung des `msxsl:script`-Elements wird dringend empfohlen, das Skript ungeachtet der verwendeten Sprache in einem CDATA-Abschnitt zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="4aae2-180">When using the `msxsl:script` element, it is highly recommended that the script, regardless of language, be placed inside a CDATA section.</span></span> <span data-ttu-id="4aae2-181">Folgender XML-Code veranschaulicht z. B. die Vorlage für den CDATA-Abschnitt, in dem der Code platziert wird.</span><span class="sxs-lookup"><span data-stu-id="4aae2-181">For example, the following XML shows the template of the CDATA section where your code is placed.</span></span>  
  
```xml  
<msxsl:script implements-prefix='yourprefix' language='CSharp'>  
    <![CDATA[  
    ... your code here ...  
    ]]>  
</msxsl:script>  
```  
  
 <span data-ttu-id="4aae2-182">Es wird dringend empfohlen, den gesamten Skriptinhalt in einem CDATA-Abschnitt zu platzieren, da Operatoren, Bezeichner oder Trennzeichen für eine angegebene Sprache möglicherweise als XML interpretiert werden können.</span><span class="sxs-lookup"><span data-stu-id="4aae2-182">It is highly recommended that all script content be placed in a CDATA section, because operators, identifiers, or delimiters for a given language have the potential of being misinterpreted as XML.</span></span> <span data-ttu-id="4aae2-183">Das folgende Codebeispiel veranschaulicht die Verwendung des logischen AND-Operators in einem Skript.</span><span class="sxs-lookup"><span data-stu-id="4aae2-183">The following example shows the use of the logical AND operator in script.</span></span>  
  
```xml  
<msxsl:script implements-prefix='yourprefix' language='CSharp'>  
    public string book(string abc, string xyz)  
    {  
        if ((abc == bar) && (abc == xyz)) return bar + xyz;  
        else return null;  
    }  
</msxsl:script>  
```  
  
 <span data-ttu-id="4aae2-184">Hierdurch wird eine Ausnahme ausgelöst, da die kaufmännischen Und-Zeichen nicht durch Escapezeichen geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="4aae2-184">This throws an exception because the ampersands are not escaped.</span></span> <span data-ttu-id="4aae2-185">Das Dokument wird als XML geladen, und der Text zwischen den `msxsl:script`-Elementtags wird nicht in besonderer Weise behandelt.</span><span class="sxs-lookup"><span data-stu-id="4aae2-185">The document is loaded as XML, and no special treatment is applied to the text between the `msxsl:script` element tags.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4aae2-186">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4aae2-186">Example</span></span>  
 <span data-ttu-id="4aae2-187">Im folgenden Beispiel wird der Umfang eines Kreises bei angegebenem Radius unter Verwendung eines eingebetteten Skripts berechnet.</span><span class="sxs-lookup"><span data-stu-id="4aae2-187">The following example uses an embedded script to calculate the circumference of a circle given its radius.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.XPath  
Imports System.Xml.Xsl  
  
Public Class Sample  
  
   Private Const filename As String = "number.xml"  
   Private Const stylesheet As String = "calc.xsl"  
  
   Public Shared Sub Main()  
  
    'Create the XslTransform and load the style sheet.  
    Dim xslt As XslTransform = New XslTransform  
    xslt.Load(stylesheet)  
  
    'Load the XML data file.  
    Dim doc As XPathDocument = New XPathDocument(filename)  
  
    'Create an XmlTextWriter to output to the console.               
    Dim writer As XmlTextWriter = New XmlTextWriter(Console.Out)  
    writer.Formatting = Formatting.Indented  
  
    'Transform the file.  
    xslt.Transform(doc, Nothing, writer, Nothing)  
    writer.Close()  
  End Sub   
End Class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.XPath;  
using System.Xml.Xsl;  
  
public class Sample  
{  
   private const String filename = "number.xml";  
   private const String stylesheet = "calc.xsl";  
  
   public static void Main()  
   {  
    //Create the XslTransform and load the style sheet.  
    XslTransform xslt = new XslTransform();  
    xslt.Load(stylesheet);  
  
    //Load the XML data file.  
    XPathDocument doc = new XPathDocument(filename);  
  
    //Create an XmlTextWriter to output to the console.               
    XmlTextWriter writer = new XmlTextWriter(Console.Out);  
    writer.Formatting = Formatting.Indented;  
  
    //Transform the file.  
    xslt.Transform(doc, null, writer, null);  
    writer.Close();  
  }  
}  
```  
  
## <a name="input"></a><span data-ttu-id="4aae2-188">Input</span><span class="sxs-lookup"><span data-stu-id="4aae2-188">Input</span></span>  
 <span data-ttu-id="4aae2-189">number.xml</span><span class="sxs-lookup"><span data-stu-id="4aae2-189">number.xml</span></span>  
  
```xml  
<?xml version='1.0'?>  
<data>  
  <circle>  
    <radius>12</radius>  
  </circle>  
  <circle>  
    <radius>37.5</radius>  
  </circle>  
</data>  
```  
  
 <span data-ttu-id="4aae2-190">calc.xsl</span><span class="sxs-lookup"><span data-stu-id="4aae2-190">calc.xsl</span></span>  
  
```xml  
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
    xmlns:msxsl="urn:schemas-microsoft-com:xslt"  
    xmlns:user="urn:my-scripts">  
  
  <msxsl:script language="C#" implements-prefix="user">  
     <![CDATA[  
     public double circumference(double radius)  
     {  
       double pi = 3.14;  
       double circ = pi*radius*2;  
       return circ;  
     }  
      ]]>  
   </msxsl:script>  
  
  <xsl:template match="data">    
  <circles>  
  
  <xsl:for-each select="circle">  
    <circle>  
    <xsl:copy-of select="node()"/>  
       <circumference>  
          <xsl:value-of select="user:circumference(radius)"/>   
       </circumference>  
    </circle>  
  </xsl:for-each>  
  </circles>  
  </xsl:template>  
</xsl:stylesheet>  
```  
  
## <a name="output"></a><span data-ttu-id="4aae2-191">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="4aae2-191">Output</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4aae2-192">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4aae2-192">See also</span></span>

- [<span data-ttu-id="4aae2-193">Implementierung des XSLT-Prozessors durch die XslTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="4aae2-193">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
