---
title: 'Vorgehensweise: Serialisieren eines Objekts'
description: In diesem Artikel wird das Serialisieren eines Objekts gezeigt. Wählen Sie ein Transportformat aus, in dem der XML-Stream entweder als Stream oder Datei gespeichert werden soll.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.assetid: a1207d05-32b2-4953-8582-959607991227
ms.openlocfilehash: 63446df3fa2c931c839eda91c648cee961715f93
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83377558"
---
# <a name="how-to-serialize-an-object"></a><span data-ttu-id="396d6-104">Vorgehensweise: Serialisieren eines Objekts</span><span class="sxs-lookup"><span data-stu-id="396d6-104">How to: Serialize an Object</span></span>
<span data-ttu-id="396d6-105">Wenn Sie ein Objekt serialisieren möchten, erstellen Sie zuerst das zu serialisierende Objekt und legen dann dessen öffentliche Eigenschaften und Felder fest.</span><span class="sxs-lookup"><span data-stu-id="396d6-105">To serialize an object, first create the object that is to be serialized and set its public properties and fields.</span></span> <span data-ttu-id="396d6-106">Dazu müssen Sie das Transportformat angeben, in dem der XML-Stream gespeichert werden soll: als Stream oder als Datei.</span><span class="sxs-lookup"><span data-stu-id="396d6-106">To do this, you must determine the transport format in which the XML stream is to be stored, either as a stream or as a file.</span></span> <span data-ttu-id="396d6-107">Wenn der XML-Stream beispielsweise in einer permanenten Form gespeichert werden muss, erstellen Sie ein <xref:System.IO.FileStream>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="396d6-107">For example, if the XML stream must be saved in a permanent form, create a <xref:System.IO.FileStream> object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="396d6-108">Weitere Beispiele zur XML-Serialisierung finden Sie unter [Examples of XML Serialization (Beispiele für die XML-Serialisierung)](../../../docs/standard/serialization/examples-of-xml-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="396d6-108">For more examples of XML serialization, see [Examples of XML Serialization](../../../docs/standard/serialization/examples-of-xml-serialization.md).</span></span>  
  
### <a name="to-serialize-an-object"></a><span data-ttu-id="396d6-109">So serialisieren Sie ein Objekt</span><span class="sxs-lookup"><span data-stu-id="396d6-109">To serialize an object</span></span>  
  
1. <span data-ttu-id="396d6-110">Erstellen Sie das Objekt, und legen Sie seine öffentlichen Felder und Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="396d6-110">Create the object and set its public fields and properties.</span></span>  
  
2. <span data-ttu-id="396d6-111">Erstellen Sie unter Verwendung des Objekttyps ein <xref:System.Xml.Serialization.XmlSerializer>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="396d6-111">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object.</span></span> <span data-ttu-id="396d6-112">Weitere Informationen hierzu finden Sie in den Ausführungen zu den <xref:System.Xml.Serialization.XmlSerializer>-Klassenkonstruktoren.</span><span class="sxs-lookup"><span data-stu-id="396d6-112">For more information, see the <xref:System.Xml.Serialization.XmlSerializer> class constructors.</span></span>  
  
3. <span data-ttu-id="396d6-113">Rufen Sie die <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A>-Methode auf, um einen XML-Stream oder eine Darstellung in Dateiform der öffentlichen Eigenschaften und Felder des Objekts zu generieren.</span><span class="sxs-lookup"><span data-stu-id="396d6-113">Call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> method to generate either an XML stream or a file representation of the object's public properties and fields.</span></span> <span data-ttu-id="396d6-114">Im folgenden Beispiel wird eine Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="396d6-114">The following example creates a file.</span></span>  
  
    ```vb  
    Dim myObject As MySerializableClass = New MySerializableClass()  
    ' Insert code to set properties and fields of the object.  
    Dim mySerializer As XmlSerializer = New XmlSerializer(GetType(MySerializableClass))  
    ' To write to a file, create a StreamWriter object.  
    Dim myWriter As StreamWriter = New StreamWriter("myFileName.xml")  
    mySerializer.Serialize(myWriter, myObject)  
    myWriter.Close()  
    ```  
  
    ```csharp  
    MySerializableClass myObject = new MySerializableClass();  
    // Insert code to set properties and fields of the object.  
    XmlSerializer mySerializer = new
    XmlSerializer(typeof(MySerializableClass));  
    // To write to a file, create a StreamWriter object.  
    StreamWriter myWriter = new StreamWriter("myFileName.xml");  
    mySerializer.Serialize(myWriter, myObject);  
    myWriter.Close();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="396d6-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="396d6-115">See also</span></span>

- [<span data-ttu-id="396d6-116">Einführung in die XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="396d6-116">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- <span data-ttu-id="396d6-117">[How to: Deserialisieren eines Objekts](../../../docs/standard/serialization/how-to-deserialize-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="396d6-117">[How to: Deserialize an Object](../../../docs/standard/serialization/how-to-deserialize-an-object.md)</span></span>
