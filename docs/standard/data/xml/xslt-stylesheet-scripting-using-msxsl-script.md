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
# <a name="xslt-stylesheet-scripting-using-msxslscript"></a>Skripterstellung für ein XSLT-Stylesheet mit \<msxsl:script>
Die <xref:System.Xml.Xsl.XslTransform>-Klasse unterstützt die Erstellung eingebetteter Skripts mit dem `script`-Element.  
  
> [!NOTE]
> Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist in .NET Framework 2.0 veraltet. Mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse können Sie XSLT-Transformationen (Extensible Stylesheet Language for Transformations) vornehmen. Weitere Informationen finden Sie unter [Verwenden der XslCompiledTransform-Klasse](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) und [Migrieren von der XslTransform-Klasse](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).  
  
 Die <xref:System.Xml.Xsl.XslTransform>-Klasse unterstützt die Erstellung eingebetteter Skripts mit dem `script`-Element. Wenn das Stylesheet geladen wird, werden alle definierten Funktionen durch Wrapping in eine Klassendefinition in die Microsoft Intermediate Language (MSIL) kompiliert, sodass kein Leistungsverlust auftritt.  
  
 Das `<msxsl:script>`-Element wird im Folgenden definiert:  
  
```xml  
<msxsl:script language = "language-name" implements-prefix = "prefix of user namespace"> </msxsl:script>  
```  
  
 Dabei ist `msxsl` ein an den Namespace `urn:schemas-microsoft-com:xslt` gebundenes Präfix.  
  
 Das `language`-Attribut ist nicht obligatorisch, aber wenn es angegeben ist, muss sein Wert einer der folgenden sein: `C#`, `VB`, `JScript`, `JavaScript`, `VisualBasic`oder `CSharp`. Wenn es nicht angegeben wird, wird die Standardsprache JScript verwendet. Beim `language-name` wird die Groß- und Kleinschreibung nicht unterschieden, daher sind "JavaScript" und "javascript" identisch.  
  
 Das `implements-prefix`-Attribut ist erforderlich. Mit diesem Attribut wird ein Namespace deklariert und mit dem Skriptblock verknüpft. Der Wert dieses Attributs ist das Präfix, das den Namespace darstellt. Dieser Namespace kann an einer beliebigen Stelle im Stylesheet definiert werden.  
  
 Da das `msxsl:script`-Element zum `urn:schemas-microsoft-com:xslt`-Namespace gehört, muss das Stylesheet die `xmlns:msxsl=urn:schemas-microsoft-com:xslt`-Namespacedeklaration enthalten.  
  
 Wenn der Aufrufer des Skripts nicht über die <xref:System.Security.Permissions.SecurityPermissionFlag>-Zugriffsberechtigung verfügt, wird das Skript in einem Stylesheet nicht kompiliert, und der Aufruf von <xref:System.Xml.Xsl.XslTransform.Load%2A> schlägt fehl.  
  
 Wenn der Aufrufer über die `UnmanagedCode`-Berechtigung verfügt, wird das Skript kompiliert. Die zulässigen Vorgänge hängen vom Beweis ab, der zur Ladezeit bereitgestellt wird.  
  
 Wenn Sie eine der <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methoden verwenden, die zum Laden des Stylesheets einen <xref:System.Xml.XmlReader> oder einen <xref:System.Xml.XPath.XPathNavigator> akzeptiert, müssen Sie die <xref:System.Xml.Xsl.XslTransform.Load%2A>-Überladung verwenden, die einen <xref:System.Security.Policy.Evidence>-Parameter als Argument akzeptiert. Zum Bereitstellen eines Beweises muss der Aufrufer über die <xref:System.Security.Permissions.SecurityPermissionFlag>-Berechtigung verfügen, um `Evidence` für die Skriptassembly zur Verfügung zu stellen. Wenn der Aufrufer nicht über diese Berechtigung verfügt, kann der `Evidence`-Parameter auf `null` festgelegt werden. Auf diese Weise schlägt die <xref:System.Xml.Xsl.XslTransform.Load%2A>-Funktion fehl, falls ein Skript gefunden wird. Die `ControlEvidence`-Berechtigung ist äußerst umfassend und sollte nur für in hohem Maße vertrauenswürdigen Code erteilt werden.  
  
 Zum Abrufen des Beweises aus der Assembly verwenden Sie `this.GetType().Assembly.Evidence`. Zum Abrufen des Beweises aus einem URI (Uniform Resource Identifier) verwenden Sie `Evidence e = XmlSecureResolver.CreateEvidenceForUrl(stylesheetURI)`.  
  
 Wenn Sie <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methoden verwenden, die einen <xref:System.Xml.XmlResolver> akzeptieren, nicht jedoch `Evidence`, wird in der Standardeinstellung als Sicherheitszone für die Assembly "Voll vertrauenswürdig" verwendet. Weitere Informationen finden Sie unter <xref:System.Security.SecurityZone> und [Benannte Berechtigungssätze](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/4652tyx7(v=vs.100)).  
  
 Funktionen können innerhalb des `msxsl:script`-Elements deklariert werden. In der folgenden Tabelle werden die Namespaces angezeigt, die standardmäßig unterstützt werden. Sie können Klassen außerhalb der aufgeführten Namespaces verwenden. Diese Klassen müssen jedoch voll qualifiziert sein.  
  
