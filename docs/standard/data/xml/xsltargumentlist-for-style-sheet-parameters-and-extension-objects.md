---
title: "\"XsltArgumentList\" für Stylesheetparameter und Erweiterungsobjekte"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: de2f0dce-6b98-4908-bba7-ed150cc50355
ms.openlocfilehash: fe227a2d3efc5c36b818b7f4431896e6f62b1f26
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685044"
---
# <a name="xsltargumentlist-for-style-sheet-parameters-and-extension-objects"></a><span data-ttu-id="e5956-102">"XsltArgumentList" für Stylesheetparameter und Erweiterungsobjekte</span><span class="sxs-lookup"><span data-stu-id="e5956-102">XsltArgumentList for Style Sheet Parameters and Extension Objects</span></span>

<span data-ttu-id="e5956-103">Die <xref:System.Xml.Xsl.XsltArgumentList> enthält XSLT-Parameter (Extensible Stylesheet Transformation) und XSLT-Erweiterungsobjekte.</span><span class="sxs-lookup"><span data-stu-id="e5956-103">The <xref:System.Xml.Xsl.XsltArgumentList> class contains Extensible Stylesheet Language for Transformations (XSLT) parameters and XSLT extension objects.</span></span> <span data-ttu-id="e5956-104">Bei der Übergabe an die <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode können diese Parameter und Erweiterungsobjekte von Stylesheets aus ausgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e5956-104">When passed into the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method, these parameters and extension objects can be invoked from style sheets.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5956-105">Die Klassen <xref:System.Xml.Xsl.XslTransform> und <xref:System.Xml.Xsl.XsltArgumentList> sind in .NET Framework 2.0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e5956-105">The <xref:System.Xml.Xsl.XslTransform> and <xref:System.Xml.Xsl.XsltArgumentList> classes are obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="e5956-106">Sie können XSLT-Transformationen mit der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse durchführen.</span><span class="sxs-lookup"><span data-stu-id="e5956-106">You can perform XSLT transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="e5956-107">Weitere Informationen finden Sie unter [Verwenden der XslCompiledTransform-Klasse](using-the-xslcompiledtransform-class.md) und [Migrieren von der XslTransform-Klasse](migrating-from-the-xsltransform-class.md).</span><span class="sxs-lookup"><span data-stu-id="e5956-107">See [Using the XslCompiledTransform Class](using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="e5956-108">Die <xref:System.Xml.Xsl.XsltArgumentList>-Klasse enthält XSLT-Parameter und XSLT-Erweiterungsobjekte.</span><span class="sxs-lookup"><span data-stu-id="e5956-108">The <xref:System.Xml.Xsl.XsltArgumentList> class contains XSLT parameters and XSLT extension objects.</span></span> <span data-ttu-id="e5956-109">Bei der Übergabe an die <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode können diese Parameter und Erweiterungsobjekte von Stylesheets aus ausgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e5956-109">When passed into the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method, these parameters and extension objects can be invoked from style sheets.</span></span>  
  
 <span data-ttu-id="e5956-110">Die Übergabe eines Objekts bietet gegenüber der Verwendung eines eingebetteten Skripts folgende Vorteile:</span><span class="sxs-lookup"><span data-stu-id="e5956-110">The following are advantages to passing an object rather than using an embedded script:</span></span>  
  
- <span data-ttu-id="e5956-111">Sie ermöglicht eine bessere Kapselung und Wiederverwendung von Klassen.</span><span class="sxs-lookup"><span data-stu-id="e5956-111">Provides better encapsulation and reuse of classes.</span></span>  
  
- <span data-ttu-id="e5956-112">Stylesheets werden kleiner und sind besser verwaltbar.</span><span class="sxs-lookup"><span data-stu-id="e5956-112">Allows style sheets to be smaller and more maintainable.</span></span>  
  
- <span data-ttu-id="e5956-113">Das Aufrufen von Methoden für Klassen, die zu anderen Namespaces gehören als zu denen, die im Rahmen der unterstützten <xref:System>-Namespaces definiert sind, wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e5956-113">Supports calling methods on classes belonging to namespaces other than those defined within the set of supported <xref:System> namespaces.</span></span>  
  
