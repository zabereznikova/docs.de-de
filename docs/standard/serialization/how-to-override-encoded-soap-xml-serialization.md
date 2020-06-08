---
title: 'Vorgehensweise: Überschreiben von codierter SOAP-XML-Serialisierung'
description: Erfahren Sie mehr über das Überschreiben der XML-Serialisierung von Objekten als SOAP-Nachrichten, das mit dem Überschreiben der Standard-XML-Serialisierung vergleichbar ist.
ms.date: 03/30/2017
helpviewer_keywords:
- overriding XML serialization
- SOAP, overriding encoded XML serialization
ms.assetid: d0791df8-04e3-46b4-a6be-fe0ed09267e8
ms.openlocfilehash: 50688cb25294f14a9dd4596258eb95adf93cdb41
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "84277985"
---
# <a name="how-to-override-encoded-soap-xml-serialization"></a><span data-ttu-id="191b5-103">Vorgehensweise: Überschreiben von codierter SOAP-XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="191b5-103">How to: Override Encoded SOAP XML Serialization</span></span>

<span data-ttu-id="191b5-104">Das Verfahren zum Überschreiben der XML-Serialisierung von Objekten als SOAP-Nachrichten ist mit dem zum Überschreiben der Standard-XML-Serialisierung vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="191b5-104">The process for overriding XML serialization of objects as SOAP messages is similar to the process for overriding standard XML serialization.</span></span> <span data-ttu-id="191b5-105">Informationen zum Überschreiben der Standard-XML-Serialisierung finden Sie unter [Vorgehensweise: Angeben eines alternativen Elementnamens für einen XML-Stream](how-to-specify-an-alternate-element-name-for-an-xml-stream.md).</span><span class="sxs-lookup"><span data-stu-id="191b5-105">For information about overriding standard XML serialization, see [How to: Specify an Alternate Element Name for an XML Stream](how-to-specify-an-alternate-element-name-for-an-xml-stream.md).</span></span>

## <a name="to-override-serialization-of-objects-as-soap-messages"></a><span data-ttu-id="191b5-106">So überschreiben Sie Serialisierung von Objekten als SOAP-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="191b5-106">To override serialization of objects as SOAP messages</span></span>

1. <span data-ttu-id="191b5-107">Erstellen Sie eine Instanz der <xref:System.Xml.Serialization.SoapAttributeOverrides>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="191b5-107">Create an instance of the <xref:System.Xml.Serialization.SoapAttributeOverrides> class.</span></span>

2. <span data-ttu-id="191b5-108">Erstellen Sie für jeden Klassenmember, der serialisiert wird, ein `SoapAttributes`-Attribut.</span><span class="sxs-lookup"><span data-stu-id="191b5-108">Create a `SoapAttributes` for each class member that is being serialized.</span></span>

3. <span data-ttu-id="191b5-109">Erstellen Sie für den zu serialisierenden Member eine Instanz eines oder mehrerer der Attribute, die sich auf die XML-Serialisierung auswirken.</span><span class="sxs-lookup"><span data-stu-id="191b5-109">Create an instance of one or more of the attributes that affect XML serialization, as appropriate, to the member being serialized.</span></span> <span data-ttu-id="191b5-110">Weitere Informationen hierzu finden Sie unter "Attribute für die Steuerung der Serialisierung von codiertem SOAP".</span><span class="sxs-lookup"><span data-stu-id="191b5-110">For more information, see "Attributes That Control Encoded SOAP Serialization".</span></span>

4. <span data-ttu-id="191b5-111">Legen Sie die entsprechende Eigenschaft von `SoapAttributes` auf das in Schritt 3 erstellte Attribut fest.</span><span class="sxs-lookup"><span data-stu-id="191b5-111">Set the appropriate property of `SoapAttributes` to the attribute created in step 3.</span></span>

5. <span data-ttu-id="191b5-112">Fügen Sie `SoapAttributes` zu `SoapAttributeOverrides` hinzu.</span><span class="sxs-lookup"><span data-stu-id="191b5-112">Add `SoapAttributes` to `SoapAttributeOverrides`.</span></span>

