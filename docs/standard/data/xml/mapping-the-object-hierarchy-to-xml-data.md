---
title: Zuordnen der Objekthierarchie zu XML-Daten
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 450e350b-6a68-4634-a2a5-33f4dc33baf0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1808121049c6344b72b1c9d99e19c46422dfa0c
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "44042557"
---
# <a name="mapping-the-object-hierarchy-to-xml-data"></a><span data-ttu-id="063cc-102">Zuordnen der Objekthierarchie zu XML-Daten</span><span class="sxs-lookup"><span data-stu-id="063cc-102">Mapping the Object Hierarchy to XML Data</span></span>
<span data-ttu-id="063cc-103">Wenn sich ein XML-Dokument im Speicher befindet, ist seine konzeptionelle Darstellung eine Struktur.</span><span class="sxs-lookup"><span data-stu-id="063cc-103">When an XML document is in memory, the conceptual representation is a tree.</span></span> <span data-ttu-id="063cc-104">Für das Programmieren verwenden Sie eine Objekthierarchie, um auf die Knoten der Struktur zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="063cc-104">For programming, you have an object hierarchy to access the nodes of the tree.</span></span> <span data-ttu-id="063cc-105">Im folgenden Beispiel wird veranschaulicht, wie aus dem XML-Inhalt Knoten werden.</span><span class="sxs-lookup"><span data-stu-id="063cc-105">The following example shows you how the XML content becomes nodes.</span></span>  
  
 <span data-ttu-id="063cc-106">Wenn der XML-Code in das Dokumentobjektmodell (DOM) eingelesen wird, werden die einzelnen Teile in Knoten umgesetzt, und diese enthalten zusätzliche Metadaten über sich selbst, z. B. ihren Knotentyp und ihre Werte.</span><span class="sxs-lookup"><span data-stu-id="063cc-106">As the XML is read into the XML Document Object Model (DOM), the pieces are translated into nodes, and these nodes retain additional metadata about themselves, such as their node type and values.</span></span> <span data-ttu-id="063cc-107">Der Knotentyp besteht aus seinem Objekt und bestimmt, welche Aktionen ausgeführt und welche Eigenschaften festgelegt oder abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="063cc-107">The node type is its object and is what determines what actions can be performed and what properties can be set or retrieved.</span></span>  
  
 <span data-ttu-id="063cc-108">Angenommen, Sie haben folgenden einfachen XML-Code:</span><span class="sxs-lookup"><span data-stu-id="063cc-108">If you have the following simple XML:</span></span>  
  
 <span data-ttu-id="063cc-109">**Eingabe**</span><span class="sxs-lookup"><span data-stu-id="063cc-109">**Input**</span></span>  
  
```xml  
<book>  
    <title>The Handmaid's Tale</title>  
</book>  
```  
  
 <span data-ttu-id="063cc-110">Diese Eingabe wird im Speicher als die folgende Knotenstruktur mit der zugewiesenen Knotentypeigenschaft dargestellt:</span><span class="sxs-lookup"><span data-stu-id="063cc-110">The input is represented in memory as the following node tree with the assigned node type property:</span></span>  
  
 <span data-ttu-id="063cc-111">![Beispiel für Knotenstruktur](../../../../docs/standard/data/xml/media/simple-xml.gif "Simple_XML")</span><span class="sxs-lookup"><span data-stu-id="063cc-111">![example node tree](../../../../docs/standard/data/xml/media/simple-xml.gif "Simple_XML")</span></span>  
