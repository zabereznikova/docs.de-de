---
title: XML-Value-Eigenschaft (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
ms.openlocfilehash: 46f81e39686da30270cd67edeb4c9f2d43e048b3
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592004"
---
# <a name="xml-value-property-visual-basic"></a>XML-Value-Eigenschaft (Visual Basic)

Bietet Zugriff auf den Wert des ersten Elements einer Auflistung von <xref:System.Xml.Linq.XElement>-Objekten.

## <a name="syntax"></a>Syntax

```vb
object.Value
```

## <a name="parts"></a>Teile

|Begriff|Definition|  
|---|---|  
|`object`|Erforderlich. Auflistung von <xref:System.Xml.Linq.XElement>-Objekten.|  

## <a name="return-value"></a>Rückgabewert

 Eine `String`, die den Wert des ersten Elements der Auflistung enthält, oder `Nothing`, wenn die Auflistung leer ist.

## <a name="remarks"></a>Hinweise

 Die <xref:System.Xml.Linq.XElement.Value%2A>-Eigenschaft erleichtert den Zugriff auf den Wert des ersten Elements in einer Auflistung von <xref:System.Xml.Linq.XElement>-Objekten. Diese Eigenschaft prüft zunächst, ob die Auflistung mindestens ein-Objekt enthält. Wenn die Auflistung leer ist, gibt diese Eigenschaft `Nothing` zurück. Andernfalls gibt diese Eigenschaft den Wert der <xref:System.Xml.Linq.XElement.Value%2A>-Eigenschaft des ersten Elements in der Auflistung zurück.

> [!NOTE]
> Wenn Sie mit dem Bezeichner "\@" auf den Wert eines XML-Attributs zugreifen, wird der Attribut Wert als `String` zurückgegeben, und Sie müssen die <xref:System.Xml.Linq.XAttribute.Value%2A>-Eigenschaft nicht explizit angeben.

 Wenn Sie auf andere Elemente in einer Auflistung zugreifen möchten, können Sie die XML-Erweiterungsindexer-Eigenschaft verwenden. Weitere Informationen finden Sie unter [Extension Indexer-Eigenschaft](extension-indexer-property.md).

## <a name="inheritance"></a>Vererbung

 Die meisten Benutzer müssen nicht <xref:System.Collections.Generic.IEnumerable%601> implementieren, weshalb dieser Abschnitt ignoriert werden kann.

 Die <xref:System.Xml.Linq.XElement.Value%2A>-Eigenschaft ist eine Erweiterungs Eigenschaft für Typen, die `IEnumerable(Of XElement)` implementieren. Die Bindung dieser Erweiterungs Eigenschaft ähnelt der Bindung von Erweiterungs Methoden: Wenn ein Typ eine der Schnittstellen implementiert und eine Eigenschaft mit dem Namen "Value" definiert, hat diese Eigenschaft Vorrang vor der Erweiterungs Eigenschaft. Das heißt, dass diese <xref:System.Xml.Linq.XElement.Value%2A>-Eigenschaft überschrieben werden kann, indem eine neue Eigenschaft in einer Klasse definiert wird, die `IEnumerable(Of XElement)` implementiert.

## <a name="example"></a>Beispiel

 Im folgenden Beispiel wird gezeigt, wie die <xref:System.Xml.Linq.XElement.Value%2A>-Eigenschaft verwendet wird, um auf den ersten Knoten in einer Auflistung von <xref:System.Xml.Linq.XElement>-Objekten zuzugreifen. Im Beispiel wird die-Eigenschaft der untergeordneten-Achse verwendet, um die Auflistung aller untergeordneten Knoten mit dem Namen `phone` zu erhalten, die sich im `contact`-Objekt befinden

 [!code-vb[VbXMLSamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#15)]

 Durch diesen Code wird folgender Text angezeigt:

 `Phone number: 206-555-0144`

## <a name="example"></a>Beispiel

 Im folgenden Beispiel wird gezeigt, wie Sie den Wert eines XML-Attributs aus einer Auflistung von <xref:System.Xml.Linq.XAttribute>-Objekten erhalten. Im Beispiel wird die Eigenschaft Attribut Achse verwendet, um den Wert des `type`-Attributs für alle `phone`-Elemente anzuzeigen.

 [!code-vb[VbXMLSamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#16)]

 Durch diesen Code wird folgender Text angezeigt:

 ```console
 home
 work
```

## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Linq.XElement>
- <xref:System.Collections.Generic.IEnumerable%601>
- [XML-Achseneigenschaften](index.md)
- [XML-Literale](../xml-literals/index.md)
- [Erstellen von XML in Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
- [Erweiterungsmethoden](../../programming-guide/language-features/procedures/extension-methods.md)
- [Erweiterungsindexereigenschaft](extension-indexer-property.md)
- [Untergeordnete XML-Achseneigenschaft](xml-child-axis-property.md)
- [XML-Attributachseneigenschaft](xml-attribute-axis-property.md)
