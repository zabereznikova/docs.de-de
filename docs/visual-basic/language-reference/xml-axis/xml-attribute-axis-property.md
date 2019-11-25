---
title: XML Attribute Axis Property
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyAttributeAxis
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
ms.openlocfilehash: 109c4b45a5e3ed4e3e4db49687df5cb127a5e0c6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352674"
---
# <a name="xml-attribute-axis-property-visual-basic"></a>XML-Attributachseneigenschaft (Visual Basic)
Provides access to the value of an attribute for an <xref:System.Xml.Linq.XElement> object or to the first element in a collection of <xref:System.Xml.Linq.XElement> objects.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
object.@attribute  
' -or-  
object.@<attribute>  
```  
  
## <a name="parts"></a>Teile  
 `object`  
 Erforderlich. An <xref:System.Xml.Linq.XElement> object or a collection of <xref:System.Xml.Linq.XElement> objects.  
  
 .@  
 Erforderlich. Denotes the start of an attribute axis property.  
  
 <  
 Dies ist optional. Denotes the beginning of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.  
  
 `attribute`  
 Erforderlich. Name of the attribute to access, of the form [`prefix`:]`name`.  
  
|Segment|Beschreibung|  
|----------|-----------------|  
|`prefix`|Dies ist optional. XML namespace prefix for the attribute. Muss ein globaler XML-Namespace sein, der mit einer `Imports`-Anweisung definiert ist.|  
|`name`|Erforderlich. Local attribute name. See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Dies ist optional. Denotes the end of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.  
  
## <a name="return-value"></a>Rückgabewert  
 A string that contains the value of `attribute`. If the attribute name does not exist, `Nothing` is returned.  
  
## <a name="remarks"></a>Hinweise  
 You can use an XML attribute axis property to access the value of an attribute by name from an <xref:System.Xml.Linq.XElement> object or from the first element in a collection of <xref:System.Xml.Linq.XElement> objects. You can retrieve an attribute value by name, or add a new attribute to an element by specifying a new name preceded by the @ identifier.  
  
 When you refer to an XML attribute using the @ identifier, the attribute value is returned as a string and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.  
  
 The naming rules for XML attributes differ from the naming rules for Visual Basic identifiers. To access an XML attribute that has a name that is not a valid Visual Basic identifier, enclose the name in angle brackets (\< and >).  
  
## <a name="xml-namespaces"></a>XML-Namespaces  
 The name in an attribute axis property can use only XML namespace prefixes declared globally by using the `Imports` statement. Es können keine XML-Namespacepräfixe verwendet werden, die lokal innerhalb von XML-Elementliteralen deklariert wurden. For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Beispiel  
 The following example shows how to get the values of the XML attributes named `type` from a collection of XML elements that are named `phone`.  
  
 [!code-vb[VbXMLSamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#12)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a>Beispiel  
 The following example shows how to create attributes for an XML element both declaratively, as part of the XML, and dynamically by adding an attribute to an instance of an <xref:System.Xml.Linq.XElement> object. The `type` attribute is created declaratively and the `owner` attribute is created dynamically.  
  
 [!code-vb[VbXMLSamples#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#44)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a>Beispiel  
 The following example uses the angle bracket syntax to get the value of the XML attribute named `number-type`, which is not a valid identifier in Visual Basic.  
  
 [!code-vb[VbXMLSamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#13)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Phone type: work`  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix. It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name "`ns:name`".  
  
 [!code-vb[VbXMLSamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples6.vb#14)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Phone type: home`  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Linq.XElement>
- [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/index.md)
- [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)
- [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