<span data-ttu-id="063cc-112">Darstellung von „book“ und „title“ in der Knotenstruktur</span><span class="sxs-lookup"><span data-stu-id="063cc-112">Book and title node tree representation</span></span>  
  
 <span data-ttu-id="063cc-113">Das `book`-Element wird zu einem **XmlElement**-Objekt, ebenso wie das nächste Element, `title`, zu einem **XmlElement**, während der Elementinhalt zu einem **XmlText**-Objekt wird.</span><span class="sxs-lookup"><span data-stu-id="063cc-113">The `book` element becomes an **XmlElement** object, the next element, `title`, also becomes an **XmlElement**, while the element content becomes an **XmlText** object.</span></span> <span data-ttu-id="063cc-114">Die Methoden und Eigenschaften von **XmlElement** unterscheiden sich von denen, die für ein **XmlText**-Objekt verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="063cc-114">In looking at the **XmlElement** methods and properties, the methods and properties are different than the methods and properties available on an **XmlText** object.</span></span> <span data-ttu-id="063cc-115">Folglich ist es wichtig, zu wissen, in welchen Knotentyp das XML-Markup umgesetzt wird, da der Knotentyp bestimmt, welche Aktionen ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="063cc-115">So knowing what node type the XML markup becomes is vital, as its node type determines the actions that can be performed.</span></span>  
  
 <span data-ttu-id="063cc-116">Im folgenden Beispiel werden XML-Daten eingelesen, und je nach Knotentyp wird unterschiedlicher Text ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="063cc-116">The following example reads in XML data and writes out different text, depending on the node type.</span></span> <span data-ttu-id="063cc-117">Dabei wird die folgende XML-Datendatei, **items.xml**, als Eingabe verwendet:</span><span class="sxs-lookup"><span data-stu-id="063cc-117">Using the following XML data file as input, **items.xml**:</span></span>  
  
 <span data-ttu-id="063cc-118">**Eingabe**</span><span class="sxs-lookup"><span data-stu-id="063cc-118">**Input**</span></span>  
  
