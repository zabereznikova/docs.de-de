---
title: Einfache Serialisierung
description: In diesem Artikel wird gezeigt, wie Sie eine Klasse mit dem SerializableAttribute serialisierbar machen, und er enthält Beispiele für Serialisierung und Deserialisierung.
ms.date: 03/30/2017
helpviewer_keywords:
- binary serialization, basic serialization
- serialization, basic serialization
ms.assetid: d899d43c-335a-433e-a589-cd187192984f
dev_langs:
- CSharp
ms.openlocfilehash: 98ea6f23467b85dc270aa323e72a8a9b0934994a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378425"
---
# <a name="basic-serialization"></a><span data-ttu-id="0951e-103">Einfache Serialisierung</span><span class="sxs-lookup"><span data-stu-id="0951e-103">Basic serialization</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

<span data-ttu-id="0951e-104">Die einfachste Möglichkeit, eine Klasse serialisierbar zu machen, besteht darin, sie folgendermaßen mit <xref:System.SerializableAttribute> zu markieren.</span><span class="sxs-lookup"><span data-stu-id="0951e-104">The easiest way to make a class serializable is to mark it with the <xref:System.SerializableAttribute> as follows.</span></span>  
  
```csharp  
[Serializable]  
public class MyObject {  
  public int n1 = 0;  
  public int n2 = 0;  
  public String str = null;  
}  
```  
  
<span data-ttu-id="0951e-105">Das nachstehende Codebeispiel zeigt, wie eine Instanz dieser Klasse in eine Datei serialisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="0951e-105">The following code example shows how an instance of this class can be serialized to a file.</span></span>  
  
```csharp  
MyObject obj = new MyObject();  
obj.n1 = 1;  
obj.n2 = 24;  
obj.str = "Some String";  
IFormatter formatter = new BinaryFormatter();  
Stream stream = new FileStream("MyFile.bin", FileMode.Create, FileAccess.Write, FileShare.None);  
formatter.Serialize(stream, obj);  
stream.Close();  
```  
  