- <span data-ttu-id="e5956-114">Bei Verwendung von <xref:System.Xml.XPath.XPathNodeIterator> wird die Übergabe von Ergebnisstrukturfragmenten an das Stylesheet unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e5956-114">Supports passing result tree fragments to the style sheet with the use of the <xref:System.Xml.XPath.XPathNodeIterator>.</span></span>  
  
## <a name="xslt-style-sheet-parameters"></a><span data-ttu-id="e5956-115">XSLT-Stylesheetparameter</span><span class="sxs-lookup"><span data-stu-id="e5956-115">XSLT Style Sheet Parameters</span></span>  

 <span data-ttu-id="e5956-116">XSLT-Parameter werden der <xref:System.Xml.Xsl.XsltArgumentList> mithilfe der <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>-Methode hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e5956-116">XSLT parameters are added to the <xref:System.Xml.Xsl.XsltArgumentList> using the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method.</span></span> <span data-ttu-id="e5956-117">Dabei wird ein qualifizierter Name und ein Namespace-URI (Uniform Resource Identifier) mit dem Parameterobjekt verknüpft.</span><span class="sxs-lookup"><span data-stu-id="e5956-117">A qualified name and namespace Uniform Resource Identifier (URI) are associated with the parameter object at that time.</span></span>  
  
 <span data-ttu-id="e5956-118">Das Parameterobjekt muss einem W3C-Typ entsprechen.</span><span class="sxs-lookup"><span data-stu-id="e5956-118">The parameter object should correspond to a World Wide Web Consortium (W3C) type.</span></span> <span data-ttu-id="e5956-119">In der folgenden Tabelle sind die jeweiligen W3C-Typen mit den entsprechenden .NET Framework-Klassen (Typ) aufgelistet, und es ist angegeben, ob es sich bei dem W3C-Typ um einen XPath-Typ (XML Path Language) oder einen XSLT-Typ handelt.</span><span class="sxs-lookup"><span data-stu-id="e5956-119">The following table shows the corresponding W3C types, the equivalent .NET Framework classes (type), and whether the W3C type is an XML Path Language (XPath) type or XSLT type.</span></span>  
  