6. <span data-ttu-id="191b5-113">Erstellen Sie `XmlTypeMapping` mithilfe von `SoapAttributeOverrides`.</span><span class="sxs-lookup"><span data-stu-id="191b5-113">Create an `XmlTypeMapping` using the `SoapAttributeOverrides`.</span></span> <span data-ttu-id="191b5-114">Verwenden Sie die `SoapReflectionImporter.ImportTypeMapping`-Methode.</span><span class="sxs-lookup"><span data-stu-id="191b5-114">Use the `SoapReflectionImporter.ImportTypeMapping` method.</span></span>

7. <span data-ttu-id="191b5-115">Erstellen Sie `XmlSerializer` mithilfe von `XmlTypeMapping`.</span><span class="sxs-lookup"><span data-stu-id="191b5-115">Create an `XmlSerializer` using `XmlTypeMapping`.</span></span>

8. <span data-ttu-id="191b5-116">Serialisieren oder deserialisieren Sie das Objekt.</span><span class="sxs-lookup"><span data-stu-id="191b5-116">Serialize or deserialize the object.</span></span>

## <a name="example"></a><span data-ttu-id="191b5-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="191b5-117">Example</span></span>

<span data-ttu-id="191b5-118">Im folgenden Codebeispiel wird eine Datei auf zwei verschiedene Arten serialisiert: Zuerst wird das Verhalten der `XmlSerializer`-Klasse nicht überschrieben und dann wird das Verhalten überschrieben.</span><span class="sxs-lookup"><span data-stu-id="191b5-118">The following code example serializes a file in two ways: first, without overriding the `XmlSerializer` class's behavior, and second, by overriding the behavior.</span></span> <span data-ttu-id="191b5-119">Das Beispiel enthält eine Klasse namens `Group` mit mehreren Membern.</span><span class="sxs-lookup"><span data-stu-id="191b5-119">The example contains a class named `Group` with several members.</span></span> <span data-ttu-id="191b5-120">Auf Klassenmember wurden verschiedene Attribute, z.B. `SoapElementAttribute`, angewendet.</span><span class="sxs-lookup"><span data-stu-id="191b5-120">Various attributes, such as the `SoapElementAttribute`, have been applied to class members.</span></span> <span data-ttu-id="191b5-121">Wenn die Klasse mit der `SerializeOriginal`-Methode serialisiert wird, steuern die Attribute den Inhalt der SOAP-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="191b5-121">When the class is serialized with the `SerializeOriginal` method, the attributes control the SOAP message content.</span></span> <span data-ttu-id="191b5-122">Beim Aufrufen der `SerializeOverride`-Methode, wird der Inhalt der `XmlSerializer`-Klasse dadurch überschrieben, dass verschiedene Attribute erstellt und die Eigenschaften eines `SoapAttributes`-Objekts entsprechend auf diese Attribute festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="191b5-122">When the `SerializeOverride` method is called, the behavior of the `XmlSerializer` is overridden by creating various attributes and setting the properties of a `SoapAttributes` to those attributes (as appropriate).</span></span>