```xml  
<?xml version="1.0"?>  
<!-- This is a sample XML document -->  
<!DOCTYPE Items [<!ENTITY number "123">]>  
<Items>  
  <Item>Test with an entity: &number;</Item>  
  <Item>test with a child element <more/> stuff</Item>  
  <Item>test with a CDATA section <![CDATA[<456>]]> def</Item>  
  <Item>Test with a char entity: A</Item>  
  <!-- Fourteen chars in this element.-->  
  <Item>1234567890ABCD</Item>  
</Items>  
```  
  
 <span data-ttu-id="063cc-119">Im folgenden Codebeispiel wird die Datei **items.xml** gelesen, dann werden für jeden Knotentyp Informationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="063cc-119">The following code example reads the **items.xml** file and displays information for each node type.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
    Private Const filename As String = "items.xml"  
  
    Public Shared Sub Main()  
  
        Dim reader As XmlTextReader = Nothing  
  
        Try  
            ' Load the reader with the data file and   
            'ignore all white space nodes.   
            reader = New XmlTextReader(filename)  
            reader.WhitespaceHandling = WhitespaceHandling.None  
  
            ' Parse the file and display each of the nodes.  
            While reader.Read()  
                Select Case reader.NodeType  
                    Case XmlNodeType.Element  
                        Console.Write("<{0}>", reader.Name)  
                    Case XmlNodeType.Text  
                        Console.Write(reader.Value)  
                    Case XmlNodeType.CDATA  
                        Console.Write("<![CDATA[{0}]]>", reader.Value)  
                    Case XmlNodeType.ProcessingInstruction  
                        Console.Write("<?{0} {1}?>", reader.Name, reader.Value)  
                    Case XmlNodeType.Comment  
                        Console.Write("<!--{0}-->", reader.Value)  
                    Case XmlNodeType.XmlDeclaration  
                        Console.Write("<?xml version='1.0'?>")  
                    Case XmlNodeType.Document  
                    Case XmlNodeType.DocumentType  
                        Console.Write("<!DOCTYPE {0} [{1}]", reader.Name, reader.Value)  
                    Case XmlNodeType.EntityReference  
                        Console.Write(reader.Name)  
                    Case XmlNodeType.EndElement  
                        Console.Write("</{0}>", reader.Name)  
                End Select  
            End While  
  
        Finally  
            If Not (reader Is Nothing) Then  
                reader.Close()  
            End If  
        End Try  
    End Sub 'Main ' End class  
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
    private const String filename = "items.xml";  
  
    public static void Main()  
    {  
        XmlTextReader reader = null;  
  
        try  
        {  
            // Load the reader with the data file and ignore   
            // all white space nodes.  
            reader = new XmlTextReader(filename);  
            reader.WhitespaceHandling = WhitespaceHandling.None;  
  
            // Parse the file and display each of the nodes.  
            while (reader.Read())  
            {  
                switch (reader.NodeType)  
                {  
                    case XmlNodeType.Element:  
                        Console.Write("<{0}>", reader.Name);  
                        break;  
                    case XmlNodeType.Text:  
                        Console.Write(reader.Value);  
                        break;  
                    case XmlNodeType.CDATA:  
                        Console.Write("<![CDATA[{0}]]>", reader.Value);  
                        break;  
                    case XmlNodeType.ProcessingInstruction:  
                        Console.Write("<?{0} {1}?>", reader.Name, reader.Value);  
                        break;  
                    case XmlNodeType.Comment:  
                        Console.Write("<!--{0}-->", reader.Value);  
                        break;  
                    case XmlNodeType.XmlDeclaration:  
                        Console.Write("<?xml version='1.0'?>");  
                        break;  
                    case XmlNodeType.Document:  
                        break;  
                    case XmlNodeType.DocumentType:  
                        Console.Write("<!DOCTYPE {0} [{1}]", reader.Name, reader.Value);  
                        break;  
                    case XmlNodeType.EntityReference:  
                        Console.Write(reader.Name);  
                        break;  
                    case XmlNodeType.EndElement:  
                        Console.Write("</{0}>", reader.Name);  
                        break;  
                }  
            }  
        }  
  
        finally  
        {  
            if (reader != null)  
                reader.Close();  
        }  
    }  
} // End class  
```  
  
 <span data-ttu-id="063cc-120">Die Ausgabe dieses Beispiels veranschaulicht die Zuordnung der Daten zu den Knotentypen.</span><span class="sxs-lookup"><span data-stu-id="063cc-120">The output from the example reveals the mapping of the data to the node types.</span></span>  
  
 <span data-ttu-id="063cc-121">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="063cc-121">**Output**</span></span>  
  
```xml  
<?xml version='1.0'?><!--This is a sample XML document --><!DOCTYPE Items [<!ENTITY number "123">]<Items><Item>Test with an entity: 123</Item><Item>test with a child element <more> stuff</Item><Item>test with a CDATA section <![CDATA[<456>]]> def</Item><Item>Test with a char entity: A</Item><--Fourteen chars in this element.--><Item>1234567890ABCD</Item></Items>  
```  
  
 <span data-ttu-id="063cc-122">Wenn Sie die Eingabe und die daraus generierte Ausgabe Zeile für Zeile betrachten, können Sie anhand der folgenden Tabelle untersuchen, welcher Knotentest welche Ausgabezeilen generiert hat. Dadurch lässt sich feststellen, welche XML-Daten in welchen Knotentyp umgesetzt wurden.</span><span class="sxs-lookup"><span data-stu-id="063cc-122">Taking the input one line at a time and using the output generated from the code, you can use the following table to analyze what node test generated which lines of output, thereby understanding what XML data became what kind of node type.</span></span>  
  
|<span data-ttu-id="063cc-123">Eingabe</span><span class="sxs-lookup"><span data-stu-id="063cc-123">Input</span></span>|<span data-ttu-id="063cc-124">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="063cc-124">Output</span></span>|<span data-ttu-id="063cc-125">Knotentyptest</span><span class="sxs-lookup"><span data-stu-id="063cc-125">Node Type Test</span></span>|  
|-----------|------------|--------------------|  
|<span data-ttu-id="063cc-126">\<?xml version="1.0"?></span><span class="sxs-lookup"><span data-stu-id="063cc-126">\<?xml version="1.0"?></span></span>|<span data-ttu-id="063cc-127">\<?xml version='1.0'?></span><span class="sxs-lookup"><span data-stu-id="063cc-127">\<?xml version='1.0'?></span></span>|<span data-ttu-id="063cc-128">XmlNodeType.XmlDeclaration</span><span class="sxs-lookup"><span data-stu-id="063cc-128">XmlNodeType.XmlDeclaration</span></span>|  
|<span data-ttu-id="063cc-129">\<!-- Dies ist ein XML-Beispieldokument --></span><span class="sxs-lookup"><span data-stu-id="063cc-129">\<!-- This is a sample XML document --></span></span>|<span data-ttu-id="063cc-130">\<!-- Dies ist ein XML-Beispieldokument --></span><span class="sxs-lookup"><span data-stu-id="063cc-130">\<!--This is a sample XML document --></span></span>|<span data-ttu-id="063cc-131">XmlNodeType.Comment</span><span class="sxs-lookup"><span data-stu-id="063cc-131">XmlNodeType.Comment</span></span>|  
|<span data-ttu-id="063cc-132">\<!DOCTYPE Items [\<!ENTITY number "123">]></span><span class="sxs-lookup"><span data-stu-id="063cc-132">\<!DOCTYPE Items [\<!ENTITY number "123">]></span></span>|<span data-ttu-id="063cc-133">\<!DOCTYPE Items [\<!ENTITY number "123">]</span><span class="sxs-lookup"><span data-stu-id="063cc-133">\<!DOCTYPE Items [\<!ENTITY number "123">]</span></span>|<span data-ttu-id="063cc-134">XmlNodeType.DocumentType</span><span class="sxs-lookup"><span data-stu-id="063cc-134">XmlNodeType.DocumentType</span></span>|  
|<span data-ttu-id="063cc-135">\<Items></span><span class="sxs-lookup"><span data-stu-id="063cc-135">\<Items></span></span>|<span data-ttu-id="063cc-136">\<Items></span><span class="sxs-lookup"><span data-stu-id="063cc-136">\<Items></span></span>|<span data-ttu-id="063cc-137">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="063cc-137">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="063cc-138">\<Item></span><span class="sxs-lookup"><span data-stu-id="063cc-138">\<Item></span></span>|<span data-ttu-id="063cc-139">\<Item></span><span class="sxs-lookup"><span data-stu-id="063cc-139">\<Item></span></span>|<span data-ttu-id="063cc-140">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="063cc-140">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="063cc-141">Test mit einer Entität: &number;</span><span class="sxs-lookup"><span data-stu-id="063cc-141">Test with an entity: &number;</span></span>|<span data-ttu-id="063cc-142">Test mit einer Entität: 123</span><span class="sxs-lookup"><span data-stu-id="063cc-142">Test with an entity: 123</span></span>|<span data-ttu-id="063cc-143">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="063cc-143">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="063cc-144">\</Item></span><span class="sxs-lookup"><span data-stu-id="063cc-144">\</Item></span></span>|<span data-ttu-id="063cc-145">\</Item></span><span class="sxs-lookup"><span data-stu-id="063cc-145">\</Item></span></span>|<span data-ttu-id="063cc-146">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="063cc-146">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="063cc-147">\<Item></span><span class="sxs-lookup"><span data-stu-id="063cc-147">\<Item></span></span>|<span data-ttu-id="063cc-148">\<Item></span><span class="sxs-lookup"><span data-stu-id="063cc-148">\<Item></span></span>|<span data-ttu-id="063cc-149">XmNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="063cc-149">XmNodeType.Element</span></span>|  
|<span data-ttu-id="063cc-150">Test mit einem untergeordneten Element</span><span class="sxs-lookup"><span data-stu-id="063cc-150">test with a child element</span></span>|<span data-ttu-id="063cc-151">Test mit einem untergeordneten Element</span><span class="sxs-lookup"><span data-stu-id="063cc-151">test with a child element</span></span>|<span data-ttu-id="063cc-152">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="063cc-152">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="063cc-153">\<more></span><span class="sxs-lookup"><span data-stu-id="063cc-153">\<more></span></span>|<span data-ttu-id="063cc-154">\<more></span><span class="sxs-lookup"><span data-stu-id="063cc-154">\<more></span></span>|<span data-ttu-id="063cc-155">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="063cc-155">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="063cc-156">stuff</span><span class="sxs-lookup"><span data-stu-id="063cc-156">stuff</span></span>|<span data-ttu-id="063cc-157">stuff</span><span class="sxs-lookup"><span data-stu-id="063cc-157">stuff</span></span>|<span data-ttu-id="063cc-158">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="063cc-158">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="063cc-159">\</Item></span><span class="sxs-lookup"><span data-stu-id="063cc-159">\</Item></span></span>|<span data-ttu-id="063cc-160">\</Item></span><span class="sxs-lookup"><span data-stu-id="063cc-160">\</Item></span></span>|<span data-ttu-id="063cc-161">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="063cc-161">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="063cc-162">\<Item></span><span class="sxs-lookup"><span data-stu-id="063cc-162">\<Item></span></span>|<span data-ttu-id="063cc-163">\<Item></span><span class="sxs-lookup"><span data-stu-id="063cc-163">\<Item></span></span>|<span data-ttu-id="063cc-164">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="063cc-164">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="063cc-165">test with a CDATA section</span><span class="sxs-lookup"><span data-stu-id="063cc-165">test with a CDATA section</span></span>|<span data-ttu-id="063cc-166">test with a CDATA section</span><span class="sxs-lookup"><span data-stu-id="063cc-166">test with a CDATA section</span></span>|<span data-ttu-id="063cc-167">XmlTest.Text</span><span class="sxs-lookup"><span data-stu-id="063cc-167">XmlTest.Text</span></span>|  
|<span data-ttu-id="063cc-168"><![CDATA[\<456>]]\></span><span class="sxs-lookup"><span data-stu-id="063cc-168"><![CDATA[\<456>]]\></span></span>|<span data-ttu-id="063cc-169"><![CDATA[\<456>]]\></span><span class="sxs-lookup"><span data-stu-id="063cc-169"><![CDATA[\<456>]]\></span></span>|<span data-ttu-id="063cc-170">XmlTest.CDATA</span><span class="sxs-lookup"><span data-stu-id="063cc-170">XmlTest.CDATA</span></span>|  
|<span data-ttu-id="063cc-171">def</span><span class="sxs-lookup"><span data-stu-id="063cc-171">def</span></span>|<span data-ttu-id="063cc-172">def</span><span class="sxs-lookup"><span data-stu-id="063cc-172">def</span></span>|<span data-ttu-id="063cc-173">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="063cc-173">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="063cc-174">\</Item></span><span class="sxs-lookup"><span data-stu-id="063cc-174">\</Item></span></span>|<span data-ttu-id="063cc-175">\</Item></span><span class="sxs-lookup"><span data-stu-id="063cc-175">\</Item></span></span>|<span data-ttu-id="063cc-176">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="063cc-176">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="063cc-177">\<Item></span><span class="sxs-lookup"><span data-stu-id="063cc-177">\<Item></span></span>|<span data-ttu-id="063cc-178">\<Item></span><span class="sxs-lookup"><span data-stu-id="063cc-178">\<Item></span></span>|<span data-ttu-id="063cc-179">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="063cc-179">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="063cc-180">Test mit einer char-Entität: &\#65;</span><span class="sxs-lookup"><span data-stu-id="063cc-180">Test with a char entity: &\#65;</span></span>|<span data-ttu-id="063cc-181">Test with a char entity: A</span><span class="sxs-lookup"><span data-stu-id="063cc-181">Test with a char entity: A</span></span>|<span data-ttu-id="063cc-182">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="063cc-182">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="063cc-183">\</Item></span><span class="sxs-lookup"><span data-stu-id="063cc-183">\</Item></span></span>|<span data-ttu-id="063cc-184">\</Item></span><span class="sxs-lookup"><span data-stu-id="063cc-184">\</Item></span></span>|<span data-ttu-id="063cc-185">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="063cc-185">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="063cc-186">\<!-- 14 Zeichen in diesem Element.--></span><span class="sxs-lookup"><span data-stu-id="063cc-186">\<!-- Fourteen chars in this element.--></span></span>|<span data-ttu-id="063cc-187">\<--14 Zeichen in diesem Element.--></span><span class="sxs-lookup"><span data-stu-id="063cc-187">\<--Fourteen chars in this element.--></span></span>|<span data-ttu-id="063cc-188">XmlNodeType.Comment</span><span class="sxs-lookup"><span data-stu-id="063cc-188">XmlNodeType.Comment</span></span>|  
|<span data-ttu-id="063cc-189">\<Item></span><span class="sxs-lookup"><span data-stu-id="063cc-189">\<Item></span></span>|<span data-ttu-id="063cc-190">\<Item></span><span class="sxs-lookup"><span data-stu-id="063cc-190">\<Item></span></span>|<span data-ttu-id="063cc-191">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="063cc-191">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="063cc-192">1234567890ABCD</span><span class="sxs-lookup"><span data-stu-id="063cc-192">1234567890ABCD</span></span>|<span data-ttu-id="063cc-193">1234567890ABCD</span><span class="sxs-lookup"><span data-stu-id="063cc-193">1234567890ABCD</span></span>|<span data-ttu-id="063cc-194">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="063cc-194">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="063cc-195">\</Item></span><span class="sxs-lookup"><span data-stu-id="063cc-195">\</Item></span></span>|<span data-ttu-id="063cc-196">\</Item></span><span class="sxs-lookup"><span data-stu-id="063cc-196">\</Item></span></span>|<span data-ttu-id="063cc-197">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="063cc-197">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="063cc-198">\</Items></span><span class="sxs-lookup"><span data-stu-id="063cc-198">\</Items></span></span>|<span data-ttu-id="063cc-199">\</Items></span><span class="sxs-lookup"><span data-stu-id="063cc-199">\</Items></span></span>|<span data-ttu-id="063cc-200">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="063cc-200">XmlNodeType.EndElement</span></span>|  
  
 <span data-ttu-id="063cc-201">Sie müssen wissen, welcher Knotentyp zugewiesen wird, da der Knotentyp steuert, welche Arten von Aktionen zulässig sind und welche Eigenschaften Sie festlegen und abrufen können.</span><span class="sxs-lookup"><span data-stu-id="063cc-201">You must know what node type is assigned, as the node type controls what kinds of actions are valid and what kind of properties you can set and retrieve.</span></span>  
  
 <span data-ttu-id="063cc-202">Die Knotenerstellung für Leerraum wird gesteuert, wenn die Daten durch das **PreserveWhitespace**-Flag in das DOM geladen werden.</span><span class="sxs-lookup"><span data-stu-id="063cc-202">Node creation for white space is controlled when the data is loaded into the DOM by the **PreserveWhitespace** flag.</span></span> <span data-ttu-id="063cc-203">Weitere Informationen finden Sie unter [Behandlung von Leerräumen und signifikanten Leerräumen beim Laden des DOM](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="063cc-203">For more information, see [White Space and Significant White Space Handling when Loading the DOM](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span></span>  
  
 <span data-ttu-id="063cc-204">Weitere Informationen zum Hinzufügen von neuen Knoten zum DOM finden Sie unter [Einfügen von Knoten in ein XML-Dokument](../../../../docs/standard/data/xml/inserting-nodes-into-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="063cc-204">To add new nodes to the DOM, see [Inserting Nodes into an XML Document](../../../../docs/standard/data/xml/inserting-nodes-into-an-xml-document.md).</span></span> <span data-ttu-id="063cc-205">Weitere Informationen zum Entfernen von Knoten aus dem DOM finden Sie unter [Entfernen von Knoten, Inhalten und Werten aus einem XML-Dokument](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="063cc-205">To remove nodes from the DOM, see [Removing Nodes, Content, and Values from an XML Document](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md).</span></span> <span data-ttu-id="063cc-206">Weitere Informationen zum Ändern des Inhalts von Knoten im DOM finden Sie unter [Ändern von Knoten, Inhalten und Werten in einem XML-Dokument](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="063cc-206">To modify the content of nodes in the DOM, see [Modifying Nodes, Content, and Values in an XML Document](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="063cc-207">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="063cc-207">See also</span></span>

- [<span data-ttu-id="063cc-208">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="063cc-208">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
