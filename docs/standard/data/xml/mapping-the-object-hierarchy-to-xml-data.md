---
title: Zuordnen der Objekthierarchie zu XML-Daten
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 450e350b-6a68-4634-a2a5-33f4dc33baf0
ms.openlocfilehash: 8507c4b323f97279c3054b76aaf8d52f14f0d4ad
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289134"
---
# <a name="mapping-the-object-hierarchy-to-xml-data"></a><span data-ttu-id="e9666-102">Zuordnen der Objekthierarchie zu XML-Daten</span><span class="sxs-lookup"><span data-stu-id="e9666-102">Mapping the Object Hierarchy to XML Data</span></span>
<span data-ttu-id="e9666-103">Wenn sich ein XML-Dokument im Speicher befindet, ist seine konzeptionelle Darstellung eine Struktur.</span><span class="sxs-lookup"><span data-stu-id="e9666-103">When an XML document is in memory, the conceptual representation is a tree.</span></span> <span data-ttu-id="e9666-104">Für das Programmieren verwenden Sie eine Objekthierarchie, um auf die Knoten der Struktur zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="e9666-104">For programming, you have an object hierarchy to access the nodes of the tree.</span></span> <span data-ttu-id="e9666-105">Im folgenden Beispiel wird veranschaulicht, wie aus dem XML-Inhalt Knoten werden.</span><span class="sxs-lookup"><span data-stu-id="e9666-105">The following example shows you how the XML content becomes nodes.</span></span>  
  
 <span data-ttu-id="e9666-106">Wenn der XML-Code in das Dokumentobjektmodell (DOM) eingelesen wird, werden die einzelnen Teile in Knoten umgesetzt, und diese enthalten zusätzliche Metadaten über sich selbst, z. B. ihren Knotentyp und ihre Werte.</span><span class="sxs-lookup"><span data-stu-id="e9666-106">As the XML is read into the XML Document Object Model (DOM), the pieces are translated into nodes, and these nodes retain additional metadata about themselves, such as their node type and values.</span></span> <span data-ttu-id="e9666-107">Der Knotentyp besteht aus seinem Objekt und bestimmt, welche Aktionen ausgeführt und welche Eigenschaften festgelegt oder abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e9666-107">The node type is its object and is what determines what actions can be performed and what properties can be set or retrieved.</span></span>  
  
 <span data-ttu-id="e9666-108">Angenommen, Sie haben folgenden einfachen XML-Code:</span><span class="sxs-lookup"><span data-stu-id="e9666-108">If you have the following simple XML:</span></span>  
  
 <span data-ttu-id="e9666-109">**Eingabe**</span><span class="sxs-lookup"><span data-stu-id="e9666-109">**Input**</span></span>  
  
```xml  
<book>  
    <title>The Handmaid's Tale</title>  
</book>  
```  
  
 <span data-ttu-id="e9666-110">Diese Eingabe wird im Speicher als die folgende Knotenstruktur mit der zugewiesenen Knotentypeigenschaft dargestellt:</span><span class="sxs-lookup"><span data-stu-id="e9666-110">The input is represented in memory as the following node tree with the assigned node type property:</span></span>  
  
 <span data-ttu-id="e9666-111">![Beispiel für Knotenstruktur](media/simple-xml.gif "Simple_XML")</span><span class="sxs-lookup"><span data-stu-id="e9666-111">![example node tree](media/simple-xml.gif "Simple_XML")</span></span>  