|<span data-ttu-id="e5956-120">W3C-Typ</span><span class="sxs-lookup"><span data-stu-id="e5956-120">W3C Type</span></span>|<span data-ttu-id="e5956-121">Entsprechende .NET Framework-Klasse (Typ)</span><span class="sxs-lookup"><span data-stu-id="e5956-121">Equivalent .NET Framework class (type)</span></span>|<span data-ttu-id="e5956-122">XPath-Typ oder XSLT-Typ</span><span class="sxs-lookup"><span data-stu-id="e5956-122">XPath type or XSLT type</span></span>|  
|--------------|----------------------------------------------|-----------------------------|  
|<span data-ttu-id="e5956-123">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="e5956-123">String</span></span>|<span data-ttu-id="e5956-124">System.String</span><span class="sxs-lookup"><span data-stu-id="e5956-124">System.String</span></span>|<span data-ttu-id="e5956-125">XPath</span><span class="sxs-lookup"><span data-stu-id="e5956-125">XPath</span></span>|  
|<span data-ttu-id="e5956-126">Boolesch</span><span class="sxs-lookup"><span data-stu-id="e5956-126">Boolean</span></span>|<span data-ttu-id="e5956-127">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="e5956-127">System.Boolean</span></span>|<span data-ttu-id="e5956-128">XPath</span><span class="sxs-lookup"><span data-stu-id="e5956-128">XPath</span></span>|  
|<span data-ttu-id="e5956-129">Anzahl</span><span class="sxs-lookup"><span data-stu-id="e5956-129">Number</span></span>|<span data-ttu-id="e5956-130">System.Double</span><span class="sxs-lookup"><span data-stu-id="e5956-130">System.Double</span></span>|<span data-ttu-id="e5956-131">XPath</span><span class="sxs-lookup"><span data-stu-id="e5956-131">XPath</span></span>|  
|<span data-ttu-id="e5956-132">Ergebnisstrukturfragment</span><span class="sxs-lookup"><span data-stu-id="e5956-132">Result Tree Fragment</span></span>|<span data-ttu-id="e5956-133">System.Xml.XPath.XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="e5956-133">System.Xml.XPath.XPathNavigator</span></span>|<span data-ttu-id="e5956-134">XSLT</span><span class="sxs-lookup"><span data-stu-id="e5956-134">XSLT</span></span>|  
|<span data-ttu-id="e5956-135">Knotengruppe</span><span class="sxs-lookup"><span data-stu-id="e5956-135">Node Set</span></span>|<span data-ttu-id="e5956-136">System.Xml.XPath.XPathNodeIterator</span><span class="sxs-lookup"><span data-stu-id="e5956-136">System.Xml.XPath.XPathNodeIterator</span></span>|<span data-ttu-id="e5956-137">XPath</span><span class="sxs-lookup"><span data-stu-id="e5956-137">XPath</span></span>|  
  
 <span data-ttu-id="e5956-138">Wenn es sich bei dem Parameterobjekt um keine der obigen Klassen handelt, wird je nach Bedarf entweder ein Double oder ein String erzwungen.</span><span class="sxs-lookup"><span data-stu-id="e5956-138">If the parameter object is not one of the above classes, it is forced to either a Double or String, as appropriate.</span></span> <span data-ttu-id="e5956-139">Für die Typen Int16, UInt16, Int32, UInt32, Int64, UInt64, Single und Decimal wird ein Double erzwungen.</span><span class="sxs-lookup"><span data-stu-id="e5956-139">Int16, UInt16, Int32, UInt32, Int64, UInt64, Single and Decimal types are forced to a Double.</span></span> <span data-ttu-id="e5956-140">Für alle anderen Typen wird mit der `ToString`-Methode ein string erzwungen.</span><span class="sxs-lookup"><span data-stu-id="e5956-140">All other types are forced to a String using the `ToString` method.</span></span>  
  
#### <a name="to-use-the-xslt-parameter-the-user-needs-to-do-the-following"></a><span data-ttu-id="e5956-141">So verwenden Sie den XSLT-Parameter:</span><span class="sxs-lookup"><span data-stu-id="e5956-141">To use the XSLT parameter, the user needs to do the following:</span></span>  
  
1. <span data-ttu-id="e5956-142">Erstellen Sie eine <xref:System.Xml.Xsl.XsltArgumentList> und fügen Sie die Objekte mit <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> hinzu.</span><span class="sxs-lookup"><span data-stu-id="e5956-142">Create an <xref:System.Xml.Xsl.XsltArgumentList> and add the objects using <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>.</span></span>  
  
2. <span data-ttu-id="e5956-143">Rufen Sie die Parameter aus dem Stylesheet auf.</span><span class="sxs-lookup"><span data-stu-id="e5956-143">Call the parameters from the style sheet.</span></span>  
  
3. <span data-ttu-id="e5956-144">Übergeben Sie die <xref:System.Xml.Xsl.XsltArgumentList> an die <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="e5956-144">Pass the <xref:System.Xml.Xsl.XsltArgumentList> to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="e5956-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e5956-145">Example</span></span>  

 <span data-ttu-id="e5956-146">Im folgenden Beispiel wird mit der <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>-Methode ein Parameter erstellt, der das berechnete Skontodatum enthält.</span><span class="sxs-lookup"><span data-stu-id="e5956-146">The following example uses the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method to create a parameter to hold a calculated discount date.</span></span> <span data-ttu-id="e5956-147">Das Skontodatum ist 20 Tage nach dem Auftragsdatum.</span><span class="sxs-lookup"><span data-stu-id="e5956-147">The discount date is calculated to be 20 days from the order date.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.XPath  
Imports System.Xml.Xsl  
  