```csharp
using System;
using System.IO;
using System.Xml;
using System.Xml.Serialization;
using System.Xml.Schema;

public class Group
{
    [SoapAttribute (Namespace = "http://www.cpandl.com")]
    public string GroupName;

    [SoapAttribute(DataType = "base64Binary")]
    public Byte [] GroupNumber;

    [SoapAttribute(DataType = "date", AttributeName = "CreationDate")]
    public DateTime Today;
    [SoapElement(DataType = "nonNegativeInteger", ElementName = "PosInt")]
    public string PositiveInt;
    // This is ignored when serialized unless it is overridden.
    [SoapIgnore]
    public bool IgnoreThis;

    public GroupType Grouptype;

    [SoapInclude(typeof(Car))]
    public Vehicle myCar(string licNumber)
    {
        Vehicle v;
        if(licNumber == "")
            {
                v = new Car();
            v.licenseNumber = "!!!!!!";
        }
        else
        {
            v = new Car();
            v.licenseNumber = licNumber;
        }
        return v;
    }
}

public abstract class Vehicle
{
    public string licenseNumber;
    public DateTime makeDate;
}

public class Car: Vehicle
{
}

public enum GroupType
{
    // These enums can be overridden.
    small,
    large
}

public class Run
{
    public static void Main()
    {
        Run test = new Run();
        test.SerializeOriginal("SoapOriginal.xml");
        test.SerializeOverride("SoapOverrides.xml");
        test.DeserializeOriginal("SoapOriginal.xml");
        test.DeserializeOverride("SoapOverrides.xml");

    }
    public void SerializeOriginal(string filename)
    {
        // Creates an instance of the XmlSerializer class.
        XmlTypeMapping myMapping =
        (new SoapReflectionImporter().ImportTypeMapping(
        typeof(Group)));
        XmlSerializer mySerializer =
        new XmlSerializer(myMapping);

        // Writing the file requires a TextWriter.
        TextWriter writer = new StreamWriter(filename);

        // Creates an instance of the class that will be serialized.
        Group myGroup = new Group();

        // Sets the object properties.
        myGroup.GroupName = ".NET";

        Byte [] hexByte = new Byte[2]{Convert.ToByte(100),
        Convert.ToByte(50)};
        myGroup.GroupNumber = hexByte;

        DateTime myDate = new DateTime(2002,5,2);
        myGroup.Today = myDate;

        myGroup.PositiveInt= "10000";
        myGroup.IgnoreThis=true;
        myGroup.Grouptype= GroupType.small;
        Car thisCar =(Car)  myGroup.myCar("1234566");

        // Prints the license number just to prove the car was created.
        Console.WriteLine("License#: " + thisCar.licenseNumber + "\n");

        // Serializes the class and closes the TextWriter.
        mySerializer.Serialize(writer, myGroup);
        writer.Close();
    }

    public void SerializeOverride(string filename)
    {
        // Creates an instance of the XmlSerializer class
        // that overrides the serialization.
        XmlSerializer overRideSerializer = CreateOverrideSerializer();

        // Writing the file requires a TextWriter.
        TextWriter writer = new StreamWriter(filename);

        // Creates an instance of the class that will be serialized.
        Group myGroup = new Group();

        // Sets the object properties.
        myGroup.GroupName = ".NET";

        Byte [] hexByte = new Byte[2]{Convert.ToByte(100),
        Convert.ToByte(50)};
        myGroup.GroupNumber = hexByte;

        DateTime myDate = new DateTime(2002,5,2);
        myGroup.Today = myDate;

        myGroup.PositiveInt= "10000";
        myGroup.IgnoreThis=true;
        myGroup.Grouptype= GroupType.small;
        Car thisCar =(Car)  myGroup.myCar("1234566");

        // Serializes the class and closes the TextWriter.
        overRideSerializer.Serialize(writer, myGroup);
         writer.Close();
    }

    public void DeserializeOriginal(string filename)
    {
        // Creates an instance of the XmlSerializer class.
        XmlTypeMapping myMapping =
        (new SoapReflectionImporter().ImportTypeMapping(
        typeof(Group)));
        XmlSerializer mySerializer =
        new XmlSerializer(myMapping);

        TextReader reader = new StreamReader(filename);

        // Deserializes and casts the object.
        Group myGroup;
        myGroup = (Group) mySerializer.Deserialize(reader);

        Console.WriteLine(myGroup.GroupName);
        Console.WriteLine(myGroup.GroupNumber[0]);
        Console.WriteLine(myGroup.GroupNumber[1]);
        Console.WriteLine(myGroup.Today);
        Console.WriteLine(myGroup.PositiveInt);
        Console.WriteLine(myGroup.IgnoreThis);
        Console.WriteLine();
    }

    public void DeserializeOverride(string filename)
    {
        // Creates an instance of the XmlSerializer class.
        XmlSerializer overRideSerializer = CreateOverrideSerializer();
        // Reading the file requires a TextReader.
        TextReader reader = new StreamReader(filename);

        // Deserializes and casts the object.
        Group myGroup;
        myGroup = (Group) overRideSerializer.Deserialize(reader);

        Console.WriteLine(myGroup.GroupName);
        Console.WriteLine(myGroup.GroupNumber[0]);
        Console.WriteLine(myGroup.GroupNumber[1]);
        Console.WriteLine(myGroup.Today);
        Console.WriteLine(myGroup.PositiveInt);
        Console.WriteLine(myGroup.IgnoreThis);
    }

    private XmlSerializer CreateOverrideSerializer()
    {
        SoapAttributeOverrides mySoapAttributeOverrides =
        new SoapAttributeOverrides();
        SoapAttributes soapAtts = new SoapAttributes();

        SoapElementAttribute mySoapElement = new SoapElementAttribute();
        mySoapElement.ElementName = "xxxx";
        soapAtts.SoapElement = mySoapElement;
        mySoapAttributeOverrides.Add(typeof(Group), "PositiveInt",
        soapAtts);

        // Overrides the IgnoreThis property.
        SoapIgnoreAttribute myIgnore = new SoapIgnoreAttribute();
        soapAtts = new SoapAttributes();
        soapAtts.SoapIgnore = false;
        mySoapAttributeOverrides.Add(typeof(Group), "IgnoreThis",
        soapAtts);

        // Overrides the GroupType enumeration.
        soapAtts = new SoapAttributes();
        SoapEnumAttribute xSoapEnum = new SoapEnumAttribute();
        xSoapEnum.Name = "Over1000";
        soapAtts.SoapEnum = xSoapEnum;

        // Adds the SoapAttributes to the
        // mySoapAttributeOverrides.
        mySoapAttributeOverrides.Add(typeof(GroupType), "large",
        soapAtts);

        // Creates a second enumeration and adds it.
        soapAtts = new SoapAttributes();
        xSoapEnum = new SoapEnumAttribute();
        xSoapEnum.Name = "ZeroTo1000";
        soapAtts.SoapEnum = xSoapEnum;
        mySoapAttributeOverrides.Add(typeof(GroupType), "small",
        soapAtts);

        // Overrides the Group type.
        soapAtts = new SoapAttributes();
        SoapTypeAttribute soapType = new SoapTypeAttribute();
        soapType.TypeName = "Team";
        soapAtts.SoapType = soapType;
        mySoapAttributeOverrides.Add(typeof(Group),soapAtts);

        // Creates an XmlTypeMapping that is used to create an instance
        // of the XmlSerializer class. Then returns the XmlSerializer.
        XmlTypeMapping myMapping = (new SoapReflectionImporter(
        mySoapAttributeOverrides)).ImportTypeMapping(typeof(Group));

        XmlSerializer ser = new XmlSerializer(myMapping);
        return ser;
    }
}
```

