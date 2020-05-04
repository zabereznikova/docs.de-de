---
title: Steuern der XML-Serialisierung mit Attributen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes, serializing
- XML serialization, examples
- derived classes, serializing
- arrays, serializing
- XML serialization, attributes
- preventing serialization
- attributes [.NET Framework], XML serialization
- serialization, examples
- serialization, attributes
ms.assetid: 47d4c39d-30e1-4c7b-8a2e-301325390647
ms.openlocfilehash: e11152dc626b1e3619b9ecbc04d8a237ca9f13d3
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "80248042"
---
# <a name="controlling-xml-serialization-using-attributes"></a>Steuern der XML-Serialisierung mit Attributen

Attribute können verwendet werden, um die XML-Serialisierung eines Objekts zu steuern oder um einen alternativen XML-Stream aus derselben Reihe von Klassen zu erstellen. Weitere Informationen zum Erstellen eines alternativen XML-Streams finden Sie unter [Vorgehensweise: Angeben eines alternativen Elementnamens für einen XML-Stream](how-to-specify-an-alternate-element-name-for-an-xml-stream.md).

> [!NOTE]
> Wenn der generierte XML-Stream Abschnitt 5 des vom World Wide Web Consortium (W3C) herausgegebenen Dokument mit dem Titel [Simple Object Access Protocol (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/) entsprechen soll, verwenden Sie die unter [Attribute zur Steuerung der Serialisierung von codiertem SOAP aufgeführten Attribute](attributes-that-control-encoded-soap-serialization.md).

Standardmäßig wird der Name eines XML-Elements durch den Klassen- oder Membernamen festgelegt. In einer einfachen Klasse namens `Book` wird, wie in folgendem Beispiel gezeigt, durch ein Feld mit der Bezeichnung `ISBN` ein XML-Elementtag \<ISBN> erstellt.

```vb
Public Class Book
    Public ISBN As String
End Class
' When an instance of the Book class is serialized, it might
' produce this XML:
' <ISBN>1234567890</ISBN>.
```

```csharp
public class Book
{
    public string ISBN;
}
// When an instance of the Book class is serialized, it might
// produce this XML:
// <ISBN>1234567890</ISBN>.
```

Sie können dieses Standardverhalten ändern, wenn Sie das Element umbenennen möchten. Der folgende Code veranschaulicht, wie ein Attribut die Änderung durch das Festlegen der <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A>-Eigenschaft von <xref:System.Xml.Serialization.XmlElementAttribute> ermöglicht.

```vb
Public Class TaxRates
   < XmlElement(ElementName = "TaxRate")> _
    Public ReturnTaxRate As Decimal
End Class
```

```csharp
public class TaxRates {
    [XmlElement(ElementName = "TaxRate")]
    public decimal ReturnTaxRate;
}
```

Weitere Informationen zu Attributen finden Sie unter [Attribute](../../../docs/standard/attributes/index.md). Eine Liste mit Attributen zur Steuerung der XML-Serialisierung finden Sie unter [Attribute zur Steuerung der XML-Serialisierung](attributes-that-control-xml-serialization.md).

## <a name="controlling-array-serialization"></a>Steuern der Serialisierung von Arrays

Die Attribute <xref:System.Xml.Serialization.XmlArrayAttribute> und <xref:System.Xml.Serialization.XmlArrayItemAttribute> dienen zum Steuern der Serialisierung von Arrays. Mit diesen Attributen können Sie den Elementnamen, den Namespace und den XSD-Schemadatentyp steuern (wie im vom World Wide Web Consortium [www.w3.org] herausgegebenen Dokument mit folgendem Titel definiert: „XML Schema Part 2: Datatypes“). Sie können auch die Typen angeben, die in einem Array enthalten sein können.

Durch <xref:System.Xml.Serialization.XmlArrayAttribute> werden die Eigenschaften des einschließenden XML-Elements bestimmt, das aus der Serialisierung eines Arrays hervorgeht. So wird beispielsweise durch das Serialisieren des unten aufgeführten Arrays standardmäßig ein XML-Element mit der Bezeichnung `Employees` erzeugt. Das `Employees`-Element enthält eine Reihe von Elementen, die nach dem Arraytyp `Employee` benannt sind.

```vb
Public Class Group
    Public Employees() As Employee
End Class
Public Class Employee
    Public Name As String
End Class
```

```csharp
public class Group {
    public Employee[] Employees;
}
public class Employee {
    public string Name;
}
```

Eine serialisierte Instanz könnte etwa wie folgt aussehen.

```xml
<Group>
<Employees>
    <Employee>
        <Name>Haley</Name>
    </Employee>
</Employees>
</Group>
```

Sie können den Namen des XML-Elements wie folgt ändern, indem Sie <xref:System.Xml.Serialization.XmlArrayAttribute> anwenden.

```vb
Public Class Group
    <XmlArray("TeamMembers")> _
    Public Employees() As Employee
End Class
```

```csharp
public class Group {
    [XmlArray("TeamMembers")]
    public Employee[] Employees;
}
```

Der resultierende XML-Stream könnte wie folgt aussehen.

```xml
<Group>
<TeamMembers>
    <Employee>
        <Name>Haley</Name>
    </Employee>
</TeamMembers>
</Group>
```

Andererseits steuert <xref:System.Xml.Serialization.XmlArrayItemAttribute>, wie die im Array enthaltenen Elemente serialisiert werden. Beachten Sie, dass das Attribut auf das Feld angewendet wird, das vom Array zurückgegeben wird.

```vb
Public Class Group
    <XmlArrayItem("MemberName")> _
    Public Employee() As Employees
End Class
```

```csharp
public class Group {
    [XmlArrayItem("MemberName")]
    public Employee[] Employees;
}
```

Der resultierende XML-Stream könnte wie folgt aussehen.

```xml
<Group>
<Employees>
    <MemberName>Haley</MemberName>
</Employees>
</Group>
```

## <a name="serializing-derived-classes"></a>Serialisieren von abgeleiteten Klassen

Außerdem ermöglicht <xref:System.Xml.Serialization.XmlArrayItemAttribute> die Serialisierung abgeleiteter Klassen. Zum Beispiel kann eine weitere Klasse mit der Bezeichnung `Manager`, die von `Employee` abgeleitet wird, dem vorigen Beispiel hinzugefügt werden. Wenn Sie <xref:System.Xml.Serialization.XmlArrayItemAttribute> nicht anwenden, schlägt der Code zur Laufzeit fehl, weil der abgeleitete Klassentyp nicht erkannt wird. Um dieses Problem zu beheben, wenden Sie das Attribut zweimal an, und legen Sie jedes Mal die <xref:System.Xml.Serialization.XmlArrayItemAttribute.Type%2A>-Eigenschaft für jeden zulässigen Typ (Basisklasse und abgeleitete Klasse) fest.

```vb
Public Class Group
    <XmlArrayItem(Type:=GetType(Employee)), _
    XmlArrayItem(Type:=GetType(Manager))> _
    Public Employees() As Employee
End Class
Public Class Employee
    Public Name As String
End Class
Public Class Manager
Inherits Employee
    Public Level As Integer
End Class
```

```csharp
public class Group {
    [XmlArrayItem(Type = typeof(Employee)),
    XmlArrayItem(Type = typeof(Manager))]
    public Employee[] Employees;
}
public class Employee {
    public string Name;
}
public class Manager:Employee {
    public int Level;
}
```

Eine serialisierte Instanz könnte etwa wie folgt aussehen.

```xml
<Group>
<Employees>
    <Employee>
        <Name>Haley</Name>
    </Employee>
    <Employee xsi:type = "Manager">
        <Name>Ann</Name>
        <Level>3</Level>
    </Employee>
</Employees>
</Group>
```

## <a name="serializing-an-array-as-a-sequence-of-elements"></a>Serialisieren eines Arrays als Abfolge von Elementen

Sie können ein Array auch als eine flache Abfolge von XML-Elementen serialisieren, indem Sie <xref:System.Xml.Serialization.XmlElementAttribute> auf das Feld anwenden, sodass das Array wie folgt zurückgegeben wird.

```vb
Public Class Group
    <XmlElement> _
    Public Employees() As Employee
End Class
```

```csharp
public class Group {
    [XmlElement]
    public Employee[] Employees;
}
```

Eine serialisierte Instanz könnte etwa wie folgt aussehen.

```xml
<Group>
<Employees>
    <Name>Haley</Name>
</Employees>
<Employees>
    <Name>Noriko</Name>
</Employees>
<Employees>
    <Name>Marco</Name>
</Employees>
</Group>
```

Eine weitere Möglichkeit, die beiden XML-Streams zu unterscheiden, besteht in der Verwendung des Tools für die XML-Schemadefinition zur Generierung der XML-Schemadokumentdateien (XSD) aus dem kompilierten Code. (Nähere Informationen zur Verwendung dieses Tools finden Sie unter [Das XML Schema Definition-Tool und die XML-Serialisierung](the-xml-schema-definition-tool-and-xml-serialization.md).) Wenn keine Attribute auf das Feld angewendet werden, wird das Element auf die folgende Weise durch das Schema beschrieben.

```xml
<xs:element minOccurs="0" maxOccurs ="1" name="Employees" type="ArrayOfEmployee" />
```

Wird <xref:System.Xml.Serialization.XmlElementAttribute> auf das Feld angewendet, wird das Element durch das resultierende Schema auf folgende Weise beschrieben.

```xml
<xs:element minOccurs="0" maxOccurs="unbounded" name="Employees" type="Employee" />
```

## <a name="serializing-an-arraylist"></a>Serialisieren einer ArrayList-Klasse

Die <xref:System.Collections.ArrayList>-Klasse kann eine Auflistung verschiedenartiger Objekte enthalten. Daher können Sie eine <xref:System.Collections.ArrayList>-Klasse wie ein Array verwenden. Statt ein Feld zu erstellen, das ein Array von Objekten mit Typbindung zurückgibt, können Sie auch ein Feld erstellen, das ein einzelnes <xref:System.Collections.ArrayList>-Objekt zurückgibt. Ebenso wie mit Arrays müssen Sie die <xref:System.Xml.Serialization.XmlSerializer>-Klasse jedoch über die Typen der in der <xref:System.Collections.ArrayList>-Klasse enthaltenen Objekte informieren. Hierzu müssen Sie dem Feld mehrere Instanzen von <xref:System.Xml.Serialization.XmlElementAttribute> zuweisen, wie im folgenden Beispiel gezeigt wird.

```vb
Public Class Group
    <XmlElement(Type:=GetType(Employee)), _
    XmlElement(Type:=GetType(Manager))> _
    Public Info As ArrayList
End Class
```

```csharp
public class Group {
    [XmlElement(Type = typeof(Employee)),
    XmlElement(Type = typeof(Manager))]
    public ArrayList Info;
}
```

## <a name="controlling-serialization-of-classes-using-xmlrootattribute-and-xmltypeattribute"></a>Kontrollieren von Serialisierung von Klassen mit den Attributen XmlRootAttribute und XmlTypeAttribute

Es gibt zwei Attribute, die (ausschließlich) auf Klassen angewendet werden können: <xref:System.Xml.Serialization.XmlRootAttribute> und <xref:System.Xml.Serialization.XmlTypeAttribute>. Diese Attribute sind sich sehr ähnlich. <xref:System.Xml.Serialization.XmlRootAttribute> kann nur auf eine einzige Klasse angewendet werden: auf die Klasse, die bei Serialisierung das öffnende und schließende Element, d.&#160;h. das Stammelement, darstellt. <xref:System.Xml.Serialization.XmlTypeAttribute> kann dagegen auf beliebige Klassen einschließlich der Stammklasse angewendet werden.

So ist beispielsweise im vorigen Beispiel die `Group`-Klasse die Stammklasse, und alle ihre öffentlichen Felder und Eigenschaften werden zu XML-Elementen, die im XML-Dokument enthalten sind. Es kann daher nur eine Stammklasse geben. Durch die Anwendung von <xref:System.Xml.Serialization.XmlRootAttribute> können Sie den von <xref:System.Xml.Serialization.XmlSerializer> generierten XML-Stream steuern. Beispielsweise können Sie den Elementnamen und den Namespace ändern.

<xref:System.Xml.Serialization.XmlTypeAttribute> ermöglicht es Ihnen, das Schema des generierten XML-Streams zu steuern. Diese Fähigkeit ist hilfreich, wenn Sie das Schema über einen XML-Webdienst veröffentlichen müssen. Im folgenden Beispiel werden das <xref:System.Xml.Serialization.XmlTypeAttribute>-Attribut und das <xref:System.Xml.Serialization.XmlRootAttribute>-Attribut auf dieselbe Klasse angewendet.

```vb
<XmlRoot("NewGroupName"), _
XmlType("NewTypeName")> _
Public Class Group
    Public Employees() As Employee
End Class
```

```csharp
[XmlRoot("NewGroupName")]
[XmlType("NewTypeName")]
public class Group {
    public Employee[] Employees;
}
```

Wenn diese Klasse kompiliert wird und ihr Schema mit dem XML Schema Definition-Tool generiert wurde, erhalten Sie als Beschreibung von `Group` den folgenden XML-Stream.

```xml
<xs:element name="NewGroupName" type="NewTypeName" />
```

Wenn Sie dagegen eine Instanz der Klasse serialisieren würden, würde das XML-Dokument lediglich `NewGroupName` enthalten.

```xml
<NewGroupName>
    . . .
</NewGroupName>
```

## <a name="preventing-serialization-with-the-xmlignoreattribute"></a>Verhindern der Serialisierung mit dem Attribut XmlIgnoreAttribute

Es kann vorkommen, dass eine öffentliche Eigenschaft oder ein öffentliches Feld nicht serialisiert werden muss. Zum Beispiel konnte ein Feld oder eine Eigenschaft zum Speichern von Metadaten verwendet werden. Wenden Sie in diesen Fällen <xref:System.Xml.Serialization.XmlIgnoreAttribute> auf das Feld oder die Eigenschaft an. <xref:System.Xml.Serialization.XmlSerializer> überspringt dann das Feld bzw. die Eigenschaft.

## <a name="see-also"></a>Siehe auch

- [Attribute zur Steuerung der XML-Serialisierung](attributes-that-control-xml-serialization.md)
- [Attribute zur Steuerung der Serialisierung von codiertem SOAP](attributes-that-control-encoded-soap-serialization.md)
- [Einführung in die XML-Serialisierung](introducing-xml-serialization.md)
- [Beispiele für die XML-Serialisierung](examples-of-xml-serialization.md)
- [How to: Angeben eines alternativen Elementnamens für einen XML-Stream](how-to-specify-an-alternate-element-name-for-an-xml-stream.md).
- [How to: Serialisieren eines Objekts](how-to-serialize-an-object.md).
- [How to: Deserialisieren eines Objekts](how-to-deserialize-an-object.md).