Public class Sample  
  
   Private Const filename As String = "order.xml"  
   Private Const stylesheet As String = "discount.xsl"  
  
   Public Shared Sub Main()  
  
    'Create the XslTransform and load the style sheet.  
    Dim xslt As XslTransform = New XslTransform  
    xslt.Load(stylesheet)  
  
    'Load the XML data file.  
    Dim doc As XPathDocument = New XPathDocument(filename)  
  
    'Create an XsltArgumentList.  
    Dim xslArg As XsltArgumentList = New XsltArgumentList  
  
    'Calculate the discount date.  
    Dim today As DateTime = DateTime.Now  
    Dim d As DateTime = today.AddDays(20)  
    xslArg.AddParam("discount", "", d.ToString())  
  
    'Create an XmlTextWriter to handle the output.  
    Dim writer As XmlTextWriter = New XmlTextWriter("orderout.xml", Nothing)  
  
    'Transform the file.  
    xslt.Transform(doc, xslArg, writer, Nothing)  
  
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
   private const String filename = "order.xml";  
   private const String stylesheet = "discount.xsl";  
  
   public static void Main() {  
  
    //Create the XslTransform and load the style sheet.  
    XslTransform xslt = new XslTransform();  
    xslt.Load(stylesheet);  
  
    //Load the XML data file.  
    XPathDocument doc = new XPathDocument(filename);  
  
    //Create an XsltArgumentList.  
    XsltArgumentList xslArg = new XsltArgumentList();  
  
    //Calculate the discount date.  
    DateTime today = DateTime.Now;  
    DateTime d = today.AddDays(20);  
    xslArg.AddParam("discount", "", d.ToString());  
  
    //Create an XmlTextWriter to handle the output.  
    XmlTextWriter writer = new XmlTextWriter("orderout.xml", null);  
  
    //Transform the file.  
    xslt.Transform(doc, xslArg, writer, null);  
    writer.Close();  
  }  
}  
```  
  
### <a name="input"></a><span data-ttu-id="e5956-148">Eingabe</span><span class="sxs-lookup"><span data-stu-id="e5956-148">Input</span></span>  

 <span data-ttu-id="e5956-149">order.xml</span><span class="sxs-lookup"><span data-stu-id="e5956-149">order.xml</span></span>  
  
```xml  
<!--Represents a customer order-->  
<order>  
  <book ISBN='10-861003-324'>  
    <title>The Handmaid's Tale</title>  
    <price>19.95</price>  
  </book>  
  <cd ISBN='2-3631-4'>  
    <title>Americana</title>  
    <price>16.95</price>  
  </cd>  
</order>  
```  
  
 <span data-ttu-id="e5956-150">discount.xsl</span><span class="sxs-lookup"><span data-stu-id="e5956-150">discount.xsl</span></span>  
  
```xml  
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">  
  <xsl:param name="discount"/>  
  <xsl:template match="/">  
    <order>  
      <xsl:variable name="sub-total" select="sum(//price)"/>  
      <total><xsl:value-of select="$sub-total"/></total>  
      15% discount if paid by: <xsl:value-of select="$discount"/>  
    </order>  
  </xsl:template>  
</xsl:stylesheet>  
```  
  
### <a name="output"></a><span data-ttu-id="e5956-151">Output</span><span class="sxs-lookup"><span data-stu-id="e5956-151">Output</span></span>  
  
```xml  
<order>  
   <total>36.9</total>
   15% discount if paid by: 5/6/2001 5:01:15 PM