<span data-ttu-id="e9666-112">Darstellung von "book" und "title" in der Knotenstruktur</span><span class="sxs-lookup"><span data-stu-id="e9666-112">Book and title node tree representation</span></span>  
  
 <span data-ttu-id="e9666-113">Das `book`-Element wird zu einem **XmlElement**-Objekt, ebenso wie das nächste Element, `title`, zu einem **XmlElement**, während der Elementinhalt zu einem **XmlText**-Objekt wird.</span><span class="sxs-lookup"><span data-stu-id="e9666-113">The `book` element becomes an **XmlElement** object, the next element, `title`, also becomes an **XmlElement**, while the element content becomes an **XmlText** object.</span></span> <span data-ttu-id="e9666-114">Die Methoden und Eigenschaften von **XmlElement** unterscheiden sich von denen, die für ein **XmlText**-Objekt verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="e9666-114">In looking at the **XmlElement** methods and properties, the methods and properties are different than the methods and properties available on an **XmlText** object.</span></span> <span data-ttu-id="e9666-115">Folglich ist es wichtig, zu wissen, in welchen Knotentyp das XML-Markup umgesetzt wird, da der Knotentyp bestimmt, welche Aktionen ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="e9666-115">So knowing what node type the XML markup becomes is vital, as its node type determines the actions that can be performed.</span></span>  
  
 <span data-ttu-id="e9666-116">Im folgenden Beispiel werden XML-Daten eingelesen, und je nach Knotentyp wird unterschiedlicher Text ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="e9666-116">The following example reads in XML data and writes out different text, depending on the node type.</span></span> <span data-ttu-id="e9666-117">Dabei wird die folgende XML-Datendatei, **items.xml**, als Eingabe verwendet:</span><span class="sxs-lookup"><span data-stu-id="e9666-117">Using the following XML data file as input, **items.xml**:</span></span>  
  
 <span data-ttu-id="e9666-118">**Eingabe**</span><span class="sxs-lookup"><span data-stu-id="e9666-118">**Input**</span></span>  
  
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
  
 <span data-ttu-id="e9666-119">Im folgenden Codebeispiel wird die Datei **items.xml** gelesen, dann werden für jeden Knotentyp Informationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e9666-119">The following code example reads the **items.xml** file and displays information for each node type.</span></span>  
  
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
  
 <span data-ttu-id="e9666-120">Die Ausgabe dieses Beispiels veranschaulicht die Zuordnung der Daten zu den Knotentypen.</span><span class="sxs-lookup"><span data-stu-id="e9666-120">The output from the example reveals the mapping of the data to the node types.</span></span>  
  
 <span data-ttu-id="e9666-121">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="e9666-121">**Output**</span></span>  
  
```xml  
<?xml version='1.0'?><!--This is a sample XML document --><!DOCTYPE Items [<!ENTITY number "123">]<Items><Item>Test with an entity: 123</Item><Item>test with a child element <more> stuff</Item><Item>test with a CDATA section <![CDATA[<456>]]> def</Item><Item>Test with a char entity: A</Item><--Fourteen chars in this element.--><Item>1234567890ABCD</Item></Items>
```  
  
 <span data-ttu-id="e9666-122">Wenn Sie die Eingabe und die daraus generierte Ausgabe Zeile für Zeile betrachten, können Sie anhand der folgenden Tabelle untersuchen, welcher Knotentest welche Ausgabezeilen generiert hat. Dadurch lässt sich feststellen, welche XML-Daten in welchen Knotentyp umgesetzt wurden.</span><span class="sxs-lookup"><span data-stu-id="e9666-122">Taking the input one line at a time and using the output generated from the code, you can use the following table to analyze what node test generated which lines of output, thereby understanding what XML data became what kind of node type.</span></span>  
  