<span data-ttu-id="0951e-106">In diesem Beispiel wird ein binäres Formatierungsprogramm zur Durchführung der Serialisierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="0951e-106">This example uses a binary formatter to do the serialization.</span></span> <span data-ttu-id="0951e-107">Sie müssen lediglich eine Instanz des Datenstroms und des zu verwendenden Formatierungsprogramms erstellen, und im Formatierungsprogramm dann die **Serialize**-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="0951e-107">All you need to do is create an instance of the stream and the formatter you intend to use, and then call the **Serialize** method on the formatter.</span></span> <span data-ttu-id="0951e-108">Der Stream und das zu serialisierende Objekt werden in diesem Aufruf als Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="0951e-108">The stream and the object to serialize are provided as parameters to this call.</span></span> <span data-ttu-id="0951e-109">Obwohl es in diesem Beispiel nicht ausdrücklich gezeigt wird, werden alle Membervariablen einer Klasse serialisiert, auch wenn Variablen als privat markiert sind.</span><span class="sxs-lookup"><span data-stu-id="0951e-109">Although it is not explicitly demonstrated in this example, all member variables of a class will be serialized—even variables marked as private.</span></span> <span data-ttu-id="0951e-110">In dieser Hinsicht unterscheidet sich die binäre Serialisierung von der <xref:System.Xml.Serialization.XmlSerializer>-Klasse, die nur öffentliche Felder serialisiert.</span><span class="sxs-lookup"><span data-stu-id="0951e-110">In this aspect, binary serialization differs from the <xref:System.Xml.Serialization.XmlSerializer> class, which only serializes public fields.</span></span> <span data-ttu-id="0951e-111">Informationen zum Ausschluss von Membervariablen von der binären Serialisierung finden Sie unter [Selektive Serialisierung](selective-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="0951e-111">For information on excluding member variables from binary serialization, see [Selective Serialization](selective-serialization.md).</span></span>  
  
<span data-ttu-id="0951e-112">Es ist ebenso einfach, das Objekt wieder in seinem früheren Zustand wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="0951e-112">Restoring the object back to its former state is just as easy.</span></span> <span data-ttu-id="0951e-113">Erstellen Sie zunächst einen Datenstrom zum Einlesen und ein <xref:System.Runtime.Serialization.Formatter>, und weisen Sie das Formatierungsprogramm dann an, das Objekt zu deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="0951e-113">First, create a stream for reading and a <xref:System.Runtime.Serialization.Formatter>, and then instruct the formatter to deserialize the object.</span></span> <span data-ttu-id="0951e-114">Das nachfolgende Codebeispiel zeigt, wie Sie hierzu vorgehen.</span><span class="sxs-lookup"><span data-stu-id="0951e-114">The code example below shows how this is done.</span></span>  
  
```csharp  
IFormatter formatter = new BinaryFormatter();  
Stream stream = new FileStream("MyFile.bin", FileMode.Open, FileAccess.Read, FileShare.Read);  
MyObject obj = (MyObject) formatter.Deserialize(stream);  
stream.Close();  
  
// Here's the proof.  
Console.WriteLine("n1: {0}", obj.n1);  
Console.WriteLine("n2: {0}", obj.n2);  
Console.WriteLine("str: {0}", obj.str);  
```  
  
<span data-ttu-id="0951e-115">Die oben verwendete <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>-Klasse ist sehr effizient und erzeugt einen kompakten Bytestream.</span><span class="sxs-lookup"><span data-stu-id="0951e-115">The <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> used above is very efficient and produces a compact byte stream.</span></span> <span data-ttu-id="0951e-116">Alle Objekte, die mit diesem Formatierungsprogramm serialisiert wurden, können mit diesem auch deserialisiert werden. Dadurch ist es das optimale Tool zur Serialisierung von Objekten, die im .NET&#160;Framework deserialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="0951e-116">All objects serialized with this formatter can also be deserialized with it, which makes it an ideal tool for serializing objects that will be deserialized on the .NET Framework.</span></span> <span data-ttu-id="0951e-117">Beachten Sie unbedingt, dass beim Deserialisieren von Objekten keine Konstruktoren aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0951e-117">It is important to note that constructors are not called when an object is deserialized.</span></span> <span data-ttu-id="0951e-118">Diese Einschränkung wird der Deserialisierung auferlegt, um die Leistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="0951e-118">This constraint is placed on deserialization for performance reasons.</span></span> <span data-ttu-id="0951e-119">Dies verstößt jedoch gegen einige der üblichen Verträge, die die Runtime mit dem Objektentwickler schließt, und Entwickler müssen sich über die Auswirkungen im Klaren sein, die die Markierung eines Objekts als serialisierbar hat.</span><span class="sxs-lookup"><span data-stu-id="0951e-119">However, this violates some of the usual contracts the runtime makes with the object writer, and developers should ensure that they understand the ramifications when marking an object as serializable.</span></span>  
  
<span data-ttu-id="0951e-120">Wenn Portabilität gefordert ist, verwenden Sie stattdessen die <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="0951e-120">If portability is a requirement, use the <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> instead.</span></span> <span data-ttu-id="0951e-121">Ersetzen Sie einfach im oben dargestellten Code die **BinaryFormatter**-Klasse durch die **SoapFormatter,** -Klasse, und rufen Sie wie zuvor**Serialisieren** und **Deserialisieren** auf.</span><span class="sxs-lookup"><span data-stu-id="0951e-121">Simply replace the **BinaryFormatter** in the code above with **SoapFormatter,** and call **Serialize** and **Deserialize** as before.</span></span> <span data-ttu-id="0951e-122">Dieses Formatierungsprogramm erzeugt die folgende Ausgabe für das oben dargestellte Beispiel.</span><span class="sxs-lookup"><span data-stu-id="0951e-122">This formatter produces the following output for the example used above.</span></span>  
  
```xml  
<SOAP-ENV:Envelope  
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"
  xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/"  
  xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"  
  SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/"  
  xmlns:a1="http://schemas.microsoft.com/clr/assem/ToFile">  
  
  <SOAP-ENV:Body>  
    <a1:MyObject id="ref-1">  
      <n1>1</n1>  
      <n2>24</n2>  
      <str id="ref-3">Some String</str>  
    </a1:MyObject>  
  </SOAP-ENV:Body>  
</SOAP-ENV:Envelope>  
```  
  
<span data-ttu-id="0951e-123">Sie müssen unbedingt beachten, dass das [Serializable](xref:System.SerializableAttribute)-Attribut nicht geerbt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0951e-123">It's important to note that the [Serializable](xref:System.SerializableAttribute) attribute cannot be inherited.</span></span> <span data-ttu-id="0951e-124">Wenn Sie eine neue Klasse von `MyObject` ableiten, muss diese neue Klasse auch mit dem Attribut markiert werden, da sie sonst nicht serialisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="0951e-124">If you derive a new class from `MyObject`, the new class must be marked with the attribute as well, or it cannot be serialized.</span></span> <span data-ttu-id="0951e-125">Wenn Sie beispielsweise eine Instanz der nachstehenden Klasse zu serialisieren versuchen, erhalten Sie <xref:System.Runtime.Serialization.SerializationException>, die Sie darüber informiert, dass der `MyStuff`-Typ nicht als serialisierbar markiert ist.</span><span class="sxs-lookup"><span data-stu-id="0951e-125">For example, when you attempt to serialize an instance of the class below, you'll get a <xref:System.Runtime.Serialization.SerializationException> informing you that the `MyStuff` type is not marked as serializable.</span></span>  
  
```csharp  
public class MyStuff : MyObject
{  
  public int n3;  
}  
```  
  
 <span data-ttu-id="0951e-126">Die Verwendung des [Serializable](xref:System.SerializableAttribute)-Attributs ist zweckmäßig, aber auch mit den oben beschriebenen Einschränkungen verbunden.</span><span class="sxs-lookup"><span data-stu-id="0951e-126">Using the [Serializable](xref:System.SerializableAttribute) attribute is convenient, but it has limitations as previously demonstrated.</span></span> <span data-ttu-id="0951e-127">Informationen dazu, wie eine Klasse für die Serialisierung markiert wird, finden Sie unter [Serialisierungsrichtlinien](serialization-guidelines.md).</span><span class="sxs-lookup"><span data-stu-id="0951e-127">Refer to the [Serialization Guidelines](serialization-guidelines.md) for information about when you should mark a class for serialization.</span></span> <span data-ttu-id="0951e-128">Die Serialisierung kann keiner Klasse hinzugefügt werden, nachdem sie kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="0951e-128">Serialization cannot be added to a class after it has been compiled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0951e-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0951e-129">See also</span></span>

- [<span data-ttu-id="0951e-130">Binäre Serialisierung</span><span class="sxs-lookup"><span data-stu-id="0951e-130">Binary Serialization</span></span>](binary-serialization.md)
- [<span data-ttu-id="0951e-131">XML- und SOAP-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="0951e-131">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