</order>  
```  
  
## <a name="xslt-extension-objects"></a><span data-ttu-id="e5956-152">XSLT-Erweiterungsobjekte</span><span class="sxs-lookup"><span data-stu-id="e5956-152">XSLT Extension Objects</span></span>  

 <span data-ttu-id="e5956-153">XSLT-Erweiterungsobjekte werden der <xref:System.Xml.Xsl.XsltArgumentList> mithilfe der <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>-Methode hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e5956-153">XSLT extension objects are added to the <xref:System.Xml.Xsl.XsltArgumentList> using the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span> <span data-ttu-id="e5956-154">Dabei wird ein qualifizierter Name und ein Namespace-URI (Uniform Resource Identifier) mit dem Parameterobjekt verknüpft.</span><span class="sxs-lookup"><span data-stu-id="e5956-154">A qualified name and namespace URI are associated with the extension object at that time.</span></span>  
  
 <span data-ttu-id="e5956-155">Wenn ein Objekt hinzugefügt wird, muss der Aufrufer von <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> in den Sicherheitsrichtlinien mit vollständiger Vertrauenswürdigkeit eingestuft sein.</span><span class="sxs-lookup"><span data-stu-id="e5956-155">When an object is added, the caller of the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> must be fully trusted in the security policy.</span></span> <span data-ttu-id="e5956-156">Wenn der Aufrufer nur teilweise vertrauenswürdig ist, schlägt das Hinzufügen fehl.</span><span class="sxs-lookup"><span data-stu-id="e5956-156">If the caller is semi-trusted, the addition will fail.</span></span>  
  
 <span data-ttu-id="e5956-157">Das erfolgreiche Hinzufügen eines Objekts garantiert jedoch nicht zwangsläufig eine erfolgreiche Ausführung.</span><span class="sxs-lookup"><span data-stu-id="e5956-157">Though an object is added successfully, it does not guarantee that the execution will be successful.</span></span> <span data-ttu-id="e5956-158">Wenn die <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode aufgerufen wird, werden die Berechtigungen mit den zur <xref:System.Xml.Xsl.XslTransform.Load%2A>-Zeit bereitgestellten Beweisen berechnet, und dem gesamten Transformationsprozess wird dieser Berechtigungssatz zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="e5956-158">When the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is called, permissions are calculated against the evidence provided at <xref:System.Xml.Xsl.XslTransform.Load%2A> time, and that permission set is assigned to the entire transformation process.</span></span> <span data-ttu-id="e5956-159">Bei dem Versuch, durch ein Erweiterungsobjekt eine Aktion zu initiieren, die eine nicht im Berechtigungssatz enthaltene Berechtigung erfordert, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e5956-159">If an extension object attempts to initiate an action that requires permissions not found in the set, an exception is thrown.</span></span>  
  
 <span data-ttu-id="e5956-160">Von Erweiterungsobjekten kann einer der vier XPath-Grunddatentypen (node-set, Boolean, number oder string) zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e5956-160">The data types returned from extension objects are one of the four basic XPath data types of number, string, Boolean, and node set.</span></span>  
  
#### <a name="to-use-the-xslt-extension-object-the-user-needs-to-do-the-following"></a><span data-ttu-id="e5956-161">So verwenden Sie das XSLT-Erweiterungsobjekt:</span><span class="sxs-lookup"><span data-stu-id="e5956-161">To use the XSLT extension object, the user needs to do the following:</span></span>  
  
1. <span data-ttu-id="e5956-162">Erstellen Sie eine <xref:System.Xml.Xsl.XsltArgumentList>, und fügen Sie das Erweiterungsobjekt mit <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> hinzu.</span><span class="sxs-lookup"><span data-stu-id="e5956-162">Create an <xref:System.Xml.Xsl.XsltArgumentList> and add the extension object using <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.</span></span>  
  
2. <span data-ttu-id="e5956-163">Rufen Sie das Erweiterungsobjekt aus dem Stylesheet auf.</span><span class="sxs-lookup"><span data-stu-id="e5956-163">Invoke the extension object from the style sheet.</span></span>  
  
3. <span data-ttu-id="e5956-164">Übergeben Sie die <xref:System.Xml.Xsl.XsltArgumentList> an die <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="e5956-164">Pass the <xref:System.Xml.Xsl.XsltArgumentList> to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="e5956-165">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e5956-165">Example</span></span>  

 <span data-ttu-id="e5956-166">Im folgenden Beispiel wird der Umfang eines Kreises bei gegebenem Radius berechnet.</span><span class="sxs-lookup"><span data-stu-id="e5956-166">The following example calculates the circumference of a circle given its radius.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.XPath  
Imports System.Xml.Xsl  
  
Public Class Sample  
   Private Const filename As String = "number.xml"  
   Private Const stylesheet As String = "circle.xsl"  
  
   Public Shared Sub Main()  
        Dim test As Sample = New Sample  
   End Sub  
  
  Public Sub New()  
    'Create the XslTransform and load the style sheet.  
    Dim xslt As XslTransform = New XslTransform  
    xslt.Load(stylesheet)  
  
    'Load the XML data file.  
    Dim doc As XPathDocument = New XPathDocument(filename)  
  
    'Create an XsltArgumentList.  
    Dim xslArg As XsltArgumentList = New XsltArgumentList  
  
    'Add an object to calculate the circumference of the circle.  
    Dim obj As Calculate = New Calculate  
    xslArg.AddExtensionObject("urn:myObj", obj)  
  
    'Create an XmlTextWriter to output to the console.  
    Dim writer As XmlTextWriter = New XmlTextWriter(Console.Out)  
  
    'Transform the file.  
    xslt.Transform(doc, xslArg, writer, Nothing)  
    writer.Close()  
  
  End Sub  
  
  'Calculates the circumference of a circle given the radius.  
  Public Class Calculate  
  
    Private circ As double = 0  
  
    Public Function Circumference(radius As Double) As Double  
       circ = Math.PI*2*radius  
       Return circ  
    End Function  
  End Class  
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
   private const String stylesheet = "circle.xsl";  
  
   public static void Main() {  
  
        Sample test = new Sample();  
    }  
  
  public Sample() {  
  
    //Create the XslTransform and load the style sheet.  
    XslTransform xslt = new XslTransform();  
    xslt.Load(stylesheet);  
  
    //Load the XML data file.  
    XPathDocument doc = new XPathDocument(filename);  
  
    //Create an XsltArgumentList.  
    XsltArgumentList xslArg = new XsltArgumentList();  
  
    //Add an object to calculate the circumference of the circle.  
    Calculate obj = new Calculate();  
    xslArg.AddExtensionObject("urn:myObj", obj);  
  
    //Create an XmlTextWriter to output to the console.  
    XmlTextWriter writer = new XmlTextWriter(Console.Out);  
  
    //Transform the file.  
    xslt.Transform(doc, xslArg, writer, null);  
    writer.Close();  
  
  }  
  
  //Calculates the circumference of a circle given the radius.  
  public class Calculate {  
  
    private double circ = 0;  
  
    public double Circumference(double radius){  
       circ = Math.PI*2*radius;  
       return circ;  
    }  
  }  
}  
```  
  