|<span data-ttu-id="e9666-123">Eingabe</span><span class="sxs-lookup"><span data-stu-id="e9666-123">Input</span></span>|<span data-ttu-id="e9666-124">Output</span><span class="sxs-lookup"><span data-stu-id="e9666-124">Output</span></span>|<span data-ttu-id="e9666-125">Knotentyptest</span><span class="sxs-lookup"><span data-stu-id="e9666-125">Node Type Test</span></span>|  
|-----------|------------|--------------------|  
|\<?xml version="1.0"?>|\<?xml version='1.0'?>|<span data-ttu-id="e9666-126">XmlNodeType.XmlDeclaration</span><span class="sxs-lookup"><span data-stu-id="e9666-126">XmlNodeType.XmlDeclaration</span></span>|  
|\<!-- This is a sample XML document -->|\<!--This is a sample XML document -->|<span data-ttu-id="e9666-127">XmlNodeType.Comment</span><span class="sxs-lookup"><span data-stu-id="e9666-127">XmlNodeType.Comment</span></span>|  
|<span data-ttu-id="e9666-128">\<!DOCTYPE Items [\<!ENTITY number "123">]></span><span class="sxs-lookup"><span data-stu-id="e9666-128">\<!DOCTYPE Items [\<!ENTITY number "123">]></span></span>|<span data-ttu-id="e9666-129">\<!DOCTYPE Items [\<!ENTITY number "123">]</span><span class="sxs-lookup"><span data-stu-id="e9666-129">\<!DOCTYPE Items [\<!ENTITY number "123">]</span></span>|<span data-ttu-id="e9666-130">XmlNodeType.DocumentType</span><span class="sxs-lookup"><span data-stu-id="e9666-130">XmlNodeType.DocumentType</span></span>|  
|\<Items>|\<Items>|<span data-ttu-id="e9666-131">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="e9666-131">XmlNodeType.Element</span></span>|  
|\<Item>|\<Item>|<span data-ttu-id="e9666-132">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="e9666-132">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="e9666-133">Test mit einer Entität: &number;</span><span class="sxs-lookup"><span data-stu-id="e9666-133">Test with an entity: &number;</span></span>|<span data-ttu-id="e9666-134">Test mit einer Entität: 123</span><span class="sxs-lookup"><span data-stu-id="e9666-134">Test with an entity: 123</span></span>|<span data-ttu-id="e9666-135">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="e9666-135">XmlNodeType.Text</span></span>|  
|\</Item>|\</Item>|<span data-ttu-id="e9666-136">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="e9666-136">XmlNodeType.EndElement</span></span>|  
|\<Item>|\<Item>|<span data-ttu-id="e9666-137">XmNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="e9666-137">XmNodeType.Element</span></span>|  
|<span data-ttu-id="e9666-138">Test mit einem untergeordneten Element</span><span class="sxs-lookup"><span data-stu-id="e9666-138">test with a child element</span></span>|<span data-ttu-id="e9666-139">Test mit einem untergeordneten Element</span><span class="sxs-lookup"><span data-stu-id="e9666-139">test with a child element</span></span>|<span data-ttu-id="e9666-140">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="e9666-140">XmlNodeType.Text</span></span>|  
|\<more>|\<more>|<span data-ttu-id="e9666-141">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="e9666-141">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="e9666-142">stuff</span><span class="sxs-lookup"><span data-stu-id="e9666-142">stuff</span></span>|<span data-ttu-id="e9666-143">stuff</span><span class="sxs-lookup"><span data-stu-id="e9666-143">stuff</span></span>|<span data-ttu-id="e9666-144">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="e9666-144">XmlNodeType.Text</span></span>|  
|\</Item>|\</Item>|<span data-ttu-id="e9666-145">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="e9666-145">XmlNodeType.EndElement</span></span>|  
|\<Item>|\<Item>|<span data-ttu-id="e9666-146">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="e9666-146">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="e9666-147">test with a CDATA section</span><span class="sxs-lookup"><span data-stu-id="e9666-147">test with a CDATA section</span></span>|<span data-ttu-id="e9666-148">test with a CDATA section</span><span class="sxs-lookup"><span data-stu-id="e9666-148">test with a CDATA section</span></span>|<span data-ttu-id="e9666-149">XmlTest.Text</span><span class="sxs-lookup"><span data-stu-id="e9666-149">XmlTest.Text</span></span>|  
|<span data-ttu-id="e9666-150"><![CDATA[\<456>]]\></span><span class="sxs-lookup"><span data-stu-id="e9666-150"><![CDATA[\<456>]]\></span></span>|<span data-ttu-id="e9666-151"><![CDATA[\<456>]]\></span><span class="sxs-lookup"><span data-stu-id="e9666-151"><![CDATA[\<456>]]\></span></span>|<span data-ttu-id="e9666-152">XmlTest.CDATA</span><span class="sxs-lookup"><span data-stu-id="e9666-152">XmlTest.CDATA</span></span>|  
|<span data-ttu-id="e9666-153">def</span><span class="sxs-lookup"><span data-stu-id="e9666-153">def</span></span>|<span data-ttu-id="e9666-154">def</span><span class="sxs-lookup"><span data-stu-id="e9666-154">def</span></span>|<span data-ttu-id="e9666-155">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="e9666-155">XmlNodeType.Text</span></span>|  
|\</Item>|\</Item>|<span data-ttu-id="e9666-156">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="e9666-156">XmlNodeType.EndElement</span></span>|  
|\<Item>|\<Item>|<span data-ttu-id="e9666-157">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="e9666-157">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="e9666-158">Test mit einer char-Entität: &\#65;</span><span class="sxs-lookup"><span data-stu-id="e9666-158">Test with a char entity: &\#65;</span></span>|<span data-ttu-id="e9666-159">Test mit einer char-Entität: A</span><span class="sxs-lookup"><span data-stu-id="e9666-159">Test with a char entity: A</span></span>|<span data-ttu-id="e9666-160">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="e9666-160">XmlNodeType.Text</span></span>|  
|\</Item>|\</Item>|<span data-ttu-id="e9666-161">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="e9666-161">XmlNodeType.EndElement</span></span>|  
|\<!-- Fourteen chars in this element.-->|\<--Fourteen chars in this element.-->|<span data-ttu-id="e9666-162">XmlNodeType.Comment</span><span class="sxs-lookup"><span data-stu-id="e9666-162">XmlNodeType.Comment</span></span>|  
|\<Item>|\<Item>|<span data-ttu-id="e9666-163">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="e9666-163">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="e9666-164">1234567890ABCD</span><span class="sxs-lookup"><span data-stu-id="e9666-164">1234567890ABCD</span></span>|<span data-ttu-id="e9666-165">1234567890ABCD</span><span class="sxs-lookup"><span data-stu-id="e9666-165">1234567890ABCD</span></span>|<span data-ttu-id="e9666-166">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="e9666-166">XmlNodeType.Text</span></span>|  
|\</Item>|\</Item>|<span data-ttu-id="e9666-167">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="e9666-167">XmlNodeType.EndElement</span></span>|  
|\</Items>|\</Items>|<span data-ttu-id="e9666-168">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="e9666-168">XmlNodeType.EndElement</span></span>|  
  
 <span data-ttu-id="e9666-169">Sie müssen wissen, welcher Knotentyp zugewiesen wird, da der Knotentyp steuert, welche Arten von Aktionen zulässig sind und welche Eigenschaften Sie festlegen und abrufen können.</span><span class="sxs-lookup"><span data-stu-id="e9666-169">You must know what node type is assigned, as the node type controls what kinds of actions are valid and what kind of properties you can set and retrieve.</span></span>  
  
 <span data-ttu-id="e9666-170">Die Knotenerstellung für Leerraum wird gesteuert, wenn die Daten durch das **PreserveWhitespace**-Flag in das DOM geladen werden.</span><span class="sxs-lookup"><span data-stu-id="e9666-170">Node creation for white space is controlled when the data is loaded into the DOM by the **PreserveWhitespace** flag.</span></span> <span data-ttu-id="e9666-171">Weitere Informationen finden Sie unter [Behandlung von Leerräumen und signifikanten Leerräumen beim Laden des DOM](white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="e9666-171">For more information, see [White Space and Significant White Space Handling when Loading the DOM](white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span></span>  
  
 <span data-ttu-id="e9666-172">Weitere Informationen zum Hinzufügen von neuen Knoten zum DOM finden Sie unter [Einfügen von Knoten in ein XML-Dokument](inserting-nodes-into-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="e9666-172">To add new nodes to the DOM, see [Inserting Nodes into an XML Document](inserting-nodes-into-an-xml-document.md).</span></span> <span data-ttu-id="e9666-173">Weitere Informationen zum Entfernen von Knoten aus dem DOM finden Sie unter [Entfernen von Knoten, Inhalten und Werten aus einem XML-Dokument](removing-nodes-content-and-values-from-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="e9666-173">To remove nodes from the DOM, see [Removing Nodes, Content, and Values from an XML Document](removing-nodes-content-and-values-from-an-xml-document.md).</span></span> <span data-ttu-id="e9666-174">Weitere Informationen zum Ändern des Inhalts von Knoten im DOM finden Sie unter [Ändern von Knoten, Inhalten und Werten in einem XML-Dokument](modifying-nodes-content-and-values-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="e9666-174">To modify the content of nodes in the DOM, see [Modifying Nodes, Content, and Values in an XML Document](modifying-nodes-content-and-values-in-an-xml-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9666-175">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9666-175">See also</span></span>

- [<span data-ttu-id="e9666-176">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="e9666-176">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
