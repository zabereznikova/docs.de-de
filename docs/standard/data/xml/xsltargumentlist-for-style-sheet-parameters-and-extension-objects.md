---
title: "\"XsltArgumentList\" für Stylesheetparameter und Erweiterungsobjekte"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: de2f0dce-6b98-4908-bba7-ed150cc50355
ms.openlocfilehash: 34ffb9923337bbad90b2170a16d610d26c7f6f23
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160195"
---
# <a name="xsltargumentlist-for-style-sheet-parameters-and-extension-objects"></a>"XsltArgumentList" für Stylesheetparameter und Erweiterungsobjekte
Die <xref:System.Xml.Xsl.XsltArgumentList> enthält XSLT-Parameter (Extensible Stylesheet Transformation) und XSLT-Erweiterungsobjekte. Bei der Übergabe an die <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode können diese Parameter und Erweiterungsobjekte von Stylesheets aus ausgerufen werden.  
  
> [!NOTE]
> Die <xref:System.Xml.Xsl.XslTransform>-Klasse und die <xref:System.Xml.Xsl.XsltArgumentList>-Klasse sind in .NET Framework, Version 2.0, veraltet. Sie können XSLT-Transformationen mit der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse durchführen. Weitere Informationen finden Sie unter [Verwenden der XslCompiledTransform-Klasse](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) und [Migrieren von der XslTransform-Klasse](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).  
  
 Die <xref:System.Xml.Xsl.XsltArgumentList>-Klasse enthält XSLT-Parameter und XSLT-Erweiterungsobjekte. Bei der Übergabe an die <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode können diese Parameter und Erweiterungsobjekte von Stylesheets aus ausgerufen werden.  
  
 Die Übergabe eines Objekts bietet gegenüber der Verwendung eines eingebetteten Skripts folgende Vorteile:  
  
- Sie ermöglicht eine bessere Kapselung und Wiederverwendung von Klassen.  
  
- Stylesheets werden kleiner und sind besser verwaltbar.  
  
- Das Aufrufen von Methoden für Klassen, die zu anderen Namespaces gehören als zu denen, die im Rahmen der unterstützten <xref:System>-Namespaces definiert sind, wird unterstützt.  
  
- Bei Verwendung von <xref:System.Xml.XPath.XPathNodeIterator> wird die Übergabe von Ergebnisstrukturfragmenten an das Stylesheet unterstützt.  
  
## <a name="xslt-style-sheet-parameters"></a>XSLT-Stylesheetparameter  
 XSLT-Parameter werden der <xref:System.Xml.Xsl.XsltArgumentList> mithilfe der <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>-Methode hinzugefügt. Dabei wird ein qualifizierter Name und ein Namespace-URI (Uniform Resource Identifier) mit dem Parameterobjekt verknüpft.  
  
 Das Parameterobjekt muss einem W3C-Typ entsprechen. In der folgenden Tabelle sind die jeweiligen W3C-Typen mit den entsprechenden .NET Framework-Klassen (Typ) aufgelistet, und es ist angegeben, ob es sich bei dem W3C-Typ um einen XPath-Typ (XML Path Language) oder einen XSLT-Typ handelt.  
  
|W3C-Typ|Entsprechende .NET Framework-Klasse (Typ)|XPath-Typ oder XSLT-Typ|  
|--------------|----------------------------------------------|-----------------------------|  
|Zeichenfolge|System.String|XPath|  
|Boolesch|System.Boolean|XPath|  
|Anzahl|System.Double|XPath|  
|Ergebnisstrukturfragment|System.Xml.XPath.XPathNavigator|XSLT|  
|Knotengruppe|System.Xml.XPath.XPathNodeIterator|XPath|  
  
 Wenn es sich bei dem Parameterobjekt um keine der obigen Klassen handelt, wird je nach Bedarf entweder ein {1}Double{2} oder ein {3}String{4} erzwungen. Für die Typen {1}Int16{2}, {3}UInt16{4}, {5}Int32{6}, {7}UInt32{8}, {9}Int64{10}, {11}UInt64{12}, {13}Single{14} und {15}Decimal{16} wird ein {17}Double{18} erzwungen. Für alle anderen Typen wird mit der `ToString`-Methode ein {2}string{3} erzwungen.  
  
#### <a name="to-use-the-xslt-parameter-the-user-needs-to-do-the-following"></a>So verwenden Sie den XSLT-Parameter:  
  
1. Erstellen Sie eine <xref:System.Xml.Xsl.XsltArgumentList> und fügen Sie die Objekte mit <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> hinzu.  
  
2. Rufen Sie die Parameter aus dem Stylesheet auf.  
  
3. Übergeben Sie die <xref:System.Xml.Xsl.XsltArgumentList> an die <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird mit der <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>-Methode ein Parameter erstellt, der das berechnete Skontodatum enthält. Das Skontodatum ist 20 Tage nach dem Auftragsdatum.  
  
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
  
### <a name="input"></a>Eingabe  
 order.xml  
  
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
  
 discount.xsl  
  
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
  
### <a name="output"></a>Ausgabe  
  
```xml  
<order>  
   <total>36.9</total>
   15% discount if paid by: 5/6/2001 5:01:15 PM
</order>  
```  
  
## <a name="xslt-extension-objects"></a>XSLT-Erweiterungsobjekte  
 XSLT-Erweiterungsobjekte werden der <xref:System.Xml.Xsl.XsltArgumentList> mithilfe der <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>-Methode hinzugefügt. Dabei wird ein qualifizierter Name und ein Namespace-URI (Uniform Resource Identifier) mit dem Parameterobjekt verknüpft.  
  
 Wenn ein Objekt hinzugefügt wird, muss der Aufrufer von <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> in den Sicherheitsrichtlinien mit vollständiger Vertrauenswürdigkeit eingestuft sein. Wenn der Aufrufer nur teilweise vertrauenswürdig ist, schlägt das Hinzufügen fehl.  
  
 Das erfolgreiche Hinzufügen eines Objekts garantiert jedoch nicht zwangsläufig eine erfolgreiche Ausführung. Wenn die <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode aufgerufen wird, werden die Berechtigungen mit den zur <xref:System.Xml.Xsl.XslTransform.Load%2A>-Zeit bereitgestellten Beweisen berechnet, und dem gesamten Transformationsprozess wird dieser Berechtigungssatz zugewiesen. Bei dem Versuch, durch ein Erweiterungsobjekt eine Aktion zu initiieren, die eine nicht im Berechtigungssatz enthaltene Berechtigung erfordert, wird eine Ausnahme ausgelöst.  
  
 Von Erweiterungsobjekten kann einer der vier XPath-Grunddatentypen (node-set, Boolean, number oder string) zurückgegeben werden.  
  
#### <a name="to-use-the-xslt-extension-object-the-user-needs-to-do-the-following"></a>So verwenden Sie das XSLT-Erweiterungsobjekt:  
  
1. Erstellen Sie eine <xref:System.Xml.Xsl.XsltArgumentList>, und fügen Sie das Erweiterungsobjekt mit <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> hinzu.  
  
2. Rufen Sie das Erweiterungsobjekt aus dem Stylesheet auf.  
  
3. Übergeben Sie die <xref:System.Xml.Xsl.XsltArgumentList> an die <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der Umfang eines Kreises bei gegebenem Radius berechnet.  
  
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
  
### <a name="input"></a>Eingabe  
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
  
 circle.xsl  
  
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
  
### <a name="output"></a>Ausgabe  
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
  
## <a name="see-also"></a>Siehe auch

- [Implementierung des XSLT-Prozessors durch die XslTransform-Klasse](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