|Standardnamespaces|Beschreibung|  
|------------------------|-----------------|  
|System|Systemklasse.|  
|System.Collection|Auflistungsklassen.|  
|System.Text|Textklassen.|  
|System.Text.RegularExpressions|Klassen für reguläre Ausdrücke.|  
|System.Xml|Kern-XML-Klassen.|  
|System.Xml.Xsl|XSLT-Klassen.|  
|System.Xml.XPath|XPath-Klassen (XML Path Language).|  
|Microsoft.VisualBasic|Klassen für Microsoft Visual Basic-Skripts|  
  
 Wenn eine Funktion deklariert wurde, ist sie in einem Skriptblock enthalten. Stylesheets können mehrere voneinander unabhängige Skriptblöcke enthalten. Sie können daher bei der Ausführung innerhalb eines Skriptblocks nur dann eine Funktion aufrufen, die Sie in einem anderen Skriptblock definiert haben, wenn diese Funktion so deklariert wurde, dass sie den gleichen Namespace und die gleiche Skriptsprache verwendet. Da jeder Skriptblock in einer eigenen Sprache vorliegen kann und der Block gemäß der Grammatikregeln für den betreffenden Sprachparser analysiert wird, müssen Sie die korrekte Syntax für die verwendete Sprache einhalten. Beispiel: Wenn Sie in einem C#-Skriptblock arbeiten, darf in dem Block kein XML-Kommentarknoten `<!-- an XML comment -->` verwendet werden.  
  
 Die bereitgestellten, durch die Skriptfunktionen definierten Argumente und Rückgabewerte müssen zu einem der XPath- oder XSLT-Typen des W3C (World Wide Web Consortium) gehören. In der folgenden Tabelle werden die jeweiligen W3C-Typen mit den entsprechenden .NET Framework-Klassen (Typen) samt der Informationen aufgeführt, ob es sich bei einem W3C-Typ um einen XPath-Typ oder einen XSLT-Typ handelt.  
  
|Typ|Entsprechende .NET Framework-Klasse (Typ)|XPath-Typ oder XSLT-Typ|  
|----------|----------------------------------------------|-----------------------------|  
|Zeichenfolge|System.String|XPath|  
|Boolean|System.Boolean|XPath|  
|Number|System.Double|XPath|  
|Ergebnisstrukturfragment|System.Xml.XPath.XPathNavigator|XSLT|  
|Knotengruppe|System.Xml.XPath.XPathNodeIterator|XPath|  
  
 Wenn die Skriptfunktion einen der folgenden numerischen Typen verwendet: Int16, UInt16, Int32, UInt32, Int64, UInt64, Single oder Decimal, werden diese Typen in Double umgewandelt, wodurch eine Zuordnung zur XPath-Typnummer des W3C erfolgt. Für alle anderen Typen wird durch einen Aufruf der `ToString`-Methode eine Umwandlung in string erzwungen.  
  
 Wenn die Skriptfunktion einen anderen als die oben genannten Typen verwendet oder wenn sie beim Laden des Stylesheets in das <xref:System.Xml.Xsl.XslTransform>-Objekt nicht kompiliert wird, wird eine Ausnahme ausgelöst.  
  
 Bei Verwendung des `msxsl:script`-Elements wird dringend empfohlen, das Skript ungeachtet der verwendeten Sprache in einem CDATA-Abschnitt zu platzieren. Folgender XML-Code veranschaulicht z. B. die Vorlage für den CDATA-Abschnitt, in dem der Code platziert wird.  
  
```xml  
<msxsl:script implements-prefix='yourprefix' language='CSharp'>  
    <![CDATA[  
    ... your code here ...  
    ]]>  
</msxsl:script>  
```  
  
 Es wird dringend empfohlen, den gesamten Skriptinhalt in einem CDATA-Abschnitt zu platzieren, da Operatoren, Bezeichner oder Trennzeichen für eine angegebene Sprache möglicherweise als XML interpretiert werden können. Das folgende Codebeispiel veranschaulicht die Verwendung des logischen AND-Operators in einem Skript.  
  
```xml  
<msxsl:script implements-prefix='yourprefix' language='CSharp'>  
    public string book(string abc, string xyz)  
    {  
        if ((abc == bar) && (abc == xyz)) return bar + xyz;  
        else return null;  
    }  
</msxsl:script>  
```  
  
 Hierdurch wird eine Ausnahme ausgelöst, da die kaufmännischen Und-Zeichen nicht durch Escapezeichen geschützt sind. Das Dokument wird als XML geladen, und der Text zwischen den `msxsl:script`-Elementtags wird nicht in besonderer Weise behandelt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der Umfang eines Kreises bei angegebenem Radius unter Verwendung eines eingebetteten Skripts berechnet.  
  
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
  
## <a name="input"></a>Input  
 number.xml  
  
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
  
 calc.xsl  
  
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
  
## <a name="output"></a>Ausgabe  
  
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
  
## <a name="see-also"></a>Siehe auch

- [Implementierung des XSLT-Prozessors durch die XslTransform-Klasse](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