### <a name="input"></a><span data-ttu-id="e5956-167">Eingabe</span><span class="sxs-lookup"><span data-stu-id="e5956-167">Input</span></span>  

 <span data-ttu-id="e5956-168">number.xml</span><span class="sxs-lookup"><span data-stu-id="e5956-168">number.xml</span></span>  
  
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
  
 <span data-ttu-id="e5956-169">circle.xsl</span><span class="sxs-lookup"><span data-stu-id="e5956-169">circle.xsl</span></span>  
  
```xml  
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
    xmlns:myObj="urn:myObj">  
  
  <xsl:template match="data">  
  <circles>  
  <xsl:for-each select="circle">  
    <circle>  
    <xsl:copy-of select="node()"/>  
       <circumference>  
          <xsl:value-of select="myObj:Circumference(radius)"/>
       </circumference>  
    </circle>  
  </xsl:for-each>  
  </circles>  
  </xsl:template>  
</xsl:stylesheet>  
```  
  
### <a name="output"></a><span data-ttu-id="e5956-170">Output</span><span class="sxs-lookup"><span data-stu-id="e5956-170">Output</span></span>  

 `<circles xmlns:myObj="urn:myObj">`  
  
 `<circle>`  
  
 `<radius>12</radius>`  
  
 `<circumference>75.398223686155</circumference>`  
  
 `</circle>`  
  
 `<circle>`  
  
 `<radius>37.5</radius>`  
  
 `<circumference>235.61944901923448</circumference>`  
  
 `</circle>`  
  
 `</circles>`  
  
## <a name="see-also"></a><span data-ttu-id="e5956-171">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5956-171">See also</span></span>

- [<span data-ttu-id="e5956-172">Implementierung des XSLT-Prozessors durch die XslTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="e5956-172">XslTransform Class Implements the XSLT Processor</span></span>](xsltransform-class-implements-the-xslt-processor.md)
