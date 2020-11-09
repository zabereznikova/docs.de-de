---
title: Steuern der XML-Serialisierung mit Attributen
description: Attribute können verwendet werden, um die XML-Serialisierung eines Objekts zu steuern oder um einen alternativen XML-Stream aus derselben Reihe von Klassen zu erstellen.
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
- attributes [.NET], XML serialization
- serialization, examples
- serialization, attributes
ms.assetid: 47d4c39d-30e1-4c7b-8a2e-301325390647
ms.openlocfilehash: 36456d373b7482c4a4267b69e031c1e45baa9abb
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "93281775"
---
# <a name="control-xml-serialization-using-attributes"></a><span data-ttu-id="c1ad3-103">Steuern der XML-Serialisierung mit Attributen</span><span class="sxs-lookup"><span data-stu-id="c1ad3-103">Control XML serialization using attributes</span></span>

<span data-ttu-id="c1ad3-104">Attribute können verwendet werden, um die XML-Serialisierung eines Objekts zu steuern oder um einen alternativen XML-Stream aus derselben Reihe von Klassen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-104">Attributes can be used to control the XML serialization of an object or to create an alternate XML stream from the same set of classes.</span></span> <span data-ttu-id="c1ad3-105">Weitere Informationen zum Erstellen eines alternativen XML-Streams finden Sie unter [Vorgehensweise: Angeben eines alternativen Elementnamens für einen XML-Stream](how-to-specify-an-alternate-element-name-for-an-xml-stream.md).</span><span class="sxs-lookup"><span data-stu-id="c1ad3-105">For more details about creating an alternate XML stream, see [How to: Specify an Alternate Element Name for an XML Stream](how-to-specify-an-alternate-element-name-for-an-xml-stream.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c1ad3-106">Wenn der generierte XML-Stream Abschnitt 5 des vom World Wide Web Consortium (W3C) herausgegebenen Dokument mit dem Titel [Simple Object Access Protocol (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/) entsprechen soll, verwenden Sie die unter [Attribute zur Steuerung der Serialisierung von codiertem SOAP aufgeführten Attribute](attributes-that-control-encoded-soap-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="c1ad3-106">If the XML generated must conform to section 5 of the World Wide Web Consortium (W3C) document titled [Simple Object Access Protocol (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/), use the attributes listed in [Attributes That Control Encoded SOAP Serialization](attributes-that-control-encoded-soap-serialization.md).</span></span>

<span data-ttu-id="c1ad3-107">Standardmäßig wird der Name eines XML-Elements durch den Klassen- oder Membernamen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-107">By default, an XML element name is determined by the class or member name.</span></span> <span data-ttu-id="c1ad3-108">In einer einfachen Klasse namens `Book` wird, wie in folgendem Beispiel gezeigt, durch ein Feld mit der Bezeichnung `ISBN` ein XML-Elementtag \<ISBN> erstellt.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-108">In a simple class named `Book`, a field named `ISBN` will produce an XML element tag \<ISBN>, as shown in the following example.</span></span>

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

<span data-ttu-id="c1ad3-109">Sie können dieses Standardverhalten ändern, wenn Sie das Element umbenennen möchten.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-109">This default behavior can be changed if you want to give the element a new name.</span></span> <span data-ttu-id="c1ad3-110">Der folgende Code veranschaulicht, wie ein Attribut die Änderung durch das Festlegen der <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A>-Eigenschaft von <xref:System.Xml.Serialization.XmlElementAttribute> ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-110">The following code shows how an attribute enables this by setting the <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A> property of a <xref:System.Xml.Serialization.XmlElementAttribute>.</span></span>

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

<span data-ttu-id="c1ad3-111">Weitere Informationen zu Attributen finden Sie unter [Attribute](../attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="c1ad3-111">For more information about attributes, see [Attributes](../attributes/index.md).</span></span> <span data-ttu-id="c1ad3-112">Eine Liste mit Attributen zur Steuerung der XML-Serialisierung finden Sie unter [Attribute zur Steuerung der XML-Serialisierung](attributes-that-control-xml-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="c1ad3-112">For a list of attributes that control XML serialization, see [Attributes That Control XML Serialization](attributes-that-control-xml-serialization.md).</span></span>

## <a name="controlling-array-serialization"></a><span data-ttu-id="c1ad3-113">Steuern der Serialisierung von Arrays</span><span class="sxs-lookup"><span data-stu-id="c1ad3-113">Controlling Array Serialization</span></span>

<span data-ttu-id="c1ad3-114">Die Attribute <xref:System.Xml.Serialization.XmlArrayAttribute> und <xref:System.Xml.Serialization.XmlArrayItemAttribute> dienen zum Steuern der Serialisierung von Arrays.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-114">The <xref:System.Xml.Serialization.XmlArrayAttribute> and the <xref:System.Xml.Serialization.XmlArrayItemAttribute> attributes are designed to control the serialization of arrays.</span></span> <span data-ttu-id="c1ad3-115">Mit diesen Attributen können Sie den Elementnamen, den Namespace und den XSD-Schemadatentyp steuern (wie im vom World Wide Web Consortium [www.w3.org] herausgegebenen Dokument mit folgendem Titel definiert: „XML Schema Part 2: Datatypes“).</span><span class="sxs-lookup"><span data-stu-id="c1ad3-115">Using these attributes, you can control the element name, namespace, and XML Schema (XSD) data type (as defined in the World Wide Web Consortium [www.w3.org] document titled "XML Schema Part 2: Datatypes").</span></span> <span data-ttu-id="c1ad3-116">Sie können auch die Typen angeben, die in einem Array enthalten sein können.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-116">You can also specify the types that can be included in an array.</span></span>

<span data-ttu-id="c1ad3-117">Durch <xref:System.Xml.Serialization.XmlArrayAttribute> werden die Eigenschaften des einschließenden XML-Elements bestimmt, das aus der Serialisierung eines Arrays hervorgeht.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-117">The <xref:System.Xml.Serialization.XmlArrayAttribute> will determine the properties of the enclosing XML element that results when an array is serialized.</span></span> <span data-ttu-id="c1ad3-118">So wird beispielsweise durch das Serialisieren des unten aufgeführten Arrays standardmäßig ein XML-Element mit der Bezeichnung `Employees` erzeugt.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-118">For example, by default, serializing the array below will result in an XML element named `Employees`.</span></span> <span data-ttu-id="c1ad3-119">Das `Employees`-Element enthält eine Reihe von Elementen, die nach dem Arraytyp `Employee` benannt sind.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-119">The `Employees` element will contain a series of elements named after the array type `Employee`.</span></span>

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

<span data-ttu-id="c1ad3-120">Eine serialisierte Instanz könnte etwa wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-120">A serialized instance might resemble the following.</span></span>

```xml
<Group>
<Employees>
    <Employee>
        <Name>Haley</Name>
    </Employee>
</Employees>
</Group>
```

<span data-ttu-id="c1ad3-121">Sie können den Namen des XML-Elements wie folgt ändern, indem Sie <xref:System.Xml.Serialization.XmlArrayAttribute> anwenden.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-121">By applying a <xref:System.Xml.Serialization.XmlArrayAttribute>, you can change the name of the XML element, as follows.</span></span>

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

<span data-ttu-id="c1ad3-122">Der resultierende XML-Stream könnte wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-122">The resulting XML might resemble the following.</span></span>

```xml
<Group>
<TeamMembers>
    <Employee>
        <Name>Haley</Name>
    </Employee>
</TeamMembers>
</Group>
```

<span data-ttu-id="c1ad3-123">Andererseits steuert <xref:System.Xml.Serialization.XmlArrayItemAttribute>, wie die im Array enthaltenen Elemente serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-123">The <xref:System.Xml.Serialization.XmlArrayItemAttribute>, on the other hand, controls how the items contained in the array are serialized.</span></span> <span data-ttu-id="c1ad3-124">Beachten Sie, dass das Attribut auf das Feld angewendet wird, das vom Array zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-124">Note that the attribute is applied to the field returning the array.</span></span>

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

<span data-ttu-id="c1ad3-125">Der resultierende XML-Stream könnte wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-125">The resulting XML might resemble the following.</span></span>

```xml
<Group>
<Employees>
    <MemberName>Haley</MemberName>
</Employees>
</Group>
```

## <a name="serializing-derived-classes"></a><span data-ttu-id="c1ad3-126">Serialisieren von abgeleiteten Klassen</span><span class="sxs-lookup"><span data-stu-id="c1ad3-126">Serializing Derived Classes</span></span>

<span data-ttu-id="c1ad3-127">Außerdem ermöglicht <xref:System.Xml.Serialization.XmlArrayItemAttribute> die Serialisierung abgeleiteter Klassen.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-127">Another use of the <xref:System.Xml.Serialization.XmlArrayItemAttribute> is to allow the serialization of derived classes.</span></span> <span data-ttu-id="c1ad3-128">Zum Beispiel kann eine weitere Klasse mit der Bezeichnung `Manager`, die von `Employee` abgeleitet wird, dem vorigen Beispiel hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-128">For example, another class named `Manager` that derives from `Employee` can be added to the previous example.</span></span> <span data-ttu-id="c1ad3-129">Wenn Sie <xref:System.Xml.Serialization.XmlArrayItemAttribute> nicht anwenden, schlägt der Code zur Laufzeit fehl, weil der abgeleitete Klassentyp nicht erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-129">If you do not apply the <xref:System.Xml.Serialization.XmlArrayItemAttribute>, the code will fail at run time because the derived class type will not be recognized.</span></span> <span data-ttu-id="c1ad3-130">Um dieses Problem zu beheben, wenden Sie das Attribut zweimal an, und legen Sie jedes Mal die <xref:System.Xml.Serialization.XmlArrayItemAttribute.Type%2A>-Eigenschaft für jeden zulässigen Typ (Basisklasse und abgeleitete Klasse) fest.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-130">To remedy this, apply the attribute twice, each time setting the <xref:System.Xml.Serialization.XmlArrayItemAttribute.Type%2A> property for each acceptable type (base and derived).</span></span>

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

<span data-ttu-id="c1ad3-131">Eine serialisierte Instanz könnte etwa wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-131">A serialized instance might resemble the following.</span></span>

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

## <a name="serializing-an-array-as-a-sequence-of-elements"></a><span data-ttu-id="c1ad3-132">Serialisieren eines Arrays als Abfolge von Elementen</span><span class="sxs-lookup"><span data-stu-id="c1ad3-132">Serializing an Array as a Sequence of Elements</span></span>

<span data-ttu-id="c1ad3-133">Sie können ein Array auch als eine flache Abfolge von XML-Elementen serialisieren, indem Sie <xref:System.Xml.Serialization.XmlElementAttribute> auf das Feld anwenden, sodass das Array wie folgt zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-133">You can also serialize an array as a flat sequence of XML elements by applying a <xref:System.Xml.Serialization.XmlElementAttribute> to the field returning the array as follows.</span></span>

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

<span data-ttu-id="c1ad3-134">Eine serialisierte Instanz könnte etwa wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-134">A serialized instance might resemble the following.</span></span>

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

<span data-ttu-id="c1ad3-135">Eine weitere Möglichkeit, die beiden XML-Streams zu unterscheiden, besteht in der Verwendung des Tools für die XML-Schemadefinition zur Generierung der XML-Schemadokumentdateien (XSD) aus dem kompilierten Code.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-135">Another way to differentiate the two XML streams is to use the XML Schema Definition tool to generate the XML Schema (XSD) document files from the compiled code.</span></span> <span data-ttu-id="c1ad3-136">(Nähere Informationen zur Verwendung dieses Tools finden Sie unter [Das XML Schema Definition-Tool und die XML-Serialisierung](the-xml-schema-definition-tool-and-xml-serialization.md).) Wenn keine Attribute auf das Feld angewendet werden, wird das Element auf die folgende Weise durch das Schema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-136">(For more details on using the tool, see [The XML Schema Definition Tool and XML Serialization](the-xml-schema-definition-tool-and-xml-serialization.md).) When no attribute is applied to the field, the schema describes the element in the following manner.</span></span>

```xml
<xs:element minOccurs="0" maxOccurs ="1" name="Employees" type="ArrayOfEmployee" />
```

<span data-ttu-id="c1ad3-137">Wird <xref:System.Xml.Serialization.XmlElementAttribute> auf das Feld angewendet, wird das Element durch das resultierende Schema auf folgende Weise beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-137">When the <xref:System.Xml.Serialization.XmlElementAttribute> is applied to the field, the resulting schema describes the element as follows.</span></span>

```xml
<xs:element minOccurs="0" maxOccurs="unbounded" name="Employees" type="Employee" />
```

## <a name="serializing-an-arraylist"></a><span data-ttu-id="c1ad3-138">Serialisieren einer ArrayList-Klasse</span><span class="sxs-lookup"><span data-stu-id="c1ad3-138">Serializing an ArrayList</span></span>

<span data-ttu-id="c1ad3-139">Die <xref:System.Collections.ArrayList>-Klasse kann eine Auflistung verschiedenartiger Objekte enthalten.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-139">The <xref:System.Collections.ArrayList> class can contain a collection of diverse objects.</span></span> <span data-ttu-id="c1ad3-140">Daher können Sie eine <xref:System.Collections.ArrayList>-Klasse wie ein Array verwenden.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-140">You can therefore use a <xref:System.Collections.ArrayList> much as you use an array.</span></span> <span data-ttu-id="c1ad3-141">Statt ein Feld zu erstellen, das ein Array von Objekten mit Typbindung zurückgibt, können Sie auch ein Feld erstellen, das ein einzelnes <xref:System.Collections.ArrayList>-Objekt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-141">Instead of creating a field that returns an array of typed objects, however, you can create a field that returns a single <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="c1ad3-142">Ebenso wie mit Arrays müssen Sie die <xref:System.Xml.Serialization.XmlSerializer>-Klasse jedoch über die Typen der in der <xref:System.Collections.ArrayList>-Klasse enthaltenen Objekte informieren.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-142">However, as with arrays, you must inform the <xref:System.Xml.Serialization.XmlSerializer> of the types of objects the <xref:System.Collections.ArrayList> contains.</span></span> <span data-ttu-id="c1ad3-143">Hierzu müssen Sie dem Feld mehrere Instanzen von <xref:System.Xml.Serialization.XmlElementAttribute> zuweisen, wie im folgenden Beispiel gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-143">To accomplish this, assign multiple instances of the <xref:System.Xml.Serialization.XmlElementAttribute> to the field, as shown in the following example.</span></span>

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

## <a name="controlling-serialization-of-classes-using-xmlrootattribute-and-xmltypeattribute"></a><span data-ttu-id="c1ad3-144">Kontrollieren von Serialisierung von Klassen mit den Attributen XmlRootAttribute und XmlTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="c1ad3-144">Controlling Serialization of Classes Using XmlRootAttribute and XmlTypeAttribute</span></span>

<span data-ttu-id="c1ad3-145">Es gibt zwei Attribute, die (ausschließlich) auf Klassen angewendet werden können: <xref:System.Xml.Serialization.XmlRootAttribute> und <xref:System.Xml.Serialization.XmlTypeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-145">There are two attributes that can be applied to a class (and only a class): <xref:System.Xml.Serialization.XmlRootAttribute> and <xref:System.Xml.Serialization.XmlTypeAttribute>.</span></span> <span data-ttu-id="c1ad3-146">Diese Attribute sind sich sehr ähnlich.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-146">These attributes are very similar.</span></span> <span data-ttu-id="c1ad3-147"><xref:System.Xml.Serialization.XmlRootAttribute> kann nur auf eine einzige Klasse angewendet werden: auf die Klasse, die bei Serialisierung das öffnende und schließende Element, d.&#160;h. das Stammelement, darstellt.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-147">The <xref:System.Xml.Serialization.XmlRootAttribute> can be applied to only one class: the class that, when serialized, represents the XML document's opening and closing element—in other words, the root element.</span></span> <span data-ttu-id="c1ad3-148"><xref:System.Xml.Serialization.XmlTypeAttribute> kann dagegen auf beliebige Klassen einschließlich der Stammklasse angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-148">The <xref:System.Xml.Serialization.XmlTypeAttribute>, on the other hand, can be applied to any class, including the root class.</span></span>

<span data-ttu-id="c1ad3-149">So ist beispielsweise im vorigen Beispiel die `Group`-Klasse die Stammklasse, und alle ihre öffentlichen Felder und Eigenschaften werden zu XML-Elementen, die im XML-Dokument enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-149">For example, in the previous examples, the `Group` class is the root class, and all its public fields and properties become the XML elements found in the XML document.</span></span> <span data-ttu-id="c1ad3-150">Es kann daher nur eine Stammklasse geben.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-150">Therefore, there can be only one root class.</span></span> <span data-ttu-id="c1ad3-151">Durch die Anwendung von <xref:System.Xml.Serialization.XmlRootAttribute> können Sie den von <xref:System.Xml.Serialization.XmlSerializer> generierten XML-Stream steuern.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-151">By applying the <xref:System.Xml.Serialization.XmlRootAttribute>, you can control the XML stream generated by the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="c1ad3-152">Beispielsweise können Sie den Elementnamen und den Namespace ändern.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-152">For example, you can change the element name and namespace.</span></span>

<span data-ttu-id="c1ad3-153"><xref:System.Xml.Serialization.XmlTypeAttribute> ermöglicht es Ihnen, das Schema des generierten XML-Streams zu steuern.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-153">The <xref:System.Xml.Serialization.XmlTypeAttribute> allows you to control the schema of the generated XML.</span></span> <span data-ttu-id="c1ad3-154">Diese Fähigkeit ist hilfreich, wenn Sie das Schema über einen XML-Webdienst veröffentlichen müssen.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-154">This capability is useful when you need to publish the schema through an XML Web service.</span></span> <span data-ttu-id="c1ad3-155">Im folgenden Beispiel werden das <xref:System.Xml.Serialization.XmlTypeAttribute>-Attribut und das <xref:System.Xml.Serialization.XmlRootAttribute>-Attribut auf dieselbe Klasse angewendet.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-155">The following example applies both the <xref:System.Xml.Serialization.XmlTypeAttribute> and the <xref:System.Xml.Serialization.XmlRootAttribute> to the same class.</span></span>

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

<span data-ttu-id="c1ad3-156">Wenn diese Klasse kompiliert wird und ihr Schema mit dem XML Schema Definition-Tool generiert wurde, erhalten Sie als Beschreibung von `Group` den folgenden XML-Stream.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-156">If this class is compiled, and the XML Schema Definition tool is used to generate its schema, you would find the following XML describing `Group`.</span></span>

```xml
<xs:element name="NewGroupName" type="NewTypeName" />
```

<span data-ttu-id="c1ad3-157">Wenn Sie dagegen eine Instanz der Klasse serialisieren würden, würde das XML-Dokument lediglich `NewGroupName` enthalten.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-157">In contrast, if you were to serialize an instance of the class, only `NewGroupName` would be found in the XML document.</span></span>

```xml
<NewGroupName>
    . . .
</NewGroupName>
```

## <a name="preventing-serialization-with-the-xmlignoreattribute"></a><span data-ttu-id="c1ad3-158">Verhindern der Serialisierung mit dem Attribut XmlIgnoreAttribute</span><span class="sxs-lookup"><span data-stu-id="c1ad3-158">Preventing Serialization with the XmlIgnoreAttribute</span></span>

<span data-ttu-id="c1ad3-159">Es kann vorkommen, dass eine öffentliche Eigenschaft oder ein öffentliches Feld nicht serialisiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-159">There might be situations when a public property or field does not need to be serialized.</span></span> <span data-ttu-id="c1ad3-160">Zum Beispiel konnte ein Feld oder eine Eigenschaft zum Speichern von Metadaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-160">For example, a field or property could be used to contain metadata.</span></span> <span data-ttu-id="c1ad3-161">Wenden Sie in diesen Fällen <xref:System.Xml.Serialization.XmlIgnoreAttribute> auf das Feld oder die Eigenschaft an. <xref:System.Xml.Serialization.XmlSerializer> überspringt dann das Feld bzw. die Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c1ad3-161">In such cases, apply the <xref:System.Xml.Serialization.XmlIgnoreAttribute> to the field or property and the <xref:System.Xml.Serialization.XmlSerializer> will skip over it.</span></span>

## <a name="see-also"></a><span data-ttu-id="c1ad3-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1ad3-162">See also</span></span>

- [<span data-ttu-id="c1ad3-163">Attribute zur Steuerung der XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="c1ad3-163">Attributes That Control XML Serialization</span></span>](attributes-that-control-xml-serialization.md)
- [<span data-ttu-id="c1ad3-164">Attribute zur Steuerung der Serialisierung von codiertem SOAP</span><span class="sxs-lookup"><span data-stu-id="c1ad3-164">Attributes That Control Encoded SOAP Serialization</span></span>](attributes-that-control-encoded-soap-serialization.md)
- [<span data-ttu-id="c1ad3-165">Einführung in die XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="c1ad3-165">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)
- [<span data-ttu-id="c1ad3-166">Beispiele für die XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="c1ad3-166">Examples of XML Serialization</span></span>](examples-of-xml-serialization.md)
- <span data-ttu-id="c1ad3-167">[How to: Angeben eines alternativen Elementnamens für einen XML-Stream](how-to-specify-an-alternate-element-name-for-an-xml-stream.md).</span><span class="sxs-lookup"><span data-stu-id="c1ad3-167">[How to: Specify an Alternate Element Name for an XML Stream](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)</span></span>
- <span data-ttu-id="c1ad3-168">[How to: Serialisieren eines Objekts](how-to-serialize-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="c1ad3-168">[How to: Serialize an Object](how-to-serialize-an-object.md)</span></span>
- <span data-ttu-id="c1ad3-169">[How to: Deserialisieren eines Objekts](how-to-deserialize-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="c1ad3-169">[How to: Deserialize an Object](how-to-deserialize-an-object.md)</span></span>
