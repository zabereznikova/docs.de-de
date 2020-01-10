---
title: Erstellen von neuen Attributen für Elemente im Dokumentobjektmodell
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: dd6dc920-b011-418a-b3db-f1580a7d9251
ms.openlocfilehash: 79a3390933256ed862d35c90db0aab2177cdfc41
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711011"
---
# <a name="creating-new-attributes-for-elements-in-the-dom"></a>Erstellen von neuen Attributen für Elemente im Dokumentobjektmodell

Das Erstellen von neuen Attributen unterscheidet sich vom Erstellen anderer Knotentypen, da Attribute keine Knoten sind, sondern Eigenschaften eines Elementknotens, und in einer mit dem Element verknüpften **XmlAttributeCollection** enthalten sind. Es gibt verschiedene Möglichkeiten, ein Attribut zu erstellen und an ein Element anzuhängen:

- Den Elementknoten abrufen und dann mit **SetAttribute** der Attributauflistung dieses Elements ein Attribut hinzufügen

- Mit der **CreateAttribute**-Methode einen **XmlAttribute**-Knoten erstellen, den Elementknoten abrufen und dann mit **SetAttributeNode** den Knoten der Attributauflistung dieses Elements hinzufügen

Im folgenden Beispiel wird gezeigt, wie einem Element mithilfe der Methode " **tstribute** " ein Attribut hinzugefügt wird:

```vb
Imports System.IO
Imports System.Xml

Public Class Sample

    Public Shared Sub Main()

        Dim doc As New XmlDocument()
        doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" & _
                    "<title>Pride And Prejudice</title>" & _
                    "</book>")
        Dim root As XmlElement = doc.DocumentElement

        ' Add a new attribute.
        root.SetAttribute("genre", "urn:samples", "novel")

        Console.WriteLine("Display the modified XML...")
        Console.WriteLine(doc.InnerXml)
    End Sub
End Class
```  
  
```csharp
using System;
using System.IO;
using System.Xml;

public class Sample
{
    public static void Main()
    {
        var doc = new XmlDocument();
        doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" +
                    "<title>Pride And Prejudice</title>" +
                    "</book>");
        XmlElement root = doc.DocumentElement;

        // Add a new attribute.
        root.SetAttribute("genre", "urn:samples", "novel");

        Console.WriteLine("Display the modified XML...");
        Console.WriteLine(doc.InnerXml);
    }
}
```

Im folgenden Beispiel wird dargestellt, wie mit der **CreateAttribute**-Methode ein neues Attribut erstellt wird. Anschließend wird das Attribut mithilfe der **SetAttributeNode**-Methode der Attributauflistung des **book**-Elements hinzugefügt.

Mit dem folgenden XML-Code
  
```xml
<book genre='novel' ISBN='1-861001-57-5'>
<title>Pride And Prejudice</title>
</book>
```

erstellen Sie ein neues Attribut. Geben Sie ihm einen Wert

```vb
Dim attr As XmlAttribute = doc.CreateAttribute("publisher")
attr.Value = "WorldWide Publishing"
```

```csharp
XmlAttribute attr = doc.CreateAttribute("publisher");
attr.Value = "WorldWide Publishing";
```

, und fügen Sie es an das Element an

```vb
doc.DocumentElement.SetAttributeNode(attr)
```

```csharp
doc.DocumentElement.SetAttributeNode(attr);
```

**Ausgabe**

```xml
<book genre="novel" ISBN="1-861001-57-5" publisher="WorldWide Publishing">
<title>Pride And Prejudice</title>
</book>
```

Das vollständige Codebeispiel finden Sie unter <xref:System.Xml.XmlDocument.CreateAttribute%2A>.

Sie können auch einen **XmlAttribute**-Knoten erstellen und diesen mit der **InsertBefore**-Methode oder der **InsertAfter**-Methode an der entsprechenden Position in der Auflistung platzieren. Wenn ein Attribut mit demselben Namen bereits in der Attributauflistung vorhanden ist, wird der bisherige **XmlAttribute**-Knoten aus der Auflistung entfernt, und der neue **XmlAttribute**-Knoten wird eingefügt. Dies erfolgt auf die gleiche Weise wie bei der **SetAttribute**-Methode. Diese Methoden erfordern als Parameter einen vorhandenen Knoten, der als Referenzpunkt für die **InsertBefore**-Methode und die **InsertAfter**-Methode dient. Wenn Sie keinen Referenzknoten bereitstellen, der angibt, wo der neue Knoten eingefügt werden soll, wird mit der **InsertAfter**-Methode der neue Knoten standardmäßig am Anfang der Auflistung eingefügt. Die Standardposition für die **InsertBefore**-Methode ist das Ende der Auflistung, wenn kein Referenzknoten angegeben wird.

Wenn Sie eine **XmlNamedNodeMap** von Attributen erstellt haben, können Sie mithilfe der <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>-Methode ein Attribut anhand des Namens hinzufügen. Weitere Informationen hierzu finden Sie unter [Knotenauflistungen in „NamedNodeMaps“ und „NodeLists“](node-collections-in-namednodemaps-and-nodelists.md).

## <a name="default-attributes"></a>Standard Attribute

Wenn Sie ein Element erstellen, das gemäß Deklaration ein Standardattribut aufweist, wird durch das Dokumentobjektmodell (DOM) ein neues Standardattribut mit seinem Standardwert erstellt und an das Element angehängt. Gleichzeitig werden die untergeordneten Knoten des Standardattributs erstellt.

## <a name="attribute-child-nodes"></a>Untergeordnete Attribut Knoten

Die Werte eines Attributknotens werden zu dessen untergeordneten Knoten. Es gibt nur zwei Typen von gültigen untergeordneten Knoten: **XmlText** -Knoten und **XmlEntityReference** -Knoten. Diese sind dahingehend als untergeordnete Knoten zu betrachten, dass sie von Methoden wie **FirstChild** und **LastChild** als untergeordnete Knoten verarbeitet werden. Dieses Merkmal eines Attributs mit untergeordneten Knoten ist von Bedeutung, wenn Sie versuchen, Attribute oder untergeordnete Knoten von Attributen zu entfernen. Weitere Informationen hierzu finden Sie unter [Entfernen von Attributen aus einem Elementknoten im DOM](removing-attributes-from-an-element-node-in-the-dom.md).

## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](xml-document-object-model-dom.md)