## <a name="see-also"></a><span data-ttu-id="191b5-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="191b5-123">See also</span></span>

- [<span data-ttu-id="191b5-124">XML- und SOAP-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="191b5-124">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
- [<span data-ttu-id="191b5-125">Attribute zur Steuerung der Serialisierung von codiertem SOAP</span><span class="sxs-lookup"><span data-stu-id="191b5-125">Attributes That Control Encoded SOAP Serialization</span></span>](attributes-that-control-encoded-soap-serialization.md)
- [<span data-ttu-id="191b5-126">XML-Serialisierung mit XML-Webdiensten</span><span class="sxs-lookup"><span data-stu-id="191b5-126">XML Serialization with XML Web Services</span></span>](xml-serialization-with-xml-web-services.md)
- <span data-ttu-id="191b5-127">[How to: Serialisieren eines Objekts](how-to-serialize-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="191b5-127">[How to: Serialize an Object](how-to-serialize-an-object.md)</span></span>
- [<span data-ttu-id="191b5-128">How to: Deserialisieren eines Objekts</span><span class="sxs-lookup"><span data-stu-id="191b5-128">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)
- <span data-ttu-id="191b5-129">[How to: Serialisieren eines Objekts als einen durch SOAP codierten XML-Stream](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md).</span><span class="sxs-lookup"><span data-stu-id="191b5-129">[How to: Serialize an Object as a SOAP-Encoded XML Stream](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)</span></span>
